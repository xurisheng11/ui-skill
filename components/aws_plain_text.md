# aws_plain_text

AWS 纯文本组件，用于在页面中渲染简单的纯文本内容。

## 参数说明

| 名称 | 类型 | 描述 | 可接受值 | 默认值 | 是否必填 | 可使用变量 | 使用方法 |
|---|---|---|---|---|---|---|---|
| text | string | 需要显示的纯文本 | - | - | 否 | true | {variable} |

## 使用示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_plain_text",
          "#text": "plain text"
        }
      ]
    }
  }
}
```
