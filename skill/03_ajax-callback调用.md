# ajax-callback 前端调用后端接口

`/ajax-callback` 是鲁班框架提供的代理路由，前端通过它携带认证头转发 HTTP 请求，解决跨域和 Auth 问题。

## GET 请求（查询数据）

```javascript
$.ajax({
  url: '/ajax-callback',
  type: 'get',
  data: {
    method: 'get',
    url: '{LUBAN_HOST}/your-module/your-api?param1=value1&param2=value2'
  },
  dataType: 'json',
  success: function(response) {
    // 处理返回数据
    set_items(response);
  },
  error: function(xhr, error) {
    console.error('请求失败', error);
  }
});
```

## POST 请求（提交数据）

```javascript
var bodyStr = JSON.stringify({ key: 'value' });
var params = 'method=post'
  + '&url=' + encodeURIComponent('{LUBAN_HOST}/your-module/your-api')
  + '&body=' + encodeURIComponent(bodyStr)
  + '&content_type=' + encodeURIComponent('application/json');

var xhr = new XMLHttpRequest();
xhr.open('POST', '/ajax-callback', true);
xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
xhr.onload = function() {
  var resp;
  try { resp = JSON.parse(xhr.responseText); } catch(e) {}
  if (xhr.status >= 200 && xhr.status < 300 && resp && resp.status === 0) {
    // 成功处理
  } else {
    console.error((resp && resp.message) || '请求失败');
  }
};
xhr.send(params);
```

## 用 $.post 简化写法（常用于加载表格数据）

```javascript
$.post(
  '/ajax-callback',
  { method: 'get', url: '{LUBAN_HOST}/module/' + id + '/list' },
  function(items) {
    set_init_items_my_table(items);
    // 注意：修改 init_items 后要调用 set_table_data 更新显示
  },
  'json'
);
```

## 下载文件（Blob 方式）

```javascript
var xhr = new XMLHttpRequest();
xhr.open(
  'GET',
  '/ajax-callback?method=get&url=' + encodeURIComponent('{LUBAN_HOST}/module/download?id=' + id),
  true
);
xhr.responseType = 'blob';
xhr.onload = function() {
  if (xhr.status === 200) {
    var url = URL.createObjectURL(xhr.response);
    var a = document.createElement('a');
    a.href = url;
    a.download = 'filename.zip';
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    URL.revokeObjectURL(url);
  }
};
xhr.send();
```

## 注意事项

- `{LUBAN_HOST}` 是框架运行时替换的占位符，在 TypeScript 中通过 `BaseUI.uiHost()` 获取
- 请求会自动携带当前用户的 Authorization、Current-Org、Current-Project、Current-Cluster 等认证头
- GET 请求推荐用 `$.ajax` 或 `$.get`，POST 请求推荐用 XHR 手动构造 form-urlencoded
