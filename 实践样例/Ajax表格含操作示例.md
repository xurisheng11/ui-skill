# Ajax 表格含操作示例

使用 ajax_url 异步加载数据的复杂表格，含多选、过滤、分页和操作按钮。

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
          "#ajax_url": "http://172.19.70.82:8084/ajax-callback/table",
          "#selection_type": "multi",
          "#header": {
            "#type": "aws_header",
            "#title": "复杂搜索",
            "#actions": {
              "#type": "aws_space_between",
              "#size": "xs",
              "#direction": "horizontal",
              "#content": {
                "button1": {"#type": "aws_button", "#text": "button1"},
                "button2": {
                  "#type": "aws_button",
                  "#text": "button2",
                  "#disabled": {"#markup": "selected_example_table.length === 0"}
                },
                "button_dropdown": {
                  "#type": "aws_button_dropdown",
                  "#text": "Short",
                  "#items": [
                    {"text": "Delete", "id": "rm", "disabled": false},
                    {"text": "Move", "id": "mv", "disabled": false},
                    {
                      "text": "Rename",
                      "id": "rn",
                      "disabled": {"#markup": "selected_example_table.length < 2"}
                    },
                    {
                      "id": "view",
                      "text": "View metrics",
                      "href": "https://example.com",
                      "external": true
                    }
                  ]
                }
              }
            }
          },
          "#sorting_column": {"sortingField": "alt"},
          "#sorting_descending": false,
          "#column_definitions": [
            {"id": "variable", "header": "Variable name", "cell": "item.name", "sortingField": "name", "isRowHeader": true},
            {"id": "alt", "header": "Alt text", "cell": "item.alt", "sortingField": "alt"},
            {"id": "description", "header": "Description", "cell": "item.description"},
            {"id": "type", "header": "Type", "cell": "item.type"},
            {"id": "size", "header": "Size", "cell": "item.size"}
          ],
          "#pagination": {"#type": "aws_pagination"},
          "#filter": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "xs",
            "#align_items": "center",
            "#content": {
              "default": {
                "#type": "aws_text_filter",
                "#filtering_placeholder": "按关键字搜索"
              },
              "input": {"#type": "aws_input"},
              "select": {
                "#type": "aws_select",
                "#placeholder": "请选择",
                "#select_options": [
                  {"label": "全部", "value": "-all-"},
                  {"label": "Small", "value": "1"},
                  {"label": "Medium", "value": "2"},
                  {"label": "Large", "value": "3"},
                  {"label": "Extra Large", "value": "4"}
                ]
              },
              "autosuggest": {
                "#type": "aws_autosuggest",
                "#default_value": "",
                "#suggest_options": [
                  {"value": "Item 1"},
                  {"value": "Small"},
                  {"value": "1"},
                  {"value": "2"}
                ]
              },
              "result": {
                "#type": "aws_box",
                "#content": {
                  "#markup": "{filter_status_example_table?filter_total_example_table+' 条记录':''}"
                }
              }
            }
          }
        }
      }
    }
  }
}
```
