# aws_space_between

间距组件，用于控制子元素之间的间距。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| direction | 字符串 | 否 | 内容布局方向 |
| size | 字符串 | 否 | 子元素之间的间距 |
| align_items | 字符串 | 否 | 子元素对齐方式 |

### direction 可选值

- `vertical` - 垂直方向（默认）
- `horizontal` - 水平方向

### size 可选值

`xxxs`, `xxs`, `xs`, `s`, `m`, `l`, `xl`, `xxl`（为空时无间距）

### align_items 可选值

- `center` - 居中对齐
- `start` - 起始对齐
- `end` - 结束对齐

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| content (默认) | 子元素 | 是 | {variable} |

## 使用示例

### 水平间距

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#size": "m",
          "#content": [
            {
              "#type": "aws_button",
              "#text": "按钮1"
            },
            {
              "#type": "aws_button",
              "#text": "按钮2"
            },
            {
              "#type": "aws_button",
              "#text": "按钮3"
            }
          ]
        }
      ]
    }
  }
}
```

### 垂直间距

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "vertical",
          "#size": "m",
          "#content": [
            {
              "#type": "aws_button",
              "#text": "按钮1"
            },
            {
              "#type": "aws_button",
              "#text": "按钮2"
            },
            {
              "#type": "aws_button",
              "#text": "按钮3"
            }
          ]
        }
      ]
    }
  }
}
```

### 不同间距大小

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#size": "xs",
          "#content": [
            {
              "#type": "aws_icon",
              "#name": "star-filled"
            },
            {
              "#type": "aws_icon",
              "#name": "star-filled"
            },
            {
              "#type": "aws_icon",
              "#name": "star-filled"
            },
            {
              "#type": "aws_icon",
              "#name": "star-filled"
            },
            {
              "#type": "aws_icon",
              "#name": "star"
            }
          ]
        }
      ]
    }
  }
}
```

### 居中对齐

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#size": "m",
          "#align_items": "center",
          "#content": [
            {
              "#type": "aws_icon",
              "#name": "settings"
            },
            {
              "#type": "aws_button",
              "#text": "设置"
            }
          ]
        }
      ]
    }
  }
}
```

### 大间距

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#size": "xl",
          "#content": [
            {
              "#type": "aws_link",
              "#href": "#",
              "#content": "首页"
            },
            {
              "#type": "aws_link",
              "#href": "#",
              "#content": "产品"
            },
            {
              "#type": "aws_link",
              "#href": "#",
              "#content": "关于"
            },
            {
              "#type": "aws_link",
              "#href": "#",
              "#content": "联系"
            }
          ]
        }
      ]
    }
  }
}
```

### 卡片间距

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#size": "l",
          "#content": [
            {
              "#type": "aws_text_content",
              "#content": {
                "#markup": "<div>卡片1</div>"
              }
            },
            {
              "#type": "aws_text_content",
              "#content": {
                "#markup": "<div>卡片2</div>"
              }
            },
            {
              "#type": "aws_text_content",
              "#content": {
                "#markup": "<div>卡片3</div>"
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 无间距

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#content": [
            {
              "#type": "aws_icon",
              "#name": "check"
            },
            {
              "#type": "aws_icon",
              "#name": "check"
            },
            {
              "#type": "aws_icon",
              "#name": "check"
            }
          ]
        }
      ]
    }
  }
}
```

### 小间距图标

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#size": "xxs",
          "#content": [
            {
              "#type": "aws_icon",
              "#name": "file"
            },
            {
              "#type": "aws_icon",
              "#name": "file"
            },
            {
              "#type": "aws_icon",
              "#name": "file"
            },
            {
              "#type": "aws_icon",
              "#name": "file"
            },
            {
              "#type": "aws_icon",
              "#name": "file"
            }
          ]
        }
      ]
    }
  }
}
```

### 起始对齐

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#size": "s",
          "#align_items": "start",
          "#content": [
            {
              "#type": "aws_icon",
              "#name": "folder"
            },
            {
              "#type": "aws_text_content",
              "#content": {
                "#markup": "<span>文件夹名称</span>"
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 结束对齐

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#size": "m",
          "#align_items": "end",
          "#content": [
            {
              "#type": "aws_text_content",
              "#content": {
                "#markup": "<span>操作</span>"
              }
            },
            {
              "#type": "aws_space_between",
              "#direction": "horizontal",
              "#size": "xs",
              "#content": [
                {
                  "#type": "aws_icon",
                  "#name": "edit"
                },
                {
                  "#type": "aws_icon",
                  "#name": "close"
                }
              ]
            }
          ]
        }
      ]
    }
  }
}
```
