# aws_attribute_editor demo

此组件的示例请参考 [组件文档](../components/aws_attribute_editor.md)。

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
          "#type": "aws_attribute_editor",
          "#default_value": [{"name": "name1", "value": "value1"}],
          "#add_button_text": "添加",
          "#definition": [
            {"label": "Name", "key": "name", "control": {"#type": "aws_input"}},
            {"label": "Value", "key": "value", "control": {"#type": "aws_toggle"}}
          ]
        }
      ]
    }
  }
}
```
