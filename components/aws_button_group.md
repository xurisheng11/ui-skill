# aws_button_group

AWS 按钮组组件，将多个图标按钮组织在工具栏中，支持切换按钮、文件上传、下拉菜单等多种类型。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 是否必需 |
|---|---|---|---|---|---|
| aria_label | string | 为按钮组工具栏元素添加aria-label。 | - | - | 否 |
| class_name (已弃用) | string | 将指定的类添加到组件的根元素。已弃用。 | - | - | 否 |
| dropdown_expand_to_viewport | boolean | 决定所有菜单下拉项的下拉放置策略。 | - | false | 否 |
| id (已弃用) | string | 将指定的ID添加到组件的根元素。已弃用。 | - | - | 否 |
| items | ReadonlyArray<ButtonGroupProps.ItemOrGroup> | 包含多个支持类型的对象数组。 | - | - | 是 |
| variant | string | 决定按钮下拉的一般样式。图标按钮使用 `icon`。 | `icon` | - | 是 |

### items 支持的类型

**icon-button**:
- `id` (string, 必填) - 按钮的唯一标识符。
- `text` (string, 必填) - 显示为提示信息的名字。
- `disabled` (boolean, 可选) - 禁用状态。
- `loading` (boolean, 可选) - 加载状态。
- `icon_name` (string, 可选) - 图标名称。
- `popover_feedback` (ReactNode, 可选) - 点击后出现的反馈文本。

**icon-toggle-button**:
- `id` (string, 必填) - 按钮的唯一标识符。
- `pressed` (boolean, 必填) - 切换按钮的按下状态。
- `text` (string, 必填) - 显示为提示信息的名字。
- `icon_name` (string, 可选) - 图标名称。
- `pressed_icon_name` (string, 可选) - 按下状态下图标的名称。
- `popover_feedback` (ReactNode, 可选) - 点击后出现的反馈文本。
- `pressed_popover_feedback` (ReactNode, 可选) - 按下状态点击后的反馈文本。
- `custom` (string|false, 可选) - 用户自定义行为。

**file-input**:
- `id` (string, 必填)
- `text` (string, 必填)
- `accept` (string, 可选) - 允许的文件类型。
- `multiple` (string, 可选) - 允许选择多个文件。

**menu-dropdown**:
- `id` (string, 必填)
- `text` (string, 必填)
- `items` (ButtonDropdownProps.ItemOrGroup[]) - 下拉项数组。

**group**:
- `text` (string) - 作为该组ARIA标签渲染的组名。
- `items` - 属于此组的项数组。

## 使用示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_group",
          "#items": [
            {
              "type": "group",
              "text": "Vote",
              "items": [
                {
                  "type": "icon-toggle-button",
                  "id": "like",
                  "iconName": "thumbs-up",
                  "pressedIconName": "thumbs-up-filled",
                  "text": "Like",
                  "pressed": {"#markup": "custom === \"like\""},
                  "custom": false
                },
                {
                  "type": "icon-toggle-button",
                  "id": "dislike",
                  "iconName": "thumbs-down",
                  "pressedIconName": "thumbs-down-filled",
                  "text": "Dislike",
                  "pressed": {"#markup": "custom === \"dislike\""},
                  "custom": {
                    "value": "custom",
                    "set_value": "set_custom",
                    "on_item_click": "[\"like\", \"dislike\"].includes(detail.id) && set_custom(detail.pressed ? detail.id : \"\")"
                  }
                }
              ]
            },
            {
              "type": "icon-button",
              "id": "copy",
              "iconName": "copy",
              "text": "Copy",
              "popoverFeedback": {
                "#type": "aws_status_indicator",
                "#status_type": "success",
                "#content": "成功"
              }
            },
            {
              "type": "menu-dropdown",
              "id": "more-actions",
              "text": "More actions",
              "items": [
                {"id": "add", "iconName": "add-plus", "text": "Add"},
                {"id": "remove", "iconName": "remove", "text": "Remove"}
              ]
            }
          ]
        }
      ]
    }
  }
}
```
