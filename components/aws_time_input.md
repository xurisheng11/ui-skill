# aws_time_input

时间输入组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 字符串 | 是 | 输入文本 |
| format | 字符串 | 否 | 时间格式 |
| use_24_hour | 布尔值 | 否 | 使用24小时制 |
| placeholder | 字符串 | 否 | 占位符 |
| disabled | 布尔值 | 否 | 是否禁用 |
| read_only | 布尔值 | 否 | 只读状态 |
| invalid | 布尔值 | 否 | 无效状态 |
| auto_focus | 布尔值 | 否 | 自动聚焦 |
| auto_complete | 布尔值 | 否 | 自动完成 |
| disable_browser_autocorrect | 布尔值 | 否 | 禁用自动更正 |

### format 可选值

- `hh` - 仅小时
- `hh:mm` - 小时和分钟
- `hh:mm:ss` - 完整时间（默认）

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
          "#type": "aws_time_input",
          "#default_value": ""
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
          "#type": "aws_time_input",
          "#default_value": "14:30:00"
        }
      ]
    }
  }
}
```

### 12小时制

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_time_input",
          "#use_24_hour": false,
          "#default_value": "02:30:00"
        }
      ]
    }
  }
}
```

### 24小时制

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_time_input",
          "#use_24_hour": true,
          "#default_value": "14:30:00"
        }
      ]
    }
  }
}
```

### 仅小时

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_time_input",
          "#format": "hh",
          "#default_value": "14"
        }
      ]
    }
  }
}
```

### 小时和分钟

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_time_input",
          "#format": "hh:mm",
          "#default_value": "14:30"
        }
      ]
    }
  }
}
```

### 带占位符

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_time_input",
          "#placeholder": "请输入时间"
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
          "#type": "aws_time_input",
          "#disabled": true,
          "#default_value": "10:00:00"
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
          "#type": "aws_time_input",
          "#read_only": true,
          "#default_value": "18:30:00"
        }
      ]
    }
  }
}
```

### 无效状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_time_input",
          "#invalid": true,
          "#default_value": "25:00:00"
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
          "#type": "aws_time_input",
          "#auto_focus": true,
          "#placeholder": "自动聚焦"
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
          "#type": "aws_time_input",
          "#auto_complete": true,
          "#placeholder": "启用自动完成"
        }
      ]
    }
  }
}
```

### 会议时间

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_time_input",
          "#default_value": "09:00:00",
          "#placeholder": "会议开始时间"
        }
      ]
    }
  }
}
```

### 营业时间

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_time_input",
          "#default_value": "08:30:00",
          "#placeholder": "开门时间"
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
          "#type": "aws_time_input",
          "#disable_browser_autocorrect": true,
          "#placeholder": "禁用了自动更正"
        }
      ]
    }
  }
}
```
