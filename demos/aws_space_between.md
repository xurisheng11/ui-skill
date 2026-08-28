# aws_space_between 示例

本文档展示 aws_space_between 组件的各种使用场景。

## 示例列表

### 1. 水平间距

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
            { "#type": "aws_button", "#text": "按钮1" },
            { "#type": "aws_button", "#text": "按钮2" },
            { "#type": "aws_button", "#text": "按钮3" }
          ]
        }
      ]
    }
  }
}
```

### 2. 垂直间距

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
          "#content": [
            { "#type": "aws_button", "#text": "按钮1" },
            { "#type": "aws_button", "#text": "按钮2" },
            { "#type": "aws_button", "#text": "按钮3" }
          ]
        }
      ]
    }
  }
}
```

### 3. 不同间距大小

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
          "#size": "xs",
          "#content": [
            { "#type": "aws_icon", "#name": "star-filled" },
            { "#type": "aws_icon", "#name": "star-filled" },
            { "#type": "aws_icon", "#name": "star-filled" },
            { "#type": "aws_icon", "#name": "star-filled" },
            { "#type": "aws_icon", "#name": "star" }
          ]
        }
      ]
    }
  }
}
```

### 4. 居中对齐

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
          "#align_items": "center",
          "#content": [
            { "#type": "aws_icon", "#name": "settings" },
            { "#type": "aws_button", "#text": "设置" }
          ]
        }
      ]
    }
  }
}
```

### 5. 大间距

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
          "#size": "xl",
          "#content": [
            { "#type": "aws_link", "#href": "#", "#content": "首页" },
            { "#type": "aws_link", "#href": "#", "#content": "产品" },
            { "#type": "aws_link", "#href": "#", "#content": "关于" },
            { "#type": "aws_link", "#href": "#", "#content": "联系" }
          ]
        }
      ]
    }
  }
}
```

### 6. 小间距图标

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
          "#size": "xxs",
          "#content": [
            { "#type": "aws_icon", "#name": "file" },
            { "#type": "aws_icon", "#name": "file" },
            { "#type": "aws_icon", "#name": "file" }
          ]
        }
      ]
    }
  }
}
```

### 7. 起始对齐

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
          "#size": "s",
          "#align_items": "start",
          "#content": [
            { "#type": "aws_icon", "#name": "folder" },
            { "#type": "aws_text_content", "#content": { "#markup": "<span>文件夹名称</span>" } }
          ]
        }
      ]
    }
  }
}
```

### 8. 结束对齐

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
          "#align_items": "end",
          "#content": [
            { "#type": "aws_text_content", "#content": { "#markup": "<span>操作</span>" } },
            {
              "#type": "aws_space_between",
              "#direction": "horizontal",
              "#size": "xs",
              "#content": [
                { "#type": "aws_icon", "#name": "edit" },
                { "#type": "aws_icon", "#name": "close" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 9. 无间距

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
          "#content": [
            { "#type": "aws_icon", "#name": "check" },
            { "#type": "aws_icon", "#name": "check" },
            { "#type": "aws_icon", "#name": "check" }
          ]
        }
      ]
    }
  }
}
```

### 10. 卡片间距

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
            { "#type": "aws_text_content", "#content": { "#markup": "<div>卡片1</div>" } },
            { "#type": "aws_text_content", "#content": { "#markup": "<div>卡片2</div>" } },
            { "#type": "aws_text_content", "#content": { "#markup": "<div>卡片3</div>" } }
          ]
        }
      ]
    }
  }
}
```

### 11. 表单项间距

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
          "#content": [
            { "#type": "aws_form_field", "#label": "姓名", "#control": { "name": { "#type": "aws_input" } } },
            { "#type": "aws_form_field", "#label": "邮箱", "#control": { "email": { "#type": "aws_input" } } },
            { "#type": "aws_form_field", "#label": "电话", "#control": { "phone": { "#type": "aws_input" } } }
          ]
        }
      ]
    }
  }
}
```

### 12. 导航菜单

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
            { "#type": "aws_link", "#href": "#", "#content": "首页" },
            { "#type": "aws_link", "#href": "#", "#content": "产品" },
            { "#type": "aws_link", "#href": "#", "#content": "服务" },
            { "#type": "aws_link", "#href": "#", "#content": "关于" }
          ]
        }
      ]
    }
  }
}
```

### 13. 按钮组

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
          "#size": "s",
          "#content": [
            { "#type": "aws_button", "#text": "保存" },
            { "#type": "aws_button", "#text": "取消", "#variant": "normal" }
          ]
        }
      ]
    }
  }
}
```

### 14. 列表项

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
            { "#type": "aws_text_content", "#content": { "#markup": "<div>列表项1</div>" } },
            { "#type": "aws_text_content", "#content": { "#markup": "<div>列表项2</div>" } },
            { "#type": "aws_text_content", "#content": { "#markup": "<div>列表项3</div>" } }
          ]
        }
      ]
    }
  }
}
```

### 15. 超大间距

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
          "#size": "xxl",
          "#content": [
            { "#type": "aws_icon", "#name": "star" },
            { "#type": "aws_icon", "#name": "star" },
            { "#type": "aws_icon", "#name": "star" }
          ]
        }
      ]
    }
  }
}
```
