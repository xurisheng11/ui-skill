# aws_input

AWS 输入框组件，用于创建输入字段，支持文本、密码、数字等多种类型。

## 参数说明

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| placeholder | 字符串 | 否 | 占位符文本 | - | - |
| input_type | 字符串 | 否 | 控件类型 | text / password / search / number / email / url | 'text' |
| default_value | 字符串 | 否 | 输入框默认值 | - | - |
| disabled | 布尔值 | 否 | 是否禁用控件 | - | false |
| read_only | 布尔值 | 否 | 是否只读 | - | false |
| invalid | 布尔值 | 否 | 是否处于无效状态 | - | false |
| name | 字符串 | 否 | 表单控件名称 | - | - |
| auto_complete | 布尔值/字符串 | 否 | 浏览器自动填充 | - | true |
| auto_focus | 布尔值 | 否 | 页面加载时获得焦点 | - | false |
| input_mode | 字符串 | 否 | 输入模式提示 | none / text / decimal / numeric / tel / search / email / url | - |
| spellcheck | 布尔值 | 否 | 拼写检查 | - | false |
| step | 数值 | 否 | 数值粒度 | number / any | - |
| aria_label | 字符串 | 否 | 无障碍标签 | - | - |
| aria_required | 布尔值 | 否 | 无障碍必填标识 | - | false |

## 变量

| 变量 | 描述 |
| --- | --- |
| value_{input_key} | 输入框中的值 |

## 方法

| 方法 | 描述 |
| --- | --- |
| setValue_{input_key} | 设置输入框的值 |

## 事件

| 名称 | 描述 |
| --- | --- |
| on_blur | 当输入焦点从控件移除时触发 |
| on_change | 当用户更改输入值时触发，detail.value 获取具体值 |

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
        "example_input": {
          "#type": "aws_input",
          "#placeholder": "请输入",
          "#default_value": "afdsafweaefa"
        }
      }
    }
  }
}
```

### 密码输入框（带显示/隐藏功能）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_form_field",
          "#description": "请输入密码",
          "#label": "密码",
          "#required": true,
          "#constraint_text": "密码长度不少于6位",
          "#attached": {"library": ["ui_common/password"]},
          "#class_name": "view-password",
          "#control": {
            "password_input": {
              "#type": "aws_input",
              "#input_type": "password"
            }
          }
        }
      ]
    }
  }
}
```

### 数字输入框

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#const_define": [
        {"value": "quantity", "set_value": "setQuantity", "default": 1}
      ],
      "#children": {
        "quantity_input": {
          "#type": "aws_input",
          "#input_type": "number",
          "#placeholder": "数量",
          "#default_value": "${quantity}",
          "#step": 1
        }
      }
    }
  }
}
```

### 带验证的表单字段

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "email_field": {
          "#type": "aws_form_field",
          "#label": "邮箱地址",
          "#required": true,
          "#constraint_text": "请输入有效的邮箱地址",
          "#control": {
            "email_input": {
              "#type": "aws_input",
              "#input_type": "email",
              "#placeholder": "example@example.com",
              "#auto_complete": "email"
            }
          }
        }
      }
    }
  }
}
```
