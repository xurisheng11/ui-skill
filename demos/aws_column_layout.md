# aws_column_layout 示例

本文档展示 aws_column_layout 组件的各种使用场景。

## 示例列表

### 1. 基础用法 - 字符串内容

展示如何使用 HTML 字符串作为内容。

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
          "#content": "<div>Content</div><div>Content</div><div>Content</div><div>Content</div><div>Content</div><div>Content</div><div>Content</div><div>Content</div>"
        }
      ]
    }
  }
}
```

### 2. 基础用法 - 数组内容

展示如何嵌入其他组件作为内容。

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

### 3. 两列布局

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
            { "#type": "aws_box", "#variant": "div", "#content": "左侧边栏" },
            { "#type": "aws_box", "#variant": "div", "#content": "主内容区域" }
          ]
        }
      ]
    }
  }
}
```

### 4. 三列布局

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
            { "#type": "aws_box", "#variant": "div", "#content": "左侧导航" },
            { "#type": "aws_box", "#variant": "div", "#content": "主内容" },
            { "#type": "aws_box", "#variant": "div", "#content": "右侧边栏" }
          ]
        }
      ]
    }
  }
}
```

### 5. 四列布局

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
            { "#type": "aws_box", "#variant": "div", "#content": "指标1" },
            { "#type": "aws_box", "#variant": "div", "#content": "指标2" },
            { "#type": "aws_box", "#variant": "div", "#content": "指标3" },
            { "#type": "aws_box", "#variant": "div", "#content": "指标4" }
          ]
        }
      ]
    }
  }
}
```

### 6. 带垂直分隔线

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

### 7. 带水平分隔线

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
            { "#type": "aws_box", "#variant": "div", "#content": "区块1" },
            { "#type": "aws_box", "#variant": "div", "#content": "区块2" },
            { "#type": "aws_box", "#variant": "div", "#content": "区块3" },
            { "#type": "aws_box", "#variant": "div", "#content": "区块4" }
          ]
        }
      ]
    }
  }
}
```

### 8. 带全部分隔线

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
          "#borders": "all",
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "单元格1" },
            { "#type": "aws_box", "#variant": "div", "#content": "单元格2" },
            { "#type": "aws_box", "#variant": "div", "#content": "单元格3" },
            { "#type": "aws_box", "#variant": "div", "#content": "单元格4" },
            { "#type": "aws_box", "#variant": "div", "#content": "单元格5" },
            { "#type": "aws_box", "#variant": "div", "#content": "单元格6" }
          ]
        }
      ]
    }
  }
}
```

### 9. 移除列间隔

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
          "#disable_gutters": true,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "无间隔1" },
            { "#type": "aws_box", "#variant": "div", "#content": "无间隔2" },
            { "#type": "aws_box", "#variant": "div", "#content": "无间隔3" },
            { "#type": "aws_box", "#variant": "div", "#content": "无间隔4" }
          ]
        }
      ]
    }
  }
}
```

### 10. 最小列宽

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
          "#min_column_width": 150,
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "最小宽度列1" },
            { "#type": "aws_box", "#variant": "div", "#content": "最小宽度列2" },
            { "#type": "aws_box", "#variant": "div", "#content": "最小宽度列3" }
          ]
        }
      ]
    }
  }
}
```

### 11. 文本网格变体

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
          "#variant": "text-grid",
          "#content": [
            { "#type": "aws_box", "#variant": "div", "#content": "标题A" },
            { "#type": "aws_box", "#variant": "div", "#content": "内容A" },
            { "#type": "aws_box", "#variant": "div", "#content": "标题B" },
            { "#type": "aws_box", "#variant": "div", "#content": "内容B" }
          ]
        }
      ]
    }
  }
}
```

### 12. 仪表盘统计卡片

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
            { "#type": "aws_box", "#variant": "div", "#content": "总访问量\n10,000" },
            { "#type": "aws_box", "#variant": "div", "#content": "活跃用户\n1,234" },
            { "#type": "aws_box", "#variant": "div", "#content": "总收入\n¥50,000" },
            { "#type": "aws_box", "#variant": "div", "#content": "转化率\n5.6%" }
          ]
        }
      ]
    }
  }
}
```

### 13. 表单双列布局

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
            { "#type": "aws_box", "#variant": "div", "#content": "姓" },
            { "#type": "aws_box", "#variant": "div", "#content": "名" },
            { "#type": "aws_box", "#variant": "div", "#content": "邮箱" },
            { "#type": "aws_box", "#variant": "div", "#content": "电话" },
            { "#type": "aws_box", "#variant": "div", "#content": "公司" },
            { "#type": "aws_box", "#variant": "div", "#content": "职位" }
          ]
        }
      ]
    }
  }
}
```

### 14. 卡片网格布局

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
            { "#type": "aws_box", "#variant": "div", "#content": "产品卡片1" },
            { "#type": "aws_box", "#variant": "div", "#content": "产品卡片2" },
            { "#type": "aws_box", "#variant": "div", "#content": "产品卡片3" },
            { "#type": "aws_box", "#variant": "div", "#content": "产品卡片4" },
            { "#type": "aws_box", "#variant": "div", "#content": "产品卡片5" },
            { "#type": "aws_box", "#variant": "div", "#content": "产品卡片6" }
          ]
        }
      ]
    }
  }
}
```
