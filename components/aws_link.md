# aws_link

链接组件，用于创建各种类型的链接。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| href | 字符串 | 否 | 链接URL |
| content | 字符串/组件 | 否 | 链接内容 |
| variant | 字符串 | 否 | 视觉样式变体 |
| color | 字符串 | 否 | 文本颜色 |
| external | 布尔值 | 否 | 是否为外部链接 |
| target | 字符串 | 否 | 链接打开位置 |
| rel | 字符串 | 否 | rel属性 |
| font_size | 字符串 | 否 | 字体大小 |
| aria_label | 字符串 | 否 | aria-label |
| external_icon_aria_label | 字符串 | 否 | 外部图标aria-label |

### variant 可选值

- `primary` - 主要链接（粗体）
- `secondary` - 次要链接（默认）
- `info` - 信息链接
- `awsui-value-large` - 大号值链接

### color 可选值

- `normal` - 正常颜色
- `inverted` - 反转颜色（用于Flashbars）

### font_size 可选值

- `body-s`, `body-m`
- `heading-xs`, `heading-s`, `heading-m`, `heading-l`, `heading-xl`, `display-l`
- `inherit`

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
          "#type": "aws_link",
          "#href": "#",
          "#content": "点击这里"
        }
      ]
    }
  }
}
```

### 外部链接

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

### 主要链接

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

### 信息链接

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
          "#type": "aws_space_between",
          "#direction": "vertical",
          "#size": "s",
          "#content": [
            {
              "#type": "aws_link",
              "#href": "#",
              "#font_size": "body-s",
              "#content": "小号文本链接"
            },
            {
              "#type": "aws_link",
              "#href": "#",
              "#font_size": "body-m",
              "#content": "中号文本链接"
            },
            {
              "#type": "aws_link",
              "#href": "#",
              "#font_size": "heading-s",
              "#content": "标题S链接"
            },
            {
              "#type": "aws_link",
              "#href": "#",
              "#font_size": "heading-m",
              "#content": "标题M链接"
            }
          ]
        }
      ]
    }
  }
}
```

### CNAME链接

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

### 带图标链接

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

### 反色链接

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

### 无href链接

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

### 链接列表

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
            {
              "#type": "aws_link",
              "#href": "#",
              "#content": "用户协议"
            },
            {
              "#type": "aws_link",
              "#href": "#",
              "#content": "隐私政策"
            },
            {
              "#type": "aws_link",
              "#href": "#",
              "#content": "联系客服"
            }
          ]
        }
      ]
    }
  }
}
```

### 导航链接组

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
              "#type": "aws_link",
              "#href": "/home",
              "#content": "首页"
            },
            {
              "#type": "aws_link",
              "#href": "/products",
              "#content": "产品"
            },
            {
              "#type": "aws_link",
              "#href": "/about",
              "#content": "关于"
            },
            {
              "#type": "aws_link",
              "#href": "/contact",
              "#content": "联系"
            }
          ]
        }
      ]
    }
  }
}
```
