# aws_content_layout

AWS 内容布局组件，用于构建页面内容区域的整体布局结构，支持头部、内容、面包屑、通知等插槽。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 必需 | 可使用变量 | 使用方法 |
|---|---|---|---|---|---|---|---|
| class_name | string | 将指定的类添加到组件的根元素。已弃用。 | - | - | 否 | | |
| default_padding | boolean | 如果你的页面使用了带有 disableContentPaddings=true 的应用布局组件，则将其设置为true。 | - | false | 否 | | |
| disable_overlap | boolean | 确定布局是否在头部和内容之间有重叠。如果为true，则移除重叠。 | - | false | 否 | | |
| header_background_style | string/function | 使用此属性来设置头部的背景样式。 | - | - | 否 | | |
| header_variant | string | 决定头部的视觉处理方式。default / high-contrast / divider。 | default / high-contrast / divider | - | 否 | | |
| id | string | 将指定的ID添加到组件的根元素。已弃用。 | - | - | 否 | | |
| max_content_width | number | 内容的最大宽度。 | - | - | 否 | | |

## 插槽

| 名称 | 描述 | 可使用变量 | 使用方法 |
|---|---|---|---|
| breadcrumbs | 使用此插槽向内容布局添加面包屑组组件。 | true | variable |
| content | 使用此插槽渲染位于头部下方布局的主要内容。 | true | {variable} |
| header | 使用此插槽渲染布局的头部内容。 | true | variable |
| notifications | 使用此插槽显示通知到内容布局。 | | |
| secondary_header | 使用此插槽在头部内添加一个次要元素，占据25%的可用空间。 | true | variable |

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
