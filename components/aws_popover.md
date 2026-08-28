# aws_popover

AWS 弹出框组件，点击触发器后在附近显示浮层内容。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 必需 | 可使用变量 | 使用方法 |
|---|---|---|---|---|---|---|---|
| class_name | string | 将指定的类添加到组件的根元素。已废弃。 | - | - | 否 | | |
| dismiss_aria_label | string | 为可访问性向关闭按钮添加 `aria-label`。 | - | - | 否 | | |
| dismiss_button | boolean | 决定是否在弹出框主体中显示关闭按钮。 | - | true | 否 | | |
| fixed_width | boolean | 无论内容如何，都将弹出框主体扩展到其最大宽度。 | - | false | 否 | | |
| header | string | 指定弹出框的可选标题文本。 | - | - | 否 | | |
| id | string | 将指定的ID添加到组件的根元素。已废弃。 | - | - | 否 | | |
| position | string | 确定打开时弹出框相对于触发器显示的位置。 | top/right/bottom/left | 'right' | 否 | | |
| render_with_portal | boolean | 启用此属性将允许弹出框使用React Portals在根堆叠上下文中渲染。 | - | false | 否 | | |
| size | string | 确定弹出框的最大宽度。 | small/medium/large | 'medium' | 否 | | |
| trigger_aria_label | string | 向文本触发按钮添加 `aria-label`。 | - | - | 否 | | |
| trigger_type | string | 指定触发区域内的内容类型。text / text-inline / custom。 | text/text-inline/custom | 'text' | 否 | | |
| wrap_trigger_text | boolean | 指定文本触发内容是否应换行。 | - | true | 否 | | |

## 插槽

| 名称 | 描述 | 可使用变量 | 使用方法 |
|---|---|---|---|
| content (default) | 弹出框的内容。 | true | {variable} |
| trigger | 用户选择时触发弹出框的元素。 | true | {variable} |

## 使用示例

### 文本触发

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_popover",
          "#content": {"#type": "aws_status_indicator", "#content": "info"},
          "#trigger": "<Button>AWS</Button>"
        }
      ]
    }
  }
}
```

### 自定义触发器（按钮）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_popover",
          "#trigger_type": "custom",
          "#content": "提示信息",
          "#trigger": {
            "#type": "aws_button",
            "#icon_name": "support",
            "#variant": "link"
          }
        }
      ]
    }
  }
}
```

### 自定义触发器（链接图标）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_popover",
          "#trigger_type": "custom",
          "#content": "提示信息",
          "#trigger": {
            "#type": "aws_link",
            "#content": {"#type": "aws_icon", "#name": "support"}
          }
        }
      ]
    }
  }
}
```
