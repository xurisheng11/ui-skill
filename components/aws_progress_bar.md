# aws_progress_bar

进度条组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| input_value | 数字 | 否 | 当前进度百分比 (0-100) |
| status | 字符串 | 否 | 进度条状态 |
| variant | 字符串 | 否 | 变体类型 |
| label | 字符串 | 否 | 操作简短描述 |
| description | 字符串 | 否 | 进度条下方信息 |
| additional_info | 字符串 | 否 | 更多信息 |
| result_text | 字符串 | 否 | 结果状态文本 |
| result_button_text | 字符串 | 否 | 结果按钮文本 |

### status 可选值

- `in-progress` - 进行中
- `success` - 成功
- `error` - 错误

### variant 可选值

- `standalone` - 独立使用（默认）
- `flash` - 用于闪存组件内
- `key-value` - 用于键值对模式

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
          "#type": "aws_progress_bar",
          "#description": "Progress bar description",
          "#label": "Progress bar label",
          "#input_value": 50,
          "#additional_info": "Additional info"
        }
      ]
    }
  }
}
```

### 不同进度

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
          "#input_value": 25,
          "#label": "下载进度"
        },
        {
          "#type": "aws_progress_bar",
          "#input_value": 50,
          "#label": "安装进度"
        },
        {
          "#type": "aws_progress_bar",
          "#input_value": 75,
          "#label": "配置进度"
        },
        {
          "#type": "aws_progress_bar",
          "#input_value": 100,
          "#label": "完成"
        }
      ]
    }
  }
}
```

### 成功状态

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

### 错误状态

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

### 进行中状态

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

### 带额外信息

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

### 带结果按钮

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

### Flash变体

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

### Key-Value变体

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

### 完整信息

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

### 文件传输

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

### 加载进度

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

### 环形进度（进度环）

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
