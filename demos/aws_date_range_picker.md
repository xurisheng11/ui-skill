# aws_date_range_picker 示例

本文档展示 aws_date_range_picker 组件的各种使用场景。

## 示例列表

### 1. 基础用法（绝对范围）

最基本的日期范围选择器示例。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2018-01-09T12:34:56",
            "endDate": "2018-01-19T15:30:00"
          }
        }
      ]
    }
  }
}
```

### 2. 仅日期模式

隐藏时间输入，只显示日期。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#date_only": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
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
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#disabled": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
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
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#read_only": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 5. 无效状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#invalid": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 6. 警告状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#warning": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 7. 扩展到视口

在可滚动容器内使用时扩展下拉列表。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#expand_to_viewport": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 8. 相对时间范围

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#range_selector_mode": "relative-only",
          "#relative_options": [
            {
              "value": {
                "amount": 7,
                "unit": "day"
              },
              "label": "过去7天"
            },
            {
              "value": {
                "amount": 30,
                "unit": "day"
              },
              "label": "过去30天"
            }
          ],
          "#default_value": {
            "type": "relative",
            "amount": 7,
            "unit": "day"
          }
        }
      ]
    }
  }
}
```

### 9. 组合模式（绝对+相对）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#range_selector_mode": "default",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 10. 带占位符

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#placeholder": "选择日期范围",
          "#range_selector_mode": "absolute-only"
        }
      ]
    }
  }
}
```

### 11. 带 control_id

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#control_id": "custom-date-range-id",
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 12. 本周日期范围

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#date_only": true,
          "#range_selector_mode": "absolute-only",
          "#start_of_week": 1,
          "#default_value": {
            "type": "absolute",
            "startDate": "2026-08-24",
            "endDate": "2026-08-30"
          }
        }
      ]
    }
  }
}
```

### 13. 本月日期范围

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#date_only": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2026-08-01",
            "endDate": "2026-08-28"
          }
        }
      ]
    }
  }
}
```

### 14. 本季度日期范围

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#date_only": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2026-07-01",
            "endDate": "2026-09-30"
          }
        }
      ]
    }
  }
}
```

### 15. 本年日期范围

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#date_only": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2026-01-01",
            "endDate": "2026-12-31"
          }
        }
      ]
    }
  }
}
```

### 16. 带时区偏移

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01T00:00:00+08:00",
            "endDate": "2024-01-31T23:59:59+08:00"
          }
        }
      ]
    }
  }
}
```

### 17. 隐藏时间偏移

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#hide_time_offset": true,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01T00:00:00",
            "endDate": "2024-01-31T23:59:59"
          }
        }
      ]
    }
  }
}
```

### 18. 时间输入格式（小时）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#time_input_format": "hh",
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01T12:00:00",
            "endDate": "2024-01-31T18:00:00"
          }
        }
      ]
    }
  }
}
```

### 19. 隐藏清除按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#show_clear_button": false,
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 20. 带中文语言环境

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#locale": "zh-CN",
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 21. 带国际化字符串

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#i18n_strings": {
            "absoluteModeTitle": "选择日期",
            "applyButtonLabel": "应用",
            "cancelButtonLabel": "取消",
            "clearButtonLabel": "清除",
            "startDateLabel": "开始日期",
            "endDateLabel": "结束日期"
          },
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01",
            "endDate": "2024-01-31"
          }
        }
      ]
    }
  }
}
```

### 22. 相对时间 - 过去24小时

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#range_selector_mode": "relative-only",
          "#relative_options": [
            {
              "value": {
                "amount": 24,
                "unit": "hour"
              },
              "label": "过去24小时"
            }
          ],
          "#default_value": {
            "type": "relative",
            "amount": 24,
            "unit": "hour"
          }
        }
      ]
    }
  }
}
```

### 23. 相对时间 - 过去一年

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#range_selector_mode": "relative-only",
          "#relative_options": [
            {
              "value": {
                "amount": 1,
                "unit": "year"
              },
              "label": "过去一年"
            }
          ],
          "#default_value": {
            "type": "relative",
            "amount": 1,
            "unit": "year"
          }
        }
      ]
    }
  }
}
```

### 24. 报告日期范围

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#control_id": "report-date-range",
          "#date_only": true,
          "#range_selector_mode": "absolute-only",
          "#placeholder": "选择报告日期范围",
          "#default_value": {
            "type": "absolute",
            "startDate": "2026-01-01",
            "endDate": "2026-03-31"
          }
        }
      ]
    }
  }
}
```

### 25. 日志查询日期范围

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_date_range_picker",
          "#control_id": "log-query-range",
          "#range_selector_mode": "relative-only",
          "#relative_options": [
            {
              "value": {
                "amount": 1,
                "unit": "hour"
              },
              "label": "过去1小时"
            },
            {
              "value": {
                "amount": 24,
                "unit": "hour"
              },
              "label": "过去24小时"
            },
            {
              "value": {
                "amount": 7,
                "unit": "day"
              },
              "label": "过去7天"
            },
            {
              "value": {
                "amount": 30,
                "unit": "day"
              },
              "label": "过去30天"
            }
          ],
          "#default_value": {
            "type": "relative",
            "amount": 24,
            "unit": "hour"
          }
        }
      ]
    }
  }
}
```
