# aws_toggle_button 示例

本文档展示 aws_toggle_button 组件的各种使用场景。

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
          "#type": "aws_toggle_button",
          "#default_value": true,
          "#icon_name": "star",
          "#pressed_icon_name": "star-filled",
          "#text": "收藏"
        }
      ]
    }
  }
}
```

### 2. 默认未选中

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#default_value": false,
          "#icon_name": "star",
          "#pressed_icon_name": "star-filled",
          "#text": "收藏"
        }
      ]
    }
  }
}
```

### 3. 仅图标模式

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#variant": "icon",
          "#default_value": false,
          "#icon_name": "heart",
          "#pressed_icon_name": "heart-filled",
          "#aria_label": "收藏"
        }
      ]
    }
  }
}
```

### 4. 禁用状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#disabled": true,
          "#default_value": true,
          "#text": "已禁用"
        }
      ]
    }
  }
}
```

### 5. 加载状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#loading": true,
          "#loading_text": "处理中...",
          "#default_value": false,
          "#text": "提交"
        }
      ]
    }
  }
}
```

### 6. 书签按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#default_value": false,
          "#icon_name": "bookmark",
          "#pressed_icon_name": "bookmark-filled",
          "#text": "书签"
        }
      ]
    }
  }
}
```

### 7. 通知按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#default_value": true,
          "#icon_name": "notification",
          "#pressed_icon_name": "notification",
          "#text": "通知",
          "#aria_label": "通知开关"
        }
      ]
    }
  }
}
```

### 8. 点赞按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#default_value": false,
          "#icon_name": "thumbs-up",
          "#pressed_icon_name": "thumbs-up-filled",
          "#text": "赞"
        }
      ]
    }
  }
}
```

### 9. 多选按钮组

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
            { "#type": "aws_toggle_button", "#variant": "icon", "#default_value": true, "#icon_name": "bold", "#aria_label": "粗体" },
            { "#type": "aws_toggle_button", "#variant": "icon", "#default_value": false, "#icon_name": "italic", "#aria_label": "斜体" },
            { "#type": "aws_toggle_button", "#variant": "icon", "#default_value": false, "#icon_name": "underline", "#aria_label": "下划线" }
          ]
        }
      ]
    }
  }
}
```

### 10. 视图切换

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
            { "#type": "aws_toggle_button", "#variant": "icon", "#default_value": true, "#icon_name": "list-view", "#aria_label": "列表视图" },
            { "#type": "aws_toggle_button", "#variant": "icon", "#default_value": false, "#icon_name": "grid-view", "#aria_label": "网格视图" }
          ]
        }
      ]
    }
  }
}
```

### 11. 跟随按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#default_value": false,
          "#icon_name": "add-plus",
          "#pressed_icon_name": "check",
          "#text": "关注"
        }
      ]
    }
  }
}
```

### 12. 编辑模式

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#default_value": false,
          "#icon_name": "edit",
          "#pressed_icon_name": "edit",
          "#text": "编辑模式"
        }
      ]
    }
  }
}
```

### 13. 可见性按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#variant": "icon",
          "#default_value": true,
          "#icon_name": "view-full",
          "#aria_label": "全屏"
        }
      ]
    }
  }
}
```

### 14. 带禁用原因

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#disabled": true,
          "#disabled_reason": "此功能暂不可用",
          "#default_value": false,
          "#text": "点击查看原因"
        }
      ]
    }
  }
}
```

### 15. 固定/不固定

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle_button",
          "#default_value": true,
          "#icon_name": "add-plus",
          "#pressed_icon_name": "check",
          "#text": "已固定"
        }
      ]
    }
  }
}
```
