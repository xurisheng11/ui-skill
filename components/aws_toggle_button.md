# aws_toggle_button

切换按钮组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 布尔值 | 是 | 是否按下 |
| text | 字符串 | 否 | 按钮文本 |
| icon_name | 字符串 | 否 | 文本旁图标 |
| pressed_icon_name | 字符串 | 否 | 按下状态图标 |
| variant | 字符串 | 否 | 变体类型 |
| disabled | 布尔值 | 否 | 是否禁用 |
| disabled_reason | 字符串 | 否 | 禁用原因 |
| loading | 布尔值 | 否 | 加载状态 |
| loading_text | 字符串 | 否 | 加载文本 |
| external | 布尔值 | 否 | 外部链接 |
| wrap_text | 布尔值 | 否 | 文本换行 |
| aria_controls | 字符串 | 否 | aria-controls |
| aria_describedby | 字符串 | 否 | aria-describedby |
| aria_label | 字符串 | 否 | aria-label |

### variant 可选值

- `normal` - 普通按钮（默认）
- `icon` - 仅图标

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

### 默认未选中

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

### 仅图标模式

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

### 禁用状态

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

### 带禁用原因

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

### 加载状态

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

### 书签按钮

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

### 通知按钮

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

### 可见性按钮

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

### 编辑模式

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

### 跟随按钮

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

### 多选按钮组

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
              "#type": "aws_toggle_button",
              "#variant": "icon",
              "#default_value": true,
              "#icon_name": "bold",
              "#aria_label": "粗体"
            },
            {
              "#type": "aws_toggle_button",
              "#variant": "icon",
              "#default_value": false,
              "#icon_name": "italic",
              "#aria_label": "斜体"
            },
            {
              "#type": "aws_toggle_button",
              "#variant": "icon",
              "#default_value": false,
              "#icon_name": "underline",
              "#aria_label": "下划线"
            }
          ]
        }
      ]
    }
  }
}
```

### 视图切换

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
              "#type": "aws_toggle_button",
              "#variant": "icon",
              "#default_value": true,
              "#icon_name": "list-view",
              "#aria_label": "列表视图"
            },
            {
              "#type": "aws_toggle_button",
              "#variant": "icon",
              "#default_value": false,
              "#icon_name": "grid-view",
              "#aria_label": "网格视图"
            }
          ]
        }
      ]
    }
  }
}
```

### 固定宽度文本

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
          "#text": "固定文本",
          "#wrap_text": false
        }
      ]
    }
  }
}
```

### 允许文本换行

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
          "#text": "允许文本换行显示在按钮上",
          "#wrap_text": true
        }
      ]
    }
  }
}
```

### 点赞按钮

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
