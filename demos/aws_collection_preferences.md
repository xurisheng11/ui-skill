# aws_collection_preferences demo

此组件的示例请参考 [组件文档](../components/aws_collection_preferences.md)。

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
          "#type": "aws_collection_preferences",
          "#default_value": {
            "pageSize": 10,
            "visibleContent": ["id", "domainName", "deliveryMethod"]
          },
          "#page_size_preference": {
            "options": [
              {"value": 10, "label": "10 resources"},
              {"value": 20, "label": "20 resources"}
            ]
          },
          "#visible_content_preference": {
            "title": "Select visible content",
            "options": [
              {
                "label": "Main distribution properties",
                "options": [
                  {"id": "id", "label": "Distribution ID", "editable": false},
                  {"id": "domainName", "label": "Domain name"},
                  {"id": "deliveryMethod", "label": "Delivery method"}
                ]
              }
            ]
          },
          "#custom_preference": {
            "cards": {
              "#type": "aws_radio_group",
              "#items": [
                {"value": "table", "label": "Table"},
                {"value": "cards", "label": "Cards"}
              ]
            }
          }
        }
      ]
    }
  }
}
```
