# aws_multi_select 示例

本文档展示 aws_multi_select 组件的各种使用场景。

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
          "#type": "aws_multi_select",
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" }
          ]
        }
      ]
    }
  }
}
```

### 2. 带默认值

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" }
          ],
          "#default_value": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" }
          ]
        }
      ]
    }
  }
}
```

### 3. 内联标签模式

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#inline_tokens": true,
          "#placeholder": "选择标签",
          "#select_options": [
            { "label": "重要", "value": "important" },
            { "label": "紧急", "value": "urgent" },
            { "label": "新功能", "value": "feature" }
          ]
        }
      ]
    }
  }
}
```

### 4. 带标签数量限制

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#token_limit": 3,
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" },
            { "label": "选项 4", "value": "4" },
            { "label": "选项 5", "value": "5" }
          ]
        }
      ]
    }
  }
}
```

### 5. 带描述

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#placeholder": "选择服务",
          "#select_options": [
            { "label": "EC2", "value": "ec2", "description": "弹性云服务器" },
            { "label": "S3", "value": "s3", "description": "简单存储服务" },
            { "label": "Lambda", "value": "lambda", "description": "无服务器计算" }
          ]
        }
      ]
    }
  }
}
```

### 6. 分组多选

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#placeholder": "选择权限",
          "#select_options": [
            {
              "label": "用户权限",
              "options": [
                { "label": "读取", "value": "read" },
                { "label": "写入", "value": "write" },
                { "label": "删除", "value": "delete" }
              ]
            },
            {
              "label": "管理员权限",
              "options": [
                { "label": "用户管理", "value": "user_manage" },
                { "label": "系统配置", "value": "sys_config" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 7. 带图标

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#placeholder": "选择资源类型",
          "#select_options": [
            { "label": "服务器", "value": "server", "icon_name": "server" },
            { "label": "数据库", "value": "database", "icon_name": "database" },
            { "label": "存储", "value": "storage", "icon_name": "folder" }
          ]
        }
      ]
    }
  }
}
```

### 8. 自动过滤

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#filtering_type": "auto",
          "#filtering_placeholder": "搜索...",
          "#select_options": [
            { "label": "红苹果", "value": "red_apple" },
            { "label": "绿苹果", "value": "green_apple" },
            { "label": "香蕉", "value": "banana" },
            { "label": "橙子", "value": "orange" }
          ]
        }
      ]
    }
  }
}
```

### 9. 选择后关闭

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#keep_open": false,
          "#placeholder": "选择一个（选择后关闭）",
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" }
          ]
        }
      ]
    }
  }
}
```

### 10. 禁用选项

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#placeholder": "选择状态",
          "#select_options": [
            { "label": "待处理", "value": "pending" },
            { "label": "进行中", "value": "processing", "disabled": true },
            { "label": "已完成", "value": "completed" }
          ]
        }
      ]
    }
  }
}
```

### 11. 编程语言选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#placeholder": "选择编程语言",
          "#select_options": [
            { "label": "JavaScript", "value": "js" },
            { "label": "Python", "value": "py" },
            { "label": "Java", "value": "java" },
            { "label": "Go", "value": "go" },
            { "label": "Rust", "value": "rust" }
          ]
        }
      ]
    }
  }
}
```

### 12. 技术栈选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#placeholder": "选择技术栈",
          "#select_options": [
            {
              "label": "前端",
              "options": [
                { "label": "React", "value": "react" },
                { "label": "Vue", "value": "vue" },
                { "label": "Angular", "value": "angular" }
              ]
            },
            {
              "label": "后端",
              "options": [
                { "label": "Node.js", "value": "nodejs" },
                { "label": "Spring", "value": "spring" },
                { "label": "Django", "value": "django" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 13. 隐藏选中标记

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#hide_tokens": true,
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" }
          ]
        }
      ]
    }
  }
}
```

### 14. 权限选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#placeholder": "选择权限",
          "#select_options": [
            { "label": "读取", "value": "read" },
            { "label": "写入", "value": "write" },
            { "label": "执行", "value": "execute" },
            { "label": "删除", "value": "delete" },
            { "label": "管理", "value": "admin" }
          ]
        }
      ]
    }
  }
}
```

### 15. 标签选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_multi_select",
          "#inline_tokens": true,
          "#placeholder": "添加标签",
          "#select_options": [
            { "label": "重要", "value": "important" },
            { "label": "紧急", "value": "urgent" },
            { "label": "新功能", "value": "feature" },
            { "label": "Bug", "value": "bug" },
            { "label": "文档", "value": "docs" },
            { "label": "优化", "value": "optimize" }
          ]
        }
      ]
    }
  }
}
```
