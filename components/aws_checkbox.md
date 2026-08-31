# aws_checkbox

AWS 复选框组件，用于在表单中选择一个或多个选项。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| default_value | 布尔值 | 是 | 指定组件是否被选中 | - | false |
| label | 字符串 | 否 | 为组件提供标签文本 | - | - |
| description | 字符串 | 否 | 为组件提供描述信息 | - | - |
| disabled | 布尔值 | 否 | 指定控件是否禁用 | - | false |
| read_only | 布尔值 | 否 | 指定控件是否只读 | - | false |
| indeterminate | 布尔值 | 否 | 指定组件处于不确定状态（半选状态） | - | false |
| name | 字符串 | 否 | 指定在 HTML 表单中使用的控件名称 | - | - |
| control_id | 字符串 | 否 | 指定原生表单元素的 ID | - | - |

### 无障碍属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| aria_label | 字符串 | 否 | 向原生控件添加 aria-label（如果没有可见标签则使用） | - | - |
| aria_labelledby | 字符串 | 否 | 向组件添加 aria-labelledby（指定标签元素的 ID） | - | - |
| aria_describedby | 字符串 | 否 | 向组件添加 aria-describedby（指定描述元素的 ID） | - | - |
| aria_controls | 字符串 | 否 | 向组件添加 aria-controls（控制次要内容的 ID） | - | - |
| aria_required | 布尔值 | 否 | 指定是否向原生控件添加 aria-required | - | false |

## 重要说明

**提交值格式**：
- 选中时提交值为字符串 `'1'`
- 未选中时提交值为字符串 `'0'`

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
        "checkbox": {
          "#type": "aws_checkbox",
          "#default_value": false,
          "#label": "同意服务条款"
        }
      }
    }
  }
}
```

### 默认选中

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox": {
          "#type": "aws_checkbox",
          "#default_value": true,
          "#label": "默认选中的复选框"
        }
      }
    }
  }
}
```

### 带描述信息

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox": {
          "#type": "aws_checkbox",
          "#label": "订阅更新",
          "#description": "勾选后您将收到最新的产品更新和优惠信息"
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
        "checkbox_disabled": {
          "#type": "aws_checkbox",
          "#default_value": false,
          "#label": "已禁用的复选框",
          "#disabled": true
        },
        "checkbox_disabled_checked": {
          "#type": "aws_checkbox",
          "#default_value": true,
          "#label": "禁用但选中的复选框",
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
        "checkbox": {
          "#type": "aws_checkbox",
          "#default_value": true,
          "#label": "只读复选框",
          "#read_only": true
        }
      }
    }
  }
}
```

### 不确定状态（半选）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox": {
          "#type": "aws_checkbox",
          "#label": "全选（部分选中）",
          "#indeterminate": true
        }
      }
    }
  }
}
```

### 带名称属性

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox": {
          "#type": "aws_checkbox",
          "#default_value": false,
          "#name": "subscribe_newsletter",
          "#label": "订阅新闻通讯"
        }
      }
    }
  }
}
```

### 带自定义控件 ID

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox": {
          "#type": "aws_checkbox",
          "#control_id": "custom-checkbox-id",
          "#default_value": false,
          "#label": "带自定义 ID 的复选框"
        }
      }
    }
  }
}
```

### 多选场景

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox_email": {
          "#type": "aws_checkbox",
          "#default_value": true,
          "#label": "邮件通知"
        },
        "checkbox_sms": {
          "#type": "aws_checkbox",
          "#default_value": false,
          "#label": "短信通知"
        },
        "checkbox_push": {
          "#type": "aws_checkbox",
          "#default_value": true,
          "#label": "推送通知"
        }
      }
    }
  }
}
```

### 协议同意

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox": {
          "#type": "aws_checkbox",
          "#default_value": false,
          "#label": "我已阅读并同意",
          "#description": "《用户协议》和《隐私政策》"
        }
      }
    }
  }
}
```

### 表单设置项

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox_auto_save": {
          "#type": "aws_checkbox",
          "#default_value": true,
          "#label": "自动保存"
        },
        "checkbox_public": {
          "#type": "aws_checkbox",
          "#default_value": false,
          "#label": "公开项目"
        },
        "checkbox_highlight": {
          "#type": "aws_checkbox",
          "#default_value": false,
          "#label": "高亮显示"
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
        "checkbox": {
          "#type": "aws_checkbox",
          "#aria_label": "启用深色模式",
          "#default_value": false
        }
      }
    }
  }
}
```

### 完整配置示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox": {
          "#type": "aws_checkbox",
          "#label": "请输入",
          "#description": "描述描述描述描述描述描述描述描述",
          "#default_value": false,
          "#name": "input_field",
          "#control_id": "input-checkbox"
        }
      }
    }
  }
}
```
