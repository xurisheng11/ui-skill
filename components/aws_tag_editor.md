# aws_tag_editor

标签编辑器组件，用于管理标签。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 数组 | 否 | 标签数组 |
| tag_limit | 数字 | 否 | 最大标签数量 |
| allowed_character_pattern | 字符串 | 否 | 可接受字符正则 |
| keys_request | 函数 | 否 | 获取所有键的函数 |
| values_request | 函数 | 否 | 获取特定键所有值的函数 |

### default_value 项结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| key | 字符串 | 标签键 |
| value | 字符串 | 标签值 |
| existing | 布尔值 | 是否为现有标签 |
| marked_for_removal | 布尔值 | 是否标记为删除 |

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
          "#type": "aws_tag_editor",
          "#default_value": [
            {
              "key": "Environment",
              "value": "Production",
              "existing": true
            },
            {
              "key": "Project",
              "value": "ISMP",
              "existing": false
            },
            {
              "key": "Owner",
              "value": "Team-A",
              "existing": false
            }
          ]
        }
      ]
    }
  }
}
```

### 空标签列表

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": []
        }
      ]
    }
  }
}
```

### 带标签限制

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#tag_limit": 5,
          "#default_value": [
            { "key": "Tag1", "value": "Value1" },
            { "key": "Tag2", "value": "Value2" }
          ]
        }
      ]
    }
  }
}
```

### 现有标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            {
              "key": "Environment",
              "value": "Production",
              "existing": true
            },
            {
              "key": "Application",
              "value": "WebApp",
              "existing": true
            },
            {
              "key": "CostCenter",
              "value": "CC-001",
              "existing": true
            }
          ]
        }
      ]
    }
  }
}
```

### 标记删除的标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            {
              "key": "Keep",
              "value": "This",
              "existing": true,
              "marked_for_removal": false
            },
            {
              "key": "Remove",
              "value": "This",
              "existing": true,
              "marked_for_removal": true
            }
          ]
        }
      ]
    }
  }
}
```

### 资源标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            {
              "key": "Name",
              "value": "Production Server",
              "existing": true
            },
            {
              "key": "Environment",
              "value": "prod",
              "existing": true
            },
            {
              "key": "Team",
              "value": "Infrastructure",
              "existing": true
            },
            {
              "key": "Backup",
              "value": "enabled",
              "existing": false
            }
          ]
        }
      ]
    }
  }
}
```

### 新建标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            {
              "key": "Department",
              "value": "IT",
              "existing": false
            },
            {
              "key": "ProjectCode",
              "value": "P2024",
              "existing": false
            }
          ]
        }
      ]
    }
  }
}
```

### 混合标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            {
              "key": "CreatedBy",
              "value": "admin",
              "existing": true,
              "marked_for_removal": false
            },
            {
              "key": "Status",
              "value": "active",
              "existing": true,
              "marked_for_removal": false
            },
            {
              "key": "Monitored",
              "value": "true",
              "existing": false
            }
          ]
        }
      ]
    }
  }
}
```
