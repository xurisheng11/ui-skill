# aws_tabs 示例

本文档展示 aws_tabs 组件的各种使用场景。

## 示例列表

### 1. 基础用法

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#default_value": "first",
          "#tabs": [
            { "label": "第一个标签", "id": "first", "content": "第一个标签页的内容区域。" },
            { "label": "第二个标签", "id": "second", "content": "第二个标签页的内容区域。" },
            { "label": "第三个标签", "id": "third", "content": "第三个标签页的内容区域。", "disabled": true }
          ]
        }
      ]
    }
  }
}
```

### 2. 带表单内容

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#default_value": "form",
          "#tabs": [
            {
              "label": "基本信息",
              "id": "basic",
              "content": {
                "formfield": {
                  "#type": "aws_form_field",
                  "#label": "姓名",
                  "#control": { "name": { "#type": "aws_input" } }
                }
              }
            },
            {
              "label": "联系方式",
              "id": "contact",
              "content": {
                "formfield": {
                  "#type": "aws_form_field",
                  "#label": "邮箱",
                  "#control": { "email": { "#type": "aws_input" } }
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

### 3. 容器变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#variant": "container",
          "#default_value": "tab1",
          "#tabs": [
            { "label": "面板1", "id": "tab1", "content": "面板1的内容" },
            { "label": "面板2", "id": "tab2", "content": "面板2的内容" }
          ]
        }
      ]
    }
  }
}
```

### 4. 堆叠变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#variant": "stacked",
          "#tabs": [
            { "label": "设置1", "id": "settings1", "content": "设置1的内容" },
            { "label": "设置2", "id": "settings2", "content": "设置2的内容" }
          ]
        }
      ]
    }
  }
}
```

### 5. 带操作按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            {
              "label": "数据",
              "id": "data",
              "content": "数据内容",
              "action": { "#type": "aws_button", "#text": "刷新" }
            },
            {
              "label": "配置",
              "id": "config",
              "content": "配置内容",
              "action": { "#type": "aws_button", "#text": "保存" }
            }
          ]
        }
      ]
    }
  }
}
```

### 6. 可关闭标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            { "label": "文件1", "id": "file1", "content": "文件1内容", "dismissible": true, "dismiss_label": "关闭" },
            { "label": "文件2", "id": "file2", "content": "文件2内容", "dismissible": true, "dismiss_label": "关闭" },
            { "label": "固定面板", "id": "fixed", "content": "此面板不能关闭" }
          ]
        }
      ]
    }
  }
}
```

### 7. 禁用标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            { "label": "可用", "id": "available", "content": "可用内容" },
            { "label": "禁用", "id": "disabled", "content": "禁用内容", "disabled": true, "disabled_reason": "维护中" },
            { "label": "另一个", "id": "another", "content": "另一个可用内容" }
          ]
        }
      ]
    }
  }
}
```

### 8. 多内容面板

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#default_value": "overview",
          "#tabs": [
            { "label": "概览", "id": "overview", "content": "概览内容" },
            { "label": "用户", "id": "users", "content": "用户列表..." },
            { "label": "订单", "id": "orders", "content": "订单列表..." },
            { "label": "设置", "id": "settings", "content": "系统设置..." }
          ]
        }
      ]
    }
  }
}
```

### 9. 无内容填充

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#disable_content_paddings": true,
          "#tabs": [
            { "label": "标签1", "id": "tab1", "content": "无边距的内容" },
            { "label": "标签2", "id": "tab2", "content": "无边距的内容2" }
          ]
        }
      ]
    }
  }
}
```

### 10. 适应高度

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#fit_height": true,
          "#tabs": [
            { "label": "面板1", "id": "panel1", "content": "适应高度的面板内容" },
            { "label": "面板2", "id": "panel2", "content": "另一个适应高度的面板" }
          ]
        }
      ]
    }
  }
}
```

### 11. 用户管理

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            { "label": "基本信息", "id": "basic", "content": "基本信息内容" },
            { "label": "权限", "id": "permissions", "content": "权限设置" },
            { "label": "操作日志", "id": "logs", "content": "操作日志" }
          ]
        }
      ]
    }
  }
}
```

### 12. 产品详情

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            { "label": "基本信息", "id": "info", "content": "产品基本信息" },
            { "label": "规格参数", "id": "specs", "content": "产品规格参数" },
            { "label": "价格", "id": "price", "content": "产品价格信息" },
            { "label": "评价", "id": "reviews", "content": "产品评价" }
          ]
        }
      ]
    }
  }
}
```

### 13. 数据分析

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#variant": "container",
          "#tabs": [
            { "label": "概览", "id": "overview", "content": "数据概览" },
            { "label": "趋势", "id": "trend", "content": "数据趋势分析" },
            { "label": "对比", "id": "compare", "content": "数据对比" }
          ]
        }
      ]
    }
  }
}
```

### 14. 系统设置

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#variant": "stacked",
          "#tabs": [
            { "label": "常规", "id": "general", "content": "常规设置" },
            { "label": "安全", "id": "security", "content": "安全设置" },
            { "label": "通知", "id": "notification", "content": "通知设置" },
            { "label": "高级", "id": "advanced", "content": "高级设置" }
          ]
        }
      ]
    }
  }
}
```

### 15. 文档阅读

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            { "label": "快速开始", "id": "quickstart", "content": "快速开始指南" },
            { "label": "API", "id": "api", "content": "API文档" },
            { "label": "示例", "id": "examples", "content": "代码示例" },
            { "label": "FAQ", "id": "faq", "content": "常见问题" }
          ]
        }
      ]
    }
  }
}
```
