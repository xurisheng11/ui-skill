# aws_progress_bar 示例

本文档展示 aws_progress_bar 组件的各种使用场景。

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
          "#type": "aws_progress_bar",
          "#label": "Progress bar label",
          "#input_value": 50,
          "#description": "Progress bar description"
        }
      ]
    }
  }
}
```

### 2. 不同进度

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        { "#type": "aws_progress_bar", "#input_value": 25, "#label": "下载进度" },
        { "#type": "aws_progress_bar", "#input_value": 50, "#label": "安装进度" },
        { "#type": "aws_progress_bar", "#input_value": 75, "#label": "配置进度" },
        { "#type": "aws_progress_bar", "#input_value": 100, "#label": "完成" }
      ]
    }
  }
}
```

### 3. 成功状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#status": "success",
          "#label": "部署完成",
          "#result_text": "部署成功！"
        }
      ]
    }
  }
}
```

### 4. 错误状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#status": "error",
          "#label": "操作失败",
          "#result_text": "发生了错误，请重试"
        }
      ]
    }
  }
}
```

### 5. 进行中状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#status": "in-progress",
          "#input_value": 65,
          "#label": "数据处理中",
          "#description": "正在处理您的数据，请稍候..."
        }
      ]
    }
  }
}
```

### 6. 带描述

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#input_value": 80,
          "#label": "文件上传",
          "#description": "正在上传大文件，请勿关闭页面"
        }
      ]
    }
  }
}
```

### 7. 带结果按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#status": "success",
          "#label": "任务完成",
          "#result_text": "备份成功",
          "#result_button_text": "查看详情"
        }
      ]
    }
  }
}
```

### 8. Key-Value变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#variant": "key-value",
          "#input_value": 85,
          "#label": "CPU 使用率"
        }
      ]
    }
  }
}
```

### 9. Flash变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#variant": "flash",
          "#input_value": 60,
          "#status": "in-progress",
          "#label": "处理中"
        }
      ]
    }
  }
}
```

### 10. 文件传输

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#input_value": 55,
          "#label": "文件传输",
          "#description": "正在传输：document.pdf",
          "#additional_info": "125 MB / 227 MB"
        }
      ]
    }
  }
}
```

### 11. 加载进度

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#input_value": 30,
          "#label": "页面加载",
          "#description": "正在加载资源..."
        }
      ]
    }
  }
}
```

### 12. 系统更新

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#input_value": 75,
          "#status": "in-progress",
          "#label": "系统更新",
          "#description": "正在下载并安装更新",
          "#additional_info": "预计剩余时间：3分钟"
        }
      ]
    }
  }
}
```

### 13. 完整信息

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#input_value": 45,
          "#label": "数据导入",
          "#additional_info": "已处理 1,234 条记录，共 2,789 条"
        }
      ]
    }
  }
}
```

### 14. 环形进度

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#input_value": 100,
          "#status": "success",
          "#label": "完成"
        }
      ]
    }
  }
}
```

### 15. 内存使用率

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_progress_bar",
          "#variant": "key-value",
          "#input_value": 67,
          "#label": "内存使用率"
        }
      ]
    }
  }
}
```
