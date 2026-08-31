# aws_box

AWS 盒子组件，用于创建具有边界和背景色的容器，常用来包裹其他组件以提供视觉上的分离。

## 参数说明

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| variant | 字符串 | 否 | 定义元素样式 | div / span / h1-h5 / p / strong / small / code / pre / samp / awsui_key_label / awsui_gen_ai_label / awsui_value_large | "div" |
| color | 字符串 | 否 | 覆盖文本颜色 | inherit / text-label / text-body-secondary / text-status-error / text-status-success / text-status-info / text-status-inactive / text-status-warning | - |
| display | 字符串 | 否 | 覆盖元素的显示方式 | block / inline / inline_block / none | - |
| float | 字符串 | 否 | 定义浮动行为 | left / right | - |
| font_size | 字符串 | 否 | 覆盖字体大小和行高 | body_s / body_m / heading_xs / heading_s / heading_m / heading_l / heading_xl / display_l | - |
| font_weight | 字符串 | 否 | 覆盖字体粗细 | light / normal / bold / heavy | - |
| margin | 字符串/对象 | 否 | 向元素添加边距 | - | - |
| padding | 字符串/对象 | 否 | 向元素添加填充 | - | - |
| tag_override | 字符串 | 否 | 覆盖默认 HTML 标签 | - | - |
| text_align | 字符串 | 否 | 定义元素内文本的对齐方式 | left / center / right | - |
| content | 字符串/组件 | 否 | 元素内容，若想使用变量或方法，请用 #markup 属性包裹 | - | - |

## margin/padding 大小值

可用值：`n` (无) / `xxxs` / `xxs` / `xs` / `s` / `m` / `l` / `xl` / `xxl` / `xxxl`

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
          "#type": "aws_box",
          "#color": "text-status-success",
          "#variant": "h1",
          "#content": "文本111111111"
        }
      ]
    }
  }
}
```

### 带内边距的盒子

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#padding": "l",
          "#variant": "div",
          "#content": "带有大内边距的盒子内容"
        }
      ]
    }
  }
}
```

### 带外边距的盒子

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#margin": {"vertical": "m", "horizontal": "l"},
          "#variant": "div",
          "#content": "带外边距的盒子"
        }
      ]
    }
  }
}
```

### 不同颜色文本

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#color": "text-status-error",
          "#content": "错误状态文本"
        },
        {
          "#type": "aws_box",
          "#color": "text-status-warning",
          "#content": "警告状态文本"
        },
        {
          "#type": "aws_box",
          "#color": "text-status-info",
          "#content": "信息状态文本"
        },
        {
          "#type": "aws_box",
          "#color": "text-status-success",
          "#content": "成功状态文本"
        }
      ]
    }
  }
}
```

### 不同字体大小

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#font_size": "heading_xl",
          "#variant": "div",
          "#content": "超大标题"
        },
        {
          "#type": "aws_box",
          "#font_size": "heading_m",
          "#variant": "div",
          "#content": "中等标题"
        },
        {
          "#type": "aws_box",
          "#font_size": "body_s",
          "#variant": "div",
          "#content": "小号正文"
        }
      ]
    }
  }
}
```

### 包裹其他组件

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#padding": "m",
          "#variant": "div",
          "#content": {
            "#type": "aws_button",
            "#text": "点击我"
          }
        }
      ]
    }
  }
}
```

### 隐藏盒子

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#display": "none",
          "#content": "这个盒子不会显示"
        }
      ]
    }
  }
}
```
