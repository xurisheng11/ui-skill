# aws_tiles 示例

本文档展示 aws_tiles 组件的各种使用场景。

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
          "#type": "aws_tiles",
          "#items": [
            { "label": "选项 1", "value": "item1" },
            { "label": "选项 2", "value": "item2" },
            { "label": "选项 3", "value": "item3" }
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
          "#type": "aws_tiles",
          "#items": [
            { "label": "基础版", "value": "basic" },
            { "label": "标准版", "value": "standard" },
            { "label": "高级版", "value": "premium" }
          ],
          "#default_value": "standard"
        }
      ]
    }
  }
}
```

### 3. 带描述

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#items": [
            { "label": "入门级", "value": "starter", "description": "适合个人使用" },
            { "label": "专业级", "value": "pro", "description": "适合小型团队" },
            { "label": "企业级", "value": "enterprise", "description": "适合大型组织" }
          ]
        }
      ]
    }
  }
}
```

### 4. 两列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#columns": 2,
          "#items": [
            { "label": "选项 A", "value": "a" },
            { "label": "选项 B", "value": "b" },
            { "label": "选项 C", "value": "c" },
            { "label": "选项 D", "value": "d" }
          ]
        }
      ]
    }
  }
}
```

### 5. 服务选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#columns": 3,
          "#items": [
            { "label": "云服务器", "value": "ecs", "description": "弹性计算服务" },
            { "label": "对象存储", "value": "oss", "description": "海量存储服务" },
            { "label": "数据库", "value": "rds", "description": "关系型数据库" }
          ]
        }
      ]
    }
  }
}
```

### 6. 颜色选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#columns": 4,
          "#items": [
            { "label": "红色", "value": "red" },
            { "label": "蓝色", "value": "blue" },
            { "label": "绿色", "value": "green" },
            { "label": "黄色", "value": "yellow" }
          ]
        }
      ]
    }
  }
}
```

### 7. 尺寸选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#columns": 4,
          "#items": [
            { "label": "S", "value": "s", "description": "155/80A" },
            { "label": "M", "value": "m", "description": "160/84A" },
            { "label": "L", "value": "l", "description": "165/88A" },
            { "label": "XL", "value": "xl", "description": "170/92A" }
          ],
          "#default_value": "m"
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
          "#type": "aws_tiles",
          "#columns": 1,
          "#items": [
            { "label": "支付方式一", "value": "pay1", "description": "支持多种银行卡" },
            { "label": "支付方式二", "value": "pay2", "description": "支持支付宝" },
            { "label": "支付方式三", "value": "pay3", "description": "支持微信支付" }
          ]
        }
      ]
    }
  }
}
```

### 9. 禁用选项

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#items": [
            { "label": "可用选项", "value": "available" },
            { "label": "已禁用", "value": "disabled", "disabled": true },
            { "label": "另一个可用", "value": "another" }
          ]
        }
      ]
    }
  }
}
```

### 10. 三列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#columns": 3,
          "#items": [
            { "label": "周一", "value": "mon" },
            { "label": "周二", "value": "tue" },
            { "label": "周三", "value": "wed" },
            { "label": "周四", "value": "thu" },
            { "label": "周五", "value": "fri" }
          ]
        }
      ]
    }
  }
}
```

### 11. 只读状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#read_only": true,
          "#items": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" }
          ],
          "#default_value": "2"
        }
      ]
    }
  }
}
```

### 12. 版本选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#items": [
            { "label": "免费版", "value": "free", "description": "基础功能" },
            { "label": "专业版", "value": "pro", "description": "高级功能" },
            { "label": "企业版", "value": "enterprise", "description": "全部功能+专属支持" }
          ],
          "#default_value": "pro"
        }
      ]
    }
  }
}
```

### 13. 区域选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#columns": 2,
          "#items": [
            { "label": "华北区域", "value": "north-china" },
            { "label": "华东区域", "value": "east-china" },
            { "label": "华南区域", "value": "south-china" },
            { "label": "西南区域", "value": "southwest-china" }
          ]
        }
      ]
    }
  }
}
```

### 14. 时间段选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#columns": 4,
          "#items": [
            { "label": "上午", "value": "morning", "description": "9:00-12:00" },
            { "label": "中午", "value": "noon", "description": "12:00-14:00" },
            { "label": "下午", "value": "afternoon", "description": "14:00-18:00" },
            { "label": "晚上", "value": "evening", "description": "18:00-21:00" }
          ]
        }
      ]
    }
  }
}
```

### 15. 网络选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tiles",
          "#columns": 3,
          "#items": [
            { "label": "经典网络", "value": "classic", "description": "传统网络架构" },
            { "label": "专有网络", "value": "vpc", "description": "自定义网络架构" },
            { "label": "混合云", "value": "hybrid", "description": "连接本地数据中心" }
          ],
          "#default_value": "vpc"
        }
      ]
    }
  }
}
```
