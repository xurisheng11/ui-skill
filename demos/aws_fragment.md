# aws_fragment demo

此组件的示例请参考 [组件文档](../components/aws_fragment.md)。

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
          "#type": "aws_header",
          "#description": {
            "#type": "aws_fragment",
            "#content": [
              {
                "#type": "aws_link",
                "#href": "#",
                "#content": "链接",
                "#external": true
              },
              {
                "#type": "aws_plain_text",
                "#text": "文本"
              }
            ]
          },
          "#title": "title"
        }
      ]
    }
  }
}
```
