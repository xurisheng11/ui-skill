# 标签输入与 Token 组示例

通过输入框和确认按钮动态添加标签，使用 token_group 展示已添加的标签列表。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "example_field": {
          "#type": "aws_form_field",
          "#control": {
            "example_input": {"#type": "aws_input"}
          },
          "#secondary_control": {
            "example_button": {
              "#type": "aws_button",
              "#text": "确认",
              "#form_action": "none",
              "#on_click": "setValue_example_token_group(prevList => ([...prevList,{label: value_example_input}]));setValue_example_input('')"
            }
          }
        },
        "example_token_group": {
          "#type": "aws_token_group",
          "#default_value": [
            {"label": "Item 1"},
            {"label": "Item 2"},
            {"label": "Item 3"}
          ]
        }
      }
    }
  }
}
```
