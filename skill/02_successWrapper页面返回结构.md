# Base.successWrapper 页面返回结构

`Base.successWrapper` 是所有 `build` 接口的固定返回方式，生成鲁班 AWS 组件的完整页面 JSON。

## 方法签名

```typescript
static successWrapper(
  data: any,              // 页面 UI 树（必填）
  functions?: any,        // 注入的 JS 代码数组（可选）
  classes = ['mb-4'],     // 根元素的 CSS 类（可选，默认 mb-4）
  const_define = []       // React 状态定义数组（可选）
): object
```

## 完整返回结构

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#attributes": { "class": ["mb-4"] },
      "#functions": [],
      "#children": {},
      "#const_define": []
    }
  }
}
```

## 最简用法（仅页面内容）

```typescript
return Base.successWrapper(
  BaseUI.spaceBetween([
    { title: BaseUI.pageTitle('title', '页面标题') },
  ])
);
```

## 带 JS 注入的用法

```typescript
return Base.successWrapper(
  BaseUI.spaceBetween([...]),   // 页面 UI
  [                             // JS 函数数组（字符串数组）
    this.someJsFunction(),
    condition && this.otherJsFunction(),  // false 会被过滤
  ],
  ['text-break'],              // CSS 类
  [                            // React 状态定义
    { value: 'display',        set_value: 'set_display',        default: false },
    { value: 'loading',        set_value: 'set_loading',        default: false },
    { value: 'selectedItem',   set_value: 'set_selectedItem',   default: null  },
  ]
);
```

## const_define 状态定义格式

每个对象定义一个 React `useState`：

```typescript
// 格式
{ value: '读取变量名', set_value: '设置变量名', default: 初始值 }

// 示例
[
  { value: 'num',                  set_value: 'set_num',                  default: 1 },
  { value: 'fnId',                 set_value: 'set_fnId',                 default: id },
  { value: 'display',              set_value: 'set_display',              default: false },
  { value: 'downloadCode',         set_value: 'set_downloadCode',         default: false },
  { value: 'upload_code_trigger',  set_value: 'setValue_upload_code_trigger', default: 0 },
  { value: 'upload_code_status',   set_value: 'setValue_upload_code_status',  default: '' },
  { value: 'upload_code_error',    set_value: 'setValue_upload_code_error',   default: '' },
]
```

在 JS 代码中：
- 读取：`display`、`upload_code_status`（直接用变量名）
- 设置：`set_display(true)`、`setValue_upload_code_trigger(v => v + 1)`

## 典型实战示例（详情页）

```typescript
return Base.successWrapper(
  BaseUI.spaceBetween([
    {
      basic_title: BaseUI.pageTitle('basic_title', fn.name),
      basic_info: BaseUI.cardPanelWithEdit(
        '基本信息',
        `${linkPrefix}/edit`,
        {
          name: BaseUI.cardItem('名称', fn.name),
          createdAt: BaseUI.cardItem('创建时间', BaseUI.datetimeFormat(fn.createdAt)),
        },
        canWrite,
      ),
    },
  ]),
  [
    this.loadDataJs(id),       // 页面加载时拉取数据
    condition && this.extraJs, // 有条件的 JS
  ],
  ['text-break'],
  [
    { value: 'loaded', set_value: 'set_loaded', default: false },
  ]
);
```
