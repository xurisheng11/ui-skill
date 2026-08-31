# aws_modal

模态框组件，用于弹窗对话框。

**注意**：弹窗内的输入元素内容不会被提交，如需提交请另外保存。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| size | 字符串 | 否 | 模态框宽度 |
| default_value | 布尔值 | 否 | 是否显示模态框 |

### size 可选值

- `small` - 小尺寸
- `medium` - 中尺寸（默认）
- `large` - 大尺寸
- `max` - 最大宽度

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| header | 模态框标题 | 是 | variable |
| content (默认) | 模态框主体内容 | 是 | {variable} |
| footer | 模态框页脚 | 是 | variable |

### 事件

| 事件名 | 参数 | 描述 |
| --- | --- | --- |
| on_dismiss | - | 关闭模态框时触发（关闭按钮/点击外部/ESC键） |

### 变量和方法

| 名称 | 描述 |
| --- | --- |
| value_{modal_key} | 弹窗状态 (true/false) |
| setValue_{modal_key}() | 设置弹窗状态 |

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

### 带页脚按钮

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
          "#on_click": "setValue_confirm_modal(true)"
        },
        "confirm_modal": {
          "#type": "aws_modal",
          "#header": "确认操作",
          "#content": "确定要执行此操作吗？此操作无法撤销。",
          "#footer": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "cancel": {
                "#type": "aws_button",
                "#text": "取消",
                "#variant": "normal",
                "#on_click": "setValue_confirm_modal(false)"
              },
              "confirm": {
                "#type": "aws_button",
                "#text": "确定",
                "#on_click": "setValue_confirm_modal(false)"
              }
            }
          }
        }
      }
    }
  }
}
```

### 小尺寸弹窗

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
          "#text": "小弹窗",
          "#on_click": "setValue_small_modal(true)"
        },
        "small_modal": {
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

### 大尺寸弹窗

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
          "#text": "大弹窗",
          "#on_click": "setValue_large_modal(true)"
        },
        "large_modal": {
          "#type": "aws_modal",
          "#size": "large",
          "#header": "详细设置",
          "#content": "这里是详细设置的内容区域..."
        }
      }
    }
  }
}
```

### 最大尺寸弹窗

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
          "#text": "最大弹窗",
          "#on_click": "setValue_max_modal(true)"
        },
        "max_modal": {
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

### 无内边距

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
          "#text": "无内边距弹窗",
          "#on_click": "setValue_nopadding_modal(true)"
        },
        "nopadding_modal": {
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

### 表单弹窗

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
          "#text": "新建项目",
          "#on_click": "setValue_form_modal(true)"
        },
        "form_modal": {
          "#type": "aws_modal",
          "#header": "新建项目",
          "#content": {
            "form": {
              "#type": "aws_form_field",
              "#label": "项目名称",
              "#control": {
                "name": {
                  "#type": "aws_input"
                }
              }
            }
          },
          "#footer": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "cancel": {
                "#type": "aws_button",
                "#text": "取消"
              },
              "submit": {
                "#type": "aws_button",
                "#text": "创建"
              }
            }
          }
        }
      }
    }
  }
}
```

### 删除确认弹窗

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
          "#text": "删除",
          "#variant": "primary",
          "#on_click": "setValue_delete_modal(true)"
        },
        "delete_modal": {
          "#type": "aws_modal",
          "#header": "确认删除",
          "#content": {
            "#markup": "<p>确定要删除此项目吗？</p><p>此操作不可撤销。</p>"
          },
          "#footer": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "cancel": {
                "#type": "aws_button",
                "#text": "取消",
                "#variant": "normal"
              },
              "delete": {
                "#type": "aws_button",
                "#text": "删除",
                "#variant": "primary"
              }
            }
          }
        }
      }
    }
  }
}
```

### 成功提示弹窗

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
          "#text": "显示成功",
          "#on_click": "setValue_success_modal(true)"
        },
        "success_modal": {
          "#type": "aws_modal",
          "#header": "操作成功",
          "#content": {
            "#type": "aws_space_between",
            "#direction": "vertical",
            "#size": "m",
            "#content": {
              "icon": {
                "#type": "aws_icon",
                "#name": "status-positive",
                "#size": "large"
              },
              "text": "您的请求已成功处理！"
            }
          }
        }
      }
    }
  }
}
```
