# useEffect 监听事件模式

JS 代码以字符串形式注入到 `#functions` 数组中，在前端作为 React Hook 执行。

## 基本模式

```javascript
// 模式1：组件挂载时执行一次（空依赖数组）
useEffect(() => {
  // 初始化加载数据
  $.post('/ajax-callback', {method:'get', url:'{LUBAN_HOST}/api/list'},
    function(data) { set_init_items_my_table(data); }, 'json');
}, []);

// 模式2：监听某个状态变化
useEffect(() => {
  if (!trigger) return; // 防止初始化时触发
  // 执行操作...
}, [trigger]);

// 模式3：监听多个状态
useEffect(() => {
  // 任一依赖变化时执行
}, [value_tab, value_filter]);
```

## 常用场景一：初始化加载表格数据

```javascript
useEffect(() => {
  (function() {
    var url = '{LUBAN_HOST}/module/' + someId + '/list';
    $.post('/ajax-callback', {method: 'get', url: url},
      function(items) {
        set_init_items_my_table(items);
      }, 'json'
    );
  })();
}, []);

// 配套：init_items 变化时更新表格显示
useEffect(() => {
  set_table_data_my_table();
}, [init_items_my_table]);
```

## 常用场景二：Tab 切换时加载数据

```javascript
useEffect(() => {
  if (value_my_tabs === 'detail_tab') {
    $.ajax({
      url: '/ajax-callback',
      type: 'get',
      data: {
        method: 'get',
        url: '{LUBAN_HOST}/module/' + id + '/detail'
      },
      dataType: 'json',
      success: function(response) {
        set_detail_data(response);
      }
    });
  }
}, [value_my_tabs]);
```

## 常用场景三：监听触发器（如上传按钮）

```javascript
useEffect(() => {
  if (!upload_trigger) return; // trigger 初始值为 0/false，不触发
  
  // 弹出文件选择框
  var input = document.getElementById('file_input');
  if (!input) {
    input = document.createElement('input');
    input.id = 'file_input';
    input.type = 'file';
    input.accept = '.zip';
    input.style.display = 'none';
    document.body.appendChild(input);
  }
  input.onchange = function(e) {
    var file = e.target.files && e.target.files[0];
    if (!file) return;
    // 处理文件...
    input.value = '';
  };
  input.click();
}, [upload_trigger]);
```

## 常用场景四：监听状态更新 DOM

```javascript
useEffect(() => {
  var statusEl = document.getElementById('status_span');
  if (statusEl) {
    if (upload_status === 'uploading') {
      statusEl.textContent = '上传中...';
      statusEl.style.color = '#888';
    } else if (upload_status === 'error') {
      statusEl.textContent = upload_error || '上传失败';
      statusEl.style.color = '#d13212';
    } else {
      statusEl.textContent = '';
    }
  }
}, [upload_status, upload_error]);
```

## 常用场景五：监听下载状态

```javascript
useEffect(() => {
  if (!downloadCode) return;
  var xhr = new XMLHttpRequest();
  xhr.open('GET', '/ajax-callback?method=get&url=' + encodeURIComponent('{LUBAN_HOST}/module/download?id=' + id), true);
  xhr.responseType = 'blob';
  xhr.onload = function() {
    if (xhr.status === 200) {
      var url = URL.createObjectURL(xhr.response);
      var a = document.createElement('a');
      a.href = url;
      a.download = 'code.zip';
      document.body.appendChild(a);
      a.click();
      document.body.removeChild(a);
      URL.revokeObjectURL(url);
    }
    set_downloadCode(false);
  };
  xhr.send();
}, [downloadCode]);
```

## 在 TypeScript 中定义 JS 注入函数

```typescript
// 方式1：私有方法返回 JS 字符串（推荐）
private loadDataJs(id: string) {
  return `
    useEffect(() => {
      $.post('/ajax-callback', {method:'get', url:'{LUBAN_HOST}/module/${id}/list'},
        function(data) { set_init_items_my_table(data); }, 'json'
      );
    }, []);
  `;
}

// 方式2：私有属性（不需要参数时）
private readonly updateTableJs = `
  useEffect(() => {
    set_table_data_my_table();
  }, [init_items_my_table]);
`;

// 在 build 方法中传入
return Base.successWrapper(
  content,
  [
    this.loadDataJs(id),
    this.updateTableJs,
    condition && this.extraJs(id),  // 条件为 false 时被忽略
  ],
);
```

## 重要约定

- 依赖数组 `[]` 里填状态变量名（不加 `value_` 前缀的裸名）
- 读取状态用变量名（`display`、`upload_trigger`）
- 设置状态用 `set_xxx()` 或 `setValue_xxx()`
- 模板字符串中用 `${变量}` 插入 TypeScript 变量值
