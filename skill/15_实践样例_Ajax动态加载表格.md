# 实践样例：Ajax 动态加载表格数据

通过 useEffect + ajax-callback 在页面加载后动态拉取表格数据，而非在 build 时直接查询。

## 完整实现模式

### 1. build 方法：表格数据留空

```typescript
@Get('/list/build')
public async build(@Query('id') id: string) {
  const header = [
    BaseUI.tableHeader('name', '名称'),
    BaseUI.tableHeaderTime('createdAt', '创建时间'),
  ];
  
  return Base.successWrapper(
    BaseUI.tableWithActions(
      this.name,
      '列表',
      { [`${this.name}_button_refresh`]: BaseUI.refreshButton() },
      BaseUI.tableSelect(header, [], 1), // ← 初始数据为空
    ),
    [
      this.loadDataJs(id),      // 加载数据 JS
      this.updateTableJs,       // 更新表格 JS
    ],
  );
}
```

### 2. 定义加载数据 JS

```typescript
private loadDataJs(id: string) {
  return `
    useEffect(() => {
      (function() {
        var url = '{LUBAN_HOST}/module/${id}/items';
        $.post('/ajax-callback', {method: 'get', url: url},
          function(items) {
            set_init_items_my_list(items);
          }, 'json'
        );
      })();
    }, []);  // 空依赖：只在组件挂载时执行一次
  `;
}

// 监听数据变化时更新表格显示
private readonly updateTableJs = `
  useEffect(() => {
    set_table_data_my_list();
  }, [init_items_my_list]);
`;
```

### 3. Tab 切换时加载（按需加载）

```typescript
private tabLoadDataJs(id: string) {
  return `
    useEffect(() => {
      if (value_detail_tabs === 'records_tab') {
        $.ajax({
          url: '/ajax-callback',
          type: 'get',
          data: {
            method: 'get',
            url: '{LUBAN_HOST}/module/${id}/records'
          },
          dataType: 'json',
          success: function(response) {
            set_init_items_records(response || []);
          },
          error: function() {
            set_init_items_records([]);
          }
        });
      }
    }, [value_detail_tabs]);
  `;
}
```

## 可用的表格状态变量

> 假设表格 key 为 `my_list`

| 变量 | 说明 |
|---|---|
| `init_items_my_list` | 表格原始数据 |
| `items_my_list` | 表格当前显示数据（经过过滤/排序） |
| `selected_my_list` | 当前选中行数组 |
| `filter_status_my_list` | 是否存在过滤条件（boolean） |
| `filter_total_my_list` | 过滤后的条数（或总条数） |
| `page_my_list` | 当前页码 |
| `total_pages_my_list` | 总页码 |

## 可用的表格方法

```javascript
set_init_items_my_list(array)  // 设置原始数据（需配合 set_table_data_my_list() 刷新）
set_items_my_list(array)       // 直接设置当前显示数据
set_table_data_my_list()       // 刷新表格显示（init_items 变化后调用）
set_selected_my_list(array)    // 设置选中项（需设置 track_by）
set_params_my_list(object)     // 设置 ajax 表格的请求参数
```

## 表格数据修改示例（从详情页更新列表行数据）

```javascript
// 将 id='xxx' 的那行的 status 字段更新为 'active'
useEffect(() => {
  if (!shouldRefreshRow) return;
  set_init_items_my_list(
    init_items_my_list.map(function(item) {
      return item.id === 'xxx' ? { ...item, status: 'active' } : item;
    })
  );
}, [shouldRefreshRow]);
```
