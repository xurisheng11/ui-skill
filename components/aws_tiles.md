# aws_tiles

瓷砖选择组件，用于卡片式单选选择。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| items | 数组 | 是 | 瓷砖选项数组 |
| default_value | 字符串/null | 是 | 选中的值 |
| columns | 数字 | 否 | 显示列数 (1-4) |
| disabled | 布尔值 | 否 | 是否禁用 |
| read_only | 布尔值 | 否 | 只读状态 |

### items 项结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| value | 字符串 | 选项值 |
| label | 组件/字符串 | 选项标签 |
| description | 组件/字符串 | 选项描述 |
| image | 组件 | 选项图片 |
| disabled | 布尔值 | 是否禁用 |

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

### 两列布局

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

### 单列布局

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
          "#type": "aws_tiles",
          "#columns": 3,
          "#items": [
            { "label": "S", "value": "s" },
            { "label": "M", "value": "m" },
            { "label": "L", "value": "l" },
            { "label": "XL", "value": "xl" },
            { "label": "XXL", "value": "xxl" }
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
          "#type": "aws_tiles",
          "#columns": 4,
          "#items": [
            { "label": "周一", "value": "mon" },
            { "label": "周二", "value": "tue" },
            { "label": "周三", "value": "wed" },
            { "label": "周四", "value": "thu" }
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

### 服务选择

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
            { "label": "数据库", "value": "rds", "description": "关系型数据库" },
            { "label": "CDN", "value": "cdn", "description": "内容分发网络" },
            { "label": "负载均衡", "value": "slb", "description": "流量分发服务" },
            { "label": "安全服务", "value": "security", "description": "安全防护服务" }
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

### 颜色选择

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

### 尺寸选择

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
