# BaseUI 常用方法速查

`BaseUI` 是所有 UI 构建的工具类，提供页面各元素的构造方法。

## 页面结构

```typescript
// 页面标题（h1）
BaseUI.pageTitle('field_id', '页面标题', 'h1', '描述文字', actionButtons)

// 垂直空间布局（最常用的容器）
BaseUI.spaceBetween(
  content,           // 主内容 {key: component} 或数组
  button?,           // 右侧按钮区（自动右对齐）
  direction?,        // 'vertical'（默认） | 'horizontal'
  size?,             // 'm'（默认） | 'xs' | 's' | 'l'
  align_items?,      // 'center' | 'start' | 'end'
)

// 容器（带背景色和标题的卡片区域）
BaseUI.container(content, title?, buttons?, description?, disable_content_paddings?)

// Tab 组
BaseUI.tabs(children, defaultTab?, id?)
BaseUI.tabItem('tab_id', 'Tab标题', content)
```

## 详情页

```typescript
// 详情卡片（带编辑按钮）
BaseUI.cardPanelWithEdit(
  '基本信息',          // 标题
  `${linkPrefix}/edit`, // 编辑按钮跳转 URL
  {                    // 内容 key-value 对
    name: BaseUI.cardItem('名称', data.name),
    createdAt: BaseUI.cardItem('创建时间', BaseUI.datetimeFormat(data.createdAt)),
  },
  canWrite,            // 是否显示编辑按钮
  undefined,           // 描述
  3,                   // 列数（默认 3）
)

// 键值对条目
BaseUI.cardItem('字段标题', '字段值')

// 时间条目（自动格式化 UTC 时间）
BaseUI.cardItemTime('创建时间', data.createdAt)

// 带链接的条目
BaseUI.cardItemLinkBlank('文档', '查看', 'https://...')

// 时间格式化（UTC -> 本地时间字符串）
BaseUI.datetimeFormat(data.createdAt) // → '2024-01-01 12:00:00'
```

## 表格

```typescript
// 带操作的完整表格组（自动处理删除弹窗）
BaseUI.tableWithActions(
  tableId,             // 'my_list'
  '标题',
  await this.buttons(tableId),  // 按钮区
  BaseUI.tableSelect(header, rows, 1, [[3, 'desc']]), // 表格本体
  undefined,           // 描述
  false,               // noCheck（是否不自动添加删除弹窗）
  '标题',              // 弹窗中显示的标题
)

// 表格本体
BaseUI.tableSelect(
  column_definitions,  // 列头定义数组
  rows,                // 数据行数组
  1,                   // 0=单选, 1=多选, -1=无选框
  [[3, 'desc']],       // 默认排序：第3列降序
)

// 列头定义
BaseUI.tableHeader('id', '列名', cell?, minWidth?, maxWidth?, width?)
BaseUI.tableHeaderTime('createdAt', '创建时间')  // 自动处理时间格式
BaseUI.tableHeaderName(cell?)                     // 名称列
BaseUI.tableHeaderTitle('标题')                   // 标题列

// 列内容：链接
BaseUI.tableLink('{item.name}', '`/path/${item.id}`')

// Ajax 动态加载表格
BaseUI.tableAjax(header, '/ajax-url', true, 1, [[1,'desc']])
```

## 按钮

```typescript
// 普通按钮（跳转型）
BaseUI.button('按钮文字', 'primary', href, disableCondition, onClick, iconName)

// 链接按钮（无边框）
BaseUI.linkButtonLight('取消', this.getUrl('/path/back'))

// 有边框链接按钮
BaseUI.linkCommonButton('编辑', this.getUrl('/path/edit'))

// 主要按钮（跳转）
BaseUI.linkButton('创建', this.getUrl('/path/create'))

// 提交按钮（表单提交）
BaseUI.submitButton('保存', 'primary')

// 点击按钮（触发 JS，不提交表单）
BaseUI.clickButton('刷新', 'window.location.href = window.location.href;')

// 刷新按钮
BaseUI.refreshButton()

// 删除按钮（触发弹窗）
BaseUI.deleteButton(tableId, '删除', disableCondition?)

// 普通提交按钮（当有表格选中时才可用）
BaseUI.commonButton('操作', tableId)

// 带权限控制的按钮示例
result['my_button_create'] = this.currentAuth().admin && BaseUI.linkButton('创建', url)
result['my_button_delete'] = (admin || write) && BaseUI.deleteButton(id, '删除')
```

## 表单字段

```typescript
// 文本输入框
BaseUI.textField(id, title, placeholder, constraintText, value, attributes, required, disabled)

// 数字输入框
BaseUI.numberField(id, title, constraintText, value, attributes, required)

// 多行文本框
BaseUI.textArea(id, title, placeholder, constraintText, value, attributes, required)

// 下拉选择
BaseUI.selectField(id, title, options, defaultValue, description, filteringType, info, constraintText, placeholder, disabled, required)

// 多选下拉
BaseUI.MultiselectField(id, title, options, defaultValue, filteringType)

// 单选组
BaseUI.radioField(id, title, value, constraintText, options, required)

// 复选框/开关
BaseUI.checkboxField(id, title, constraintText, value, required)

// 密码框
BaseUI.passwordField(id, title, placeholder, constraintText, value, attributes, required)

// 日期选择器
BaseUI.datePicker(id, title, placeholder, constraintText, value, attributes, required)

// 验证规则（常用 pattern）
BaseUI.validatePattern.identifier  // 标识：小写字母开头
BaseUI.validatePattern.name        // 名称：1-63字符
BaseUI.validatePattern.version     // 版本号：x.y.z
BaseUI.validatePattern.description // 描述：最多255字符
BaseUI.validatePattern.number      // 正整数
```

## 弹窗

```typescript
// 表格删除弹窗（自动与表格绑定）
BaseUI.tableDeleteModal(tableId, '标题', cardTitle?, properties?)
// 触发：deleteButton 会自动调用 setValue_${tableId}_modal(true)

// 自定义弹窗
{
  '#type': 'aws_modal',
  '#header': '弹窗标题',
  '#on_dismiss': `setValue_modal(false)`,
  '#content': content,
  '#footer': BaseUI.panelWithActions({ cancel: ..., confirm: ... })
}
```

## 状态指示器

```typescript
BaseUI.statusIndicator(
  BaseUI.markupItem('item.status_type'),  // success/error/warning/loading/stopped/pending
  BaseUI.markupItem('{item.status_label}')
)
```

## 其他常用

```typescript
// JSX 直接插入
BaseUI.markupItem('<div id="my_chart"></div>')

// 链接
BaseUI.link('链接文字', url, isExternal?, fontSize?, variant?)

// box 容器（灵活样式）
BaseUI.box(content, color?, float?, fontSize?, fontWeight?, tagOverride?, variant?, padding?)

// 添加额外属性
BaseUI.addSetting(component, { '#prefix': '...', '#suffix': '...' })

// 分割线 / 空间
BaseUI.horizontalPanel(content, size?)  // 横排

// 分段控件
BaseUI.segmentedControl(options, defaultValue)

// 属性编辑器（键值对列表）
BaseUI.attributeEditorAws(fields, defaultValue, empty, disableAddButton)

// 剪贴板
BaseUI.clipboard(text, variant, copyButtonText)
```
