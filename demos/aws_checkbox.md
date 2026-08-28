# aws_checkbox 示例

本文档展示 aws_checkbox 组件的各种使用场景。

## 示例列表

### 1. 基础用法

最基本的复选框示例。

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

### 2. 默认选中

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

### 3. 带描述信息

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

### 4. 禁用状态

两个禁用的复选框示例，一个未选中，一个选中。

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

### 5. 只读状态

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

### 6. 不确定状态（半选）

用于实现"全选"功能时，部分选中状态。

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

### 7. 多选场景

通知偏好设置的多选示例。

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

### 8. 协议同意

注册表单中的协议同意复选框。

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

### 9. 表单设置项

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

### 10. 带名称属性

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

### 11. 无障碍使用

使用 aria-label 提供无障碍标签。

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

### 12. 完整配置示例

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
          "#description": "描述描述描述描述描述描述描述描述"
        }
      }
    }
  }
}
```

### 13. 功能开关

应用设置中的功能开关示例。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "checkbox_dark_mode": {
          "#type": "aws_checkbox",
          "#default_value": false,
          "#label": "深色模式"
        },
        "checkbox_compact": {
          "#type": "aws_checkbox",
          "#default_value": true,
          "#label": "紧凑布局"
        },
        "checkbox_animations": {
          "#type": "aws_checkbox",
          "#default_value": true,
          "#label": "启用动画"
        }
      }
    }
  }
}
```
