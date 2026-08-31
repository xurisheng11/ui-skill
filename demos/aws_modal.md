# aws_modal 示例

本文档展示 aws_modal 组件的各种使用场景。

## 示例列表

### 1. 基础用法

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": {
          "#type": "aws_button",
          "#text": "打开弹窗",
          "#on_click": "setValue_modal(true)"
        },
        "modal": {
          "#type": "aws_modal",
          "#header": "提示",
          "#content": "这是一个模态框"
        }
      }
    }
  }
}
```

### 2. 确认弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": {
          "#type": "aws_button",
          "#text": "确认操作",
          "#on_click": "setValue_confirm(true)"
        },
        "confirm": {
          "#type": "aws_modal",
          "#header": "确认操作",
          "#content": "确定要执行此操作吗？",
          "#footer": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "cancel": { "#type": "aws_button", "#text": "取消" },
              "confirm": { "#type": "aws_button", "#text": "确定" }
            }
          }
        }
      }
    }
  }
}
```

### 3. 删除确认

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "删除", "#variant": "primary" },
        "modal": {
          "#type": "aws_modal",
          "#header": "确认删除",
          "#content": "确定要删除此项目吗？",
          "#footer": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "cancel": { "#type": "aws_button", "#text": "取消", "#variant": "normal" },
              "delete": { "#type": "aws_button", "#text": "删除", "#variant": "primary" }
            }
          }
        }
      }
    }
  }
}
```

### 4. 小尺寸弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "小弹窗" },
        "modal": {
          "#type": "aws_modal",
          "#size": "small",
          "#header": "提示",
          "#content": "操作成功！"
        }
      }
    }
  }
}
```

### 5. 大尺寸弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "大弹窗" },
        "modal": {
          "#type": "aws_modal",
          "#size": "large",
          "#header": "详细设置",
          "#content": "详细设置的内容区域..."
        }
      }
    }
  }
}
```

### 6. 最大尺寸弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "最大弹窗" },
        "modal": {
          "#type": "aws_modal",
          "#size": "max",
          "#header": "全屏内容",
          "#content": "这是最大尺寸的弹窗内容..."
        }
      }
    }
  }
}
```

### 7. 表单弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "新建项目" },
        "modal": {
          "#type": "aws_modal",
          "#header": "新建项目",
          "#content": {
            "form": {
              "#type": "aws_form_field",
              "#label": "项目名称",
              "#control": { "name": { "#type": "aws_input" } }
            }
          },
          "#footer": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "cancel": { "#type": "aws_button", "#text": "取消" },
              "submit": { "#type": "aws_button", "#text": "创建" }
            }
          }
        }
      }
    }
  }
}
```

### 8. 成功提示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "显示成功" },
        "modal": {
          "#type": "aws_modal",
          "#header": "操作成功",
          "#content": {
            "#type": "aws_space_between",
            "#direction": "vertical",
            "#size": "m",
            "#content": {
              "icon": { "#type": "aws_icon", "#name": "status-positive", "#size": "large" },
              "text": "您的请求已成功处理！"
            }
          }
        }
      }
    }
  }
}
```

### 9. 无内边距

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "自定义内容" },
        "modal": {
          "#type": "aws_modal",
          "#disable_content_paddings": true,
          "#header": "自定义内容",
          "#content": "内容区域没有默认内边距..."
        }
      }
    }
  }
}
```

### 10. 中尺寸（默认）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "中等弹窗" },
        "modal": {
          "#type": "aws_modal",
          "#size": "medium",
          "#header": "中等尺寸",
          "#content": "这是中等尺寸的弹窗内容。"
        }
      }
    }
  }
}
```

### 11. 警告弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "显示警告" },
        "modal": {
          "#type": "aws_modal",
          "#header": "警告",
          "#content": {
            "#type": "aws_space_between",
            "#direction": "vertical",
            "#size": "m",
            "#content": {
              "icon": { "#type": "aws_icon", "#name": "status-warning", "#size": "large" },
              "text": "此操作可能导致数据丢失，请谨慎操作。"
            }
          }
        }
      }
    }
  }
}
```

### 12. 错误弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "显示错误" },
        "modal": {
          "#type": "aws_modal",
          "#header": "操作失败",
          "#content": {
            "#type": "aws_space_between",
            "#direction": "vertical",
            "#size": "m",
            "#content": {
              "icon": { "#type": "aws_icon", "#name": "status-negative", "#size": "large" },
              "text": "发生了错误，请重试。"
            }
          }
        }
      }
    }
  }
}
```

### 13. 登录弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "登录" },
        "modal": {
          "#type": "aws_modal",
          "#header": "用户登录",
          "#content": {
            "#type": "aws_space_between",
            "#direction": "vertical",
            "#size": "m",
            "#content": {
              "user": { "#type": "aws_form_field", "#label": "用户名", "#control": { "u": { "#type": "aws_input" } } },
              "pass": { "#type": "aws_form_field", "#label": "密码", "#control": { "p": { "#type": "aws_input", "#input_type": "password" } } }
            }
          },
          "#footer": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "cancel": { "#type": "aws_button", "#text": "取消" },
              "login": { "#type": "aws_button", "#text": "登录", "#variant": "primary" }
            }
          }
        }
      }
    }
  }
}
```

### 14. 设置弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "系统设置" },
        "modal": {
          "#type": "aws_modal",
          "#header": "系统设置",
          "#content": "在此可以配置各种系统参数..."
        }
      }
    }
  }
}
```

### 15. 信息弹窗

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "button": { "#type": "aws_button", "#text": "查看详情" },
        "modal": {
          "#type": "aws_modal",
          "#header": "详细信息",
          "#content": {
            "#type": "aws_key_value_pairs",
            "#items": [
              { "label": "名称", "value": "示例项目" },
              { "label": "ID", "value": "PRJ-12345" },
              { "label": "状态", "value": "进行中" }
            ]
          }
        }
      }
    }
  }
}
```
