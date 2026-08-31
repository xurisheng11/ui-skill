# aws_form_field 示例

本文档展示 aws_form_field 组件的各种使用场景。

## 示例列表

### 1. 基础表单字段

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
          "#label": "用户名",
          "#control": {
            "input": {
              "#type": "aws_input"
            }
          }
        }
      ]
    }
  }
}
```

### 2. 带描述和约束

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
          "#description": "用于登录的唯一标识",
          "#label": "用户名",
          "#constraint_text": "4-20个字符，仅限字母和数字",
          "#control": {
            "username": {
              "#type": "aws_input"
            }
          }
        }
      ]
    }
  }
}
```

### 3. 必填字段

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
          "#label": "邮箱地址",
          "#required": true,
          "#control": {
            "email": {
              "#type": "aws_input"
            }
          }
        }
      ]
    }
  }
}
```

### 4. 带信息链接

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
          "#label": "密码",
          "#info": {
            "#type": "aws_link",
            "#content": "密码规则",
            "#variant": "info"
          },
          "#control": {
            "password": {
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

### 5. 带次级控件

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
          "#label": "验证码",
          "#secondary_control": {
            "#type": "aws_button",
            "#text": "获取验证码"
          },
          "#control": {
            "code": {
              "#type": "aws_input"
            }
          }
        }
      ]
    }
  }
}
```

### 6. 错误状态

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
          "#label": "邮箱",
          "#error_text": "请输入有效的邮箱地址",
          "#control": {
            "email": {
              "#type": "aws_input"
            }
          }
        }
      ]
    }
  }
}
```

### 7. 警告状态

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
          "#label": "用户名",
          "#warning_text": "用户名可能已被占用",
          "#control": {
            "username": {
              "#type": "aws_input"
            }
          }
        }
      ]
    }
  }
}
```

### 8. 正则校验

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
          "#label": "备注",
          "#required": true,
          "#pattern": "^[\\s\\S]{0,255}$",
          "#constraint_text": "最多255个字符",
          "#control": {
            "remark": {
              "#type": "aws_text_area"
            }
          }
        }
      ]
    }
  }
}
```

### 9. stretch 模式

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
          "#stretch": true,
          "#label": "搜索",
          "#secondary_control": {
            "#type": "aws_button",
            "#text": "搜索"
          },
          "#control": {
            "search": {
              "#type": "aws_input"
            }
          }
        }
      ]
    }
  }
}
```

### 10. 下拉选择

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
          "#label": "国家",
          "#control": {
            "country": {
              "#type": "aws_select",
              "#select_options": [
                { "label": "中国", "value": "cn" },
                { "label": "美国", "value": "us" },
                { "label": "日本", "value": "jp" }
              ]
            }
          }
        }
      ]
    }
  }
}
```

### 11. 多选

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
          "#label": "标签",
          "#control": {
            "tags": {
              "#type": "aws_multi_select",
              "#select_options": [
                { "label": "重要", "value": "important" },
                { "label": "紧急", "value": "urgent" },
                { "label": "新功能", "value": "new" }
              ]
            }
          }
        }
      ]
    }
  }
}
```

### 12. 日期选择

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
          "#label": "出生日期",
          "#control": {
            "birthday": {
              "#type": "aws_date_picker"
            }
          }
        }
      ]
    }
  }
}
```

### 13. 单选组

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
          "#label": "支付方式",
          "#control": {
            "payment": {
              "#type": "aws_radio_group",
              "#items": [
                { "value": "alipay", "label": "支付宝" },
                { "value": "wechat", "label": "微信支付" },
                { "value": "card", "label": "银行卡" }
              ]
            }
          }
        }
      ]
    }
  }
}
```

### 14. 滑块

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
          "#label": "音量",
          "#control": {
            "volume": {
              "#type": "aws_slider",
              "#max": 100,
              "#min": 0
            }
          }
        }
      ]
    }
  }
}
```

### 15. 完整注册表单

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
          "#label": "姓名",
          "#required": true,
          "#control": {
            "name": {
              "#type": "aws_input"
            }
          }
        },
        {
          "#type": "aws_form_field",
          "#label": "邮箱",
          "#required": true,
          "#constraint_text": "请输入有效的企业邮箱",
          "#control": {
            "email": {
              "#type": "aws_input"
            }
          }
        },
        {
          "#type": "aws_form_field",
          "#label": "部门",
          "#control": {
            "dept": {
              "#type": "aws_select",
              "#select_options": [
                { "label": "技术部", "value": "tech" },
                { "label": "市场部", "value": "marketing" },
                { "label": "财务部", "value": "finance" }
              ]
            }
          }
        },
        {
          "#type": "aws_form_field",
          "#label": "备注",
          "#control": {
            "note": {
              "#type": "aws_text_area",
              "#rows": 4
            }
          }
        }
      ]
    }
  }
}
```
