# aws_column_layout

AWS 列布局组件，用于创建响应式的多列网格布局。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| columns | 数字 | 否 | 指定网格每一行中的列数。当未设置 min_column_width 时，最多支持 4 列 | - | 1 |
| min_column_width | 数字 | 否 | 每列期望的最小宽度（像素），与 columns 配合使用决定列数 | - | - |
| disable_gutters | 布尔值 | 否 | 决定是否移除列之间的默认间隔 | - | false |
| borders | 字符串 | 否 | 控制是否在行和列之间放置分隔线 | none / vertical / horizontal / all | "none" |
| variant | 字符串 | 否 | 指定内容类型，决定网格的间距 | default / text-grid | "default" |

### borders 可选值说明

| 值 | 描述 |
| --- | --- |
| none | 无分隔线 |
| vertical | 仅垂直分隔线 |
| horizontal | 仅水平分隔线 |
| all | 水平和垂直分隔线都有 |

### variant 可选值说明

| 值 | 描述 |
| --- | --- |
| default | 默认间距 |
| text-grid | 文本网格间距 |

## content 内容说明

content 属性支持两种格式：

1. **字符串格式**：HTML 内容字符串
2. **数组格式**：嵌入其他 AWS 组件的数组

## 使用示例

### 基础用法 - 字符串内容

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 3,
          "#content": "<div>内容1</div><div>内容2</div><div>内容3</div><div>内容4</div><div>内容5</div><div>内容6</div>"
        }
      ]
    }
  }
}
```

### 基础用法 - 数组内容（嵌入组件）

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 2,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "文本对齐" },
            { "#type": "aws_box", "#variant": "div", "#content": "文本对齐" },
            { "#type": "aws_box", "#variant": "div", "#content": "文本对齐" },
            { "#type": "aws_box", "#variant": "div", "#content": "文本对齐" }
          ]
        }
      ]
    }
  }
}
```

### 单列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 1,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "全宽内容区块" }
          ]
        }
      ]
    }
  }
}
```

### 两列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 2,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "左侧内容" },
            { "#type": "aws_box", "#variant": "div", "#content": "右侧内容" }
          ]
        }
      ]
    }
  }
}
```

### 三列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 3,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "第一列" },
            { "#type": "aws_box", "#variant": "div", "#content": "第二列" },
            { "#type": "aws_box", "#variant": "div", "#content": "第三列" }
          ]
        }
      ]
    }
  }
}
```

### 四列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 4,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "第一列" },
            { "#type": "aws_box", "#variant": "div", "#content": "第二列" },
            { "#type": "aws_box", "#variant": "div", "#content": "第三列" },
            { "#type": "aws_box", "#variant": "div", "#content": "第四列" }
          ]
        }
      ]
    }
  }
}
```

### 带最小列宽

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 4,
          "#min_column_width": 200,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "列内容" },
            { "#type": "aws_box", "#variant": "div", "#content": "列内容" },
            { "#type": "aws_box", "#variant": "div", "#content": "列内容" },
            { "#type": "aws_box", "#variant": "div", "#content": "列内容" }
          ]
        }
      ]
    }
  }
}
```

### 移除列间隔

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 3,
          "#disable_gutters": true,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "无间隔内容1" },
            { "#type": "aws_box", "#variant": "div", "#content": "无间隔内容2" },
            { "#type": "aws_box", "#variant": "div", "#content": "无间隔内容3" }
          ]
        }
      ]
    }
  }
}
```

### 垂直分隔线

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 3,
          "#borders": "vertical",
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "第一列" },
            { "#type": "aws_box", "#variant": "div", "#content": "第二列" },
            { "#type": "aws_box", "#variant": "div", "#content": "第三列" }
          ]
        }
      ]
    }
  }
}
```

### 水平分隔线

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 2,
          "#borders": "horizontal",
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "行1-列1" },
            { "#type": "aws_box", "#variant": "div", "#content": "行1-列2" },
            { "#type": "aws_box", "#variant": "div", "#content": "行2-列1" },
            { "#type": "aws_box", "#variant": "div", "#content": "行2-列2" }
          ]
        }
      ]
    }
  }
}
```

### 全部分隔线

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 2,
          "#borders": "all",
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "单元格1" },
            { "#type": "aws_box", "#variant": "div", "#content": "单元格2" },
            { "#type": "aws_box", "#variant": "div", "#content": "单元格3" },
            { "#type": "aws_box", "#variant": "div", "#content": "单元格4" }
          ]
        }
      ]
    }
  }
}
```

### 文本网格变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 3,
          "#variant": "text-grid",
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "文本1" },
            { "#type": "aws_box", "#variant": "div", "#content": "文本2" },
            { "#type": "aws_box", "#variant": "div", "#content": "文本3" }
          ]
        }
      ]
    }
  }
}
```

### 仪表盘布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 4,
          "#borders": "vertical",
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "总用户数" },
            { "#type": "aws_box", "#variant": "div", "#content": "活跃用户" },
            { "#type": "aws_box", "#variant": "div", "#content": "总收入" },
            { "#type": "aws_box", "#variant": "div", "#content": "转化率" }
          ]
        }
      ]
    }
  }
}
```

### 表单布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_column_layout",
          "#columns": 2,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "姓名" },
            { "#type": "aws_box", "#variant": "div", "#content": "邮箱" },
            { "#type": "aws_box", "#variant": "div", "#content": "电话" },
            { "#type": "aws_box", "#variant": "div", "#content": "地址" }
          ]
        }
      ]
    }
  }
}
```
