# aws_cards

AWS 卡片组件，以卡片形式展示数据集合，支持选择、过滤、分页、自定义布局等功能。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 必需 |
|---|---|---|---|---|---|
| aria_labels | CardsProps.AriaLabels | 为选择组件（复选框和单选按钮）添加标签。 | - | - | 否 |
| card_definition | CardsProps.CardDefinition | 定义每个卡片中显示的内容。包含 header（(item) => ReactNode）和 sections（array）。 | - | - | 是 |
| cards_per_row | ReadonlyArray<CardsProps.CardsLayout> | 决定了任何容器宽度间隔内的每行卡片数量。包含 cards（每行卡片数）和 minWidth（容器最小宽度）。最大不超过20张/行。 | - | [{"cards":1},{"minWidth":768,"cards":2},{"minWidth":992,"cards":3},...] | 否 |
| class_name | string | 已废弃。 | - | - | 否 |
| entire_card_clickable | boolean | 激活此属性使整个卡片可点击以选择它。 | - | false | 否 |
| first_index | number | 第一个卡片的索引（基于1）。 | - | 1 | 否 |
| id | string | 已废弃。 | - | - | 否 |
| is_item_disabled | (item: T) => boolean | 确定哪些项目被禁用。 | - | - | 否 |
| items | ReadonlyArray<T> | 指定作为卡片数据源的项目。 | [] | - | 是 |
| loading | boolean | 以加载状态渲染卡片。 | - | false | 否 |
| loading_text | string | 指定在加载状态下显示的文本。 | - | - | 否 |
| selected_items | ReadonlyArray<T> | 指定选定项目的列表。 | - | - | 否 |
| selection_type | string | 指定选择模式。 | single / multi | - | 否 |
| sticky_header | boolean | 如果设置为true，则当用户向下滚动时，卡片头部保持可见。 | - | false | 否 |
| total_items_count | number | 卡片总数。 | - | - | 否 |
| track_by | CardsProps.TrackBy<T> | 指定items中的唯一标识它们的属性。 | - | - | 否 |
| variant | string | 指定卡片变体。 | container / full-page | 'container' | 否 |
| visible_sections | ReadonlyArray<string> | 指定包含每个可见部分的ID的数组。 | - | - | 否 |

## 插槽

| 名称 | 描述 |
|---|---|
| empty | 当项目列表为空时显示。 |
| filter | 使用此插槽向组件添加过滤控件。 |
| header | 表格容器的标题元素。 |
| pagination | 使用此插槽向组件添加分页组件。 |
| preferences | 使用此插槽向组件添加集合首选项。 |

## 使用示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "yaya_card": {
          "#type": "aws_cards",
          "#selected": [],
          "#card_definition": {
            "header": {"#type": "aws_link", "#content": "{item.name}"},
            "sections": [
              {"id": "description", "header": "Description", "content": "item.description"},
              {"id": "type", "header": "Type", "content": "item.type"},
              {"id": "size", "header": "Size", "content": "item.size"}
            ]
          },
          "#cards_per_row": [
            {"cards": 1},
            {"minWidth": 500, "cards": 2}
          ],
          "#items": [
            {"name": "Item 1", "alt": "First", "description": "This is the first item", "type": "1", "size": "Small"},
            {"name": "Item 2", "alt": "Second", "description": "This is the second item", "type": "2", "size": "Medium"}
          ],
          "#trackBy": "name",
          "#selection_type": "multi",
          "#pagination": {"#type": "aws_pagination"},
          "#filter": {
            "default": {"#type": "aws_text_filter"}
          }
        }
      }
    }
  }
}
```
