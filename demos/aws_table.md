# aws_table demo

此组件的示例请参考 [组件文档](../components/aws_table.md)。

## 示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "example_table": {
          "#type": "aws_table",
          "#sticky_columns": {"first": 1},
          "#selection_type": "single",
          "#header": {"#type": "aws_header", "#title": "表格"},
          "#items": [
            {"name": "Item 1", "alt": "First", "description": "This is the first item", "type": "1", "size": "Small"},
            {"name": "Item 2", "alt": "Second", "description": "This is the second item", "type": "2", "size": "Medium"}
          ],
          "#selected": [],
          "#track_by": "name",
          "#column_definitions": [
            {
              "id": "variable",
              "header": "Variable name",
              "cell": {
                "#type": "aws_link",
                "#content": "{item.name}",
                "#href": {"#markup": "`/a/b/${item.name}`"}
              },
              "sortingField": "name",
              "isRowHeader": true
            },
            {"id": "alt", "header": "Alt text", "cell": "item.alt", "sortingField": "alt"},
            {"id": "description", "header": "Description", "cell": "item.description"},
            {"id": "type", "header": "Type", "cell": "item.type"},
            {"id": "size", "header": "Size", "cell": "item.size"}
          ],
          "#pagination": {"#type": "aws_pagination"},
          "#filter": {
            "default": {
              "#type": "aws_text_filter",
              "#filtering_placeholder": "按关键字搜索",
              "#count_text": {"#markup": "filter_status_example_table?filter_total_example_table+' 匹配项':''"}
            }
          }
        }
      }
    }
  }
}
```
