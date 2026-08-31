# aws_table

AWS 表格组件，用于展示结构化数据，支持排序、选择、过滤、分页、内联编辑等功能。

> **注意：**
> 1. table 中输入框类型的元素需要自定义 const 变量！请参考演示站点
> 2. table 条目中的按钮无法使用提交功能！

## 参数说明

| 名称 | 类型 | 描述 | 接受值 | 默认值 | 必需 |
|---|---|---|---|---|---|
| aria_labels | TableProps.AriaLabels | 为选择组件（复选框和单选按钮）指定替代文本。 | - | - | 否 |
| column_definitions | ReadonlyArray<TableProps.ColumnDefinition<T>> | 列配置对象，包括列的唯一标识符、列头显示、单元格内容显示、宽度等设置，还支持排序字段、自定义排序比较器等高级功能。 | - | - | 是 |
| content_density | string | 切换表格的内容密度。 | comfortable / compact | 'comfortable' | 否 |
| enable_keyboard_navigation | boolean | 激活高级键盘导航和聚焦行为。 | - | false | 否 |
| expandable_rows | TableProps.ExpandableRows | 使用此属性定义可扩展的表格行。 | - | - | 否 |
| first_index | number | 表格中第一个项目的索引（基于1）。 | - | 1 | 否 |
| is_item_disabled | (item: T) => boolean | 确定给定项目是否被禁用。 | - | - | 否 |
| items | ReadonlyArray<T> | 指定显示在表格行中的数据。 | - | [] | 是 |
| loading | boolean | 渲染表格处于加载状态。 | - | false | 否 |
| loading_text | string | 指定表格处于加载状态时显示的文本。 | - | - | 否 |
| resizable_columns | boolean | 指定是否可以调整列宽。 | - | false | 否 |
| selected | ReadonlyArray<T> | 默认选定项目的列表，使用时注意需指定 track_by。 | - | [] | 否 |
| selection_type | string | 指定选择类型，留空则没有选框。 | single / multi | - | 否 |
| sorting_column | TableProps.SortingColumn | 指定当前排序列的定义对象。 | - | - | 否 |
| sorting_descending | boolean | 指定是否使用降序排序。 | - | false | 否 |
| sticky_columns | TableProps.StickyColumns | 指定应该保持固定的第一列和/或最后列的数目。包含 first 和 last 属性。 | - | - | 否 |
| sticky_header | boolean | 如果设置为 true，当用户向下滚动时，表格标题保持可见。 | - | false | 否 |
| striped_rows | boolean | 指定表格行是否交替着色。 | - | false | 否 |
| submit_edit | function | 指定用户提交内联编辑后将调用的函数。 | - | - | 否 |
| total_items_count | number | 表格中所有项目的总数。 | - | - | 否 |
| track_by | TableProps.TrackBy<T> | 指定唯一标识单个项目的属性。 | - | - | 否 |
| wrap_lines | boolean | 指定表格单元格内的文本是否换行。 | - | false | 否 |
| items_per_page | number | 每页条数。 | - | 10 | 否 |
| ajax_url | string | 使用ajax模式时接口调用的链接。 | - | - | 否 |
| filter_columns | array | 限制使用前端搜索时被搜索的列。 | - | - | 否 |

## 插槽

| 名称 | 描述 |
|---|---|
| empty | 当 items 属性为空数组时显示。 |
| filter | 使用此插槽向表格添加过滤控件，可嵌套 aws_input、aws_date_input、aws_date_picker、aws_time_input、aws_autosuggest、aws_text_filter、aws_select。 |
| footer | 表格容器的页脚。 |
| header | 表格容器的标题元素。 |
| pagination | 使用此插槽向表格添加分页组件。仅支持一个分页组件。 |

## 可以使用的变量

| 名称 | 描述 |
|---|---|
| selected_{table_key} | 被选中的item，当且仅当存在单选/多选框时可用。 |
| filter_status_{table_key} | 是否存在搜索，为真时即存在搜索项。 |
| filter_total_{table_key} | 搜索结果的数量。 |
| total_pages_{table_key} | 总页码。 |
| page_{table_key} | 当前页码。 |
| init_items_{table_key} | table数据，仅适用于普通table。 |
| items_{table_key} | table当前显示数据。 |
| params_{table_key} | object，在ajax table中调用接口时传递给接口的参数。 |
| filter_value_{table_key}_{filter_key} | 搜索框的值。 |

## 可使用的方法

| 名称 | 描述 |
|---|---|
| set_init_items_{table_key}(array/object) | 修改table的数据，仅适用于普通table，修改后需调用 set_table_data_{table_key}() 更新显示。 |
| set_items_{table_key}(array/object) | 修改当前显示的table数据。 |
| set_table_data_{table_key}(array/object) | 更新table当前的显示。 |
| set_selected_{table_key}(array/object) | 修改table选中项，注意使用此功能必须设置track_by属性。 |
| set_params_{table_key}(object) | 修改传递给接口的参数。 |

## 使用示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "example_table": {
          "#type": "aws_table",
          "#sticky_columns": {"first": 1},
          "#selection_type": "single",
          "#header": {"#type": "aws_header", "#title": "表格"},
          "#items": [
            {"name": "Item 1", "alt": "First", "description": "This is the first item", "type": "1", "size": "Small"},
            {"name": "Item 2", "alt": "Second", "description": "This is the second item", "type": "2", "size": "Medium"}
          ],
          "#selected": [],
          "#track_by": "name",
          "#column_definitions": [
            {
              "id": "variable",
              "header": "Variable name",
              "cell": {
                "#type": "aws_link",
                "#content": "{item.name}",
                "#href": {"#markup": "`/a/b/${item.name}`"}
              },
              "sortingField": "name",
              "isRowHeader": true
            },
            {"id": "alt", "header": "Alt text", "cell": "item.alt", "sortingField": "alt"},
            {"id": "description", "header": "Description", "cell": "item.description"},
            {"id": "type", "header": "Type", "cell": "item.type"},
            {"id": "size", "header": "Size", "cell": "item.size"}
          ],
          "#pagination": {"#type": "aws_pagination"},
          "#filter": {
            "default": {
              "#type": "aws_text_filter",
              "#filtering_placeholder": "按关键字搜索",
              "#count_text": {"#markup": "filter_status_example_table?filter_total_example_table+' 匹配项':''"}
            }
          }
        }
      }
    }
  }
}
```
