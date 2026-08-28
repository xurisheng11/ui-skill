# aws_toggle

开关切换组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| default_value | 布尔值 | 是 | 是否选中 |
| disabled | 布尔值 | 否 | 是否禁用 |
| read_only | 布尔值 | 否 | 只读状态 |
| description | 字符串 | 否 | 标签下方描述 |

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| content | 切换旁白的标签 | 是 | {variable} |

**注意**：提交时选中为'1'，未选中为'0'（字符串形式）

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
          "#type": "aws_toggle",
          "#content": "开关"
        }
      ]
    }
  }
}
```

### 默认选中

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle",
          "#default_value": true,
          "#content": "已启用"
        }
      ]
    }
  }
}
```

### 默认未选中

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle",
          "#default_value": false,
          "#content": "已禁用"
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
          "#type": "aws_toggle",
          "#content": "接收通知",
          "#description": "开启后您将收到系统通知"
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
          "#type": "aws_toggle",
          "#disabled": true,
          "#content": "禁用状态"
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
          "#type": "aws_toggle",
          "#read_only": true,
          "#default_value": true,
          "#content": "只读状态"
        }
      ]
    }
  }
}
```

### 启用功能

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle",
          "#default_value": false,
          "#content": "启用调试模式",
          "#description": "开启后显示详细的调试信息"
        }
      ]
    }
  }
}
```

### 隐私设置

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle",
          "#default_value": true,
          "#content": "公开个人资料",
          "#description": "其他用户可以查看您的基本信息"
        }
      ]
    }
  }
}
```

### 通知开关

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_toggle",
          "#default_value": true,
          "#content": "邮件通知"
        },
        {
          "#type": "aws_toggle",
          "#default_value": true,
          "#content": "短信通知"
        },
        {
          "#type": "aws_toggle",
          "#default_value": false,
          "#content": "推送通知"
        }
      ]
    }
  }
}
```

### 系统设置

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "vertical",
          "#size": "m",
          "#content": [
            {
              "#type": "aws_toggle",
              "#default_value": true,
              "#content": "自动保存",
              "#description": "自动保存您的更改"
            },
            {
              "#type": "aws_toggle",
              "#default_value": false,
              "#content": "深色模式",
              "#description": "使用深色主题"
            },
            {
              "#type": "aws_toggle",
              "#default_value": true,
              "#content": "声音提示",
              "#description": "操作时播放提示音"
            }
          ]
        }
      ]
    }
  }
}
```

### 开关列表

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_space_between",
          "#direction": "vertical",
          "#size": "s",
          "#content": [
            {
              "#type": "aws_toggle",
              "#default_value": true,
              "#content": "Wi-Fi"
            },
            {
              "#type": "aws_toggle",
              "#default_value": false,
              "#content": "蓝牙"
            },
            {
              "#type": "aws_toggle",
              "#default_value": true,
              "#content": "飞行模式"
            },
            {
              "#type": "aws_toggle",
              "#default_value": false,
              "#content": "热点"
            }
          ]
        }
      ]
    }
  }
}
```
