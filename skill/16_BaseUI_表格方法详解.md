# BaseUI 完整方法参考（补充篇）

## 一、表格相关

### tableSelect — 表格本体构建

```typescript
// 签名
BaseUI.tableSelect(
  column_definitions,  // 列头定义数组
  rows,                // 数据行
  multiple,            // -1=无选框 | 0=单选 | 1=多选
  order?,              // 默认排序 [[列序号(1起), 'desc'|'asc']]
  selectors?,          // 过滤条件数组（详见下方）
  pagination?,         // 是否显示分页，默认 true
  items_per_page?,     // 每页条数，默认 10
  selected?,           // 默认选中项，默认 []
  track_by?,           // 唯一标识字段名
  disorder_columns?,   // 不排序的列序号数组（1起）
)
```

```typescript
// 常用写法
BaseUI.tableSelect(header, rows, 1, [[3, 'desc']])           // 多选，按第3列降序
BaseUI.tableSelect(header, rows, 0, [[1, 'asc']])            // 单选，按第1列升序
BaseUI.tableSelect(header, rows, -1)                         // 无选框
BaseUI.tableSelect(header, rows, 1, [[2,'desc']], selectors) // 带过滤条件
```

### tableSelect 的 selectors 过滤条件

`selectors` 是附加在搜索框旁边的额外过滤器数组：

```typescript
// 格式1：select 下拉过滤（最常用）
const selectors = [
  {
    target_column: 3,            // 对第3列过滤（1起）
    search_options: {            // 选项 map（key 被当做 value）
      'ACTIVE': { label: '活跃', value: 'ACTIVE' },
      'INACTIVE': { label: '停用', value: 'INACTIVE' },
    },
    placeholder: '状态',
    blank_option: '全部',        // 空选项文字
  }
];

// 格式2：date_range_picker 日期范围过滤
const selectors = [
  {
    type: 'aws_date_range_picker',
    target_column: 4,
    relative_options: [          // 可选：相对时间选项
      { key: 'previous-1-hour', amount: 1, unit: 'hour', type: 'relative' },
      { key: 'previous-1-day',  amount: 1, unit: 'day',  type: 'relative' },
    ],
  }
];

// 格式3：text_filter 额外文本搜索框
const selectors = [
  { type: 'aws_text_filter', target_column: 2, placeholder: '搜索名称' }
];

// 格式4：关闭所有搜索（无过滤条件）
const selectors = [{ '#type': 'none' }];
```

### tableAjax — Ajax 动态加载表格

```typescript
// 签名
BaseUI.tableAjax(
  header,           // 列头定义数组
  url,              // ajax 接口 URL（空字符串=不开启 ajax）
  needCheckBox,     // 是否需要选框
  multiple,         // 0=单选 | 1=多选
  order?,           // 默认排序
  disorder_columns?,// 不排序的列序号
  selectors?,       // 过滤条件
  selected?,        // 默认选中
  rows?,            // 初始数据（ajax 开启时通常为 []）
  track_by?,        // 唯一标识字段
)

// 等价于 tableSelect + '#ajax_url'
```

```typescript
// 实战写法
BaseUI.tableAjax(
  header,
  `${BaseUI.uiHost()}/module/list`,  // ajax 接口
  true,   // 需要选框
  1,      // 多选
  [[3, 'desc']],
)
```

### tableWithActions 变体说明

```typescript
// 标准版（自动检测删除按钮并添加确认弹窗）
BaseUI.tableWithActions(tableId, title, actions, table, desc?, noCheck?, headerContent?, cardTitle?, properties?)

// 新版（用于需要 identify 字段的删除弹窗）
BaseUI.tableWithActionsNew(id, title, actions, table, desc?, noCheck?)

// 地区/集群专用版（删除弹窗内容不同）
BaseUI.tableWithActionsRegionCluster(tableId, title, actions, table, desc?, noCheck?)
```

### 常用列头快捷方法

```typescript
BaseUI.tableHeaderTime('createdAt', '创建时间')       // 时间列（自动格式化）
BaseUI.tableHeaderCreated()                           // → tableHeaderTime('createdAt','创建时间')
BaseUI.tableHeaderUpdated()                           // → tableHeaderTime('updatedAt','更新时间')
BaseUI.tableHeaderName(cell?)                         // 名称列，150px
BaseUI.tableHeaderTitle('名称')                       // title 字段列
BaseUI.tableHeaderDescription()                       // description 字段列
BaseUI.tableHeaderTitleLink('/path/prefix')           // 名称列+详情链接
BaseUI.tableHeaderIdentify('/path/prefix')            // identify 字段+详情链接
BaseUI.tableHeaderIdentifyNoLink()                    // identify 字段，无链接
BaseUI.tableHeaderAccountName('/path/prefix')         // accountName 字段+详情链接
```

### 表格 cell 内容辅助方法

```typescript
BaseUI.tableItemTime('item.createdAt')                // 时间格式化（输出 faas_time_format(...)）
BaseUI.tableItemLightText('item.status')              // 灰色字体文本
BaseUI.badge('文字', 'red')                           // 徽章（颜色: blue/grey/green/red/...）
BaseUI.tableLink('{item.name}', '`/path/${item.id}`') // 带链接的单元格
BaseUI.statusIndicator(statusType, content)           // 状态指示器
```
