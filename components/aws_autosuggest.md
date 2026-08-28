# aws_autosuggest

自动建议组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 字符串 | 是 | 输入文本 |
| suggest_options | 数组 | 否 | 建议选项数组 |
| placeholder | 字符串 | 否 | 占位符文本 |
| disabled | 布尔值 | 否 | 是否禁用 |
| invalid | 布尔值 | 否 | 无效状态 |
| read_only | 布尔值 | 否 | 只读状态 |
| filtering_type | 字符串 | 否 | 过滤类型 |
| status_type | 字符串 | 否 | 加载状态 |
| auto_focus | 布尔值 | 否 | 自动聚焦 |

### suggest_options 选项结构

**Option**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| value | 字符串 | 选项值 |
| label | 字符串 | 显示文本 |
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
| empty | 无建议时显示 | 是 | variable |

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
          "#type": "aws_autosuggest",
          "#default_value": "",
          "#suggest_options": [
            { "value": "建议 1" },
            { "value": "建议 2" },
            { "value": "建议 3" },
            { "value": "建议 4" }
          ]
        }
      ]
    }
  }
}
```

### 带默认值

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_autosuggest",
          "#default_value": "Apple",
          "#suggest_options": [
            { "value": "Apple 苹果" },
            { "value": "Banana 香蕉" },
            { "value": "Cherry 樱桃" }
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
          "#type": "aws_autosuggest",
          "#placeholder": "输入以搜索...",
          "#suggest_options": [
            { "value": "北京" },
            { "value": "上海" },
            { "value": "广州" },
            { "value": "深圳" }
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
          "#type": "aws_autosuggest",
          "#suggest_options": [
            { "value": "EC2", "description": "弹性云服务器" },
            { "value": "S3", "description": "简单存储服务" },
            { "value": "Lambda", "description": "无服务器计算" }
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
          "#type": "aws_autosuggest",
          "#suggest_options": [
            { "value": "文件夹", "icon_name": "folder" },
            { "value": "文件", "icon_name": "file" },
            { "value": "图片", "icon_name": "file-open" }
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
          "#type": "aws_autosuggest",
          "#suggest_options": [
            { "value": "开发环境", "label_tag": "推荐" },
            { "value": "测试环境", "label_tag": "常用" },
            { "value": "生产环境", "label_tag": "重要" }
          ]
        }
      ]
    }
  }
}
```

### 分组建议

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_autosuggest",
          "#suggest_options": [
            {
              "label": "前端框架",
              "options": [
                { "value": "React" },
                { "value": "Vue" },
                { "value": "Angular" }
              ]
            },
            {
              "label": "后端框架",
              "options": [
                { "value": "Node.js" },
                { "value": "Python" },
                { "value": "Java" }
              ]
            }
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
          "#type": "aws_autosuggest",
          "#suggest_options": [
            { "value": "可用选项" },
            { "value": "已禁用", "disabled": true },
            { "value": "另一个可用" }
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
          "#type": "aws_autosuggest",
          "#disabled": true,
          "#default_value": "禁用的输入",
          "#suggest_options": [
            { "value": "选项1" },
            { "value": "选项2" }
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
          "#type": "aws_autosuggest",
          "#read_only": true,
          "#default_value": "只读内容",
          "#suggest_options": [
            { "value": "选项1" },
            { "value": "选项2" }
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
          "#type": "aws_autosuggest",
          "#filtering_type": "auto",
          "#suggest_options": [
            { "value": "JavaScript" },
            { "value": "Java" },
            { "value": "Python" },
            { "value": "TypeScript" }
          ]
        }
      ]
    }
  }
}
```

### 无建议时显示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_autosuggest",
          "#suggest_options": [
            { "value": "苹果" },
            { "value": "香蕉" }
          ],
          "#empty": "没有找到匹配的建议"
        }
      ]
    }
  }
}
```

### 搜索颜色

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_autosuggest",
          "#placeholder": "搜索颜色...",
          "#suggest_options": [
            { "value": "红色" },
            { "value": "蓝色" },
            { "value": "绿色" },
            { "value": "黄色" },
            { "value": "紫色" }
          ]
        }
      ]
    }
  }
}
```

### 搜索国家

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_autosuggest",
          "#placeholder": "搜索国家...",
          "#suggest_options": [
            { "value": "中国", "description": "Asia" },
            { "value": "美国", "description": "North America" },
            { "value": "英国", "description": "Europe" },
            { "value": "日本", "description": "Asia" }
          ]
        }
      ]
    }
  }
}
```

### 搜索编程语言

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_autosuggest",
          "#placeholder": "搜索编程语言...",
          "#suggest_options": [
            { "value": "JavaScript", "description": "Web开发" },
            { "value": "Python", "description": "数据分析/AI" },
            { "value": "Go", "description": "系统编程" },
            { "value": "Rust", "description": "系统编程" }
          ]
        }
      ]
    }
  }
}
```
