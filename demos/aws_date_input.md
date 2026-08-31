# aws_date_input 示例

本文档展示 aws_date_input 组件的各种使用场景。

## 示例列表

### 1. 基础用法

最基本的日期输入框示例。

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

### 2. 带占位符

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

### 3. 禁用状态

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

### 4. 只读状态

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

### 5. 自动获得焦点

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
          "#auto_focus": true,
          "#default_value": ""
        }
      }
    }
  }
}
```

### 6. 带控件名称

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

### 7. 无障碍使用

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

### 8. 无效状态

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
          "#default_value": "2021-01-01"
        }
      }
    }
  }
}
```

### 9. 警告状态

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

### 10. 生日日期

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
          "#name": "birthday",
          "#aria_label": "生日",
          "#placeholder": "年-月-日",
          "#default_value": "1995-08-15"
        }
      }
    }
  }
}
```

### 11. 会议日期

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
          "#name": "meeting_date",
          "#aria_label": "会议日期",
          "#placeholder": "选择会议日期",
          "#default_value": "2026-09-20"
        }
      }
    }
  }
}
```

### 12. 入职日期

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
          "#name": "hire_date",
          "#aria_label": "入职日期",
          "#placeholder": "选择入职日期",
          "#default_value": "2020-06-01"
        }
      }
    }
  }
}
```

### 13. 截止日期

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
          "#name": "deadline",
          "#aria_label": "项目截止日期",
          "#placeholder": "选择截止日期",
          "#default_value": "2026-12-31"
        }
      }
    }
  }
}
```

### 14. 带 control_id

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
          "#control_id": "custom-date-input-id",
          "#name": "event_date",
          "#default_value": "2026-01-01"
        }
      }
    }
  }
}
```
