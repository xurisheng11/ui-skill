# aws_content_layout demo

此组件的示例请参考 [组件文档](../components/aws_content_layout.md)。

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
          "#type": "aws_content_layout",
          "#header": {
            "#type": "aws_header",
            "#counter": "(3)",
            "#actions": {"#type": "aws_button", "#text": "Button"},
            "#info": "infoooooooo",
            "#description": "description",
            "#title": "title"
          },
          "#content": {
            "#type": "aws_container",
            "#header": {
              "#type": "aws_box",
              "#content": [
                {"#type": "aws_box", "#variant": "h2", "#content": "Title"},
                {"#type": "aws_button", "#text": "header action"}
              ]
            },
            "#footer": {"#type": "aws_button", "#text": "footer action"},
            "#content": "content"
          }
        }
      ]
    }
  }
}
```
