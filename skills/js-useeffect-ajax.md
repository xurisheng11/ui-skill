# JavaScript useEffect 和 ajax-callback 模式

## 概述

在 `Base.successWrapper()` 的第二个参数传入 JS 函数数组，实现动态交互逻辑。

## useEffect 基础模式

```typescript
const jsFunction = `
useEffect(() => {
  // 初始化逻辑
  if (!value_app || !value_app.value) return;
  
  // 异步请求
  $.ajax({
    url: '/ajax-callback',
    type: 'get',
    data: {
      method: 'get',
      url: '${BaseUI.uiHost()}/api/endpoint'
    },
    dataType: 'json',
    success: function(response) {
      // 处理响应
      set_version(response);
      setValue_version(response[0]);
    },
    error: function(xhr, error) {
      console.error('请求失败', error);
    }
  });
}, [value_app])
`;

return Base.successWrapper(
  content,
  [jsFunction],
  ['class-name']
);
```

## ajax-callback 调用

用于在 JS 中调用后端接口，获取数据并更新状态。

### GET 请求

```javascript
$.ajax({
  url: '/ajax-callback',
  type: 'get',
  data: {
    method: 'get',
    url: '${BaseUI.uiHost()}/api/endpoint?param=' + value_param.value
  },
  dataType: 'json',
  success: function(response) {
    if (response && response.length > 0) {
      set_options(response);
      setValue_select(response[0]);
    }
  },
  error: function(xhr, error) {
    console.error('请求失败', error);
  }
});
```

### POST 请求

```javascript
$.ajax({
  url: '/ajax-callback',
  type: 'post',
  data: {
    method: 'post',
    url: '${BaseUI.uiHost()}/api/endpoint',
    data: JSON.stringify({ key: value }),
    contentType: 'application/json'
  },
  dataType: 'json',
  success: function(response) {
    // 处理响应
  }
});
```

## 状态更新函数

### set_xxx - 设置选项数组

```javascript
set_options([{ value: '1', label: '选项1' }, { value: '2', label: '选项2' }]);
```

### setValue_xxx - 设置单个值

```javascript
setValue_select({ value: '1', label: '选项1' });
setValue_input('text value');
```

### set_xxx(val) - 通用设置

```javascript
set_num(1);
set_hasVersion(true);
set_configured_level('L1');
```

## 监听依赖

```javascript
useEffect(() => {
  // 逻辑
}, [value_app, value_version, num])
```

## 完整示例：版本列表获取

```typescript
private getVersionsJs = `
useEffect(() => {
  if (!value_app || !value_app.value) return;
  
  var url = "/ajax-callback";
  var data = {
    method: "get",
    url: "${BaseUI.uiHost()}/common/versions?app=" + value_app.value
  };
  
  $.ajax({
    url: url,
    type: 'get',
    data: data,
    dataType: 'json',
    success: function(response, xhr) {
      if (response && response.length > 0) {
        var allOption = { value: 'all', label: '全部版本' };
        var versionsWithAll = [allOption].concat(response);
        set_version(versionsWithAll);
        setValue_version(versionsWithAll[1]);
      } else {
        set_version([]);
        setValue_version(null);
      }
    },
    error: function(xhr, error) {
      console.error('请求失败', error);
    }
  });
}, [value_app])
`;

return Base.successWrapper(
  content,
  [this.getVersionsJs],
  ['mb-4']
);
```

## 完整示例：数据列表获取

```typescript
private getLevelsJs() {
  return `
useEffect(() => {
  if (num !== 2) {
    set_num(2);
  }
  if (!value_app || !value_app.value) return;
  if (!value_version || !value_version.value) return;

  var versionValue = value_version.value;
  var parts = versionValue.split(':');
  var pipelineId = parts[0] || '';
  var runId = parts[1] || '';
  if (!pipelineId || !runId) return;

  $.ajax({
    url: '/ajax-callback',
    type: 'get',
    data: {
      method: 'get',
      url: '${BaseUI.uiHost()}/api/level-result?pipelineId=' + pipelineId + '&runId=' + runId
    },
    dataType: 'json',
    success: function(response) {
      if (!response) return;
      var data = response;
      
      set_configured_level(data.configuredLevel || '未设置');
      set_current_level(data.actualLevel || '--');
      
      if (data.result === '通过') {
        set_scan_result_type('success');
        set_scan_result_text('通过');
      } else if (data.result === '不通过') {
        set_scan_result_type('error');
        set_scan_result_text('不通过');
      } else {
        set_scan_result_type('pending');
        set_scan_result_text('未评定');
      }
      
      if (Array.isArray(data.items) && data.items.length > 0) {
        set_items_list(data.items);
      }
    },
    error: function(error) {
      set_current_level('--');
      set_scan_result_type('pending');
      set_scan_result_text('未评定');
    }
  });
}, [value_app, value_version, num])
`;
}
```

