# aws_token_group 示例

本文档展示 aws_token_group 组件的各种使用场景。

## 示例列表

### 1. 基础用法

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
            { "label": "标签 1", "dismissLabel": "移除" },
            { "label": "标签 2", "dismissLabel": "移除" },
            { "label": "标签 3", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 2. 带描述

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
            { "label": "紧急", "description": "需要立即处理", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 3. 带标签

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
            { "label": "教程", "label_tag": "热门", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 4. 带图标

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
            { "label": "文件", "icon_name": "file", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 5. 限制显示数量

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
            { "label": "标签 3", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 6. 只读状态

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

### 7. 垂直对齐

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
            { "label": "垂直标签 2", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 8. 技术标签

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
            { "label": "React", "icon_name": "external", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 9. 状态标签

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
            { "label": "已完成", "tags": ["完成"] }
          ]
        }
      ]
    }
  }
}
```

### 10. 项目标签

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
            { "label": "项目B", "tags": ["已完成"], "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 11. 禁用令牌

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

### 12. 无外部填充

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

### 13. 分类标签

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
            { "label": "食品", "label_tag": "类别" }
          ]
        }
      ]
    }
  }
}
```

### 14. 筛选标签

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
            { "label": "已选中", "dismissLabel": "取消筛选" },
            { "label": "标签2", "dismissLabel": "移除" },
            { "label": "标签3", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```

### 15. 成员标签

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
            { "label": "张三", "icon_name": "user-profile", "dismissLabel": "移除" },
            { "label": "李四", "icon_name": "user-profile", "dismissLabel": "移除" },
            { "label": "王五", "icon_name": "user-profile", "dismissLabel": "移除" }
          ]
        }
      ]
    }
  }
}
```
