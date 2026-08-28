# aws_tabs

选项卡组件，用于切换不同内容面板。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 字符串 | 否 | 当前激活选项卡的id |
| tabs | 数组 | 是 | 选项卡数组 |
| variant | 字符串 | 否 | 选项卡变体 |
| disable_content_paddings | 布尔值 | 否 | 移除内容填充 |
| fit_height | 布尔值 | 否 | 适应高度 |

### variant 可选值

- `default` - 默认样式
- `container` - 容器内使用
- `stacked` - 堆叠容器

### 变量和方法

| 名称 | 描述 |
| --- | --- |
| value_{tab_key} | 当前打开tab的id |
| setValue_{tab_key}(tab_id) | 设置切换到某个tab |

### tabs 项结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| id | 字符串 | 选项卡标识符 |
| label | 组件/字符串 | 选项卡标签 |
| content | 组件 | 选项卡内容 |
| disabled | 布尔值 | 是否禁用 |
| disabled_reason | 字符串 | 禁用原因 |
| dismissible | 布尔值 | 是否可关闭 |
| dismiss_label | 字符串 | 关闭按钮aria-label |
| action | 组件 | 选项卡操作 |
| on_dismiss | 函数 | 关闭回调 |
| href | 字符串 | 链接地址 |

**注意**：若在tabs中嵌套luban_form组件，不可使用布局-区块中的use ajax选项，且luban_form的返回值中不可包含aws_wrapper包装器。

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
          "#type": "aws_tabs",
          "#default_value": "first",
          "#tabs": [
            {
              "label": "第一个标签",
              "id": "first",
              "content": "第一个标签页的内容区域。"
            },
            {
              "label": "第二个标签",
              "id": "second",
              "content": "第二个标签页的内容区域。"
            },
            {
              "label": "第三个标签",
              "id": "third",
              "content": "第三个标签页的内容区域。",
              "disabled": true
            }
          ]
        }
      ]
    }
  }
}
```

### 带表单内容

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#default_value": "form",
          "#tabs": [
            {
              "label": "基本信息",
              "id": "basic",
              "content": {
                "formfield": {
                  "#type": "aws_form_field",
                  "#description": "请填写基本信息",
                  "#label": "姓名",
                  "#control": {
                    "name": {
                      "#type": "aws_input"
                    }
                  }
                }
              }
            },
            {
              "label": "联系方式",
              "id": "contact",
              "content": {
                "formfield": {
                  "#type": "aws_form_field",
                  "#label": "邮箱",
                  "#control": {
                    "email": {
                      "#type": "aws_input"
                    }
                  }
                }
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 容器变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#variant": "container",
          "#default_value": "tab1",
          "#tabs": [
            {
              "label": "面板1",
              "id": "tab1",
              "content": "面板1的内容"
            },
            {
              "label": "面板2",
              "id": "tab2",
              "content": "面板2的内容"
            }
          ]
        }
      ]
    }
  }
}
```

### 堆叠变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#variant": "stacked",
          "#tabs": [
            {
              "label": "设置1",
              "id": "settings1",
              "content": "设置1的内容"
            },
            {
              "label": "设置2",
              "id": "settings2",
              "content": "设置2的内容"
            }
          ]
        }
      ]
    }
  }
}
```

### 带操作按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            {
              "label": "数据",
              "id": "data",
              "content": "数据内容",
              "action": {
                "#type": "aws_button",
                "#text": "刷新"
              }
            },
            {
              "label": "配置",
              "id": "config",
              "content": "配置内容",
              "action": {
                "#type": "aws_button",
                "#text": "保存"
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 可关闭标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            {
              "label": "文件1",
              "id": "file1",
              "content": "文件1内容",
              "dismissible": true,
              "dismiss_label": "关闭文件1"
            },
            {
              "label": "文件2",
              "id": "file2",
              "content": "文件2内容",
              "dismissible": true,
              "dismiss_label": "关闭文件2"
            },
            {
              "label": "固定面板",
              "id": "fixed",
              "content": "此面板不能关闭"
            }
          ]
        }
      ]
    }
  }
}
```

### 禁用标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            {
              "label": "可用",
              "id": "available",
              "content": "可用内容"
            },
            {
              "label": "禁用",
              "id": "disabled",
              "content": "禁用内容",
              "disabled": true,
              "disabled_reason": "此功能正在维护中"
            },
            {
              "label": "另一个可用",
              "id": "another",
              "content": "另一个可用内容"
            }
          ]
        }
      ]
    }
  }
}
```

### 多内容面板

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#default_value": "overview",
          "#tabs": [
            {
              "label": "概览",
              "id": "overview",
              "content": {
                "#type": "aws_key_value_pairs",
                "#items": [
                  { "label": "总用户", "value": "1,234" },
                  { "label": "活跃用户", "value": "856" },
                  { "label": "总订单", "value": "5,678" }
                ]
              }
            },
            {
              "label": "用户",
              "id": "users",
              "content": "用户列表..."
            },
            {
              "label": "订单",
              "id": "orders",
              "content": "订单列表..."
            },
            {
              "label": "设置",
              "id": "settings",
              "content": "系统设置..."
            }
          ]
        }
      ]
    }
  }
}
```

### 带链接的标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#tabs": [
            {
              "label": "首页",
              "id": "home",
              "content": "首页内容",
              "href": "/home"
            },
            {
              "label": "产品",
              "id": "products",
              "content": "产品列表",
              "href": "/products"
            },
            {
              "label": "关于",
              "id": "about",
              "content": "关于页面"
            }
          ]
        }
      ]
    }
  }
}
```

### 无内容填充

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#disable_content_paddings": true,
          "#tabs": [
            {
              "label": "标签1",
              "id": "tab1",
              "content": "无边距的内容"
            },
            {
              "label": "标签2",
              "id": "tab2",
              "content": "无边距的内容2"
            }
          ]
        }
      ]
    }
  }
}
```

### 适应高度

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tabs",
          "#fit_height": true,
          "#tabs": [
            {
              "label": "面板1",
              "id": "panel1",
              "content": "适应高度的面板内容"
            },
            {
              "label": "面板2",
              "id": "panel2",
              "content": "另一个适应高度的面板"
            }
          ]
        }
      ]
    }
  }
}
```
