# aws_icon

图标组件，用于显示各种图标。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| name | 字符串 | 否 | 图标名称 |
| size | 字符串 | 否 | 图标大小 |
| variant | 字符串 | 否 | 图标颜色变体 |
| alt | 字符串 | 否 | 自定义图标的替代文本 |
| url | 字符串 | 否 | 自定义图标URL |
| svg | 字符串 | 否 | 自定义SVG代码 |

### size 可选值

- `small` - 小尺寸
- `normal` - 默认尺寸
- `medium` - 中尺寸
- `big` - 大尺寸
- `large` - 最大尺寸
- `inherit` - 继承父元素尺寸

### variant 可选值

- `normal` - 正常颜色
- `disabled` - 禁用状态
- `error` - 错误颜色
- `inverted` - 反转颜色
- `link` - 链接颜色
- `subtle` - 淡色
- `success` - 成功颜色
- `warning` - 警告颜色

### 可用图标名称

add-plus, anchor-link, angle-left-double, angle-left, angle-right-double, angle-right, angle-up, angle-down, arrow-left, arrow-right, audio-full, audio-half, audio-off, backward-10-seconds, bug, call, calendar, caret-down-filled, caret-down, caret-left-filled, caret-right-filled, caret-up-filled, caret-up, check, contact, close, closed-caption, closed-caption-unavailable, copy, command-prompt, delete-marker, download, drag-indicator, edit, ellipsis, envelope, exit-full-screen, expand, external, face-happy, face-happy-filled, face-neutral, face-neutral-filled, face-sad, face-sad-filled, file-open, file, filter, flag, folder-open, folder, forward-10-seconds, full-screen, gen-ai, globe, grid-view, group-active, group, heart, heart-filled, insert-row, key, keyboard, list-view, location-pin, lock-private, map, menu, microphone, microphone-off, mini-player, multiscreen, notification, pause, play, redo, refresh, remove, resize-area, script, search, security, settings, send, share, shrink, star-filled, star-half, star, status-in-progress, status-info, status-negative, status-pending, status-positive, status-stopped, status-warning, subtract-minus, suggestions, support, thumbs-down-filled, thumbs-down, thumbs-up-filled, thumbs-up, ticket, transcript, treeview-collapse, treeview-expand, undo, unlocked, upload-download, upload, user-profile-active, user-profile, video-off, video-on, video-unavailable, video-camera-off, video-camera-on, video-camera-unavailable, view-full, view-horizontal, view-vertical, zoom-in, zoom-out, zoom-to-fit

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
          "#type": "aws_icon",
          "#name": "settings"
        }
      ]
    }
  }
}
```

### 不同尺寸

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

### 不同颜色变体

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

### 常用图标示例

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
              "#name": "settings"
            },
            {
              "#type": "aws_icon",
              "#name": "search"
            },
            {
              "#type": "aws_icon",
              "#name": "add-plus"
            },
            {
              "#type": "aws_icon",
              "#name": "close"
            },
            {
              "#type": "aws_icon",
              "#name": "refresh"
            },
            {
              "#type": "aws_icon",
              "#name": "download"
            },
            {
              "#type": "aws_icon",
              "#name": "upload"
            },
            {
              "#type": "aws_icon",
              "#name": "copy"
            }
          ]
        }
      ]
    }
  }
}
```

### 导航图标

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
              "#name": "angle-left"
            },
            {
              "#type": "aws_icon",
              "#name": "angle-right"
            },
            {
              "#type": "aws_icon",
              "#name": "angle-up"
            },
            {
              "#type": "aws_icon",
              "#name": "angle-down"
            },
            {
              "#type": "aws_icon",
              "#name": "arrow-left"
            },
            {
              "#type": "aws_icon",
              "#name": "arrow-right"
            }
          ]
        }
      ]
    }
  }
}
```

### 文件相关图标

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
              "#name": "file"
            },
            {
              "#type": "aws_icon",
              "#name": "file-open"
            },
            {
              "#type": "aws_icon",
              "#name": "folder"
            },
            {
              "#type": "aws_icon",
              "#name": "folder-open"
            }
          ]
        }
      ]
    }
  }
}
```

### 状态图标

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
              "#name": "status-positive"
            },
            {
              "#type": "aws_icon",
              "#name": "status-warning"
            },
            {
              "#type": "aws_icon",
              "#name": "status-negative"
            },
            {
              "#type": "aws_icon",
              "#name": "status-info"
            },
            {
              "#type": "aws_icon",
              "#name": "status-in-progress"
            },
            {
              "#type": "aws_icon",
              "#name": "status-stopped"
            }
          ]
        }
      ]
    }
  }
}
```

### 评分/收藏图标

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
          "#name": "star-filled",
          "#size": "large",
          "#variant": "warning"
        },
        {
          "#type": "aws_icon",
          "#name": "star-filled",
          "#size": "large",
          "#variant": "warning"
        },
        {
          "#type": "aws_icon",
          "#name": "star-filled",
          "#size": "large",
          "#variant": "warning"
        },
        {
          "#type": "aws_icon",
          "#name": "star-half",
          "#size": "large",
          "#variant": "warning"
        },
        {
          "#type": "aws_icon",
          "#name": "star",
          "#size": "large"
        }
      ]
    }
  }
}
```

### 用户图标

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
              "#name": "user-profile"
            },
            {
              "#type": "aws_icon",
              "#name": "user-profile-active",
              "#variant": "success"
            },
            {
              "#type": "aws_icon",
              "#name": "contact"
            }
          ]
        }
      ]
    }
  }
}
```
