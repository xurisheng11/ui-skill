# 显示隐藏控制：#prefix / #suffix 模式

通过 `#prefix` 和 `#suffix` 属性实现 JSX 条件渲染，控制组件的显示与隐藏。

## 原理

`#prefix` 和 `#suffix` 会被直接拼接到组件 JSX 代码的前后，形成完整的 JSX 表达式：

```
{prefix}{组件JSX}{suffix}
```

## 最常用：三元表达式控制显隐

```typescript
// 当 display 为 true 时显示按钮，否则显示空字符串
BaseUI.addSetting(
  BaseUI.clickButton('上传代码', 'setValue_trigger(v => v + 1)'),
  {
    '#prefix': '{ display ?',
    '#suffix': ':""}',
  }
)
// 生成: { display ? <Button onClick={...}>上传代码</Button> : "" }
```

## 通用写法

```typescript
// 条件为 true 显示，false 显示空
{
  '#prefix': '{ conditionVariable ?',
  '#suffix': ':""}',
}

// 条件为 false 显示，true 显示空（取反）
{
  '#prefix': '{ !conditionVariable ?',
  '#suffix': ':""}',
}

// 复杂条件
{
  '#prefix': '{ selected_my_table.length > 0 ?',
  '#suffix': ':""}',
}

// 使用 value_ 前缀读取组件状态
{
  '#prefix': '{ value_radio_field === "option1" ?',
  '#suffix': ':""}',
}
```

## 在 BaseUI.addSetting 中使用

`addSetting` 本质是 `Object.assign`，给任意组件追加属性：

```typescript
// 给按钮添加条件显示
BaseUI.addSetting(
  BaseUI.button('操作按钮', 'primary'),
  {
    '#prefix': '{ display ?',
    '#suffix': ':""}',
  }
)

// 给整个容器添加条件显示
BaseUI.addSetting(
  BaseUI.container(content, '标题'),
  {
    '#prefix': '{ value_tab === "detail_tab" ?',
    '#suffix': ':""}',
  }
)
```

## 实战示例：两个按钮按状态互斥显示

```typescript
// 在详情页工具栏中，上传/下载按钮根据 display 状态显示
const toolbar = BaseUI.spaceBetween(
  {
    upload: BaseUI.addSetting(
      BaseUI.clickButton('上传代码', 'setValue_upload_trigger(v => v + 1)'),
      { '#prefix': '{ display ?', '#suffix': ':""}' }
    ),
    download: BaseUI.addSetting(
      BaseUI.clickButton('下载代码', 'set_downloadCode(true)'),
      { '#prefix': '{ display ?', '#suffix': ':""}' }
    ),
  },
  undefined,
  'horizontal',
)
```

## 与 aws_box display 属性的区别

| 方式 | 原理 | 隐藏后 DOM | 适合场景 |
|---|---|---|---|
| `#prefix`/`#suffix` | JSX 三元表达式，条件为假时渲染空字符串 | **不存在** | 有 space_between 间距问题时 |
| `aws_box #display` | CSS display 属性 | **存在**（只是不可见） | 简单隐藏，表单校验仍需触发时 |

```typescript
// 方式1：prefix/suffix（DOM 不存在，space_between 无间距）
BaseUI.addSetting(component, {
  '#prefix': '{ condition ?',
  '#suffix': ':""}',
})

// 方式2：aws_box display（DOM 存在，表单校验仍触发）
{
  '#type': 'aws_box',
  '#display': { '#markup': "condition ? 'block' : 'none'" },
  '#content': component
}
```

## JSON 直接写法（不经过 TypeScript）

```json
{
  "#type": "aws_button",
  "#text": "操作",
  "#prefix": "{ display ?",
  "#suffix": ":\"\"}"
}
```
