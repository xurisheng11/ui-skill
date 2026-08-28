# aws_token_group

令牌组组件，用于显示和管理令牌标签。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 数组 | 否 | 令牌数组 |
| alignment | 字符串 | 否 | 对齐方向 |
| limit | 数字 | 否 | 最大显示数 |
| read_only | 布尔值 | 否 | 只读状态 |
| disable_outer_padding | 布尔值 | 否 | 移除外部填充 |

### alignment 可选值

- `horizontal` - 水平对齐（默认）
- `vertical` - 垂直对齐

### default_value 项结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| label | 字符串 | 令牌标题 |
| description | 字符串 | 标签下方信息 |
| disabled | 布尔值 | 是否禁用 |
| label_tag | 字符串 | 标签旁边指导 |
| tags | 数组 | 指导标签列表 |
| dismiss_label | 字符串 | 移除按钮aria-label |
| icon_name | 字符串 | 图标名称 |

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
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "标签 1", "dismissLabel": "移除标签 1" },
            { "label": "标签 2", "dismissLabel": "移除标签 2" },
            { "label": "标签 3", "dismissLabel": "移除标签 3" }
          ]
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
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "重要", "description": "优先级高", "dismissLabel": "移除" },
            { "label": "紧急", "description": "需要立即处理", "dismissLabel": "移除" },
            { "label": "新功能", "description": "新添加的功能", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 带标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "文档", "label_tag": "新", "dismissLabel": "移除" },
            { "label": "教程", "label_tag": "热门", "dismissLabel": "移除" },
            { "label": "API", "label_tag": "官方", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 带图标

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "文件夹", "icon_name": "folder", "dismissLabel": "移除" },
            { "label": "文件", "icon_name": "file", "dismissLabel": "移除" },
            { "label": "图片", "icon_name": "file-open", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 带多个标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "项目A", "tags": ["重要", "进行中"], "dismissLabel": "移除" },
            { "label": "项目B", "tags": ["已完成"], "dismissLabel": "移除" },
            { "label": "项目C", "tags": ["待审核", "紧急"], "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 禁用令牌

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "可编辑", "dismissLabel": "移除" },
            { "label": "已禁用", "disabled": true },
            { "label": "另一个可编辑", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 限制显示数量

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#limit": 2,
          "#default_value": [
            { "label": "标签 1", "dismissLabel": "移除" },
            { "label": "标签 2", "dismissLabel": "移除" },
            { "label": "标签 3", "dismissLabel": "移除" },
            { "label": "标签 4", "dismissLabel": "移除" },
            { "label": "标签 5", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 只读状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#read_only": true,
          "#default_value": [
            { "label": "只读标签 1" },
            { "label": "只读标签 2" },
            { "label": "只读标签 3" }
          ]
        }
      ]
    }
  }
}
```

### 垂直对齐

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#alignment": "vertical",
          "#default_value": [
            { "label": "垂直标签 1", "dismissLabel": "移除" },
            { "label": "垂直标签 2", "dismissLabel": "移除" },
            { "label": "垂直标签 3", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 无外部填充

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#disable_outer_padding": true,
          "#default_value": [
            { "label": "标签 1", "dismissLabel": "移除" },
            { "label": "标签 2", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 技术标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "JavaScript", "icon_name": "code", "dismissLabel": "移除" },
            { "label": "Python", "icon_name": "code", "dismissLabel": "移除" },
            { "label": "React", "icon_name": "external", "dismissLabel": "移除" },
            { "label": "Node.js", "icon_name": "external", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 分类标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "电子产品", "label_tag": "类别" },
            { "label": "服装", "label_tag": "类别" },
            { "label": "食品", "label_tag": "类别" },
            { "label": "图书", "label_tag": "类别" }
          ]
        }
      ]
    }
  }
}
```

### 状态标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_token_group",
          "#default_value": [
            { "label": "待处理", "tags": ["重要"] },
            { "label": "进行中", "tags": ["进行"] },
            { "label": "已完成", "tags": ["完成"] },
            { "label": "已取消", "tags": ["无效"] }
          ]
        }
      ]
    }
  }
}
```
