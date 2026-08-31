# aws_toggle 示例

本文档展示 aws_toggle 组件的各种使用场景。

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
          "#type": "aws_toggle",
          "#content": "开关"
        }
      ]
    }
  }
}
```

### 2. 默认选中

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
          "#type": "aws_toggle",
          "#content": "接收通知",
          "#description": "开启后您将收到系统通知"
        }
      ]
    }
  }
}
```

### 4. 禁用状态

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

### 5. 通知开关

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_toggle", "#default_value": true, "#content": "邮件通知" },
        { "#type": "aws_toggle", "#default_value": true, "#content": "短信通知" },
        { "#type": "aws_toggle", "#default_value": false, "#content": "推送通知" }
      ]
    }
  }
}
```

### 6. 系统设置

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
            { "#type": "aws_toggle", "#default_value": true, "#content": "自动保存", "#description": "自动保存您的更改" },
            { "#type": "aws_toggle", "#default_value": false, "#content": "深色模式", "#description": "使用深色主题" },
            { "#type": "aws_toggle", "#default_value": true, "#content": "声音提示", "#description": "操作时播放提示音" }
          ]
        }
      ]
    }
  }
}
```

### 7. 只读状态

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

### 8. 功能开关

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_toggle", "#default_value": true, "#content": "启用调试模式" },
        { "#type": "aws_toggle", "#default_value": false, "#content": "启用缓存" },
        { "#type": "aws_toggle", "#default_value": true, "#content": "启用压缩" }
      ]
    }
  }
}
```

### 9. 隐私设置

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

### 10. 开关列表

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
            { "#type": "aws_toggle", "#default_value": true, "#content": "Wi-Fi" },
            { "#type": "aws_toggle", "#default_value": false, "#content": "蓝牙" },
            { "#type": "aws_toggle", "#default_value": true, "#content": "飞行模式" },
            { "#type": "aws_toggle", "#default_value": false, "#content": "热点" }
          ]
        }
      ]
    }
  }
}
```

### 11. 启用功能

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

### 12. 默认未选中

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

### 13. 安全设置

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_toggle", "#default_value": true, "#content": "双因素认证" },
        { "#type": "aws_toggle", "#default_value": false, "#content": "登录提醒" },
        { "#type": "aws_toggle", "#default_value": true, "#content": "会话超时" }
      ]
    }
  }
}
```

### 14. 同步设置

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_toggle", "#default_value": true, "#content": "自动同步" },
        { "#type": "aws_toggle", "#default_value": false, "#content": "仅在Wi-Fi下同步" },
        { "#type": "aws_toggle", "#default_value": true, "#content": "后台同步" }
      ]
    }
  }
}
```

### 15. 权限控制

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_toggle", "#default_value": true, "#content": "允许评论" },
        { "#type": "aws_toggle", "#default_value": false, "#content": "允许分享" },
        { "#type": "aws_toggle", "#default_value": true, "#content": "允许下载" }
      ]
    }
  }
}
```
