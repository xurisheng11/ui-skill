# aws_anchor_navigation

AWS 锚点导航组件，用于在页面内进行锚点跳转导航，支持多级嵌套。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 是否必需 |
|---|---|---|---|---|---|
| default_value | string | 指定活动的锚点 href。当设置时，组件将以受控方式运行，内部滚动监听将被禁用。 | - | false | 否 |
| anchors | Array<AnchorNavigationProps.Anchor> | 锚点列表。每个锚点对象具有以下属性：text (string) - 锚点项的文本；href (string) - 锚点所指向的目标 HTML 元素的 id 属性，例如："#section1.1"；level (number) - 锚点的嵌套层级；info (string \| undefined) - 显示在链接旁边的额外信息。**注意**：锚点列表应按照它们在页面上出现的顺序进行排序。 | - | - | 是 |
| aria_labelledby | string | 为组件添加 aria-labelledby 属性。使用此属性来标识标记锚点导航的标题或标签。 | - | - | 否 |
| class_name | string | **已废弃**。为组件的根元素添加指定的类名。 | - | - | 否 |
| id | string | **已废弃**。为组件的根元素添加指定的 ID。 | - | - | 否 |
| scroll_spy_offset | number | 指定激活锚点时考虑的高度（以像素为单位）作为偏移量。当你有固定或粘性头部可能会在你滚动时与内容重叠时，这非常有用。默认为 0。 | - | 0 | 否 |

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
          "#type": "aws_anchor_navigation",
          "#default_value": "#section2",
          "#anchors": [
            {"text": "Section 1", "href": "#playground", "level": 1},
            {"text": "Section 2", "href": "#section2", "level": 1},
            {"text": "Section 3", "href": "#section3", "level": 1}
          ]
        }
      ]
    }
  }
}
```
