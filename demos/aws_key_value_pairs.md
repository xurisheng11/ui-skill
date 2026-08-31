# aws_key_value_pairs 示例

本文档展示 aws_key_value_pairs 组件的各种使用场景。

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
          "#type": "aws_key_value_pairs",
          "#items": [
            { "label": "名称", "value": "示例项目" },
            { "label": "ID", "value": "PRJ-12345" },
            { "label": "状态", "value": "进行中" }
          ]
        }
      ]
    }
  }
}
```

### 2. 三列布局

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
            { "label": "Distribution ID", "value": "E1WG1ZNPRXT0D4" },
            { "label": "Instance ID", "value": "i-1234567890" },
            { "label": "Region", "value": "us-east-1" }
          ]
        }
      ]
    }
  }
}
```

### 3. 带信息链接

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
            }
          ]
        }
      ]
    }
  }
}
```

### 4. 带复制功能

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
            }
          ]
        }
      ]
    }
  }
}
```

### 5. 分组展示

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
                { "label": "项目名称", "value": "ISMP系统" },
                { "label": "版本", "value": "v2.0" }
              ]
            },
            {
              "type": "group",
              "title": "统计信息",
              "items": [
                { "label": "用户数", "value": "1,234" },
                { "label": "访问量", "value": "56,789" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 6. 两列布局

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
            { "label": "实例ID", "value": "i-0abc1234567890def" },
            { "label": "状态", "value": "运行中" },
            { "label": "类型", "value": "t3.medium" },
            { "label": "区域", "value": "亚太区域 (东京)" }
          ]
        }
      ]
    }
  }
}
```

### 7. 四列布局

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

### 8. 单列布局

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
          "#columns": 1,
          "#items": [
            { "label": "完整地址", "value": "北京市朝阳区xxx路xxx号" },
            { "label": "联系电话", "value": "400-xxx-xxxx" },
            { "label": "电子邮箱", "value": "contact@example.com" }
          ]
        }
      ]
    }
  }
}
```

### 9. 带链接值

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
              "label": "文档链接",
              "value": {
                "#type": "aws_link",
                "#content": "查看文档",
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

### 10. 服务器信息

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#items": [
        { "label": "实例ID", "value": "i-0abc1234567890def" },
        { "label": "状态", "value": "运行中" },
        { "label": "类型", "value": "t3.medium" },
        { "label": "区域", "value": "亚太区域 (东京)" },
        { "label": "VPC", "value": "vpc-12345678" },
        { "label": "子网", "value": "subnet-abcdef12" },
        { "label": "安全组", "value": "sg-0abcd1234efgh5678" },
        { "label": "启动时间", "value": "2024-01-15 10:30:00" }
      ]
    }
  }
}
```

### 11. 状态指示器值

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
              "label": "服务状态",
              "value": {
                "#type": "aws_status_indicator",
                "#status_type": "success",
                "#content": "健康"
              }
            }
          ]
        }
      ]
    }
  }
}
```

### 12. 产品信息

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
            { "label": "产品名称", "value": "云服务器 ECS" },
            { "label": "产品规格", "value": "2核4G" },
            { "label": "操作系统", "value": "Ubuntu 22.04" },
            { "label": "存储", "value": "100GB SSD" }
          ]
        }
      ]
    }
  }
}
```

### 13. 联系人信息

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
            { "label": "姓名", "value": "张三" },
            { "label": "职位", "value": "技术总监" },
            { "label": "部门", "value": "研发部" },
            { "label": "邮箱", "value": "zhangsan@example.com" },
            { "label": "电话", "value": "400-xxx-xxxx" }
          ]
        }
      ]
    }
  }
}
```

### 14. 账户信息

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
            { "label": "账户ID", "value": "ACC-12345678" },
            { "label": "账户类型", "value": "企业版" },
            { "label": "创建时间", "value": "2023-06-01" },
            { "label": "到期时间", "value": "2025-06-01" },
            { "label": "余额", "value": "¥10,000.00" },
            { "label": "状态", "value": "正常" }
          ]
        }
      ]
    }
  }
}
```

### 15. 网络配置

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
            { "label": "IP地址", "value": "192.168.1.100" },
            { "label": "子网掩码", "value": "255.255.255.0" },
            { "label": "网关", "value": "192.168.1.1" },
            { "label": "DNS", "value": "8.8.8.8" },
            { "label": "MAC地址", "value": "00:11:22:33:44:55" }
          ]
        }
      ]
    }
  }
}
```
