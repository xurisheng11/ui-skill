# aws_text_area

文本域组件，用于多行文本输入。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 字符串 | 是 | 输入文本 |
| placeholder | 字符串 | 否 | 占位符文本 |
| rows | 数字 | 否 | 行数 |
| disabled | 布尔值 | 否 | 是否禁用 |
| read_only | 布尔值 | 否 | 只读状态 |
| invalid | 布尔值 | 否 | 无效状态 |
| auto_focus | 布尔值 | 否 | 自动聚焦 |
| spellcheck | 布尔值 | 否 | 拼写检查 |
| auto_complete | 布尔值/字符串 | 否 | 自动完成 |
| disable_browser_autocorrect | 布尔值 | 否 | 禁用浏览器自动更正 |

## 使用示例

### 基础用法

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

### 带默认值

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

### 指定行数

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

### 短文本域

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

### 长文本域

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
          "#placeholder": "请输入详细的文章内容...",
          "#rows": 10
        }
      ]
    }
  }
}
```

### 禁用状态

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
          "#default_value": "此文本域已被禁用，无法编辑。"
        }
      ]
    }
  }
}
```

### 只读状态

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
          "#default_value": "此内容为只读，可以查看但不能修改。"
        }
      ]
    }
  }
}
```

### 自动聚焦

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

### 禁用拼写检查

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

### 禁用自动更正

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

### 备注输入

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

### 反馈内容

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

### 评论输入

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

### 启用自动完成

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

### 禁用自动完成

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
