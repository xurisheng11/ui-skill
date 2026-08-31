# aws_select

下拉选择组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| select_options | 数组 | 否 | 选项数组 |
| default_value | 对象 | 是 | 当前选中的选项 |
| placeholder | 字符串 | 否 | 占位符文本 |
| disabled | 布尔值 | 否 | 是否禁用 |
| invalid | 布尔值 | 否 | 无效状态 |
| read_only | 布尔值 | 否 | 只读状态 |
| filtering_type | 字符串 | 否 | 过滤类型 |
| status_type | 字符串 | 否 | 加载状态 |
| trigger_variant | 字符串 | 否 | 触发器变体 |
| virtual_scroll | 布尔值 | 否 | 虚拟滚动（超过500项时） |
| expand_to_viewport | 布尔值 | 否 | 展开到视口 |
| auto_focus | 布尔值 | 否 | 自动聚焦 |

### select_options 选项结构

**Option**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| label | 字符串 | 显示文本 |
| value | 字符串 | 选项值 |
| description | 字符串 | 描述文本 |
| disabled | 布尔值 | 是否禁用 |
| icon_name | 字符串 | 图标名称 |
| label_tag | 字符串 | 标签 |

**OptionGroup**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| label | 字符串 | 组标题 |
| options | 数组 | 组内选项 |
| disabled | 布尔值 | 是否禁用整个组 |

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
          "#type": "aws_select",
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" }
          ],
          "#default_value": {
            "label": "选项 1",
            "value": "1"
          }
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
          "#type": "aws_select",
          "#placeholder": "请选择一个选项",
          "#select_options": [
            { "label": "北京", "value": "bj" },
            { "label": "上海", "value": "sh" },
            { "label": "广州", "value": "gz" },
            { "label": "深圳", "value": "sz" }
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
          "#type": "aws_select",
          "#placeholder": "选择实例类型",
          "#select_options": [
            { "label": "通用型", "value": "general", "description": "适用于通用计算场景" },
            { "label": "计算型", "value": "compute", "description": "适用于计算密集型场景" },
            { "label": "内存型", "value": "memory", "description": "适用于内存密集型场景" }
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
          "#type": "aws_select",
          "#select_options": [
            { "label": "文件夹", "value": "folder", "icon_name": "folder" },
            { "label": "文件", "value": "file", "icon_name": "file" },
            { "label": "图片", "value": "image", "icon_name": "file-open" }
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
          "#type": "aws_select",
          "#placeholder": "选择状态",
          "#select_options": [
            { "label": "运行中", "value": "running" },
            { "label": "已停止", "value": "stopped", "disabled": true },
            { "label": "已删除", "value": "deleted", "disabled": true }
          ]
        }
      ]
    }
  }
}
```

### 分组选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#placeholder": "选择服务",
          "#select_options": [
            {
              "label": "计算服务",
              "options": [
                { "label": "EC2", "value": "ec2" },
                { "label": "Lambda", "value": "lambda" },
                { "label": "ECS", "value": "ecs" }
              ]
            },
            {
              "label": "存储服务",
              "options": [
                { "label": "S3", "value": "s3" },
                { "label": "EBS", "value": "ebs" }
              ]
            },
            {
              "label": "数据库服务（不可用）",
              "disabled": true,
              "options": [
                { "label": "RDS", "value": "rds" },
                { "label": "DynamoDB", "value": "dynamodb" }
              ]
            }
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
          "#type": "aws_select",
          "#select_options": [
            { "label": "开发环境", "value": "dev", "label_tag": "推荐" },
            { "label": "测试环境", "value": "test", "label_tag": "常用" },
            { "label": "生产环境", "value": "prod", "label_tag": "重要" }
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
          "#type": "aws_select",
          "#disabled": true,
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" }
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
          "#type": "aws_select",
          "#filtering_type": "auto",
          "#filtering_placeholder": "搜索...",
          "#select_options": [
            { "label": "Apple 苹果", "value": "apple" },
            { "label": "Banana 香蕉", "value": "banana" },
            { "label": "Cherry 樱桃", "value": "cherry" },
            { "label": "Date 枣", "value": "date" }
          ]
        }
      ]
    }
  }
}
```

### 显示完整选项

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#trigger_variant": "option",
          "#select_options": [
            { "label": "北京", "value": "bj", "icon_name": "location-pin" },
            { "label": "上海", "value": "sh", "icon_name": "location-pin" },
            { "label": "广州", "value": "gz", "icon_name": "location-pin" }
          ]
        }
      ]
    }
  }
}
```

### 无匹配时显示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#filtering_type": "auto",
          "#no_match": "未找到匹配的选项",
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

### 空状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#empty": "暂无选项，请稍后再试",
          "#select_options": []
        }
      ]
    }
  }
}
```
