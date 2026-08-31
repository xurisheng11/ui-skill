# aws_calendar

日历组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 字符串 | 是 | 当前日期 (YYYY-MM-DD) |
| granularity | 字符串 | 否 | 选择粒度 |
| locale | 字符串 | 否 | 语言环境 |
| start_of_week | 数字 | 否 | 周开始日 (0-6) |
| is_date_enabled | 函数 | 否 | 日期是否可用 |
| date_disabled_reason | 函数 | 否 | 日期禁用原因 |
| disabled | 布尔值 | 否 | 是否禁用 |

### granularity 可选值

- `day` - 按天（默认）
- `month` - 按月

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
          "#type": "aws_calendar",
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
          "#type": "aws_calendar",
          "#default_value": "2024-01-15"
        }
      ]
    }
  }
}
```

### 按月选择

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

### 中文环境

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

### 周一开始

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

### 周日开始

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
          "#type": "aws_calendar",
          "#disabled": true,
          "#default_value": "2024-02-20"
        }
      ]
    }
  }
}
```

### 日期范围选择

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

### 会议日期

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

### 生日选择

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

### 预约日期

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

### 年月选择器

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

### 今天是

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

### 周末禁用示例

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
          "#default_value": "2024-07-22"
        }
      ]
    }
  }
}
```

### 指定日期

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
