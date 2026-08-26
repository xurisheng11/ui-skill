# Aws Input Demo

## 基础示例

### 文本输入框

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

## 进阶示例

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

### 带状态管理的输入框

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#const_define": [
        {"value": "username", "set_value": "setUsername", "default": ""},
        {"value": "email", "set_value": "setEmail", "default": "user@example.com"}
      ],
      "#children": {
        "username_field": {
          "#type": "aws_form_field",
          "#label": "用户名",
          "#required": true,
          "#control": {
            "username_input": {
              "#type": "aws_input",
              "#placeholder": "请输入用户名",
              "#default_value": "${username}",
              "#auto_focus": true
            }
          }
        },
        "email_field": {
          "#type": "aws_form_field",
          "#label": "邮箱",
          "#control": {
            "email_input": {
              "#type": "aws_input",
              "#input_type": "email",
              "#placeholder": "请输入邮箱",
              "#default_value": "${email}",
              "#auto_complete": "email"
            }
          }
        }
      }
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
        {"value": "age", "set_value": "setAge", "default": 18}
      ],
      "#children": {
        "age_field": {
          "#type": "aws_form_field",
          "#label": "年龄",
          "#control": {
            "age_input": {
              "#type": "aws_input",
              "#input_type": "number",
              "#placeholder": "请输入年龄",
              "#default_value": "${age}",
              "#step": 1
            }
          }
        }
      }
    }
  }
}
```

### 搜索输入框

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "search_input": {
          "#type": "aws_input",
          "#input_type": "search",
          "#placeholder": "搜索...",
          "#input_mode": "search"
        }
      }
    }
  }
}
```

### 只读输入框

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "readonly_input": {
          "#type": "aws_input",
          "#placeholder": "只读输入框",
          "#default_value": "无法编辑的内容",
          "#read_only": true
        }
      }
    }
  }
}
```

### 禁用状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "disabled_input": {
          "#type": "aws_input",
          "#placeholder": "已禁用的输入框",
          "#default_value": "暂不可用",
          "#disabled": true
        }
      }
    }
  }
}
```
