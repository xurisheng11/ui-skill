# aws_time_input 示例

本文档展示 aws_time_input 组件的各种使用场景。

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
          "#type": "aws_time_input",
          "#default_value": ""
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
          "#type": "aws_time_input",
          "#default_value": "14:30:00"
        }
      ]
    }
  }
}
```

### 3. 12小时制

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

### 4. 仅小时

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

### 5. 小时和分钟

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

### 6. 带占位符

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

### 7. 禁用状态

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

### 8. 只读状态

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

### 9. 会议时间

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

### 10. 营业时间

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

### 11. 自动聚焦

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

### 12. 无效状态

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

### 13. 启用自动完成

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

### 14. 关闭时间

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
          "#default_value": "18:00:00",
          "#placeholder": "关门时间"
        }
      ]
    }
  }
}
```

### 15. 24小时制

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
          "#default_value": "23:59:59"
        }
      ]
    }
  }
}
```
