# aws_copy_to_clipboard 示例

本文档展示 aws_copy_to_clipboard 组件的各种使用场景。

## 示例列表

### 1. 基础用法（button 变体）

最常用的复制按钮样式，显示带图标的按钮和文本。

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

### 2. 内联变体（inline）

在文本上下文中显示图标按钮，适合嵌入文本内容中。

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

### 3. 图标变体（icon）

只显示图标按钮，节省空间。

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
          "#text_to_copy": "secret-key-12345",
          "#variant": "icon",
          "#copy_success_text": "已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 4. 带自定义按钮文本

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
          "#text_to_copy": "REFERRAL-CODE-2024",
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

### 5. 复制链接

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
          "#text_to_copy": "https://example.com/invite/abc123xyz",
          "#variant": "button",
          "#copy_button_text": "复制链接",
          "#copy_success_text": "链接已复制到剪贴板",
          "#copy_error_text": "复制失败，请手动复制链接"
        }
      ]
    }
  }
}
```

### 6. 复制命令行

适合复制代码或命令片段。

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
          "#text_to_copy": "git clone https://github.com/example/repo.git",
          "#variant": "icon",
          "#copy_success_text": "命令已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 7. 复制 API 密钥

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
          "#copy_error_text": "无法复制，请检查浏览器权限"
        }
      ]
    }
  }
}
```

### 8. 复制数据库连接字符串

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
          "#text_to_copy": "postgresql://username:password@hostname:5432/database",
          "#variant": "inline",
          "#copy_success_text": "连接字符串已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 9. 复制序列号

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
          "#text_to_copy": "SN-2024-0000123456",
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

### 10. 复制优惠券码

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
          "#text_to_copy": "SAVE20OFF",
          "#variant": "button",
          "#copy_button_text": "复制优惠码",
          "#copy_success_text": "优惠码已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 11. 复制多行文本

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
          "#text_to_copy": "地址：第一行\n城市：第二行\n邮编：第三行",
          "#variant": "button",
          "#copy_button_text": "复制地址",
          "#copy_success_text": "地址已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 12. 复制 JSON 配置

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
          "#text_to_copy": "{\"app_name\": \"MyApp\", \"version\": \"1.0.0\", \"debug\": true}",
          "#variant": "icon",
          "#copy_success_text": "JSON 已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 13. 复制电子邮箱

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
          "#text_to_copy": "contact@example.com",
          "#variant": "button",
          "#copy_button_text": "复制邮箱",
          "#copy_success_text": "邮箱地址已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```

### 14. 复制银行卡号

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
          "#text_to_copy": "6222 **** **** 1234",
          "#variant": "icon",
          "#copy_button_aria_label": "复制银行卡号",
          "#copy_success_text": "卡号已复制",
          "#copy_error_text": "复制失败"
        }
      ]
    }
  }
}
```
