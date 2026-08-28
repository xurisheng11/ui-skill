# aws_popover demo

此组件的示例请参考 [组件文档](../components/aws_popover.md)。

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
          "#type": "aws_popover",
          "#content": {"#type": "aws_status_indicator", "#content": "info"},
          "#trigger": "<Button>AWS</Button>"
        }
      ]
    }
  }
}
```
