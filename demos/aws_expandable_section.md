# aws_expandable_section 示例

本文档展示 aws_expandable_section 组件的各种使用场景。

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
          "#type": "aws_expandable_section",
          "#header_text": "点击展开",
          "#content": "这是展开后的内容区域。"
        }
      ]
    }
  }
}
```

### 2. 带操作按钮

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#header_text": "设置选项",
          "#header_actions": {
            "#type": "aws_button",
            "#text": "保存"
          },
          "#content": "这里是设置选项的具体内容。"
        }
      ]
    }
  }
}
```

### 3. 容器变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#variant": "container",
          "#header_text": "详细信息",
          "#header_description": "查看更多详细信息",
          "#header_counter": "(3)",
          "#content": "详细的容器内容..."
        }
      ]
    }
  }
}
```

### 4. 默认展开

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#default_expanded": true,
          "#header_text": "默认展开的区域",
          "#content": "此区域在页面加载时默认展开显示。"
        }
      ]
    }
  }
}
```

### 5. FAQ 场景

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#header_text": "如何重置密码？",
          "#content": "访问登录页面，点击\"忘记密码\"链接。"
        },
        {
          "#type": "aws_expandable_section",
          "#header_text": "如何联系客服？",
          "#content": "拨打客服热线：400-xxx-xxxx"
        }
      ]
    }
  }
}
```

### 6. 配置面板

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#variant": "container",
          "#header_text": "基础配置",
          "#content": "基础配置的具体选项..."
        },
        {
          "#type": "aws_expandable_section",
          "#variant": "container",
          "#header_text": "高级配置",
          "#content": "高级配置的具体选项..."
        }
      ]
    }
  }
}
```

### 7. 导航变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#variant": "navigation",
          "#header_text": "导航菜单",
          "#content": "导航菜单内容..."
        }
      ]
    }
  }
}
```

### 8. 页脚变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#variant": "footer",
          "#header_text": "更多信息",
          "#content": "页脚内容..."
        }
      ]
    }
  }
}
```

### 9. 内联变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#variant": "inline",
          "#header_text": "内联区域",
          "#content": "减少内边距的内联内容..."
        }
      ]
    }
  }
}
```

### 10. 堆叠变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#variant": "stacked",
          "#header_text": "堆叠区域1",
          "#content": "堆叠内容1..."
        },
        {
          "#type": "aws_expandable_section",
          "#variant": "stacked",
          "#header_text": "堆叠区域2",
          "#content": "堆叠内容2..."
        }
      ]
    }
  }
}
```

### 11. 带标题标签覆盖

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#variant": "container",
          "#heading_tag_override": "h3",
          "#header_text": "H3 标题",
          "#content": "使用H3标签的内容..."
        }
      ]
    }
  }
}
```

### 12. 多级内容

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#header_text": "章节一",
          "#content": "章节一的内容..."
        },
        {
          "#type": "aws_expandable_section",
          "#header_text": "章节二",
          "#content": "章节二的内容..."
        },
        {
          "#type": "aws_expandable_section",
          "#header_text": "章节三",
          "#content": "章节三的内容..."
        }
      ]
    }
  }
}
```

### 13. 带信息链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#header_text": "系统要求",
          "#header_info": "查看完整要求",
          "#content": "最低系统要求：\n- 内存：4GB\n- 硬盘：10GB可用空间"
        }
      ]
    }
  }
}
```

### 14. 产品特性

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#default_expanded": true,
          "#header_text": "核心功能",
          "#content": "1. 数据分析\n2. 报表生成\n3. 实时监控"
        },
        {
          "#type": "aws_expandable_section",
          "#header_text": "安全特性",
          "#content": "1. 数据加密\n2. 访问控制\n3. 审计日志"
        },
        {
          "#type": "aws_expandable_section",
          "#header_text": "集成能力",
          "#content": "1. REST API\n2. Webhook\n3. 单点登录"
        }
      ]
    }
  }
}
```

### 15. 许可证信息

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_expandable_section",
          "#header_text": "许可证协议",
          "#header_actions": {
            "#type": "aws_link",
            "#content": "查看完整协议",
            "#href": "#"
          },
          "#content": "本软件遵循MIT许可证条款..."
        }
      ]
    }
  }
}
```
