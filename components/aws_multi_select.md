# aws_multi_select

多选下拉组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| select_options | 数组 | 否 | 选项数组 |
| default_value | 数组 | 是 | 当前选中的选项数组 |
| placeholder | 字符串 | 否 | 占位符文本 |
| disabled | 布尔值 | 否 | 是否禁用 |
| invalid | 布尔值 | 否 | 无效状态 |
| read_only | 布尔值 | 否 | 只读状态 |
| filtering_type | 字符串 | 否 | 过滤类型 |
| status_type | 字符串 | 否 | 加载状态 |
| inline_tokens | 布尔值 | 否 | 选中内容显示在输入框内 |
| hide_tokens | 布尔值 | 否 | 隐藏选中标记 |
| token_limit | 数字 | 否 | 最大显示标记数 |
| keep_open | 布尔值 | 否 | 选择后保持打开 |
| virtual_scroll | 布尔值 | 否 | 虚拟滚动 |
| expand_to_viewport | 布尔值 | 否 | 展开到视口 |
| auto_focus | 布尔值 | 否 | 自动聚焦 |

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| empty | 无选项时显示 | 是 | variable |
| no_match | 过滤无匹配时显示 | 是 | variable |

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
          "#type": "aws_multi_select",
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" },
            { "label": "选项 4", "value": "4" },
            { "label": "选项 5", "value": "5" }
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

### 带占位符

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
          "#placeholder": "请选择多个选项",
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

### 内联标签模式

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
            { "label": "新功能", "value": "feature" },
            { "label": "Bug", "value": "bug" },
            { "label": "文档", "value": "docs" }
          ],
          "#default_value": [
            { "label": "重要", "value": "important" },
            { "label": "紧急", "value": "urgent" }
          ]
        }
      ]
    }
  }
}
```

### 带标签数量限制

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
            { "label": "选项 5", "value": "5" },
            { "label": "选项 6", "value": "6" }
          ],
          "#default_value": [
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
          "#type": "aws_multi_select",
          "#placeholder": "选择服务",
          "#select_options": [
            { "label": "EC2", "value": "ec2", "description": "弹性云服务器" },
            { "label": "S3", "value": "s3", "description": "简单存储服务" },
            { "label": "Lambda", "value": "lambda", "description": "无服务器计算" },
            { "label": "RDS", "value": "rds", "description": "关系型数据库" }
          ]
        }
      ]
    }
  }
}
```

### 分组多选

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
          "#type": "aws_multi_select",
          "#placeholder": "选择资源类型",
          "#select_options": [
            { "label": "服务器", "value": "server", "icon_name": "server" },
            { "label": "数据库", "value": "database", "icon_name": "database" },
            { "label": "存储", "value": "storage", "icon_name": "bucket" },
            { "label": "网络", "value": "network", "icon_name": "network" }
          ]
        }
      ]
    }
  }
}
```

### 禁用选项

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
            { "label": "已完成", "value": "completed" },
            { "label": "已取消", "value": "cancelled", "disabled": true }
          ]
        }
      ]
    }
  }
}
```

### 自动过滤

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
            { "label": "橙子", "value": "orange" },
            { "label": "葡萄", "value": "grape" }
          ]
        }
      ]
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
      "#children": [
        {
          "#type": "aws_multi_select",
          "#disabled": true,
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" }
          ],
          "#default_value": [
            { "label": "选项 1", "value": "1" }
          ]
        }
      ]
    }
  }
}
```

### 无匹配提示

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
          "#no_match": "没有找到匹配项",
          "#select_options": [
            { "label": "选项 A", "value": "a" },
            { "label": "选项 B", "value": "b" }
          ]
        }
      ]
    }
  }
}
```

### 选择后关闭

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
