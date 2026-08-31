# BaseUI 布局与容器方法详解

## spaceBetween — 最常用的垂直/水平布局

```typescript
// 签名
BaseUI.spaceBetween(
  content,        // 主内容：{key: component} 对象 或 数组
  button?,        // 右侧按钮区（自动浮右）
  direction?,     // 'vertical'（默认）| 'horizontal'
  size?,          // 'm'（默认）| 'xs' | 's' | 'l' | 'xl'
  align_items?,   // 'center' | 'start' | 'end'
)
// 返回包含 aws_space_between 的数组
```

```typescript
// 常见写法

// 垂直布局（页面主体，自动将 button 浮右底部）
BaseUI.spaceBetween(
  { header: pageTitle, info: container, ... },
  { button_cancel: cancelBtn, button_save: saveBtn },
)

// 水平布局（按钮区、搜索区）
BaseUI.spaceBetween(
  { btn1: ..., btn2: ..., btn3: ... },
  undefined,
  'horizontal',
  'xs',
)

// 水平+垂直居中对齐（搜索栏+结果数）
BaseUI.spaceBetween(
  { search: textFilter, select: dropdown, result: box },
  undefined,
  'horizontal',
  'xs',
  'center',
)

// 嵌套：外层垂直，button 区域自动变成右对齐的水平布局
BaseUI.spaceBetween(
  { title: header, content: container },
  { cancel: linkBtn, save: submitBtn },  // 自动 horizontal xs center right
)
```

## container — 带背景的卡片容器

```typescript
BaseUI.container(
  content,                    // 主内容
  title?,                     // 容器标题（不填则无 header）
  buttons?,                   // 右上角按钮 {key: button}
  description?,               // 标题下的描述文字
  disable_content_paddings?,  // 移除内容区内边距，默认 false
  className?,                 // 额外 CSS 类名
)
```

```typescript
// 基础用法
BaseUI.container(BaseUI.spaceBetween(formFields), '基本信息')

// 带编辑按钮
BaseUI.container(content, '基本信息',
  { edit_btn: BaseUI.linkCommonButton('编辑', editUrl) })

// 无内边距（嵌套表格时常用）
BaseUI.container(tableContent, '列表', undefined, undefined, true)
```

## box — 通用包装元素

```typescript
BaseUI.box(
  content,
  color?,      // 文字颜色：'text-status-inactive'(灰) | '#333' 等
  float?,      // 浮动：'right' | 'left'
  font_size?,  // 如 'mt-1'（实际是 class）
  font_weight?,
  tag_override?, // HTML 标签：'span' | 'div' | 'p'
  variant?,    // AWS box variant
  padding?,    // padding
  align?,      // text-align
  display?,    // display 值（用于显示隐藏）
)

// 快捷方法
BaseUI.boxNew(content, color?, fontWeight?, classes?, variant?)  // 支持 class 属性
BaseUI.box_new(content, display)      // display 由 markup 控制
BaseUI.box_display(content, display)  // display 直接传字符串
```

```typescript
// 常用场景

// 灰色次要文字
BaseUI.box('次要信息', 'text-status-inactive')

// 右浮动（让按钮区靠右）
BaseUI.box(btnGroup, undefined, 'right')

// 条件显示
BaseUI.box_new(content, { '#markup': "condition ? 'block' : 'none'" })

// 带自定义 class
BaseUI.boxNew(content, undefined, undefined, 'my-custom-class')
```

## horizontalPanel — 横向排列

```typescript
BaseUI.horizontalPanel(content, size?)
// 等价于 spaceBetween(content, undefined, 'horizontal', size || 'm')
```

## aws_column_layout — 多列网格布局

```typescript
BaseUI.aws_column_layout(columns, content)
// 生成固定列数的网格布局，与 spaceBetween 不同的是列数固定

// 示例：3 列布局
BaseUI.aws_column_layout(3, {
  col1: component1,
  col2: component2,
  col3: component3,
})
```

## panelWithActions — 带 actions 的标题栏

```typescript
BaseUI.panelWithActions(
  actionContent,  // 按钮内容 {key: button}
  title?,         // 标题文字
  variant?,       // header variant
)
// 输出：aws_header + aws_space_between(horizontal xs) 结构
```

```typescript
// 弹窗底部按钮行（常用）
BaseUI.panelWithActions({
  cancel: BaseUI.clickButton('取消', 'setValue_modal(false)'),
  confirm: BaseUI.button('确定', 'primary'),
})

// 表格 header（自动生成标题+按钮区）
// tableWithActions 内部就是调用 panelWithActions
```

## pageTitle — 页面 H1 标题

