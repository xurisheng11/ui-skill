# BaseUI 表单字段方法详解

所有表单字段方法最终都经由 `formField` 包装，生成标准的 `aws_form_field` 结构。

## formField — 底层包装（所有字段的基础）

```typescript
// 签名
BaseUI.formField(
  id,                // 控件的 key（也是提交时的字段名）
  title,             // 标签文字，不填则无标签
  field,             // 控件对象（aws_input / aws_select / ...）
  constraint_text?,  // 约束说明文字
  attributes?,       // 扩展属性 { pattern, pattern_err, class, ... }
  required?,         // 是否必填，默认 true
  titleDescription?, // 标签下方的描述
  info?,             // 标签右侧的 info 链接/提示
  showRequired?,     // 是否在标签显示"- 可选"，默认 true
)
```

**非必填字段**：标题末尾写 `'字段名 - 可选'`，或 `required=false`，框架自动在标签后显示斜体"- 可选"。

```typescript
// 必填
BaseUI.textField('name', '名称', '', null, data.name)

// 可选（方式1：标题带" - 可选"）
BaseUI.textArea('description', '描述 - 可选', '', null, data.description, {}, false)

// 可选（方式2：required=false）
BaseUI.textField('remark', '备注', '', null, data.remark, {}, false)
```

## 所有表单字段方法

### textField — 文本输入框

```typescript
BaseUI.textField(
  id,               // 'my_field'
  title,            // '字段名'
  placeholder,      // '请输入...'
  constraint_text,  // '最多63个字符' 或 BaseUI.validatePattern.name.message
  value?,           // 默认值（编辑时填 data.xxx）
  attributes?,      // { pattern: '...', pattern_err: '...' }
  required?,        // 默认 true
  disabled?,        // 是否禁用，默认 false
  titleDescription?,// 标签下说明文字
  maxlength?,       // 最大输入长度
  info?,            // info 提示
  secondary_control?,// 右侧附加控件
  onChange?,        // change 事件 JS
)

// 常用写法
BaseUI.textField('name', '名称', '', BaseUI.validatePattern.name.message, data.name,
  { pattern: BaseUI.validatePattern.name.pattern })
```

### numberField — 数字输入框

```typescript
BaseUI.numberField(
  id, title, constraint_text,
  value?,      // 默认值
  attributes?, // { pattern: BaseUI.validatePattern.number.pattern }
  required?,   // 默认 true
  disabled?,   // 默认 false
)

// 示例
BaseUI.numberField('port', '端口', BaseUI.validatePattern.number.message, data.port,
  { pattern: BaseUI.validatePattern.number.pattern })
```

### textArea — 多行文本框

```typescript
BaseUI.textArea(
  id, title, placeholder, constraint_text,
  value?,     maxLength?,  disabled?
)

// 示例
BaseUI.textArea('description', '描述 - 可选', '', BaseUI.validatePattern.description.message,
  data.description, { pattern: BaseUI.validatePattern.description.pattern }, false)
```

### passwordField — 密码输入框

```typescript
BaseUI.passwordField(id, title, placeholder, constraint_text, value?, attributes?, required?)
```

### selectField — 下拉选择

```typescript
BaseUI.selectField(
  id, title,
  options,         // [{ label: '选项1', value: 'v1' }, ...]
  defaultValue?,   // { label: '...', value: '...' } 或 undefined
  titleDescription?,
  filtering_type?, // 'none'(默认) | 'auto'(可搜索)
  info?,
  constraintText?,
  placeholder?,    // 默认'请选择'
  disabled?,
  required?,
  onChange?,       // change 事件 JS
)

// 示例
BaseUI.selectField('type', '类型', typeOptions, 
  data.type ? { label: data.type, value: data.type } : undefined)

// 带搜索的下拉（选项多时用）
BaseUI.selectField('env', '环境', envOptions, undefined, undefined, 'auto')
```

### MultiselectField — 多选下拉

```typescript
BaseUI.MultiselectField(
  id, title,
  options,       // 选项数组
  defaultValue,  // 数组形式 [{ label, value }, ...]
  filtering_type?
)
```

### radioField — 单选组

```typescript
BaseUI.radioField(
  id, title,
  value,     // 默认选中值
  constraint_text,
  options,   // [{ label: '选项1', value: 'v1' }, ...]
  required?
)

// 示例
BaseUI.radioField('scope', '范围', 'PUBLIC', null, [
  { label: '公开', value: 'PUBLIC' },
  { label: '私有', value: 'PRIVATE' },
])
```

### checkboxField — 开关/复选框（实际用 aws_toggle）

```typescript
BaseUI.checkboxField(
  id,
  title,           // 开关旁边的文字
  constraint_text,
  value?,          // 默认值，默认 false
  required?        // 默认 false
)

// 示例
BaseUI.checkboxField('enable_scan', '启用代码扫描', '支持代码扫描功能。', false)
```

### textTiles — 卡片式单选（Tiles）

```typescript
BaseUI.textTiles(
  id, title, constraint_text,
  attributes?,
  required?,
  titleDescription?,
  info?,
  secondary_control?,
  items?,         // [{ label: '选项1', value: 'v1', description: '...' }]
  columns?,       // 每行列数，默认 3
  defaultValue?,  // 默认选中值
)

// 示例
BaseUI.textTiles('install_type', '安装类型', null, {}, true, undefined, undefined, undefined,
  [
    { label: '授权码安装', value: 'LICENSE', description: '通过授权码激活' },
    { label: '免费安装',   value: 'FREE',    description: '无需授权码' },
  ], 2, 'FREE'
)
```

### datePicker — 日期选择器

```typescript
BaseUI.datePicker(id, title, placeholder, constraint_text, value?, attributes?, required?)
```

### tokenGroup — 标签组（带表单包装）

```typescript
BaseUI.tokenGroup(id, title, constraint_text, value?, attributes?, required?)
// value 格式：[{ label: 'tag1' }, { label: 'tag2' }]
```

### hiddenInput — 隐藏输入框

```typescript
// 用于传递后端需要的隐藏字段（如 id）
BaseUI.hiddenInput('id', data.id)       // 文本框隐藏
BaseUI.hiddenTextArea('data', jsonStr)   // 文本域隐藏（存大量数据时）
```

### textBox — 只读显示字段（box 包装）

```typescript
// 把固定内容显示在表单字段位置，不可编辑
BaseUI.textBox(id, title, constraint_text, content, attributes?, required?, info?)

// 示例
BaseUI.textBox('current_version', '当前版本', null, data.version)
```

## submit 中解析表单值

```typescript
// select 值解析（JSON 字符串 → value）
this.selectValue(body.type)          // → 'TYPE_A'
this.selectName(body.type)           // → 'TYPE_A'（同 selectValue）

// multiselect 值解析（JSON 字符串 → 逗号分隔值）
this.multiSelectValue(body.tags)     // → 'v1,v2,v3'
this.multiLabelValue(body.tags)      // → '标签1,标签2,标签3'

// checkbox/toggle 解析
this.isChecked(body.enable_scan)     // true 或 false

// 数字字段解析
parseInt(body.port, 10)
```
