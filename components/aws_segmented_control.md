# aws_segmented_control

AWS 分段控件组件，用于在多个互斥选项之间进行切换。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 必需 |
|---|---|---|---|---|---|
| aria_labelledby | string | 将aria-labelledby添加到组件。 | - | - | 否 |
| class_name | string | 将指定的类添加到组件的根元素。已废弃。 | - | - | 否 |
| id | string | 将指定的ID添加到组件的根元素。已废弃。 | - | - | 否 |
| label | string | 定义整个分段控件的标签。 | - | - | 否 |
| options | ReadonlyArray<SegmentedControlProps.Option> | 表示选项的对象数组。每个段包含：id (string)、disabled (boolean, 可选)、disabledReason (string, 可选)、iconName (string, 可选)、iconAlt (string, 可选)、iconUrl (string, 可选)、iconSvg (ReactNode, 可选)、text (string, 可选)。 | - | - | 否 |
| default_value | null / string | 已选选项的ID。如果你想清除选择，请使用null。 | - | - | 是 |

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
          "#type": "aws_segmented_control",
          "#label": "Default segmented control",
          "#default_value": "option1",
          "#options": [
            {"text": "Option 1", "id": "option1"},
            {"text": "Option 2", "id": "option2"},
            {"text": "Option 3", "id": "option3"}
          ]
        }
      ]
    }
  }
}
```
