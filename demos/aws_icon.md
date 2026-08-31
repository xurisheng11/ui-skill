# aws_icon 示例

本文档展示 aws_icon 组件的各种使用场景。

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
          "#type": "aws_icon",
          "#name": "settings"
        }
      ]
    }
  }
}
```

### 2. 不同尺寸

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
              "#type": "aws_icon",
              "#name": "star",
              "#size": "small"
            },
            {
              "#type": "aws_icon",
              "#name": "star",
              "#size": "normal"
            },
            {
              "#type": "aws_icon",
              "#name": "star",
              "#size": "medium"
            },
            {
              "#type": "aws_icon",
              "#name": "star",
              "#size": "big"
            },
            {
              "#type": "aws_icon",
              "#name": "star",
              "#size": "large"
            }
          ]
        }
      ]
    }
  }
}
```

### 3. 不同颜色变体

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
              "#type": "aws_icon",
              "#name": "status-positive",
              "#variant": "success"
            },
            {
              "#type": "aws_icon",
              "#name": "status-warning",
              "#variant": "warning"
            },
            {
              "#type": "aws_icon",
              "#name": "status-negative",
              "#variant": "error"
            },
            {
              "#type": "aws_icon",
              "#name": "status-info",
              "#variant": "normal"
            }
          ]
        }
      ]
    }
  }
}
```

### 4. 常用图标

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
            { "#type": "aws_icon", "#name": "settings" },
            { "#type": "aws_icon", "#name": "search" },
            { "#type": "aws_icon", "#name": "add-plus" },
            { "#type": "aws_icon", "#name": "close" },
            { "#type": "aws_icon", "#name": "refresh" },
            { "#type": "aws_icon", "#name": "download" },
            { "#type": "aws_icon", "#name": "upload" },
            { "#type": "aws_icon", "#name": "copy" }
          ]
        }
      ]
    }
  }
}
```

### 5. 导航图标

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
            { "#type": "aws_icon", "#name": "angle-left" },
            { "#type": "aws_icon", "#name": "angle-right" },
            { "#type": "aws_icon", "#name": "angle-up" },
            { "#type": "aws_icon", "#name": "angle-down" },
            { "#type": "aws_icon", "#name": "arrow-left" },
            { "#type": "aws_icon", "#name": "arrow-right" }
          ]
        }
      ]
    }
  }
}
```

### 6. 文件图标

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
            { "#type": "aws_icon", "#name": "file" },
            { "#type": "aws_icon", "#name": "file-open" },
            { "#type": "aws_icon", "#name": "folder" },
            { "#type": "aws_icon", "#name": "folder-open" }
          ]
        }
      ]
    }
  }
}
```

### 7. 状态图标

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
            { "#type": "aws_icon", "#name": "status-positive" },
            { "#type": "aws_icon", "#name": "status-warning" },
            { "#type": "aws_icon", "#name": "status-negative" },
            { "#type": "aws_icon", "#name": "status-info" },
            { "#type": "aws_icon", "#name": "status-in-progress" },
            { "#type": "aws_icon", "#name": "status-stopped" }
          ]
        }
      ]
    }
  }
}
```

### 8. 评分图标

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
          "#content": [
            { "#type": "aws_icon", "#name": "star-filled", "#size": "large", "#variant": "warning" },
            { "#type": "aws_icon", "#name": "star-filled", "#size": "large", "#variant": "warning" },
            { "#type": "aws_icon", "#name": "star-filled", "#size": "large", "#variant": "warning" },
            { "#type": "aws_icon", "#name": "star-half", "#size": "large", "#variant": "warning" },
            { "#type": "aws_icon", "#name": "star", "#size": "large" }
          ]
        }
      ]
    }
  }
}
```

### 9. 用户图标

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
            { "#type": "aws_icon", "#name": "user-profile" },
            { "#type": "aws_icon", "#name": "user-profile-active", "#variant": "success" },
            { "#type": "aws_icon", "#name": "contact" }
          ]
        }
      ]
    }
  }
}
```

### 10. 媒体图标

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
            { "#type": "aws_icon", "#name": "play" },
            { "#type": "aws_icon", "#name": "pause" },
            { "#type": "aws_icon", "#name": "video-on" },
            { "#type": "aws_icon", "#name": "video-off" },
            { "#type": "aws_icon", "#name": "microphone" },
            { "#type": "aws_icon", "#name": "microphone-off" }
          ]
        }
      ]
    }
  }
}
```

### 11. 操作图标

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
            { "#type": "aws_icon", "#name": "edit" },
            { "#type": "aws_icon", "#name": "delete-marker" },
            { "#type": "aws_icon", "#name": "copy" },
            { "#type": "aws_icon", "#name": "redo" },
            { "#type": "aws_icon", "#name": "undo" }
          ]
        }
      ]
    }
  }
}
```

### 12. 安全图标

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
            { "#type": "aws_icon", "#name": "lock-private" },
            { "#type": "aws_icon", "#name": "unlocked" },
            { "#type": "aws_icon", "#name": "security" },
            { "#type": "aws_icon", "#name": "key" }
          ]
        }
      ]
    }
  }
}
```

### 13. 表情图标

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
            { "#type": "aws_icon", "#name": "face-happy" },
            { "#type": "aws_icon", "#name": "face-neutral" },
            { "#type": "aws_icon", "#name": "face-sad" }
          ]
        }
      ]
    }
  }
}
```

### 14. 视图图标

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
            { "#type": "aws_icon", "#name": "view-full" },
            { "#type": "aws_icon", "#name": "view-horizontal" },
            { "#type": "aws_icon", "#name": "view-vertical" },
            { "#type": "aws_icon", "#name": "zoom-in" },
            { "#type": "aws_icon", "#name": "zoom-out" }
          ]
        }
      ]
    }
  }
}
```

### 15. 大尺寸图标

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_icon",
          "#name": "check",
          "#size": "large",
          "#variant": "success"
        }
      ]
    }
  }
}
```