```typescript
BaseUI.pageTitle(
  field,        // 标识（影响变量名，如 '#title'）
  title,        // 显示的标题文字
  variant?,     // 'h1'（默认）| 'h2' | 'h3'
  description?, // 标题下方描述文字
  actions?,     // 右侧操作区
)
```

```typescript
// 页面标题
BaseUI.pageTitle('basic_title', '函数名称')

// 带操作的标题
BaseUI.pageTitle('basic_title', fn.name, 'h1', '描述文字', {
  edit: BaseUI.linkCommonButton('编辑', editUrl),
  deploy: BaseUI.button('部署', 'primary', deployUrl),
})
```

## tabs / tabItem — Tab 组

```typescript
// Tab 组
BaseUI.tabs(
  children,    // {tabId: tabItem, ...}
  defaultTab?, // 默认激活的 tab id
  id?,         // 若有 id，额外包一层（供 JS 操作用）
)

// 单个 Tab 项
BaseUI.tabItem(id, label, content)
```

```typescript
// 完整 Tab 组示例
BaseUI.tabs(
  {
    basic_tab:  BaseUI.tabItem('basic_tab',  '基本信息', basicContent),
    config_tab: BaseUI.tabItem('config_tab', '配置',     configContent),
    log_tab:    BaseUI.tabItem('log_tab',    '日志',     logContent),
  },
  tab || 'basic_tab',  // 默认 tab（可从 Query 参数传入）
)

// Tab 激活时的变量名：value_{tabsId}
// 如 Tab 所在容器 key 为 'my_tabs'，则读取 value_my_tabs 获取当前激活 tab
```

## cardPanel / cardPanelWithEdit — 详情卡片

```typescript
// 基础卡片
BaseUI.cardPanel(title, content, buttons?, description?)

// 带编辑按钮的详情卡片（最常用）
BaseUI.cardPanelWithEdit(
  title,       // '基本信息'
  editUrl,     // 编辑页 URL（this.getUrl(...)）
  items,       // {key: BaseUI.cardItem('标签','值')} 或 数组
  editable?,   // 是否显示编辑按钮
  description?,
  columns?,    // 列数，默认 3
)

// 带多个按钮的详情卡片
BaseUI.cardPanelWithButtons(
  title,
  [{ key: 'edit', title: '编辑', url: editUrl }, ...],
  items,
  description?,
)
```

```typescript
// cardItem 系列
BaseUI.cardItem('标签', '值')
BaseUI.cardItemTime('创建时间', data.createdAt)          // 自动时间格式化
BaseUI.cardItemLinkBlank('文档', '查看文档', 'https://...') // 带外链
BaseUI.cardItemWithContent('字段', customComponent)       // 自定义内容
BaseUI.awsCardItem('name字段', 'description字段')         // aws cards 用
```

## segmentedControl — 分段控件

```typescript
BaseUI.segmentedControl(
  options,       // [{ text: '5分钟', id: '5m' }, ...]
  defaultValue,  // 默认选中的 id
)
```

## alert — 提示框

```typescript
BaseUI.alert(header, content, alert_type?)
// alert_type: 'error'（默认）| 'warning' | 'success' | 'info'
```

## clipboard — 复制到剪贴板

```typescript
BaseUI.clipboard(
  text,              // 要复制的文本
  variant?,          // 'inline'（默认）| 'icon'
  copy_button_text?, // 按钮文字
  copy_success_text?,// 复制成功提示
)
```

## markupItem — 原生 HTML/JSX 插入

```typescript
// 插入原生 HTML（不包含花括号）
BaseUI.markupItem('<div id="my_chart"></div>')

// 插入 JSX 表达式（包含花括号时加 {} 包裹）
BaseUI.markupItem('{items.map(item => <li>{item.name}</li>)}')

// 插入 JS 变量/表达式（作为属性值时）
'#href': BaseUI.markupItem('`/path/${item.id}`')
'#disabled': BaseUI.markupItem('selected_table.length === 0')
```

## codeView — 代码展示

```typescript
BaseUI.codeView('javascript', code)
BaseUI.codeView('yaml', yamlContent)
BaseUI.codeView('json', jsonStr)
```

## help_panel — 帮助面板

```typescript
BaseUI.help_panel(content)
// 生成 aws_help_panel 组件
```

## offCanvas — 侧边抽屉

```typescript
BaseUI.offCanvas(title, body?, header?)
// 生成 aws_offcanvas 组件
```

## groupButtons — 下拉按钮组

```typescript
// 把多个按钮对象转换成 aws_button_dropdown
BaseUI.groupButtons('操作', {
  btn_view:   BaseUI.button('查看', 'link', '/path'),
  btn_edit:   BaseUI.button('编辑', 'link', '/edit'),
  btn_delete: BaseUI.deleteButton(tableId, '删除'),
})
```
