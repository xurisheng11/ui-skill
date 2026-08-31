# aws_header 示例

本文档展示 aws_header 组件的各种使用场景。

## 示例列表

### 1. 页面标题 H1

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#variant": "h1",
          "#title": "仪表盘总览"
        }
      ]
    }
  }
}
```

### 2. 带计数器

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#title": "用户管理",
          "#counter": "(128)"
        }
      ]
    }
  }
}
```

### 3. 带操作按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#title": "产品列表",
          "#actions": {
            "#type": "aws_button",
            "#text": "新建产品"
          }
        }
      ]
    }
  }
}
```

### 4. 带描述

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#title": "系统设置",
          "#description": "配置应用程序的各种选项和参数"
        }
      ]
    }
  }
}
```

### 5. 带信息链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#title": "数据报表",
          "#info": "查看使用帮助"
        }
      ]
    }
  }
}
```

### 6. 容器标题 H2

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#variant": "h2",
          "#title": "基本信息"
        }
      ]
    }
  }
}
```

### 7. 部分标题 H3

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#variant": "h3",
          "#title": "联系方式"
        }
      ]
    }
  }
}
```

### 8. 粘性标题

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#variant": "awsui-h1-sticky",
          "#title": "卡片标题",
          "#actions": {
            "#type": "aws_icon",
            "#name": "settings"
          }
        }
      ]
    }
  }
}
```

### 9. 完整页面头部

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#variant": "h1",
          "#title": "项目管理",
          "#description": "管理您的项目、团队成员和资源分配",
          "#counter": "(12个项目)",
          "#info": {
            "#type": "aws_link",
            "#content": "了解更多",
            "#variant": "info"
          },
          "#actions": {
            "#type": "aws_button",
            "#text": "新建项目"
          }
        }
      ]
    }
  }
}
```

### 10. 带多个操作

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#title": "文档管理",
          "#actions": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "btn1": {
                "#type": "aws_button",
                "#text": "导入"
              },
              "btn2": {
                "#type": "aws_button",
                "#text": "导出"
              },
              "btn3": {
                "#type": "aws_button",
                "#text": "新建"
              }
            }
          }
        }
      ]
    }
  }
}
```

### 11. 带标题覆盖

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#heading_tag_override": "h1",
          "#title": "使用H1标签的H2样式"
        }
      ]
    }
  }
}
```

### 12. 简单标题

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#title": "页面标题"
        }
      ]
    }
  }
}
```

### 13. 带图标

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#title": "设置",
          "#actions": {
            "#type": "aws_icon",
            "#name": "settings"
          }
        }
      ]
    }
  }
}
```

### 14. 表单头部

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#variant": "h2",
          "#title": "新建用户",
          "#description": "填写以下信息以创建新用户",
          "#actions": {
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
      ]
    }
  }
}
```

### 15. 统计数据头部

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#variant": "h1",
          "#title": "销售报表",
          "#description": "本月销售数据分析",
          "#counter": "更新时间：2024-01-15"
        }
      ]
    }
  }
}
```
