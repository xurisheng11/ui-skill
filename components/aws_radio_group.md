# aws_radio_group

单选按钮组组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| items | 数组 | 是 | 单选按钮数组 |
| default_value | 字符串/null | 是 | 选中的值 |
| name | 字符串 | 否 | 单选按钮组名称 |
| disabled | 布尔值 | 否 | 是否禁用 |
| read_only | 布尔值 | 否 | 只读状态 |
| aria_required | 布尔值 | 否 | aria-required |

### items 项结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| value | 字符串 | 单选按钮的值 |
| label | 组件/字符串 | 标签内容 |
| description | 组件/字符串 | 描述文本 |
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
          "#type": "aws_radio_group",
          "#items": [
            { "value": "first", "label": "第一个选项" },
            { "value": "second", "label": "第二个选项" },
            { "value": "third", "label": "第三个选项" }
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
          "#type": "aws_radio_group",
          "#items": [
            { "value": "option1", "label": "选项一" },
            { "value": "option2", "label": "选项二" },
            { "value": "option3", "label": "选项三" }
          ],
          "#default_value": "option2"
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
          "#type": "aws_radio_group",
          "#items": [
            { "value": "basic", "label": "基础版", "description": "包含基础功能" },
            { "value": "pro", "label": "专业版", "description": "包含高级功能" },
            { "value": "enterprise", "label": "企业版", "description": "包含全部功能" }
          ],
          "#default_value": "basic"
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
          "#type": "aws_radio_group",
          "#items": [
            { "value": "enabled", "label": "启用" },
            { "value": "disabled", "label": "禁用", "disabled": true },
            { "value": "maintenance", "label": "维护中", "disabled": true }
          ],
          "#default_value": "enabled"
        }
      ]
    }
  }
}
```

### 状态选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_radio_group",
          "#items": [
            { "value": "running", "label": "运行中" },
            { "value": "stopped", "label": "已停止" },
            { "value": "restarting", "label": "重启中" }
          ],
          "#default_value": "running"
        }
      ]
    }
  }
}
```

### 配送方式

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_radio_group",
          "#items": [
            { "value": "standard", "label": "标准配送", "description": "3-5个工作日" },
            { "value": "express", "label": "快速配送", "description": "1-2个工作日" },
            { "value": "same_day", "label": "当日达", "description": "4小时内送达" }
          ],
          "#default_value": "standard"
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
          "#type": "aws_radio_group",
          "#items": [
            { "value": "yes", "label": "是" },
            { "value": "no", "label": "否" }
          ],
          "#default_value": "yes",
          "#read_only": true
        }
      ]
    }
  }
}
```

### 支付方式

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_radio_group",
          "#items": [
            { "value": "alipay", "label": "支付宝" },
            { "value": "wechat", "label": "微信支付" },
            { "value": "card", "label": "银行卡" },
            { "value": "cash", "label": "现金" }
          ]
        }
      ]
    }
  }
}
```

### 主题选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_radio_group",
          "#items": [
            { "value": "light", "label": "浅色主题" },
            { "value": "dark", "label": "深色主题" },
            { "value": "auto", "label": "跟随系统" }
          ],
          "#default_value": "auto"
        }
      ]
    }
  }
}
```
