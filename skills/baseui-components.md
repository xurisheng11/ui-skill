# BaseUI 组件封装

## 概述

BaseUI 类封装了 Luban 前端框架的常用组件，提供统一的构建方式。

## 按钮组件

### 普通按钮

```typescript
BaseUI.button(title, variant, href, disable_definition, on_click, icon_name, classes)
```

- `title`: 按钮文字
- `variant`: 样式类型 `'primary'` | `'normal'` | `'link'`
- `href`: 链接地址
- `disable_definition`: 禁用条件表达式
- `on_click`: 点击事件 JS 代码
- `icon_name`: 图标名称

示例：
```typescript
BaseUI.button('提交', 'primary')
BaseUI.button('取消', 'normal', '/list')
```

### 点击按钮（带 JS 事件）

```typescript
BaseUI.clickButton(title, click, variant, disable_definition, classes)
```

示例：
```typescript
BaseUI.clickButton('删除', `setValue_${modalName}(true)`, 'normal', 'selected_ids.length === 0')
```

### 提交按钮

```typescript
BaseUI.submitButton(title, variant = 'primary')
```

示例：
```typescript
BaseUI.submitButton('保存')
BaseUI.submitButton('创建')
```

### 刷新按钮

```typescript
BaseUI.refreshButton()
```

### 链接按钮

```typescript
BaseUI.linkButton(title, url)
BaseUI.linkButtonLight(title, url, variant)
BaseUI.linkCommonButton(title, url)
```

### 删除按钮（带模态框）

```typescript
BaseUI.deleteButton(id, title, disable_when)
```

### 普通提交按钮

```typescript
BaseUI.commonButton(title, tableId, click_when)
```

示例：
```typescript
// tableId 为空时无禁用
BaseUI.commonButton('编辑', 'table_list')
// 禁用条件
BaseUI.commonButton('删除', 'table_list', 'selected_table_list.length === 0')
```

## 表单字段

### 文本输入框

```typescript
BaseUI.textField(
  id,           // 字段ID
  title,        // 标题
  placeholder,  // 占位符
  constraint_text, // 约束说明
  value,        // 默认值
  attributes,   // 属性（pattern 等）
  required,     // 是否必填
  disabled,     // 是否禁用
  titleDescription, // 标题说明
  maxlength,    // 最大长度
  info,         // 提示信息
  secondary_control, // 次要控件
  onChange      // onChange 事件
)
```

### 多行文本框

```typescript
BaseUI.textArea(
  id,
  title,
  placeholder,
  constraint_text,
  value,
  attributes,
  required,
  maxLength,
  disabled,
  showRequired
)
```

### 数字输入框

```typescript
BaseUI.numberField(id, title, constraint_text, value, attributes, required, disabled)
```

### 密码输入框

```typescript
BaseUI.passwordField(id, title, placeholder, constraint_text, value, attributes, required)
```

### 日期选择器

```typescript
BaseUI.datePicker(id, title, placeholder, constraint_text, value, attributes, required)
```

### 下拉选择框

```typescript
BaseUI.selectField(
  id,
  title,
  options,     // 选项数组 [{label, value}, ...]
  defaultValue,
  titleDescription,
  filtering_type,  // 'auto' | 'none'
  info,
  constraintText,
  placeholder,
  disabled,
  required,
  onChange
)
```

### Radio 单选框

```typescript
BaseUI.radioField(id, title, value, constraint_text, options, required)
```

### Checkbox 多选框/开关

```typescript
BaseUI.checkboxField(id, title, constraint_text, value, required)
```

### Token Group

```typescript
BaseUI.tokenGroup(id, title, constraint_text, value, attributes, required)
```

## 布局组件

### 横向排列

```typescript
BaseUI.horizontalPanel(content, size)
BaseUI.spaceBetween(content, actions, direction, size, align)
```

示例：
```typescript
BaseUI.spaceBetween(
  {
    field1: BaseUI.textField(...),
    field2: BaseUI.selectField(...),
  },
  buttonContent,
  'horizontal',  // 水平排列
  'm',          // 中等间距
  'center'      // 垂直居中
)
```

### 纵向排列

```typescript
BaseUI.spaceBetween(content, actions, 'vertical', size)
```

### 卡片容器

```typescript
BaseUI.container(content, title, buttons, description, disable_content_paddings, className)
BaseUI.cardPanel(title, content, buttons, description)
```

### 卡片面板（可编辑）

```typescript
BaseUI.cardPanelWithEdit(
  title,
  editUrl,
  items,
  editable,
  description,
  columns
)
```

### 页面标题

```typescript
BaseUI.pageTitle(field, title, variant, description, actions)
```

## 表格组件

### 表格列头

```typescript
BaseUI.tableHeader(id, header, cell, minWidth, maxWidth, width)
```

