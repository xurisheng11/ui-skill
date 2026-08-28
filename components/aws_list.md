# aws_list

AWS 列表组件，用于展示条目列表，支持可排序（拖放）功能。

## 参数说明

| 名称 | 类型 | 描述 | 接受值 | 默认值 | 是否必填 |
|---|---|---|---|---|---|
| aria_describedby | string | 为列表添加 aria-describedby 属性。 | - | - | 否 |
| aria_label | string | 为列表添加 aria-label 属性。 | - | - | 否 |
| aria_labelledby | string | 为列表添加 aria-labelledby 属性。 | - | - | 否 |
| disable_item_paddings | boolean | 移除列表项内部及周围的 padding。 | - | false | 否 |
| disable_paddings | boolean | 移除列表顶部和底部的 padding。不适用于可排序列表。 | - | false | 否 |
| i18n_strings | SortableAreaProps.DndAreaI18nStrings | 包含组件所需的所有本地化字符串的对象。 | - | - | 否 |
| items | ReadonlyArray<T> | 要在列表中显示的项目。 | - | - | **是** |
| render_item | (item: T) => {...} | 渲染一个项目。返回包含特定键的对象。 | - | - | **是** |
| sort_disabled | boolean | 禁用排序拖动操作手柄。 | - | false | 否 |
| sortable | boolean | 通过启用拖放功能使列表可排序。 | - | false | 否 |
| tag_override | string | 要渲染的 HTML 标签。 | ol / ul | - | 否 |

### render_item 返回值

| 名称 | 类型 | 描述 |
|---|---|---|
| id | string | 项目的唯一标识符。 |
| content | React.ReactNode | 项目的内容。 |
| secondary_content | React.ReactNode | (可选) 次要内容，例如项目描述。 |
| icon | React.ReactNode | (可选) 一个图标，显示在起始位置。 |
| action | React.ReactNode | (可选) 操作按钮。 |
| announcement_label | string | (可选) 项目的播报标签，用于排序时。 |

## 事件

| 名称 | 详情 | 描述 | 是否可取消 |
|---|---|---|---|
| on_sorting_change | ListProps.SortingState<T> { items: ReadonlyArray<T> } | 当在可排序列表中重新排序项目时调用。 | 否 |

## 使用示例

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
