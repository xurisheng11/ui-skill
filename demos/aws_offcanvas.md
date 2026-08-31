# aws_offcanvas demo

此组件的示例请参考 [组件文档](../components/aws_offcanvas.md)。

## 示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "#type": "aws_offcanvas",
        "#title": "信息111",
        "#header": {"#type": "aws_header", "#title": "信息222"},
        "#content": {"#markup": "<h3>h3 section content</h3>"},
        "#footer": {"#markup": "<h3>h3 section footer</h3>"}
      }
    }
  }
}
```
