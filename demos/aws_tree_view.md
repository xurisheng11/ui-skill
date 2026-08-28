# aws_tree_view demo

此组件的示例请参考 [组件文档](../components/aws_tree_view.md)。

## 示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_list": {
          "#type": "aws_tree_view",
          "#items": [
            {
              "id": "1",
              "content": "Feature X",
              "iconName": "folder",
              "nestedItems": [
                {
                  "id": "1.1",
                  "content": "tests",
                  "iconName": "folder",
                  "nestedItems": [
                    {"id": "1.1.1", "content": "unit.test.tsx", "iconName": "file"},
                    {"id": "1.1.2", "content": "integ.test.ts", "iconName": "file"}
                  ]
                },
                {"id": "1.2", "iconName": "folder", "content": "assets"},
                {"id": "1.3", "iconName": "file", "content": "index.tsx"}
              ]
            },
            {
              "id": "2",
              "content": "Feature Y",
              "iconName": "folder",
              "nestedItems": [
                {"id": "2.1", "content": "index.tsx", "iconName": "file"}
              ]
            },
            {"id": "3", "content": "package.json", "iconName": "file"}
          ],
          "#render_item": {
            "icon": {"#type": "aws_icon", "#name": {"#markup": "item.iconName"}},
            "content": "item.content"
          }
        }
      }
    }
  }
}
```
