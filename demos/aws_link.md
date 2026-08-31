# aws_link 示例

本文档展示 aws_link 组件的各种使用场景。

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
          "#type": "aws_link",
          "#href": "#",
          "#content": "点击这里"
        }
      ]
    }
  }
}
```

### 2. 外部链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#href": "https://www.example.com",
          "#content": "访问官方网站",
          "#external": true,
          "#target": "_blank"
        }
      ]
    }
  }
}
```

### 3. 主要链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#href": "#",
          "#variant": "primary",
          "#content": "了解更多"
        }
      ]
    }
  }
}
```

### 4. 信息链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#variant": "info",
          "#content": "查看帮助"
        }
      ]
    }
  }
}
```

### 5. CNAME链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#href": "#",
          "#content": "abc.service.example.com",
          "#external": true
        }
      ]
    }
  }
}
```

### 6. 不同字体大小

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
            { "#type": "aws_link", "#href": "#", "#font_size": "body-s", "#content": "小号文本链接" },
            { "#type": "aws_link", "#href": "#", "#font_size": "body-m", "#content": "中号文本链接" },
            { "#type": "aws_link", "#href": "#", "#font_size": "heading-s", "#content": "标题S链接" }
          ]
        }
      ]
    }
  }
}
```

### 7. 链接列表

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
            { "#type": "aws_link", "#href": "#", "#content": "用户协议" },
            { "#type": "aws_link", "#href": "#", "#content": "隐私政策" },
            { "#type": "aws_link", "#href": "#", "#content": "联系客服" }
          ]
        }
      ]
    }
  }
}
```

### 8. 导航链接组

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
            { "#type": "aws_link", "#href": "/home", "#content": "首页" },
            { "#type": "aws_link", "#href": "/products", "#content": "产品" },
            { "#type": "aws_link", "#href": "/about", "#content": "关于" },
            { "#type": "aws_link", "#href": "/contact", "#content": "联系" }
          ]
        }
      ]
    }
  }
}
```

### 9. 无href链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#content": "这是一个按钮式链接"
        }
      ]
    }
  }
}
```

### 10. 反色链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#href": "#",
          "#color": "inverted",
          "#content": "了解更多"
        }
      ]
    }
  }
}
```

### 11. 次要链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#href": "#",
          "#variant": "secondary",
          "#content": "次要操作"
        }
      ]
    }
  }
}
```

### 12. 大值链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#href": "#",
          "#variant": "awsui-value-large",
          "#content": "大号值链接"
        }
      ]
    }
  }
}
```

### 13. 下载链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_link",
          "#href": "#",
          "#content": "下载文档"
        }
      ]
    }
  }
}
```

### 14. 文档链接

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
            { "#type": "aws_link", "#href": "#", "#content": "快速开始指南" },
            { "#type": "aws_link", "#href": "#", "#content": "API 参考文档" },
            { "#type": "aws_link", "#href": "#", "#content": "最佳实践" },
            { "#type": "aws_link", "#href": "#", "#content": "常见问题" }
          ]
        }
      ]
    }
  }
}
```

### 15. 底部链接

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
          "#size": "m",
          "#content": [
            { "#type": "aws_link", "#href": "#", "#content": "关于我们" },
            { "#type": "aws_link", "#href": "#", "#content": "隐私政策" },
            { "#type": "aws_link", "#href": "#", "#content": "使用条款" },
            { "#type": "aws_link", "#href": "#", "#content": "网站地图" }
          ]
        }
      ]
    }
  }
}
```
