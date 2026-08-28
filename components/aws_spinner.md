# aws_spinner

加载指示器组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| size | 字符串 | 否 | 加载指示器大小 |
| variant | 字符串 | 否 | 颜色变体 |

### size 可选值

- `normal` - 默认大小
- `big` - 大尺寸
- `large` - 最大尺寸

### variant 可选值

- `normal` - 正常颜色
- `disabled` - 禁用状态颜色
- `inverted` - 反转颜色

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
          "#type": "aws_spinner"
        }
      ]
    }
  }
}
```

### 不同尺寸

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
            {
              "#type": "aws_spinner",
              "#size": "normal"
            },
            {
              "#type": "aws_spinner",
              "#size": "big"
            },
            {
              "#type": "aws_spinner",
              "#size": "large"
            }
          ]
        }
      ]
    }
  }
}
```

### 带文本

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
            "spinner": {
              "#type": "aws_spinner",
              "#size": "large"
            },
            "text": "加载中，请稍候..."
          }
        }
      ]
    }
  }
}
```

### 在按钮中

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button",
          "#loading": true,
          "#loading_text": "处理中..."
        }
      ]
    }
  }
}
```

### 禁用状态变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_spinner",
          "#variant": "disabled"
        }
      ]
    }
  }
}
```

### 反转变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_spinner",
          "#variant": "inverted"
        }
      ]
    }
  }
}
```

### 全屏加载

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
            "spinner": {
              "#type": "aws_spinner",
              "#size": "large"
            },
            "text": "正在加载数据..."
          }
        }
      ]
    }
  }
}
```

### 页面加载中

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
            "spinner": {
              "#type": "aws_spinner",
              "#size": "large"
            },
            "text": "页面加载中，请稍候..."
          }
        }
      ]
    }
  }
}
```
