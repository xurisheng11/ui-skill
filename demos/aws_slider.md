# aws_slider 示例

本文档展示 aws_slider 组件的各种使用场景。

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
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#default_value": 50
        }
      ]
    }
  }
}
```

### 2. 带步长

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#step": 10,
          "#default_value": 30
        }
      ]
    }
  }
}
```

### 3. 带刻度

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#step": 25,
          "#tick_marks": true,
          "#default_value": 50
        }
      ]
    }
  }
}
```

### 4. 隐藏填充线

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#hide_fill_line": true,
          "#default_value": 50
        }
      ]
    }
  }
}
```

### 5. 带参考值

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#reference_values": [25, 50, 75],
          "#default_value": 50
        }
      ]
    }
  }
}
```

### 6. 音量控制

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#step": 5,
          "#default_value": 70
        }
      ]
    }
  }
}
```

### 7. 价格范围

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 10000,
          "#min": 0,
          "#step": 100,
          "#default_value": 5000,
          "#reference_values": [2500, 5000, 7500]
        }
      ]
    }
  }
}
```

### 8. 透明度滑块

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#default_value": 100,
          "#tick_marks": true
        }
      ]
    }
  }
}
```

### 9. 禁用状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#disabled": true,
          "#default_value": 50
        }
      ]
    }
  }
}
```

### 10. 只读状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#read_only": true,
          "#default_value": 75
        }
      ]
    }
  }
}
```

### 11. 无效状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#invalid": true,
          "#default_value": 50
        }
      ]
    }
  }
}
```

### 12. 亮度调节

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#step": 1,
          "#default_value": 80
        }
      ]
    }
  }
}
```

### 13. 进度百分比

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#step": 5,
          "#tick_marks": true,
          "#default_value": 65
        }
      ]
    }
  }
}
```

### 14. 评分滑块

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 5,
          "#min": 1,
          "#step": 1,
          "#default_value": 4
        }
      ]
    }
  }
}
```

### 15. 速度控制

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_slider",
          "#max": 100,
          "#min": 0,
          "#step": 10,
          "#default_value": 50
        }
      ]
    }
  }
}
```
