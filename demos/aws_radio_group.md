# aws_radio_group 示例

本文档展示 aws_radio_group 组件的各种使用场景。

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

### 4. 禁用选项

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

### 5. 支付方式

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
            { "value": "card", "label": "银行卡" }
          ]
        }
      ]
    }
  }
}
```

### 6. 配送方式

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

### 7. 主题选择

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

### 8. 是/否选择

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
          "#default_value": "yes"
        }
      ]
    }
  }
}
```

### 9. 状态选择

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

### 10. 版本选择

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
            { "value": "v1", "label": "版本 1.0" },
            { "value": "v2", "label": "版本 2.0" },
            { "value": "v3", "label": "版本 3.0" }
          ],
          "#default_value": "v2"
        }
      ]
    }
  }
}
```

### 11. 优先级选择

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
            { "value": "low", "label": "低" },
            { "value": "medium", "label": "中" },
            { "value": "high", "label": "高" },
            { "value": "urgent", "label": "紧急" }
          ]
        }
      ]
    }
  }
}
```

### 12. 性别选择

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
            { "value": "male", "label": "男" },
            { "value": "female", "label": "女" },
            { "value": "other", "label": "其他" }
          ]
        }
      ]
    }
  }
}
```

### 13. 通知设置

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
            { "value": "all", "label": "接收所有通知" },
            { "value": "important", "label": "仅接收重要通知" },
            { "value": "none", "label": "不接收通知" }
          ],
          "#default_value": "important"
        }
      ]
    }
  }
}
```

### 14. 只读状态

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

### 15. 语言选择

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
            { "value": "zh", "label": "简体中文" },
            { "value": "tw", "label": "繁体中文" },
            { "value": "en", "label": "English" }
          ],
          "#default_value": "zh"
        }
      ]
    }
  }
}
```
