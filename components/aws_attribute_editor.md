# aws_attribute_editor

AWS 属性编辑器组件，用于动态添加/删除/编辑键值对形式的属性列表。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 是否必需 | 可使用变量 | 使用方法 |
|---|---|---|---|---|---|---|---|
| add_button_text | string | 指定添加按钮上显示的文本。 | - | - | 是 | | |
| class_name | string | 将指定的类添加到组件的根元素。已废弃。 | - | - | 否 | | |
| definition | ReadonlyArray<AttributeEditorProps.FieldDefinition<T>> | 定义编辑器配置。数组中的每个对象代表行中的一个表单字段。包含：key（必填）、label、info、errorText、warningText、constraintText、control。最多支持四个字段（使用 grid_layout 时可超过）。 | - | - | 是 | | |
| grid_layout | ReadonlyArray<AttributeEditorProps.GridLayout> | 可选地指定属性的布局。包含 rows（行布局数组）、breakpoint（断点）、remove_button（移除按钮配置）。 | - | - | 否 | | |
| disable_add_button | boolean | 确定添加按钮是否禁用。 | - | false | 否 | | |
| i18n_strings | AttributeEditorProps.I18nStrings | 包含组件所需的所有必要本地化字符串的对象。 | - | - | 否 | | |
| id | string | 已废弃。为组件的根元素添加指定的 ID。 | - | - | 否 | | |
| is_item_removable | (item: T) => boolean | 决定项目是否可移除的函数。 | - | () => true | 否 | | |
| default_value | ReadonlyArray<T> | 指定作为所有行的数据源的项目。 | - | [] | 否 | | |
| remove_button_aria_label | (item: T) => string | 为移除按钮添加 `aria-label`。 | - | - | 否 | | |
| remove_button_text | string | 指定移除按钮上显示的文本。 | - | - | 否 | | |
| additional_info | - | 显示在添加按钮下方。用于与属性编辑器相关的附加信息。 | - | - | 否 | true | variable |
| empty | - | 当没有项目要显示时显示。 | - | - | 否 | true | variable |

**支持的子元素类型包括 aws_input、aws_toggle、aws_checkbox、aws_radio_group、aws_select、aws_multi_select、aws_date_input、aws_time_input**

## 使用示例

### 基础用法

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_attribute_editor",
          "#default_value": [{"name": "name1", "value": "value1"}],
          "#add_button_text": "添加",
          "#definition": [
            {"label": "Name", "key": "name", "control": {"#type": "aws_input"}},
            {"label": "Value", "key": "value", "control": {"#type": "aws_toggle"}}
          ]
        }
      ]
    }
  }
}
```

### 使用 grid_layout 设置宽度

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_attribute_editor",
          "#default_value": [{"input": "name1", "input2": "value1"}],
          "#add_button_text": "添加",
          "#grid_layout": [{"rows": [[1,1,2,2]]}],
          "#definition": [
            {"label": "input", "key": "input", "control": {"#type": "aws_input"}},
            {"label": "input2", "key": "input2", "control": {"#type": "aws_input"}},
            {"label": "input3", "key": "input3", "control": {"#type": "aws_input"}},
            {"label": "input4", "key": "input4", "control": {"#type": "aws_input"}}
          ]
        }
      ]
    }
  }
}
```
