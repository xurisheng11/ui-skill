# aws_date_range_picker

AWS 日期范围选择器组件，用户可以输入或选择日期范围。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| default_value | 对象 | 是 | 当前日期范围值（绝对或相对） | - | - |
| range_selector_mode | 字符串 | 否 | 范围选择器模式 | 'default' / 'absolute-only' / 'relative-only' | 'default' |
| date_only | 布尔值 | 否 | 仅日期模式，隐藏时间输入 | - | false |
| placeholder | 字符串 | 否 | 占位符文本 | - | - |
| control_id | 字符串 | 否 | 原生表单元素的 ID | - | - |
| disabled | 布尔值 | 否 | 禁用控件 | - | false |
| read_only | 布尔值 | 否 | 只读控件 | - | false |
| invalid | 布尔值 | 否 | 覆盖无效状态 | - | false |
| warning | 布尔值 | 否 | 覆盖警告状态 | - | false |
| expand_to_viewport | 布尔值 | 否 | 下拉列表扩展到视口外 | - | false |
| locale | 字符串 | 否 | 语言环境 | - | '' |
| start_of_week | 数字 | 否 | 一周起始日（0-6 对应周日到周六） | - | - |
| show_clear_button | 布尔值 | 否 | 显示清除按钮 | - | true |

### 时间相关属性

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| time_input_format | 字符串 | 时间输入格式 |
| hide_time_offset | 布尔值 | 隐藏时间偏移量 |
| get_time_offset | 函数 | 定义时区偏移量 |

### 绝对时间格式

| 属性名 | 类型 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- |
| absolute_format | 字符串 | 绝对时间范围格式 | 'iso' / 'long-localized' | 'iso' |

### 日期控制属性

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| is_date_enabled | 函数 | 定义特定日期是否启用 |
| date_disabled_reason | 函数 | 提供禁用日期的原因 |
| is_valid_range | 函数 | 定义范围是否有效 |

### 相对时间选项

| 属性名 | 类型 | 描述 | 必填 |
| --- | --- | --- | --- |
| relative_options | 数组 | 相对时间范围选项 | 是 |

### 自定义控件

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| custom_absolute_range_control | 函数 | 自定义绝对范围控件 |
| custom_relative_range_units | 数组 | 自定义相对范围时间单位 |

### 国际化属性

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| i18n_strings | 对象 | 本地化字符串对象 |

### i18n_strings 对象结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| absoluteModeTitle | 字符串 | 绝对模式标题 |
| applyButtonLabel | 字符串 | 应用按钮文本 |
| cancelButtonLabel | 字符串 | 取消按钮文本 |
| clearButtonLabel | 字符串 | 清除按钮文本 |
| startDateLabel | 字符串 | 开始日期标签 |
| endDateLabel | 字符串 | 结束日期标签 |
| startTimeLabel | 字符串 | 开始时间标签 |
| endTimeLabel | 字符串 | 结束时间标签 |
| relativeModeTitle | 字符串 | 相对模式标题 |
| modeSelectionLabel | 字符串 | 模式选择标签 |

### 无障碍属性

| 属性名 | 类型 | 描述 |
| --- | --- | --- |
| aria_labelledby | 字符串 | 向组件添加 aria-labelledby |
| aria_describedby | 字符串 | 向组件添加 aria-describedby |

## default_value 结构

```json
{
  "type": "absolute",
  "startDate": "2018-01-09T12:34:56",
  "endDate": "2018-01-19T15:30:00"
}
```

或

```json
{
  "type": "relative",
  "amount": 7,
  "unit": "day"
}
```

## 使用示例

### 基础用法（绝对范围）

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

### 仅日期模式

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

### 警告状态

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

### 扩展到视口

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

### 相对时间范围

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

### 组合模式（绝对+相对）

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
          "#type": "aws_date_range_picker",
          "#placeholder": "选择日期范围",
          "#range_selector_mode": "absolute-only"
        }
      ]
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

### 本周日期范围

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

### 本月日期范围

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

### 本季度日期范围

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

### 本年日期范围

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

### 带时区偏移

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
          "#get_time_offset": {
            "type": "function",
            "description": "(date: Date) => number"
          },
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

### 隐藏时间偏移

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

### 时间输入格式（小时）

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

### 时间输入格式（时分）

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
          "#time_input_format": "hh:mm",
          "#range_selector_mode": "absolute-only",
          "#default_value": {
            "type": "absolute",
            "startDate": "2024-01-01T12:30:00",
            "endDate": "2024-01-31T18:45:00"
          }
        }
      ]
    }
  }
}
```

### 隐藏清除按钮

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

### 带中文语言环境

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

### 带国际化字符串

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
            "endDateLabel": "结束日期",
            "relativeModeTitle": "选择相对时间"
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
