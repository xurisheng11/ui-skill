# aws_status_indicator

状态指示器组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| status_type | 字符串 | 否 | 状态类型 |
| wrap_text | 布尔值 | 否 | 文本是否换行 |
| color_override | 字符串 | 否 | 颜色覆盖 |
| icon_aria_label | 字符串 | 否 | 图标aria-label |

### status_type 可选值

- `success` - 成功状态
- `error` - 错误状态
- `warning` - 警告状态
- `info` - 信息状态
- `stopped` - 停止状态
- `pending` - 待处理状态
- `in-progress` - 进行中状态
- `loading` - 加载状态

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| content | 内容 | 是 | {variable} |

## 使用示例

### 基础用法

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "success",
          "#content": "成功"
        },
        {
          "#type": "aws_status_indicator",
          "#status_type": "error",
          "#content": "失败"
        }
      ]
    }
  }
}
```

### 全部状态

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
              "#type": "aws_status_indicator",
              "#status_type": "success",
              "#content": "成功"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "error",
              "#content": "错误"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "warning",
              "#content": "警告"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "info",
              "#content": "信息"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "stopped",
              "#content": "已停止"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "pending",
              "#content": "待处理"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "in-progress",
              "#content": "进行中"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "loading",
              "#content": "加载中"
            }
          ]
        }
      ]
    }
  }
}
```

### 带图标标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "success",
          "#icon_aria_label": "成功状态",
          "#content": "部署成功"
        }
      ]
    }
  }
}
```

### 不换行

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "info",
          "#wrap_text": false,
          "#content": "这是一个很长的状态文本如果超出容器宽度将会被截断"
        }
      ]
    }
  }
}
```

### 换行（默认）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "info",
          "#wrap_text": true,
          "#content": "这是一个很长的状态文本\n它会在容器宽度不够时自动换行显示"
        }
      ]
    }
  }
}
```

### 颜色覆盖

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "success",
          "#color_override": "blue",
          "#content": "蓝色成功"
        }
      ]
    }
  }
}
```

### 表格中使用

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
          "#size": "s",
          "#content": [
            {
              "#type": "aws_status_indicator",
              "#status_type": "success",
              "#content": "运行中"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "warning",
              "#content": "存储空间不足"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "error",
              "#content": "连接失败"
            }
          ]
        }
      ]
    }
  }
}
```

### 状态列表

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
              "#type": "aws_space_between",
              "#direction": "horizontal",
              "#size": "m",
              "#content": {
                "status": {
                  "#type": "aws_status_indicator",
                  "#status_type": "success",
                  "#content": "服务A"
                },
                "desc": {
                  "#type": "aws_text_content",
                  "#content": {
                    "#markup": "<span>正常运行</span>"
                  }
                }
              }
            },
            {
              "#type": "aws_space_between",
              "#direction": "horizontal",
              "#size": "m",
              "#content": {
                "status": {
                  "#type": "aws_status_indicator",
                  "#status_type": "warning",
                  "#content": "服务B"
                },
                "desc": {
                  "#type": "aws_text_content",
                  "#content": {
                    "#markup": "<span>部分降级</span>"
                  }
                }
              }
            },
            {
              "#type": "aws_space_between",
              "#direction": "horizontal",
              "#size": "m",
              "#content": {
                "status": {
                  "#type": "aws_status_indicator",
                  "#status_type": "error",
                  "#content": "服务C"
                },
                "desc": {
                  "#type": "aws_text_content",
                  "#content": {
                    "#markup": "<span>服务不可用</span>"
                  }
                }
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 卡片状态

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
              "#type": "aws_status_indicator",
              "#status_type": "success",
              "#content": "在线"
            },
            {
              "#type": "aws_status_indicator",
              "#status_type": "stopped",
              "#content": "离线"
            }
          ]
        }
      ]
    }
  }
}
```
