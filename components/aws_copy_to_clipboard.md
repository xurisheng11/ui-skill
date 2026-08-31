# aws_copy_to_clipboard

AWS 复制到剪贴板组件，允许用户一键复制文本内容到剪贴板。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| text_to_copy | 字符串 | 是 | 要复制的文本内容。当 variant="inline" 时，显示在按钮旁 | - | - |
| variant | 字符串 | 否 | 决定复制按钮的样式 | button / icon / inline | "button" |
| copy_button_text | 字符串 | 否 | 复制按钮的文本（仅 variant="button" 时生效） | - | - |
| copy_button_aria_label | 字符串 | 否 | 复制按钮的 aria-label，用于无障碍访问 | - | - |
| copy_success_text | 字符串 | 是 | 复制成功时显示的消息 | - | - |
| copy_error_text | 字符串 | 是 | 复制失败时显示的错误消息 | - | - |
| popover_render_with_portal | 布尔值 | 否 | 是否使用 React Portals 渲染弹出框 | - | false |

### variant 可选值说明

| 值 | 描述 |
| --- | --- |
| button | 显示带图标的次要按钮和文本 |
| icon | 显示独立的图标按钮（无文本） |
| inline | 在文本上下文中显示图标按钮（无文本） |

## 重要说明

**安全限制**：复制功能仅可在 HTTPS 环境下使用。

## 使用示例

### 基础用法（button 变体）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "https://www.baidu.com",
          "#copy_success_text": "复制成功",
          "#copy_error_text": "复制失败，请重试"
        }
      ]
    }
  }
}
```

### 内联变体（inline）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "https://www.baidu.com",
          "#variant": "inline",
          "#copy_success_text": "复制成功",
          "#copy_error_text": "复制失败，请重试"
        }
      ]
    }
  }
}
```

### 图标变体（icon）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "secret-api-key-12345",
          "#variant": "icon",
          "#copy_success_text": "已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 带自定义按钮文本

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "invitation-code-ABC123",
          "#variant": "button",
          "#copy_button_text": "复制邀请码",
          "#copy_success_text": "邀请码已复制",
          "#copy_error_text": "复制失败，请重试"
        }
      ]
    }
  }
}
```

### 带无障碍标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "content-to-copy-123",
          "#variant": "button",
          "#copy_button_aria_label": "复制内容到剪贴板",
          "#copy_success_text": "已复制到剪贴板",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 复制链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "https://example.com/share/abc123",
          "#variant": "button",
          "#copy_button_text": "复制链接",
          "#copy_success_text": "链接已复制到剪贴板",
          "#copy_error_text": "复制失败，请手动复制"
        }
      ]
    }
  }
}
```

### 复制代码

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "npm install @aws/aws-sdk",
          "#variant": "icon",
          "#copy_success_text": "命令已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 复制 API 密钥

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "sk_live_51ABC123xyz789",
          "#variant": "icon",
          "#copy_button_aria_label": "复制 API 密钥",
          "#copy_success_text": "API 密钥已复制",
          "#copy_error_text": "无法复制，请检查浏览器设置"
        }
      ]
    }
  }
}
```

### 复制配置值

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "DATABASE_URL=postgresql://user:pass@localhost:5432/dbname",
          "#variant": "inline",
          "#copy_success_text": "配置已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 复制序列号

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "SN-2024-001234567",
          "#variant": "button",
          "#copy_button_text": "复制序列号",
          "#copy_success_text": "序列号已复制",
          "#copy_error_text": "复制失败，请重试"
        }
      ]
    }
  }
}
```

### 复制多行文本

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "第一行内容\n第二行内容\n第三行内容",
          "#variant": "button",
          "#copy_button_text": "复制全部",
          "#copy_success_text": "多行文本已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 复制 JSON 数据

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_copy_to_clipboard",
          "#text_to_copy": "{\"name\": \"张三\", \"email\": \"zhangsan@example.com\"}",
          "#variant": "icon",
          "#copy_success_text": "JSON 已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```