## 加载遮罩示例

```javascript
// 创建加载遮罩元素
const loadingOverlay = document.createElement('div');
loadingOverlay.id = 'loading-overlay';

// 设置遮罩样式
Object.assign(loadingOverlay.style, {
  position: 'fixed',
  top: '0',
  left: '0',
  width: '100%',
  height: '100%',
  backgroundColor: 'rgba(0, 0, 0, 0.3)',
  display: 'none',
  justifyContent: 'center',
  alignItems: 'center',
  zIndex: '9999'
});

// 创建加载动画
const spinner = document.createElement('div');
spinner.className = 'loading-spinner';
Object.assign(spinner.style, {
  border: '5px solid #f3f3f3',
  borderTop: '5px solid #666666',
  borderRadius: '50%',
  width: '50px',
  height: '50px',
  animation: 'spin 1s linear infinite'
});

// 添加旋转动画
const styleElement = document.createElement('style');
styleElement.textContent = \`
  @keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
  }
\`;
document.head.appendChild(styleElement);

loadingOverlay.appendChild(spinner);
document.body.appendChild(loadingOverlay);
loadingOverlay.style.display = 'flex';

// 隐藏遮罩
loadingOverlay.style.display = 'none';
document.body.removeChild(loadingOverlay);
```

## 动态函数定义

```javascript
const fetchFunction = \`
function fetchData(param) {
  $.ajax({
    url: '/ajax-callback',
    type: 'get',
    data: {
      method: 'get',
      url: '${BaseUI.uiHost()}/api/data?param=' + param
    },
    dataType: 'json',
    success: function(response) {
      set_data(response);
    }
  });
}
\`;

const useEffectJs = \`
useEffect(() => {
  if (value_param) {
    fetchData(value_param);
  }
}, [value_param])
\`;

return Base.successWrapper(
  content,
  [fetchFunction, useEffectJs],
  ['class-name']
);
```

## 获取下拉选项

```javascript
const getOptionsFunction = \`
useEffect(() => {
  let url = "${BaseUI.uiHost()}/audit/aggregations/eventName"
  url += (url.includes('?') ? '&' : '?') + "serviceName=ismp"
  
  $.post("/ajax-callback", {
    method: "get",
    url: url
  }, function(options) {
    options = options.map(o => ({ label: o.key, value: o.key }))
    options.unshift({ label: '全部', value: 'all' })
    set_event_name_options(options)
  }, 'json');
}, [])
\`;
```

## 刷新功能

```javascript
const refreshJs = \`
useEffect(() => {
  // 刷新数据
  fetchData();
}, [])
\`;

// 按钮点击触发
BaseUI.clickButton('', 'set_refresh_num(refresh_num + 1);', 'normal')
```

## 条件请求

```javascript
useEffect(() => {
  // 选择"全部"时不请求
  if (value_app.value === 'all') {
    set_version([]);
    setValue_version(null);
    set_hasVersion(false);
    return;
  }
  
  set_hasVersion(true);
  // 发起请求
  $.ajax({...});
}, [value_app])
```

## 多条件组合

```javascript
useEffect(() => {
  var year = value_year && value_year.value ? value_year.value : '';
  var month = value_month && value_month.value !== undefined ? value_month.value : '0';
  
  var url = '${BaseUI.uiHost()}/api/result';
  var params = [];
  if (year) params.push('year=' + year);
  if (month !== '0') params.push('month=' + month);
  if (params.length > 0) url += '?' + params.join('&');
  
  $.ajax({
    url: '/ajax-callback',
    type: 'get',
    data: { method: 'get', url: url },
    dataType: 'json',
    success: function(response) {
      set_data(response);
    }
  });
}, [value_year, value_month, num])
```

## 表格数据更新

```javascript
const tableUpdateJs = \`
useEffect(() => {
  set_table_data_list();
}, [items_list])
\`;

// 设置表格初始数据
set_init_items_list(tableItems);
// 更新表格
set_table_data_list();
```
