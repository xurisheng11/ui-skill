# aws_button 示例

本文档展示 aws_button 组件的各种使用场景。

## 示例列表

### 1. 基础用法 - 四种变体

展示 primary、normal、link 三种基本变体按钮。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "主要按钮",
          "#variant": "primary"
        },
        {
          "#type": "aws_button",
          "#text": "普通按钮",
          "#variant": "normal"
        },
        {
          "#type": "aws_button",
          "#text": "链接按钮",
          "#variant": "link"
        }
      ]
    }
  }
}
```

### 2. 带图标按钮

展示不同位置和类型的图标按钮。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "保存",
          "#icon_name": "check"
        },
        {
          "#type": "aws_button",
          "#text": "取消",
          "#icon_name": "close"
        },
        {
          "#type": "aws_button",
          "#text": "下一步",
          "#icon_name": "arrow-right",
          "#icon_align": "right"
        }
      ]
    }
  }
}
```

### 3. 工具栏按钮组

模拟常见的工具栏按钮场景。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#variant": "icon",
          "#icon_name": "undo",
          "#aria_label": "撤销"
        },
        {
          "#type": "aws_button",
          "#variant": "icon",
          "#icon_name": "redo",
          "#aria_label": "重做"
        },
        {
          "#type": "aws_button",
          "#variant": "icon",
          "#icon_name": "copy",
          "#aria_label": "复制"
        },
        {
          "#type": "aws_button",
          "#variant": "icon",
          "#icon_name": "cut",
          "#aria_label": "剪切"
        }
      ]
    }
  }
}
```

### 4. 表单操作按钮

表单底部常见的操作按钮组合。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "取消",
          "#variant": "normal"
        },
        {
          "#type": "aws_button",
          "#text": "保存草稿",
          "#variant": "normal",
          "#icon_name": "file"
        },
        {
          "#type": "aws_button",
          "#text": "提交",
          "#variant": "primary",
          "#icon_name": "send"
        }
      ]
    }
  }
}
```

### 5. 禁用状态

展示禁用按钮的不同场景。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "提交",
          "#variant": "primary",
          "#disabled": true
        },
        {
          "#type": "aws_button",
          "#text": "提交（原因提示）",
          "#variant": "primary",
          "#disabled": true,
          "#disabled_reason": "请先完成所有必填项"
        }
      ]
    }
  }
}
```

### 6. 加载状态

展示加载中的按钮状态。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "正在加载",
          "#loading": true,
          "#loading_text": "数据加载中，请稍候..."
        }
      ]
    }
  }
}
```

### 7. 卡片操作按钮

卡片组件中常见的操作按钮组合。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "查看详情",
          "#icon_name": "file-open"
        },
        {
          "#type": "aws_button",
          "#text": "编辑",
          "#icon_name": "edit"
        },
        {
          "#type": "aws_button",
          "#text": "删除",
          "#icon_name": "delete-marker"
        }
      ]
    }
  }
}
```

### 8. 导航操作

页面顶部的导航操作按钮。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "新增",
          "#variant": "primary",
          "#icon_name": "add-plus"
        },
        {
          "#type": "aws_button",
          "#variant": "icon",
          "#icon_name": "refresh",
          "#aria_label": "刷新"
        },
        {
          "#type": "aws_button",
          "#variant": "icon",
          "#icon_name": "settings",
          "#aria_label": "设置"
        }
      ]
    }
  }
}
```

### 9. 链接样式按钮

用于外部链接或辅助导航。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "查看帮助文档",
          "#href": "#help",
          "#variant": "link",
          "#icon_name": "external"
        },
        {
          "#type": "aws_button",
          "#text": "了解更多",
          "#href": "#more",
          "#variant": "link",
          "#icon_name": "arrow-right",
          "#icon_align": "right"
        }
      ]
    }
  }
}
```

### 10. 下载按钮

文件下载场景的按钮。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "下载报告",
          "#icon_name": "download",
          "#href": "#download/report",
          "#download": "annual-report-2024.pdf"
        },
        {
          "#type": "aws_button",
          "#text": "导出 Excel",
          "#icon_name": "upload-download"
        }
      ]
    }
  }
}
```

### 11. 状态指示按钮

带有状态图标的按钮。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "成功状态",
          "#icon_name": "status-positive"
        },
        {
          "#type": "aws_button",
          "#text": "进行中",
          "#icon_name": "status-in-progress"
        },
        {
          "#type": "aws_button",
          "#text": "警告状态",
          "#icon_name": "status-warning"
        },
        {
          "#type": "aws_button",
          "#text": "错误状态",
          "#icon_name": "status-negative"
        }
      ]
    }
  }
}
```

### 12. 全宽按钮

移动端或卡片底部的全宽按钮。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#text": "立即购买",
          "#variant": "primary",
          "#full_width": true,
          "#icon_name": "shopping-cart"
        }
      ]
    }
  }
}
```
