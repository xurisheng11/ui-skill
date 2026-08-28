# aws_segmented_control demo

此组件的示例请参考 [组件文档](../components/aws_segmented_control.md)。

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
          "#type": "aws_segmented_control",
          "#label": "Default segmented control",
          "#default_value": "option1",
          "#options": [
            {"text": "Option 1", "id": "option1"},
            {"text": "Option 2", "id": "option2"},
            {"text": "Option 3", "id": "option3"}
          ]
        }
      ]
    }
  }
}
```
