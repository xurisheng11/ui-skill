# aws_button

AWS 按钮组件，用于触发动作的标准按钮组件。支持多种变体、图标、加载状态和无障碍属性。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| variant | 字符串 | 否 | 确定按钮的一般样式 | normal / primary / link / icon / inline-icon / inline-link | 'normal' |
| text | 字符串 | 是 | 按钮元素中显示的文本 | - | - |
| disabled | 布尔值 | 否 | 将按钮渲染为禁用状态并阻止点击 | - | false |
| disabled_reason | 字符串 | 否 | 提供按钮被禁用的原因（仅在 disabled 为 true 时生效） | - | - |
| loading | 布尔值 | 否 | 将按钮渲染为加载状态 | - | false |
| loading_text | 字符串 | 否 | 加载状态时屏幕阅读器宣布的文本 | - | - |
| href | 字符串 | 否 | 将链接样式应用于按钮 | - | - |
| target | 字符串 | 否 | 指定在哪里打开链接 URL | - | - |
| rel | 字符串 | 否 | 为链接添加 rel 属性 | - | - |
| download | 布尔/字符串 | 否 | 提示用户下载而不是导航 | - | - |
| full_width | 布尔值 | 否 | 设置按钮宽度为父容器宽度的 100% | - | false |
| wrap_text | 布尔值 | 否 | 指定文本内容是否换行 | - | true |
| form | 字符串 | 否 | 要与按钮关联的 form 元素的 id | - | - |
| form_action | 字符串 | 否 | 按钮点击执行的表单动作 | submit / none | 'submit' |
| is_validate | 布尔值 | 否 | 指定是否执行表单校验 | - | true |

### 图标属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| icon_name | 字符串 | 否 | 在文本旁边显示一个图标 | 详见下方图标列表 | - |
| icon_align | 字符串 | 否 | 指定图标的对齐方式 | left / right | 'left' |
| icon_url | 字符串 | 否 | 指定自定义图标的 URL | - | - |
| icon_alt | 字符串 | 否 | 为自定义图标指定替代文本 | - | - |

### 无障碍属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| aria_label | 字符串 | 否 | 为按钮添加 aria-label 属性 | - | - |
| aria_describedby | 字符串 | 否 | 为按钮添加 aria-describedby 属性 | - | - |
| aria_expanded | 布尔值 | 否 | 当按钮控制可展开元素时使用 | - | false |
| aria_controls | 字符串 | 否 | 当按钮控制某个元素时使用 | - | - |

### variant 可选值说明

| 值 | 描述 |
| --- | --- |
| normal | 次级按钮 |
| primary | 主按钮（高亮样式） |
| link | 三级按钮（链接样式） |
| icon | 仅显示图标（无文本） |
| inline-icon | 仅图标按钮（位于文本上下文中） |
| inline-link | 无外边距的三级按钮 |

### icon_name 可选图标

add-plus, anchor-link, angle-left-double, angle-left, angle-right-double, angle-right, angle-up, angle-down, arrow-left, arrow-right, audio-full, audio-half, audio-off, bug, call, calendar, caret-down-filled, caret-down, caret-left-filled, caret-right-filled, caret-up-filled, caret-up, check, contact, close, copy, delete-marker, download, drag-indicator, edit, ellipsis, envelope, expand, external, file-open, file, filter, flag, folder-open, folder, gen-ai, group-active, group, heart, heart-filled, insert-row, key, keyboard, lock-private, menu, microphone, microphone-off, multiscreen, notification, redo, refresh, remove, resize-area, script, search, security, settings, send, share, shrink, star-filled, star-half, star, status-in-progress, status-info, status-negative, status-pending, status-positive, status-stopped, status-warning, subtract-minus, suggestions, thumbs-down-filled, thumbs-down, thumbs-up-filled, thumbs-up, ticket, treeview-collapse, treeview-expand, undo, unlocked, upload-download, upload, user-profile-active, user-profile, video-off, video-on, video-unavailable, view-full, view-horizontal, view-vertical, zoom-in, zoom-out, zoom-to-fit

## 事件说明

| 事件 | 描述 | 是否可取消 |
| --- | --- | --- |
| on_click | 当用户点击按钮且按钮未处于禁用或加载状态时调用 | true |
| on_follow | 当用户左键单击按钮且未按下修饰键，并且按钮设置了 href 时调用 | true |

### ClickDetail 事件详情

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| alt_key | boolean | 是否按下 Alt 键 |
| button | number | 鼠标按钮编号 |
| ctrl_key | boolean | 是否按下 Ctrl 键 |
| meta_key | boolean | 是否按下 Meta 键 |
| shift_key | boolean | 是否按下 Shift 键 |

## 使用示例

### 基础用法 - 不同变体

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

### 带图标按钮

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
          "#text": "拨打电话",
          "#variant": "primary",
          "#icon_name": "call"
        },
        {
          "#type": "aws_button",
          "#text": "下载文件",
          "#variant": "normal",
          "#icon_name": "download"
        },
        {
          "#type": "aws_button",
          "#text": "编辑",
          "#icon_name": "edit"
        }
      ]
    }
  }
}
```

### 图标对齐方式

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
          "#text": "图标在左边",
          "#icon_align": "left",
          "#icon_name": "arrow-right"
        },
        {
          "#type": "aws_button",
          "#text": "图标在右边",
          "#icon_align": "right",
          "#icon_name": "arrow-right"
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
          "#type": "aws_button",
          "#text": "禁用按钮",
          "#disabled": true
        },
        {
          "#type": "aws_button",
          "#text": "禁用主要按钮",
          "#variant": "primary",
          "#disabled": true
        }
      ]
    }
  }
}
```

### 禁用原因提示

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
          "#disabled": true,
          "#disabled_reason": "请先填写所有必填项"
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
          "#type": "aws_button",
          "#text": "提交中",
          "#loading": true,
          "#loading_text": "正在提交，请稍候..."
        }
      ]
    }
  }
}
```

### 链接按钮

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
          "#href": "https://help.example.com",
          "#target": "_blank",
          "#variant": "link"
        }
      ]
    }
  }
}
```

### 图标按钮

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
          "#icon_name": "settings",
          "#aria_label": "设置"
        },
        {
          "#type": "aws_button",
          "#variant": "icon",
          "#icon_name": "search",
          "#aria_label": "搜索"
        },
        {
          "#type": "aws_button",
          "#variant": "icon",
          "#icon_name": "notification",
          "#aria_label": "通知"
        }
      ]
    }
  }
}
```

### 全宽按钮

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
          "#text": "全宽提交按钮",
          "#variant": "primary",
          "#full_width": true
        }
      ]
    }
  }
}
```

### 表单按钮

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
          "#text": "提交表单",
          "#variant": "primary",
          "#form_action": "submit"
        },
        {
          "#type": "aws_button",
          "#text": "重置",
          "#form_action": "none"
        }
      ]
    }
  }
}
```

### 下载按钮

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
          "#href": "/api/reports/download",
          "#download": "report-2024.pdf"
        }
      ]
    }
  }
}
```

### 常用图标按钮组合

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
          "#text": "刷新",
          "#icon_name": "refresh"
        },
        {
          "#type": "aws_button",
          "#text": "添加",
          "#variant": "primary",
          "#icon_name": "add-plus"
        },
        {
          "#type": "aws_button",
          "#text": "删除",
          "#icon_name": "delete-marker"
        },
        {
          "#type": "aws_button",
          "#text": "编辑",
          "#icon_name": "edit"
        },
        {
          "#type": "aws_button",
          "#text": "分享",
          "#icon_name": "share"
        }
      ]
    }
  }
}
```
