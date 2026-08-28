# aws_text_filter

AWS 文本过滤组件，用于对集合（表格、卡片等）内容进行文本搜索过滤。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 是否必需 | 可使用变量 | 使用方法 |
|---|---|---|---|---|---|---|---|
| aria_describedby | string | 为组件添加 `aria-describedby` 属性。 | - | - | 否 | | |
| aria_labelledby | string | 为组件添加 `aria-labelledby` 属性。 | - | - | 否 | | |
| class_name | string | 将指定的类添加到组件的根元素。已废弃。 | - | - | 否 | | |
| control_id | string | 指定原生表单元素的 ID。 | - | - | 否 | | |
| count_text | string | 接受一个可读的、本地化的字符串，表示结果的数量。例如，"1 match" 或 "165 matches"。计数文本仅在过滤文本不为空时显示。 | - | - | 否 | true | variable |
| disable_browser_autocorrect | boolean | 指定是否禁用浏览器自动纠正和相关功能。 | - | false | 否 | | |
| disabled | boolean | 指定过滤输入是否禁用。 | - | false | 否 | | |
| filtering_aria_label | string | 在过滤输入上添加 `aria-label`。 | - | - | 否 | | |
| filtering_clear_aria_label | string | 过滤输入清除按钮的标签。 | - | - | 否 | | |
| filtering_placeholder | string | 过滤输入的占位符。 | - | - | 否 | | |
| default_value | string | 过滤输入的当前值。 | - | - | 是 | | |
| id | string | 已废弃。为组件的根元素添加指定的 ID。 | - | - | 否 | | |
| loading | boolean | 在相关集合加载时设置为 true。 | - | false | 否 | | |

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
          "#type": "aws_text_filter",
          "#count_text": "18 matches"
        }
      ]
    }
  }
}
```
