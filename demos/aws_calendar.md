# aws_calendar 示例

本文档展示 aws_calendar 组件的各种使用场景。

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
          "#type": "aws_calendar",
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
          "#type": "aws_calendar",
          "#default_value": "2024-01-15"
        }
      ]
    }
  }
}
```

### 3. 按月选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#granularity": "month",
          "#default_value": "2024-01"
        }
      ]
    }
  }
}
```

### 4. 中文环境

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#locale": "zh-CN",
          "#default_value": "2024-06-01"
        }
      ]
    }
  }
}
```

### 5. 周一开始

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#start_of_week": 1,
          "#default_value": "2024-01-08"
        }
      ]
    }
  }
}
```

### 6. 周日开始

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#start_of_week": 0,
          "#default_value": "2024-01-07"
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
          "#type": "aws_calendar",
          "#disabled": true,
          "#default_value": "2024-02-20"
        }
      ]
    }
  }
}
```

### 8. 日期范围选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#default_value": "2024-03-15"
        }
      ]
    }
  }
}
```

### 9. 会议日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#default_value": "2024-04-10"
        }
      ]
    }
  }
}
```

### 10. 生日选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#default_value": "1990-06-01"
        }
      ]
    }
  }
}
```

### 11. 预约日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#default_value": "2024-05-20"
        }
      ]
    }
  }
}
```

### 12. 年月选择器

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#granularity": "month",
          "#default_value": "2024-09"
        }
      ]
    }
  }
}
```

### 13. 今天是

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#default_value": "2024-08-28"
        }
      ]
    }
  }
}
```

### 14. 指定日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#default_value": "2024-12-25"
        }
      ]
    }
  }
}
```

### 15. 项目截止日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_calendar",
          "#default_value": "2024-07-15"
        }
      ]
    }
  }
}
```
