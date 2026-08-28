# aws_date_picker

AWS 日期选择器组件，用户可以通过输入或日历选择日期。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| default_value | 字符串 | 是 | 当前输入值，格式为 YYYY-MM-DD | - | '' |
| name | 字符串 | 否 | 指定用于 HTML 表单中的控件名称 | - | - |
| placeholder | 字符串 | 否 | 占位符文本 | - | '' |
| control_id | 字符串 | 否 | 原生表单元素的 ID | - | - |
| disabled | 布尔值 | 否 | 禁用控件 | - | false |
| read_only | 布尔值 | 否 | 只读控件 | - | false |
| invalid | 布尔值 | 否 | 覆盖无效状态 | - | false |
| warning | 布尔值 | 否 | 覆盖警告状态 | - | false |
| auto_focus | 布尔值 | 否 | 页面加载时自动获得焦点 | - | false |
| expand_to_viewport | 布尔值 | 否 | 下拉列表扩展到视口外 | - | false |
| granularity | 字符串 | 否 | 日期选择粒度 | day / month | 'day' |
| locale | 字符串 | 否 | 语言环境 | - | '' |
| start_of_week | 数字 | 否 | 一周起始日（0-6 对应周日到周六） | - | - |

### 日期控制属性

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| is_date_enabled | 函数 | 定义特定日期是否启用 |
| date_disabled_reason | 函数 | 提供禁用日期的原因 |

### 国际化属性

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| i18n_strings | 对象 | 本地化字符串对象 |

### i18n_strings 对象结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| current_month_aria_label | 字符串 | 当前月份的 aria-label |
| next_month_aria_label | 字符串 | 下个月的 aria-label |
| next_year_aria_label | 字符串 | 明年的 aria-label |
| previous_month_aria_label | 字符串 | 上个月的 aria-label |
| previous_year_aria_label | 字符串 | 去年的 aria-label |
| today_aria_label | 字符串 | 今天的 aria-label |

### 无障碍属性

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| aria_label | 字符串 | 向原生控件添加 aria-label |
| aria_labelledby | 字符串 | 向组件添加 aria-labelledby |
| aria_describedby | 字符串 | 向组件添加 aria-describedby |
| aria_required | 布尔值 | 指定是否添加 aria-required |
| open_calendar_aria_label | 函数 | 生成打开日历按钮的 aria-label |

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
        "aws_date_picker": {
          "#type": "aws_date_picker",
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

### 禁用状态

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

### 只读状态

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

### 自动获得焦点

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

### 带控件名称

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

### 无障碍使用

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

### 无效状态

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

### 警告状态

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

### 扩展到视口

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

### 选择月份粒度

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

### 自定义一周起始日

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

### 中文语言环境

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

### 带国际化字符串

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

### 会议日期选择

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

### 入职日期

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

### 截止日期

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

### 带 control_id

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