常用快捷方法：
```typescript
BaseUI.tableHeaderTime(id, header)        // 时间列
BaseUI.tableHeaderName()                   // 名称列
BaseUI.tableHeaderTitle(header)            // 标题列
BaseUI.tableHeaderCreated()                // 创建时间
BaseUI.tableHeaderUpdated()               // 更新时间
BaseUI.tableHeaderDescription()           // 描述列
```

### 表格（带操作栏）

```typescript
BaseUI.tableWithActions(
  tableId,
  title,
  actions,
  table,
  description,
  noCheck,
  headerContent,
  cardTitle,
  properties
)
```

### 动态翻页表格

```typescript
BaseUI.tableAjax(
  header,
  url,
  needCheckBox,
  multiple,
  order,
  disorder_columns,
  selectors,
  selected,
  rows,
  track_by
)
```

### 表格选择

```typescript
BaseUI.tableSelect(
  column_definitions,
  rows,
  multiple,
  order,
  selectors,
  pagination,
  items_per_page,
  selected,
  track_by,
  disorder_columns
)
```

### 表格链接

```typescript
BaseUI.tableLink(content, url, newPage)
```

## 模态框

### 删除确认模态框

```typescript
BaseUI.tableDeleteModal(tableId, title, cardTitle, properties)
BaseUI.commonDeleteModal(tableId, title, value, cardTitle, properties)
```

### 抽查确认模态框

```typescript
BaseUI.spotCheckModal(modalName, hideFailButton)
```

## Tab 组件

```typescript
BaseUI.tabs(children, defaultTab, id)
BaseUI.tabItem(id, header, content)
```

示例：
```typescript
BaseUI.tabs(
  {
    tab1: BaseUI.tabItem('tab1', '标签1', content1),
    tab2: BaseUI.tabItem('tab2', '标签2', content2),
  },
  'tab1'  // 默认选中
)
```

## 状态指示器

```typescript
BaseUI.statusIndicator(statusType, content)
```

- `statusType`: `'loading'` | `'success'` | `'error'` | `'pending'` | `'warning'` | `'stopped'`

## 徽章

```typescript
BaseUI.badge(value, color)
```

## Box 组件

```typescript
BaseUI.box(content, color, float, font_size, font_weight, tag_override, variant, padding, align, display)
BaseUI.boxNew(content, display)
BaseUI.box_display(content, display)
```

## 标记内容

```typescript
BaseUI.markupItem(markupContent)
```

示例：
```typescript
BaseUI.markupItem('<b>加粗文字</b>')
BaseUI.markupItem('{variable}')
BaseUI.markupItem('`template literal`')
```

## 属性添加/修改

```typescript
BaseUI.addSetting(element, setting)
```

用于添加 `#prefix`、`#suffix` 等属性。

## 通用选项构建

```typescript
BaseUI.cardItem(label, value)
```

返回 `{ label, value }` 格式，用于 select 选项。

## 表单字段包装

```typescript
BaseUI.formField(
  id,
  title,
  field,
  constraint_text,
  attributes,
  required,
  titleDescription,
  info,
  showRequired
)
```

## 展开区域

```typescript
BaseUI.ExpandableSection(text, content, actions)
```

## 辅助内容面板

```typescript
BaseUI.help_panel(content)
```

## OffCanvas 侧边面板

```typescript
BaseUI.offCanvas(body, header)
```

## 日期时间格式化

```typescript
BaseUI.datetimeFormat(utc_datetime)
BaseUI.formatTime(totalSeconds)
BaseUI.runTime(runStatus, totalSeconds)
```

## 按钮组

```typescript
BaseUI.groupButtons(title, buttons)
```

## 代码展示

```typescript
BaseUI.codeView(language, code)
```

## 复制到剪贴板

```typescript
BaseUI.getTriggerCopyContent(value, variant)
```

## 验证模式

在 `BaseUI.validatePattern` 中预定义了常用验证：

```typescript
BaseUI.validatePattern.titleNew     // 标题验证
BaseUI.validatePattern.description   // 描述验证
BaseUI.validatePattern.technicalCode // 技术类编号
BaseUI.validatePattern.managementCode // 管理类编号
BaseUI.validatePattern.checkProcedures // 检查程序
BaseUI.validatePattern.requiredDocuments // 文档资料
```

## AWS Select 下拉框

```typescript
BaseUI.selectAws(
  options,
  defaultValue,
  placeholder,
  required,
  filtering_type,
  disabled,
  prefix,
  suffix,
  onChange
)
```

## Multi Select 多选

```typescript
BaseUI.MultiselectAws(options, defaultValue, placeholder, required, filtering_type)
BaseUI.MultiselectField(id, title, options, defaultValue, filtering_type)
```
