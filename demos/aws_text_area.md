# aws_text_area 示例

本文档展示 aws_text_area 组件的各种使用场景。

## 示例列表

### 1. 基础用法

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#placeholder": "请输入内容"
        }
      ]
    }
  }
}
```

### 2. 带默认值

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#default_value": "这是预填充的文本内容。"
        }
      ]
    }
  }
}
```

### 3. 指定行数

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#placeholder": "请输入详细描述...",
          "#rows": 5
        }
      ]
    }
  }
}
```

### 4. 短文本域

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#placeholder": "简短回复...",
          "#rows": 2
        }
      ]
    }
  }
}
```

### 5. 禁用状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#disabled": true,
          "#default_value": "此文本域已被禁用。"
        }
      ]
    }
  }
}
```

### 6. 只读状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#read_only": true,
          "#default_value": "此内容为只读。"
        }
      ]
    }
  }
}
```

### 7. 自动聚焦

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#auto_focus": true,
          "#placeholder": "页面加载后自动聚焦于此"
        }
      ]
    }
  }
}
```

### 8. 备注输入

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#placeholder": "请输入备注信息（最多500字）",
          "#rows": 4
        }
      ]
    }
  }
}
```

### 9. 反馈内容

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#placeholder": "请详细描述您遇到的问题或建议...",
          "#rows": 6
        }
      ]
    }
  }
}
```

### 10. 评论输入

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#placeholder": "写下您的评论...",
          "#rows": 3
        }
      ]
    }
  }
}
```

### 11. 长文本域

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#placeholder": "请输入详细文章内容...",
          "#rows": 10
        }
      ]
    }
  }
}
```

### 12. 禁用拼写检查

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#spellcheck": false,
          "#placeholder": "禁用了拼写检查的文本域"
        }
      ]
    }
  }
}
```

### 13. 禁用自动更正

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#disable_browser_autocorrect": true,
          "#placeholder": "禁用了自动更正..."
        }
      ]
    }
  }
}
```

### 14. 启用自动完成

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#auto_complete": true,
          "#placeholder": "启用自动完成..."
        }
      ]
    }
  }
}
```

### 15. 禁用自动完成

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_area",
          "#auto_complete": false,
          "#placeholder": "禁用了自动完成，适用于敏感信息..."
        }
      ]
    }
  }
}
```
