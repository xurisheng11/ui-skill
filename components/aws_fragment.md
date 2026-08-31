# aws_fragment

AWS 片段组件，用于包裹多个元素，常用于在只允许单个子元素的属性中放置多个元素。

## 参数说明

| 名称 | 类型 | 描述 | 可接受值 | 默认值 | 是否必填 | 可使用变量 | 使用方法 |
|---|---|---|---|---|---|---|---|
| content | element array/object | 包裹的多个元素 | - | - | 否 | true | {variable} |

## 使用示例

例如，在 header 的 description 属性内使用多个元素：

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
