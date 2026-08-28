# aws_slider

滑块组件，用于选择数值范围。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| min | 数字 | 是 | 最小值 |
| max | 数字 | 是 | 最大值 |
| default_value | 数字 | 否 | 当前值 |
| step | 数字 | 否 | 步长 |
| disabled | 布尔值 | 否 | 是否禁用 |
| read_only | 布尔值 | 否 | 只读状态 |
| invalid | 布尔值 | 否 | 无效状态 |
| hide_fill_line | 布尔值 | 否 | 隐藏填充线 |
| tick_marks | 布尔值 | 否 | 显示刻度标记 |
| reference_values | 数组 | 否 | 参考值标签 |
| value_formatter | 函数 | 否 | 值格式化函数 |

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

### 带步长

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

### 带刻度

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

### 隐藏填充线

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

### 带参考值

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

### 无效状态

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

### 音量滑块

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

### 透明度滑块

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

### 价格范围

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
