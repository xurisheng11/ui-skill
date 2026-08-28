# aws_spinner 示例

本文档展示 aws_spinner 组件的各种使用场景。

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
          "#type": "aws_spinner"
        }
      ]
    }
  }
}
```

### 2. 不同尺寸

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
          "#direction": "horizontal",
          "#size": "l",
          "#content": [
            { "#type": "aws_spinner", "#size": "normal" },
            { "#type": "aws_spinner", "#size": "big" },
            { "#type": "aws_spinner", "#size": "large" }
          ]
        }
      ]
    }
  }
}
```

### 3. 带文本

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
          "#content": {
            "spinner": { "#type": "aws_spinner", "#size": "large" },
            "text": "加载中，请稍候..."
          }
        }
      ]
    }
  }
}
```

### 4. 禁用状态变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_spinner", "#variant": "disabled" }
      ]
    }
  }
}
```

### 5. 反转变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_spinner", "#variant": "inverted" }
      ]
    }
  }
}
```

### 6. 全屏加载

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
          "#content": {
            "spinner": { "#type": "aws_spinner", "#size": "large" },
            "text": "正在加载数据..."
          }
        }
      ]
    }
  }
}
```

### 7. 页面加载中

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
          "#content": {
            "spinner": { "#type": "aws_spinner", "#size": "large" },
            "text": "页面加载中，请稍候..."
          }
        }
      ]
    }
  }
}
```

### 8. 提交处理中

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
          "#content": {
            "spinner": { "#type": "aws_spinner", "#size": "normal" },
            "text": "正在提交，请勿关闭页面..."
          }
        }
      ]
    }
  }
}
```

### 9. 同步数据

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
          "#content": {
            "spinner": { "#type": "aws_spinner" },
            "text": "正在同步数据..."
          }
        }
      ]
    }
  }
}
```

### 10. 小尺寸加载

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_spinner", "#size": "normal" }
      ]
    }
  }
}
```

### 11. 大尺寸加载

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_spinner", "#size": "large" }
      ]
    }
  }
}
```

### 12. 等待用户操作

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
          "#content": {
            "spinner": { "#type": "aws_spinner", "#size": "big" },
            "text": "请稍候，正在准备数据..."
          }
        }
      ]
    }
  }
}
```

### 13. 导出数据中

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
          "#content": {
            "spinner": { "#type": "aws_spinner", "#size": "large" },
            "text": "正在导出数据，请稍候..."
          }
        }
      ]
    }
  }
}
```

### 14. 登录验证中

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
          "#content": {
            "spinner": { "#type": "aws_spinner" },
            "text": "正在验证身份..."
          }
        }
      ]
    }
  }
}
```

### 15. 初始化中

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
          "#content": {
            "spinner": { "#type": "aws_spinner", "#size": "large" },
            "text": "系统初始化中..."
          }
        }
      ]
    }
  }
}
```
