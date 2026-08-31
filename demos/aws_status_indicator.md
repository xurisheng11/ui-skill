# aws_status_indicator 示例

本文档展示 aws_status_indicator 组件的各种使用场景。

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
        { "#type": "aws_status_indicator", "#status_type": "success", "#content": "成功" },
        { "#type": "aws_status_indicator", "#status_type": "error", "#content": "失败" }
      ]
    }
  }
}
```

### 2. 全部状态

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
            { "#type": "aws_status_indicator", "#status_type": "success", "#content": "成功" },
            { "#type": "aws_status_indicator", "#status_type": "error", "#content": "错误" },
            { "#type": "aws_status_indicator", "#status_type": "warning", "#content": "警告" },
            { "#type": "aws_status_indicator", "#status_type": "info", "#content": "信息" },
            { "#type": "aws_status_indicator", "#status_type": "stopped", "#content": "已停止" },
            { "#type": "aws_status_indicator", "#status_type": "pending", "#content": "待处理" },
            { "#type": "aws_status_indicator", "#status_type": "in-progress", "#content": "进行中" },
            { "#type": "aws_status_indicator", "#status_type": "loading", "#content": "加载中" }
          ]
        }
      ]
    }
  }
}
```

### 3. 表格状态

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
            { "#type": "aws_status_indicator", "#status_type": "success", "#content": "运行中" },
            { "#type": "aws_status_indicator", "#status_type": "warning", "#content": "存储空间不足" },
            { "#type": "aws_status_indicator", "#status_type": "error", "#content": "连接失败" }
          ]
        }
      ]
    }
  }
}
```

### 4. 卡片状态

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
            { "#type": "aws_status_indicator", "#status_type": "success", "#content": "在线" },
            { "#type": "aws_status_indicator", "#status_type": "stopped", "#content": "离线" }
          ]
        }
      ]
    }
  }
}
```

### 5. 不换行

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "info",
          "#wrap_text": false,
          "#content": "这是一个很长的状态文本如果超出容器宽度将会被截断"
        }
      ]
    }
  }
}
```

### 6. 换行（默认）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "info",
          "#wrap_text": true,
          "#content": "这是一个很长的状态文本\n它会在容器宽度不够时自动换行显示"
        }
      ]
    }
  }
}
```

### 7. 颜色覆盖

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "success",
          "#color_override": "blue",
          "#content": "蓝色成功"
        }
      ]
    }
  }
}
```

### 8. 带图标标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "success",
          "#icon_aria_label": "成功状态",
          "#content": "部署成功"
        }
      ]
    }
  }
}
```

### 9. 订单状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_status_indicator", "#status_type": "success", "#content": "已支付" },
        { "#type": "aws_status_indicator", "#status_type": "in-progress", "#content": "处理中" },
        { "#type": "aws_status_indicator", "#status_type": "pending", "#content": "待发货" },
        { "#type": "aws_status_indicator", "#status_type": "pending", "#content": "已发货" },
        { "#type": "aws_status_indicator", "#status_type": "success", "#content": "已完成" }
      ]
    }
  }
}
```

### 10. 服务状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_status_indicator", "#status_type": "success", "#content": "服务正常" },
        { "#type": "aws_status_indicator", "#status_type": "warning", "#content": "部分降级" },
        { "#type": "aws_status_indicator", "#status_type": "error", "#content": "服务不可用" }
      ]
    }
  }
}
```

### 11. 部署状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_status_indicator",
          "#status_type": "in-progress",
          "#content": "部署中..."
        }
      ]
    }
  }
}
```

### 12. 任务状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_status_indicator", "#status_type": "success", "#content": "已完成" },
        { "#type": "aws_status_indicator", "#status_type": "error", "#content": "已失败" },
        { "#type": "aws_status_indicator", "#status_type": "stopped", "#content": "已取消" }
      ]
    }
  }
}
```

### 13. 账户状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_status_indicator", "#status_type": "success", "#content": "正常" },
        { "#type": "aws_status_indicator", "#status_type": "warning", "#content": "即将过期" },
        { "#type": "aws_status_indicator", "#status_type": "error", "#content": "已过期" }
      ]
    }
  }
}
```

### 14. 用户状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_status_indicator", "#status_type": "success", "#content": "活跃" },
        { "#type": "aws_status_indicator", "#status_type": "info", "#content": "未激活" },
        { "#type": "aws_status_indicator", "#status_type": "stopped", "#content": "已禁用" }
      ]
    }
  }
}
```

### 15. 同步状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_status_indicator", "#status_type": "success", "#content": "已同步" },
        { "#type": "aws_status_indicator", "#status_type": "in-progress", "#content": "同步中" },
        { "#type": "aws_status_indicator", "#status_type": "warning", "#content": "同步延迟" }
      ]
    }
  }
}
```
