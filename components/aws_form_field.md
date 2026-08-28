# aws_form_field

表单字段组件，用于包装表单控件并提供标签、描述、错误提示等功能。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| control_id | 字符串 | 否 | 主表单控件的ID，用于关联标签 |
| stretch | 布尔值 | 否 | 控件是否扩展到12列 |

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| label | 表单字段的主要标签 | 是 | variable |
| description | 标签下方显示的详细信息 | 是 | variable |
| info | 标签旁边显示"信息"链接 | 是 | variable |
| control (默认) | 主表单控件 | 是 | {variable} |
| secondary_control | 次级控件（如按钮） | 是 | variable |
| constraint_text | 控件下方的约束文本 | 是 | variable |
| error_text | 验证错误消息 | 是 | variable |
| warning_text | 验证警告消息 | 是 | variable |

### 表单校验属性

| 属性名 | 类型 | 描述 | 默认值 |
| --- | --- | --- | --- |
| required | 布尔值 | 是否必填 | false |
| require_err | 字符串 | 必填错误提示 | "请填写此字段。" |
| pattern | 字符串 | 正则表达式（需二次转义） | - |
| pattern_err | 字符串 | 正则校验错误提示 | - |

### 支持校验的组件

`aws_input`, `aws_date_input`, `aws_date_picker`, `aws_checkbox`, `aws_radio_group`, `aws_slider`, `aws_text_area`, `aws_tiles`, `aws_time_input`, `aws_autosuggest`, `aws_text_filter`, `aws_select`, `aws_multi_select`

**注意**：选框类型组件仅支持 required 校验，不支持 pattern 校验。

### 变量和方法（校验时）

| 名称 | 描述 |
| --- | --- |
| errorText_{input_key} | 显示的错误文本 |
| setErrorText_{input_key}() | 设置错误文本 |

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
          "#type": "aws_form_field",
          "#label": "用户名",
          "#description": "请输入您的用户名",
          "#constraint_text": "用户名长度为4-20个字符",
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

### 带信息链接

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
          "#info": {
            "#type": "aws_link",
            "#content": "什么是企业邮箱？",
            "#variant": "info"
          },
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

### 必填字段

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
          "#required": true,
          "#constraint_text": "密码至少8位，包含数字和字母",
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

### 带次级控件（按钮）

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
          "#required": true,
          "#secondary_control": {
            "#type": "aws_button",
            "#text": "获取验证码"
          },
          "#control": {
            "verify_code": {
              "#type": "aws_input"
            }
          }
        }
      ]
    }
  }
}
```

### 正则校验（文本域）

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

### 错误状态

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

### 警告状态

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
          "#warning_text": "用户名包含特殊字符，建议修改",
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

### 完整表单示例

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
            "department": {
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

### stretch 模式

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
          "#label": "搜索内容",
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
