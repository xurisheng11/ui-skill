# aws_container

AWS 容器组件，用于创建带有标题、内容和页脚的卡片式容器布局。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| variant | 字符串 | 否 | 指定容器变体 | default / stacked | "default" |
| disable_content_paddings | 布尔值 | 否 | 是否移除内容区域的内边距 | - | false |
| disable_header_paddings | 布尔值 | 否 | 是否移除头部的内边距 | - | false |
| fit_height | 布尔值 | 否 | 启用后容器会适应可用高度，使同行容器高度一致 | - | false |

### media 属性

| 属性 | 类型 | 描述 | 可接受值 |
| --- | --- | --- | --- |
| content | 字符串 | 媒体元素内容（img、video、picture、iframe） | - |
| position | 字符串 | 媒体元素位置 | top / bottom / side |
| width | 字符串 | 媒体元素宽度 | CSS 宽度值（如 "33%"） |
| height | 字符串 | 媒体元素高度 | CSS 高度值 |

### variant 可选值说明

| 值 | 描述 |
| --- | --- |
| default | 在独立上下文中使用 |
| stacked | 在相邻的堆叠容器旁使用 |

### 子属性

#### header

容器的标题区域，嵌入 `aws_header` 组件，支持以下属性：
- title：标题文本
- description：描述文本
- info：信息文本
- counter：计数器
- actions：操作按钮区域

#### footer

容器的页脚区域，嵌入其他 AWS 组件。

#### content

容器的内容区域，支持字符串或嵌入其他 AWS 组件。

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
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#title": "容器标题",
            "#description": "这是容器的描述信息"
          },
          "#content": "这是容器的内容区域"
        }
      ]
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
      "#children": [
        {
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#counter": "(3)",
            "#actions": {
              "#type": "aws_button",
              "#text": "Button"
            },
            "#info": "infoooooooo",
            "#description": "description",
            "#title": "title"
          },
          "#footer": {
            "#type": "aws_button",
            "#text": "footer action"
          },
          "#media": {
            "content": "<img src='/core/misc/logo.svg' alt='placeholder' />",
            "position": "side",
            "width": "33%"
          },
          "#content": "content"
        }
      ]
    }
  }
}
```

### 带媒体元素

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#title": "产品展示"
          },
          "#media": {
            "content": "<img src='https://example.com/product.jpg' alt='产品图片' />",
            "position": "top",
            "width": "100%"
          },
          "#content": "这里是产品的详细描述内容"
        }
      ]
    }
  }
}
```

### 媒体元素在侧面

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#title": "图文并排"
          },
          "#media": {
            "content": "<img src='https://example.com/image.jpg' alt='图片' />",
            "position": "side",
            "width": "40%"
          },
          "#content": "这里是内容区域，图片显示在侧面"
        }
      ]
    }
  }
}
```

### 堆叠变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#variant": "stacked",
          "#header": {
            "#type": "aws_header",
            "#title": "卡片1"
          },
          "#content": "堆叠容器1的内容"
        },
        {
          "#type": "aws_container",
          "#variant": "stacked",
          "#header": {
            "#type": "aws_header",
            "#title": "卡片2"
          },
          "#content": "堆叠容器2的内容"
        },
        {
          "#type": "aws_container",
          "#variant": "stacked",
          "#header": {
            "#type": "aws_header",
            "#title": "卡片3"
          },
          "#content": "堆叠容器3的内容"
        }
      ]
    }
  }
}
```

### 移除内边距

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#disable_content_paddings": true,
          "#disable_header_paddings": true,
          "#header": {
            "#type": "aws_header",
            "#title": "无内边距容器"
          },
          "#content": "内容区域没有内边距"
        }
      ]
    }
  }
}
```

### 自适应高度

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#fit_height": true,
          "#header": {
            "#type": "aws_header",
            "#title": "自适应高度容器1"
          },
          "#content": "这个容器会根据内容自动调整高度"
        },
        {
          "#type": "aws_container",
          "#fit_height": true,
          "#header": {
            "#type": "aws_header",
            "#title": "自适应高度容器2"
          },
          "#content": "多个容器会拉伸到相同高度"
        }
      ]
    }
  }
}
```

### 带页脚操作

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#title": "设置面板"
          },
          "#content": "配置您的应用设置选项",
          "#footer": {
            "#type": "aws_button",
            "#text": "保存设置"
          }
        }
      ]
    }
  }
}
```

### 带多个操作按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#title": "用户管理",
            "#counter": "(5)",
            "#actions": {
              "#type": "aws_button",
              "#text": "添加用户"
            }
          },
          "#content": "用户列表内容区域"
        }
      ]
    }
  }
}
```

### 带信息提示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#title": "系统状态",
            "#info": "上次更新：2024-01-01",
            "#description": "显示系统当前运行状态"
          },
          "#content": "系统运行正常"
        }
      ]
    }
  }
}
```

### 内容区域嵌入组件

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#title": "数据统计"
          },
          "#content": {
            "#type": "aws_column_layout",
            "#columns": 3,
            "#content": [
              { "#type": "aws_box", "#variant": "div", "#content": "统计项1" },
              { "#type": "aws_box", "#variant": "div", "#content": "统计项2" },
              { "#type": "aws_box", "#variant": "div", "#content": "统计项3" }
            ]
          }
        }
      ]
    }
  }
}
```

### 视频媒体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_container",
          "#header": {
            "#type": "aws_header",
            "#title": "视频演示"
          },
          "#media": {
            "content": "<video src='https://example.com/video.mp4' controls></video>",
            "position": "top",
            "width": "100%"
          },
          "#content": "视频描述信息"
        }
      ]
    }
  }
}
```

### 多容器并排

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 2,
          "#content": [
            {
              "#type": "aws_container",
              "#header": {
                "#type": "aws_header",
                "#title": "容器A"
              },
              "#content": "左侧容器内容"
            },
            {
              "#type": "aws_container",
              "#header": {
                "#type": "aws_header",
                "#title": "容器B"
              },
              "#content": "右侧容器内容"
            }
          ]
        }
      ]
    }
  }
}
```
