# aws_date_input

AWS 日期输入组件，一个用于输入日期值的表单元素。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| default_value | 字符串 | 是 | 当前输入值，格式为 YYYY-MM-DD | - | - |
| name | 字符串 | 否 | 指定用于 HTML 表单中的控件名称 | - | - |
| placeholder | 字符串 | 否 | 占位符文本 | - | - |
| control_id | 字符串 | 否 | 原生表单元素的 ID | - | - |
| disabled | 布尔值 | 否 | 禁用控件 | - | false |
| read_only | 布尔值 | 否 | 只读控件 | - | false |
| invalid | 布尔值 | 否 | 覆盖无效状态 | - | false |
| warning | 布尔值 | 否 | 覆盖警告状态 | - | false |
| auto_focus | 布尔值 | 否 | 页面加载时自动获得焦点 | - | false |

### 无障碍属性

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| aria_label | 字符串 | 向原生控件添加 aria-label |
| aria_labelledby | 字符串 | 向组件添加 aria-labelledby |
| aria_describedby | 字符串 | 向组件添加 aria-describedby |
| aria_required | 布尔值 | 指定是否添加 aria-required |

## 使用示例

### 基础用法

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#default_value": "2021-01-01"
        }
      }
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
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#placeholder": "选择日期",
          "#default_value": ""
        }
      }
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
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#default_value": "2021-01-01",
          "#disabled": true
        }
      }
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
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#default_value": "2021-01-01",
          "#read_only": true
        }
      }
    }
  }
}
```

### 自动获得焦点

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#auto_focus": true
        }
      }
    }
  }
}
```

### 带控件名称

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#name": "birth_date",
          "#default_value": "1990-05-15"
        }
      }
    }
  }
}
```

### 无障碍使用

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#aria_label": "出生日期",
          "#aria_required": true,
          "#default_value": ""
        }
      }
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
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#invalid": true,
          "#default_value": "invalid-date"
        }
      }
    }
  }
}
```

### 警告状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#warning": true,
          "#default_value": "2021-01-01"
        }
      }
    }
  }
}
```

### 今天日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#default_value": "2026-08-28"
        }
      }
    }
  }
}
```

### 未来日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#placeholder": "选择会议日期",
          "#default_value": "2027-01-15"
        }
      }
    }
  }
}
```

### 历史日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_input": {
          "#type": "aws_date_input",
          "#placeholder": "选择入职日期",
          "#default_value": "2020-03-01"
        }
      }
    }
  }
}
```
