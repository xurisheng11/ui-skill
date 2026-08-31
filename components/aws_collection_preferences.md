# aws_collection_preferences

AWS 集合首选项组件，用于配置表格/卡片的页面大小、可见列、换行等显示偏好。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 是否必需 |
|---|---|---|---|---|---|
| cancel_label | string | 模态框底部取消按钮的标签。 | - | - | 否 |
| class_name | string | 将指定的类添加到组件的根元素。已废弃。 | - | - | 否 |
| confirm_label | string | 模态框底部确认按钮的标签。 | - | - | 否 |
| content_density_preference | CollectionPreferencesProps.ContentDensityPreference | 配置内容密度偏好（舒适/紧凑）。包含 label 和 description。 | - | - | 否 |
| content_display_preference | CollectionPreferencesProps.ContentDisplayPreference | 配置内置的内容显示偏好，用于表列的顺序和可见性配置。不能与 visible_content_preference 同时使用。 | - | - | 否 |
| custom_preference | function | 配置自定义偏好。函数接收 customValue 和 setCustomValue 两个参数。 | - | - | 否 |
| disabled | boolean | 决定是否禁用偏好触发按钮。 | - | false | 否 |
| id | string | 将指定的ID添加到组件的根元素。已废弃。 | - | - | 否 |
| page_size_preference | CollectionPreferencesProps.PageSizePreference | 配置内置的"页面大小选择"偏好。包含 title 和 options。 | - | - | 否 |
| preferences | CollectionPreferencesProps.Preferences | 指定当前偏好值。包括 pageSize、wrapLines、contentDisplay 等。 | - | - | 否 |
| sticky_columns_preference | CollectionPreferencesProps.StickyColumnsPreference | 配置可针对左右列设置的粘滞列偏好。 | - | - | 否 |
| striped_rows_preference | CollectionPreferencesProps.StripedRowsPreference | 配置内置的"斑马行"偏好。包含 label 和 description。 | - | - | 否 |
| title | string | 指定偏好模态对话框的标题。 | - | - | 否 |
| visible_content_preference | CollectionPreferencesProps.VisibleContentPreference | 配置内置的卡片可见部分偏好或表格可见列偏好。推荐用于卡片，表格应使用 content_display_preference。不能与 content_display_preference 同时使用。 | - | - | 否 |
| wrap_lines_preference | CollectionPreferencesProps.WrapLinesPreference | 配置内置的"换行"偏好。包含 label 和 description。 | - | - | 否 |

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
          "#type": "aws_collection_preferences",
          "#default_value": {
            "pageSize": 10,
            "visibleContent": ["id", "domainName", "deliveryMethod"]
          },
          "#page_size_preference": {
            "options": [
              {"value": 10, "label": "10 resources"},
              {"value": 20, "label": "20 resources"}
            ]
          },
          "#visible_content_preference": {
            "title": "Select visible content",
            "options": [
              {
                "label": "Main distribution properties",
                "options": [
                  {"id": "id", "label": "Distribution ID", "editable": false},
                  {"id": "domainName", "label": "Domain name"},
                  {"id": "deliveryMethod", "label": "Delivery method"}
                ]
              }
            ]
          },
          "#custom_preference": {
            "cards": {
              "#type": "aws_radio_group",
              "#items": [
                {"value": "table", "label": "Table"},
                {"value": "cards", "label": "Cards"}
              ]
            }
          }
        }
      ]
    }
  }
}
```
