# aws_list demo

此组件的示例请参考 [组件文档](../components/aws_list.md)。

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
          "#type": "aws_list",
          "#items": [
            {
              "id": "instance",
              "content": "Instance",
              "description": "A virtual server in the cloud, typically running in Amazon EC2."
            },
            {
              "id": "bucket",
              "content": "Bucket",
              "description": "A container for storing objects in Amazon S3."
            },
            {
              "id": "vpc",
              "content": "VPC (Virtual Private Cloud)",
              "description": "A logically isolated section of the AWS cloud."
            }
          ],
          "#render_item": {
            "id": "item.id",
            "content": {
              "#prefix": "item.content?",
              "#type": "aws_link",
              "#content": "{item.content}",
              "#suffix": ":'--'"
            },
            "secondaryContent": "item.description"
          },
          "#sortable": true
        }
      }
    }
  }
}
```
