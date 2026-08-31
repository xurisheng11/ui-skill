# Aws Box Demo

## 基础示例

### 彩色标题文本

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

## 进阶示例

### 带内边距的内容块

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
          "#content": "这是一个带有大内边距的内容块"
        }
      ]
    }
  }
}
```

### 卡片样式的盒子

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
          "#margin": "m",
          "#variant": "div",
          "#content": {
            "#type": "aws_header",
            "#headingText": "卡片标题"
          }
        },
        {
          "#type": "aws_box",
          "#padding": "m",
          "#variant": "div",
          "#content": "卡片内容区域，可以包含任意组件和文本。"
        }
      ]
    }
  }
}
```

### 多种颜色状态

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
          "#variant": "strong",
          "#content": "错误：操作失败"
        },
        {
          "#type": "aws_box",
          "#color": "text-status-warning",
          "#variant": "strong",
          "#content": "警告：请检查输入"
        },
        {
          "#type": "aws_box",
          "#color": "text-status-info",
          "#variant": "strong",
          "#content": "提示：信息已保存"
        },
        {
          "#type": "aws_box",
          "#color": "text-status-success",
          "#variant": "strong",
          "#content": "成功：任务完成"
        }
      ]
    }
  }
}
```

### 字体样式

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
          "#font_weight": "bold",
          "#content": "超大加粗标题"
        },
        {
          "#type": "aws_box",
          "#font_size": "heading_m",
          "#font_weight": "normal",
          "#content": "中等普通标题"
        },
        {
          "#type": "aws_box",
          "#font_size": "body_m",
          "#font_weight": "light",
          "#content": "正文轻量文本"
        }
      ]
    }
  }
}
```

### 对齐方式

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
          "#text_align": "left",
          "#content": "左对齐文本"
        },
        {
          "#type": "aws_box",
          "#text_align": "center",
          "#content": "居中文本"
        },
        {
          "#type": "aws_box",
          "#text_align": "right",
          "#content": "右对齐文本"
        }
      ]
    }
  }
}
```

### 不同 HTML 标签

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
          "#variant": "h1",
          "#content": "一级标题 H1"
        },
        {
          "#type": "aws_box",
          "#variant": "h2",
          "#content": "二级标题 H2"
        },
        {
          "#type": "aws_box",
          "#variant": "h3",
          "#content": "三级标题 H3"
        },
        {
          "#type": "aws_box",
          "#variant": "strong",
          "#content": "加粗文本"
        },
        {
          "#type": "aws_box",
          "#variant": "small",
          "#content": "小号文本"
        },
        {
          "#type": "aws_box",
          "#variant": "code",
          "#content": "代码文本"
        }
      ]
    }
  }
}
```

### 组合布局

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
          "#margin": "m",
          "#display": "inline_block",
          "#variant": "div",
          "#content": "组件 A"
        },
        {
          "#type": "aws_box",
          "#padding": "m",
          "#margin": "m",
          "#display": "inline_block",
          "#variant": "div",
          "#content": "组件 B"
        },
        {
          "#type": "aws_box",
          "#padding": "m",
          "#margin": "m",
          "#display": "inline_block",
          "#variant": "div",
          "#content": "组件 C"
        }
      ]
    }
  }
}
```
