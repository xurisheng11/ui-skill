# aws_date_picker 示例

本文档展示 aws_date_picker 组件的各种使用场景。

## 示例列表

### 1. 基础用法

最基本的日期选择器示例。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
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
        "aws_date_picker": {
          "#type": "aws_date_picker",
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
        "aws_date_picker": {
          "#type": "aws_date_picker",
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
        "aws_date_picker": {
          "#type": "aws_date_picker",
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
        "aws_date_picker": {
          "#type": "aws_date_picker",
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
        "aws_date_picker": {
          "#type": "aws_date_picker",
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
        "aws_date_picker": {
          "#type": "aws_date_picker",
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
        "aws_date_picker": {
          "#type": "aws_date_picker",
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
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#warning": true,
          "#default_value": "2021-01-01"
        }
      }
    }
  }
}
```

### 10. 扩展到视口

在表格或分割视图等可滚动容器内使用时，可以让下拉日历扩展到视口。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#expand_to_viewport": true,
          "#default_value": "2021-01-01"
        }
      }
    }
  }
}
```

### 11. 月份粒度

只允许选择月份。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#granularity": "month",
          "#placeholder": "选择月份",
          "#default_value": ""
        }
      }
    }
  }
}
```

### 12. 自定义一周起始日

设置一周从周一开始。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#start_of_week": 1,
          "#default_value": "2021-01-01"
        }
      }
    }
  }
}
```

### 13. 中文语言环境

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#locale": "zh-CN",
          "#placeholder": "选择日期",
          "#default_value": ""
        }
      }
    }
  }
}
```

### 14. 带国际化字符串

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#i18n_strings": {
            "current_month_aria_label": "当前月份",
            "next_month_aria_label": "下个月",
            "previous_month_aria_label": "上个月",
            "today_aria_label": "今天"
          },
          "#default_value": "2021-01-01"
        }
      }
    }
  }
}
```

### 15. 会议日期选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
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

### 16. 入职日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
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

### 17. 截止日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
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

### 18. 带 control_id

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#control_id": "custom-date-picker-id",
          "#name": "event_date",
          "#default_value": "2026-01-01"
        }
      }
    }
  }
}
```

### 19. 生日选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#name": "birthday",
          "#aria_label": "生日",
          "#placeholder": "年-月-日",
          "#start_of_week": 1,
          "#default_value": "1995-08-15"
        }
      }
    }
  }
}
```

### 20. 出发日期

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_date_picker": {
          "#type": "aws_date_picker",
          "#name": "departure_date",
          "#aria_label": "出发日期",
          "#placeholder": "选择出发日期",
          "#default_value": "2026-10-01"
        }
      }
    }
  }
}
```
