# aws_html_tooltip

AWS HTML 工具提示组件，为文本内容提供悬浮提示信息。

## 参数说明

| 名称 | 类型 | 描述 | 可接受值 | 默认值 | 是否必填 | 可使用变量 | 使用方法 |
|---|---|---|---|---|---|---|---|
| title | string | tooltip中显示的内容 | - | - | 否 | true | variable |
| text | string/array/object | 需要显示的内容 | - | - | 否 | true | {variable} |

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
          "#type": "aws_html_tooltip",
          "#title": "tooltip",
          "#text": "text"
        }
      ]
    }
  }
}
```
