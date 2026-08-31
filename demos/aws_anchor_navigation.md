# aws_anchor_navigation demo

此组件的示例请参考 [组件文档](../components/aws_anchor_navigation.md)。

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
          "#type": "aws_anchor_navigation",
          "#default_value": "#section2",
          "#anchors": [
            {"text": "Section 1", "href": "#playground", "level": 1},
            {"text": "Section 2", "href": "#section2", "level": 1},
            {"text": "Section 3", "href": "#section3", "level": 1}
          ]
        }
      ]
    }
  }
}
```
