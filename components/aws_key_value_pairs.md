# aws_key_value_pairs

键值对组件，用于以网格形式展示数据。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| columns | 数字 | 否 | 每行列数 (1-4)，默认1 |
| items | 数组 | 是 | 键值对项数组 |
| aria_label | 字符串 | 否 | 容器aria-label |
| aria_labelledby | 字符串 | 否 | 容器aria-labelledby |

### items 项结构

**type: pair（默认）**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| label | 字符串 | 键标签 |
| value | 组件/字符串 | 对应值 |
| info | 组件 | 键旁边的信息链接 |

**type: group**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| title | 字符串 | 列标题 |
| items | 数组 | 键值对项数组 |

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
          "#type": "aws_key_value_pairs",
          "#items": [
            {
              "label": "名称",
              "value": "示例项目"
            },
            {
              "label": "ID",
              "value": "PRJ-12345"
            },
            {
              "label": "状态",
              "value": "进行中"
            }
          ]
        }
      ]
    }
  }
}
```

### 三列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_key_value_pairs",
          "#columns": 3,
          "#items": [
            {
              "label": "Distribution ID",
              "value": "E1WG1ZNPRXT0D4"
            },
            {
              "label": "Instance ID",
              "value": "i-1234567890"
            },
            {
              "label": "Region",
              "value": "us-east-1"
            }
          ]
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
          "#type": "aws_key_value_pairs",
          "#items": [
            {
              "label": "Distribution ID",
              "value": "E1WG1ZNPRXT0D4",
              "info": {
                "#type": "aws_link",
                "#content": "查看详情",
                "#variant": "info"
              }
            },
            {
              "label": "Instance ID",
              "value": "i-1234567890",
              "info": {
                "#type": "aws_link",
                "#content": "管理",
                "#variant": "info"
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 带复制功能

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_key_value_pairs",
          "#items": [
            {
              "label": "ARN",
              "value": {
                "#type": "aws_copy_to_clipboard",
                "#text_to_copy": "arn:aws:service:region:account:resource",
                "#variant": "inline"
              }
            },
            {
              "label": "IP地址",
              "value": {
                "#type": "aws_copy_to_clipboard",
                "#text_to_copy": "192.168.1.1",
                "#variant": "inline"
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 带外部链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_key_value_pairs",
          "#items": [
            {
              "label": "文档",
              "value": {
                "#type": "aws_link",
                "#content": "查看文档",
                "#href": "#",
                "#external": true
              }
            },
            {
              "label": "控制台",
              "value": {
                "#type": "aws_link",
                "#content": "打开控制台",
                "#href": "#",
                "#external": true
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 分组展示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_key_value_pairs",
          "#columns": 2,
          "#items": [
            {
              "type": "group",
              "title": "基本信息",
              "items": [
                {
                  "label": "项目名称",
                  "value": "ISMP系统"
                },
                {
                  "label": "版本",
                  "value": "v2.0"
                }
              ]
            },
            {
              "type": "group",
              "title": "统计信息",
              "items": [
                {
                  "label": "用户数",
                  "value": "1,234"
                },
                {
                  "label": "访问量",
                  "value": "56,789"
                }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 完整信息展示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_key_value_pairs",
          "#columns": 2,
          "#items": [
            {
              "label": "实例ID",
              "value": "i-0abc1234567890def",
              "info": {
                "#type": "aws_link",
                "#content": "查看",
                "#variant": "info"
              }
            },
            {
              "label": "状态",
              "value": "运行中",
              "info": {
                "#type": "aws_status_indicator",
                "#status_type": "success",
                "#content": "健康"
              }
            },
            {
              "label": "类型",
              "value": "t3.medium"
            },
            {
              "label": "区域",
              "value": "亚太区域 (东京)"
            },
            {
              "label": "VPC",
              "value": "vpc-12345678"
            },
            {
              "label": "子网",
              "value": "subnet-abcdef12"
            },
            {
              "label": "安全组",
              "value": "sg-0abcd1234efgh5678"
            },
            {
              "label": "启动时间",
              "value": "2024-01-15 10:30:00"
            }
          ]
        }
      ]
    }
  }
}
```

### 四列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_key_value_pairs",
          "#columns": 4,
          "#items": [
            { "label": "字段1", "value": "值1" },
            { "label": "字段2", "value": "值2" },
            { "label": "字段3", "value": "值3" },
            { "label": "字段4", "value": "值4" }
          ]
        }
      ]
    }
  }
}
```
