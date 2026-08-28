# aws_header

头部组件，用于页面或容器的标题。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可选值 |
| --- | --- | --- | --- | --- |
| variant | 字符串 | 否 | 头部变体 | h1, h2, h3, awsui-h1-sticky |
| heading_tag_override | 字符串 | 否 | 覆盖默认HTML标题标签 | h1-h5 |
| counter | 字符串 | 否 | 标题右侧的次要文本（如计数器） | - |
| class_name | 字符串 | 否 | 添加到根元素的类名（已弃用） | - |
| id | 字符串 | 否 | 添加到根元素的ID（已弃用） | - |

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| title (默认) | 标题文本 | 是 | {variable} |
| description | 标题下方的补充文本 | 是 | variable |
| actions | 容器动作区域（按钮、链接等） | 是 | variable |
| info | 标题旁边的信息链接区域 | 是 | variable |
| counter | 次要文本显示区域 | 是 | variable |

## 使用示例

### 页面标题 (h1)

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
          "#variant": "h1",
          "#title": "仪表盘总览"
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
          "#type": "aws_header",
          "#title": "用户管理",
          "#counter": "(128)",
          "#actions": {
            "#type": "aws_button",
            "#text": "新建用户"
          }
        }
      ]
    }
  }
}
```

### 带描述

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
          "#title": "系统设置",
          "#description": "配置应用程序的各种选项和参数",
          "#actions": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "btn1": {
                "#type": "aws_button",
                "#text": "保存"
              },
              "btn2": {
                "#type": "aws_button",
                "#text": "重置",
                "#variant": "normal"
              }
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
          "#type": "aws_header",
          "#title": "数据报表",
          "#info": "查看报表使用帮助",
          "#counter": "(45)",
          "#actions": {
            "#type": "aws_button",
            "#text": "导出"
          }
        }
      ]
    }
  }
}
```

### 容器标题 (h2)

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
          "#variant": "h2",
          "#title": "基本信息"
        }
      ]
    }
  }
}
```

### 部分标题 (h3)

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
          "#variant": "h3",
          "#title": "联系方式"
        }
      ]
    }
  }
}
```

### 粘性标题

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
          "#variant": "awsui-h1-sticky",
          "#title": "卡片标题",
          "#actions": {
            "#type": "aws_icon",
            "#name": "settings"
          }
        }
      ]
    }
  }
}
```

### 复杂页面头部

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
          "#variant": "h1",
          "#title": "项目管理",
          "#description": "管理您的项目、团队成员和资源分配",
          "#counter": "(12个项目)",
          "#info": {
            "#type": "aws_link",
            "#content": "了解更多",
            "#variant": "info"
          },
          "#actions": {
            "#type": "aws_space_between",
            "#direction": "horizontal",
            "#size": "s",
            "#content": {
              "btn1": {
                "#type": "aws_button",
                "#text": "新建项目"
              },
              "btn2": {
                "#type": "aws_button",
                "#text": "导入"
              }
            }
          }
        }
      ]
    }
  }
}
```
