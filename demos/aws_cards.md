# aws_cards demo

此组件的示例请参考 [组件文档](../components/aws_cards.md)。

## 示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "yaya_card": {
          "#type": "aws_cards",
          "#selected": [],
          "#card_definition": {
            "header": {"#type": "aws_link", "#content": "{item.name}"},
            "sections": [
              {"id": "description", "header": "Description", "content": "item.description"},
              {"id": "type", "header": "Type", "content": "item.type"},
              {"id": "size", "header": "Size", "content": "item.size"}
            ]
          },
          "#cards_per_row": [
            {"cards": 1},
            {"minWidth": 500, "cards": 2}
          ],
          "#items": [
            {"name": "Item 1", "alt": "First", "description": "This is the first item", "type": "1", "size": "Small"},
            {"name": "Item 2", "alt": "Second", "description": "This is the second item", "type": "2", "size": "Medium"}
          ],
          "#trackBy": "name",
          "#selection_type": "multi",
          "#pagination": {"#type": "aws_pagination"},
          "#filter": {
            "default": {"#type": "aws_text_filter"}
          }
        }
      }
    }
  }
}
```
