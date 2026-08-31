# Aws Wrapper Demo

## 概述

`aws_wrapper` 是所有 AWS 组件的容器组件。所有 AWS 组件必须包裹在 `aws_wrapper` 中使用。

## 基础示例

### 单个输入框

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

### 带变量定义和状态管理

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#const_define": [
        {"value": "username", "set_value": "setUsername", "default": ""},
        {"value": "password", "set_value": "setPassword", "default": ""}
      ],
      "#children": {
        "form": {
          "#type": "aws_container",
          "#header": "登录表单",
          "#children": {
            "usernameInput": {
              "#type": "aws_input",
              "#label": "用户名",
              "#placeholder": "请输入用户名",
              "#default_value": "${username}"
            },
            "passwordInput": {
              "#type": "aws_input",
              "#label": "密码",
              "#type": "password",
              "#placeholder": "请输入密码",
              "#default_value": "${password}"
            }
          }
        }
      }
    }
  }
}
```

### 多个组件组合

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
          "#header_text": "用户管理"
        },
        {
          "#type": "aws_box",
          "#padding": "m",
          "#children": {
            "table": {
              "#type": "aws_table",
              "#columns": ["姓名", "邮箱", "状态"],
              "#data": [
                ["张三", "zhangsan@example.com", "活跃"],
                ["李四", "lisi@example.com", "停用"]
              ]
            }
          }
        },
        {
          "#type": "aws_space_between",
          "#direction": "horizontal",
          "#children": [
            {
              "#type": "aws_button",
              "#text": "取消",
              "#variant": "link"
            },
            {
              "#type": "aws_button",
              "#text": "提交",
              "#variant": "primary"
            }
          ]
        }
      ]
    }
  }
}
```
