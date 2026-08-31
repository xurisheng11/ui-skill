# aws_container 示例

本文档展示 aws_container 组件的各种使用场景。

## 示例列表

### 1. 基础用法

最简单的容器示例，包含标题和内容。

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
            "#title": "容器标题"
          },
          "#content": "这是容器的内容区域"
        }
      ]
    }
  }
}
```

### 2. 完整配置

展示容器所有配置的示例。

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

### 3. 带媒体元素（顶部）

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
            "#title": "带图片的容器"
          },
          "#media": {
            "content": "<img src='https://via.placeholder.com/600x200' alt='示例图片' />",
            "position": "top",
            "width": "100%"
          },
          "#content": "图片显示在内容上方"
        }
      ]
    }
  }
}
```

### 4. 带媒体元素（侧面）

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
            "content": "<img src='https://via.placeholder.com/200x200' alt='示例图片' />",
            "position": "side",
            "width": "30%"
          },
          "#content": "图片显示在左侧，内容显示在右侧。这种布局适合展示产品信息或功能介绍。"
        }
      ]
    }
  }
}
```

### 5. 堆叠容器

多个容器使用 stacked 变体垂直堆叠。

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
            "#title": "卡片1 - 概况"
          },
          "#content": "这是第一个堆叠容器的内容区域"
        },
        {
          "#type": "aws_container",
          "#variant": "stacked",
          "#header": {
            "#type": "aws_header",
            "#title": "卡片2 - 详情"
          },
          "#content": "这是第二个堆叠容器的内容区域"
        },
        {
          "#type": "aws_container",
          "#variant": "stacked",
          "#header": {
            "#type": "aws_header",
            "#title": "卡片3 - 统计"
          },
          "#content": "这是第三个堆叠容器的内容区域"
        }
      ]
    }
  }
}
```

### 6. 带页脚操作

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
            "#title": "保存设置"
          },
          "#content": "请配置以下选项以完成设置",
          "#footer": {
            "#type": "aws_button",
            "#text": "保存"
          }
        }
      ]
    }
  }
}
```

### 7. 自适应高度

多个容器使用 fit_height 属性保持相同高度。

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
          "#columns": 3,
          "#content": [
            {
              "#type": "aws_container",
              "#fit_height": true,
              "#header": {
                "#type": "aws_header",
                "#title": "指标A"
              },
              "#content": "数据面板A"
            },
            {
              "#type": "aws_container",
              "#fit_height": true,
              "#header": {
                "#type": "aws_header",
                "#title": "指标B"
              },
              "#content": "数据面板B\n\n第二行\n\n第三行\n\n第四行"
            },
            {
              "#type": "aws_container",
              "#fit_height": true,
              "#header": {
                "#type": "aws_header",
                "#title": "指标C"
              },
              "#content": "数据面板C"
            }
          ]
        }
      ]
    }
  }
}
```

### 8. 带多个操作

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
            "#counter": "(10)",
            "#actions": {
              "#type": "aws_button",
              "#text": "添加"
            }
          },
          "#content": "用户列表内容区域，显示所有系统用户"
        }
      ]
    }
  }
}
```

### 9. 带信息提示

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
            "#info": "在线",
            "#description": "最后检查时间：2024-01-15 10:30"
          },
          "#content": "所有系统组件运行正常"
        }
      ]
    }
  }
}
```

### 10. 移除内边距

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
            "#title": "紧凑容器"
          },
          "#content": "<div style='background: #f0f0f0; padding: 20px;'>自定义内边距内容</div>"
        }
      ]
    }
  }
}
```

### 11. 内容区域嵌入组件

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
              { "#type": "aws_box", "#variant": "div", "#content": "总用户：1,234" },
              { "#type": "aws_box", "#variant": "div", "#content": "活跃用户：567" },
              { "#type": "aws_box", "#variant": "div", "#content": "转化率：45.9%" }
            ]
          }
        }
      ]
    }
  }
}
```

### 12. 产品卡片

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
            "#title": "智能手表 Pro",
            "#info": "¥2,999"
          },
          "#media": {
            "content": "<img src='https://via.placeholder.com/300x200' alt='产品图片' />",
            "position": "top",
            "width": "100%"
          },
          "#content": "高性能智能手表，支持心率监测、GPS定位、防水等功能",
          "#footer": {
            "#type": "aws_button",
            "#text": "立即购买"
          }
        }
      ]
    }
  }
}
```

### 13. 仪表盘卡片

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
          "#columns": 4,
          "#content": [
            {
              "#type": "aws_container",
              "#header": {
                "#type": "aws_header",
                "#title": "总访问量"
              },
              "#content": "12,345"
            },
            {
              "#type": "aws_container",
              "#header": {
                "#type": "aws_header",
                "#title": "活跃用户"
              },
              "#content": "1,234"
            },
            {
              "#type": "aws_container",
              "#header": {
                "#type": "aws_header",
                "#title": "总收入"
              },
              "#content": "¥56,789"
            },
            {
              "#type": "aws_container",
              "#header": {
                "#type": "aws_header",
                "#title": "转化率"
              },
              "#content": "5.6%"
            }
          ]
        }
      ]
    }
  }
}
```
