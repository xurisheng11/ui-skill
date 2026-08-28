# aws_offcanvas

AWS 侧边抽屉组件，从页面一侧滑出的弹层，用于显示详细信息或辅助内容。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 是否必需 |
|---|---|---|---|---|---|
| backdrop | boolean | 是否启用背景遮罩层。如果设置为 `true`，则会在弹出内容后方显示一个半透明的遮罩层。 | true, false | false | 否 |
| header | string | 弹出内容的头部信息。 | 字符串 | '' | 否 |
| footer | string | 弹出内容的底部信息。 | 字符串 | '' | 否 |
| content | string | 弹出内容的主体部分。 | 字符串 | '' | 否 |
| off_canvas_id | string | 弹出内容的唯一标识符。 | 字符串 | '' | 否 |
| title | string | 弹出内容的标题文字。 | 字符串 | '' | 否 |

## 使用示例

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
