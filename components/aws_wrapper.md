# aws_wrapper

**所有 AWS 组件必须包裹在 `[[aws_wrapper]]` 组件中使用，且 aws_wrapper 仅需在最外层使用一次，不允许在 aws_wrapper 中嵌套 aws_wrapper。**

## 参数说明

| 参数 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| `#type` | string | 是 | 固定为 `aws_wrapper` |
| `#children` | object/array | 是 | AWS 组件合集 |
| `#const_define` | array | 否 | 定义变量，包含 value, set_value, default |
| `#functions` | array | 否 | 定义 JS 方法 |

## const_define 参数说明

| 参数 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| value | string | 是 | 变量名 |
| set_value | string | 是 | 修改变量的方法名 |
| default | any | 否 | 默认值，未设置默认为 null |

## 使用示例

### 基础用法

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "input": {
          "#type": "aws_input",
          "#placeholder": "请输入",
          "#class_name": "aws_input111 222",
          "#default_value": "afdsafweaefa"
        }
      }
    }
  }
}
```

### 带变量定义

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#const_define": [
        {"value": "inputValue", "set_value": "setInputValue", "default": ""}
      ],
      "#children": {
        "input": {
          "#type": "aws_input",
          "#placeholder": "请输入",
          "#default_value": "${inputValue}"
        }
      }
    }
  }
}
```

### 多个组件

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_header",
          "#header_text": "标题"
        },
        {
          "#type": "aws_input",
          "#placeholder": "请输入名称"
        },
        {
          "#type": "aws_button",
          "#text": "提交",
          "#variant": "primary"
        }
      ]
    }
  }
}
```

## 注意事项

1. `children` 是组件的集合或数组
2. 即使 `children` 内只有一个组件，也必须为 `"#children": {"key": {"#type": "组件名"}}` 或 `"#children": [{"#type": "组件名"}]`
3. **不能**直接写入组件本身，例如 `"#children": {"#type": "组件名"}` 是错误的
