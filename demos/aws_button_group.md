# aws_button_group demo

此组件的示例请参考 [组件文档](../components/aws_button_group.md)。

## 示例

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
