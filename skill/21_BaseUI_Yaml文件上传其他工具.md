# BaseUI Yaml / 文件上传 / 隐藏字段 / 其他工具方法

## Yaml 相关

### yamlField — YAML 编辑器（表单中）

```typescript
// 返回 [spinner_box, hidden_textarea] 数组
// 框架自动将 box 渲染为 CodeMirror YAML 编辑器
BaseUI.yamlField(id, data?)

// 示例
const yamlContent = {
  yaml_editor: BaseUI.yamlField('yaml_content', existingYaml)
}
// 注意：返回数组，需展开后放入 spaceBetween 的 content
BaseUI.spaceBetween([...Object.values(formFields), ...BaseUI.yamlField('yaml_content', data.yaml)])
```

### yamlFunction — YAML 主题标记

```typescript
// 配合 '#theme': 'yaml' 使用，触发前端 YAML 高亮渲染
BaseUI.yamlFunction(id, read_only?)
// read_only=true 时只读，cursor=-1
// read_only=false 时可编辑，cursor=530（默认光标位置）
```

### yamlTextArea — YAML 文本域（简单版）

```typescript
BaseUI.yamlTextArea(id, content?)
// 生成 '#theme': 'yaml' 结构，适合简单场景
```

## 文件上传相关

### filelubanField — 鲁班文件上传（表单内嵌）

```typescript
BaseUI.filelubanField(
  oss,                  // { accessKey, secretKey, endPoint, bucket }
  title,                // 上传组件标题
  placeholder,          // 占位文字
  description,          // 描述文字
  uploadPath,           // S3 目标路径（目录）
  uploadDefaultFileName?, // 固定文件名（如 'code'）
  uploadFileExts?,        // 限制扩展名（如 '.zip'）
  multiple?,              // 是否多文件，默认 0
  attributes?,
  required?,
  size?,                  // 最大文件大小（字节），默认 10MB
  value?,                 // 默认值
)
```

```typescript
// 实战示例（上传 zip 文件）
BaseUI.filelubanField(
  {
    accessKey: Base.OSS_KEY,
    secretKey: Base.OSS_SECRET,
    endPoint:  Base.OSS_URL,
    bucket:    Base.OSS_BUCKET,
  },
  '',                         // 无标题
  '',                         // 无占位
  '仅支持 .zip 文件，文件大小不超过10M',
  dir,                        // 上传目标目录
  'code',                     // 固定文件名（上传后为 code.zip）
  '.zip',                     // 只允许 zip
)
```

### uploadCodeModal — 代码上传弹窗（封装）

```typescript
BaseUI.uploadCodeModal(
  modalName,  // 弹窗状态变量名，如 'upload_code_modal'
  dir,        // 上传目标目录（S3 路径）
)
// 生成完整的上传弹窗（含文件选择器+取消/上传按钮）
```

## 隐藏字段

```typescript
// 隐藏文本框（传递 id 等不可见数据）
BaseUI.hiddenInput('id', data.id)
BaseUI.hiddenInput('project_id', this.currentProject())

// 隐藏文本域（传递大量数据，如 JSON 字符串）
BaseUI.hiddenTextArea('config_json', JSON.stringify(data.config))

// 原生 hidden（较少用）
BaseUI.hiddenField('some_value')
```

## Icon 图标

```typescript
BaseUI.aws_icon(name?, size?, variant?)

// 常见图标名
'add-plus'        // 添加
'remove'          // 删除
'refresh'         // 刷新
'settings'        // 设置
'user-profile'    // 用户
'notification'    // 通知
'copy'            // 复制
'upload'          // 上传
'download'        // 下载
'search'          // 搜索
'filter'          // 过滤
'folder'          // 文件夹
'file'            // 文件
'star'            // 收藏
'thumbs-up'       // 点赞
'support'         // 支持/帮助
'external'        // 外链

// 示例
BaseUI.aws_icon('settings', 'normal', 'subtle')
```

## statusIndicator — 状态指示器

```typescript
BaseUI.statusIndicator(statusType, content)
// statusType: 'success' | 'error' | 'warning' | 'loading' | 'stopped' | 'pending' | 'info'

// 在详情页使用（文字）
BaseUI.statusIndicator('success', '运行中')
BaseUI.statusIndicator('error', '失败')
BaseUI.statusIndicator('loading', '部署中...')

// 在表格 cell 中使用（变量）
BaseUI.statusIndicator(
  BaseUI.markupItem('item.status_type'),
  BaseUI.markupItem('{item.status_content}')
)
```

```typescript
// 状态转换函数示例（后端处理状态）
protected getStatusContent(status: string) {
  switch (status) {
    case 'RUNNING':  return { status_type: 'success', status_content: '运行中' };
    case 'FAILED':   return { status_type: 'error',   status_content: '失败' };
    case 'STOPPING': return { status_type: 'loading', status_content: '停止中' };
    case 'STOPPED':  return { status_type: 'stopped', status_content: '已停止' };
    default:         return { status_type: 'pending', status_content: status };
  }
}
```

## badge — 徽章标签

```typescript
BaseUI.badge('NEW', 'blue')
BaseUI.badge('已授权', 'green')
BaseUI.badge('已过期', 'red')
BaseUI.badge('待审核', 'grey')

// 颜色: 'blue' | 'grey' | 'green' | 'red'
```

## link — 超链接

```typescript
BaseUI.link(
  title,       // 链接文字（或 component）
  url,         // 链接地址
  newPage?,    // 是否新标签打开，默认 false
  font_size?,
  variant?,    // 'primary' | 'secondary' | 'info'
)

// 在 cardItem 中放链接
BaseUI.cardItem('文档', BaseUI.link('查看文档', 'https://...', true))

// 在 cardItem 中放外链（快捷方法）
BaseUI.cardItemLinkBlank('文档', '查看文档', 'https://...')
```

## apiMethodMarkup — HTTP 方法样式

```typescript
// 给 HTTP 方法名添加颜色样式
BaseUI.apiMethodMarkup('GET')    // → <span class="taas-api-method-get">GET</span>
BaseUI.apiMethodMarkup('POST')
BaseUI.apiMethodMarkup('PUT')
BaseUI.apiMethodMarkup('DELETE')
```

## cardContent — 卡片内容包装

```typescript
// 表单容器内的 space_between
BaseUI.cardContent(formFields)
// 等价于 spaceBetween(formFields) 的简化写法
```

## textAreaAws — 独立多行文本框（不含 formField 包装）

```typescript
BaseUI.textAreaAws(default_value?, rows?, disabled?)
// 直接返回 aws_text_area 组件（不包裹 aws_form_field）
// 通常用于只读展示场景
```

## awsTokenGroup — Token 标签组（不含 formField 包装）

```typescript
BaseUI.awsTokenGroup(value?)
// 直接返回 aws_token_group 组件
// value 格式: [{ label: 'tag1' }, { label: 'tag2' }]
```

## datetimeFormat — 后端时间格式化

```typescript
// 在 build 方法（后端）中格式化时间，直接输出字符串
BaseUI.datetimeFormat(data.createdAt)
// → '2024-01-15 14:30:00'

// 注意：这是 TypeScript 中调用的，不是前端 JS
// 前端用 faas_time_format()，后端用 BaseUI.datetimeFormat()
```
