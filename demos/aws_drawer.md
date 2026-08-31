# aws_drawer 示例

本文档展示 aws_drawer 组件的各种使用场景。

## 示例列表

### 1. 基础用法

最基本的抽屉示例。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "抽屉标题",
          "#content": "这是抽屉的内容区域，可以包含任意文本内容。"
        }
      ]
    }
  }
}
```

### 2. 带加载状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "加载中的抽屉",
          "#content": "正在加载内容...",
          "#loading": true
        }
      ]
    }
  }
}
```

### 3. 带国际化字符串

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "设置面板",
          "#content": "抽屉内容",
          "#i18n_strings": {
            "loadingText": "加载中..."
          }
        }
      ]
    }
  }
}
```

### 4. 带变量的 header

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "${drawerTitle}",
          "#content": "${drawerContent}"
        }
      ]
    }
  }
}
```

### 5. 详细设置面板

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "详细设置",
          "#content": "在此可以配置各种详细设置选项，包括用户偏好、通知设置、安全选项等。"
        }
      ]
    }
  }
}
```

### 6. 用户信息抽屉

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "用户信息",
          "#content": "姓名：张三\n邮箱：zhangsan@example.com\n角色：管理员"
        }
      ]
    }
  }
}
```

### 7. 确认对话框

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "确认操作",
          "#content": "确定要执行此操作吗？此操作无法撤销。"
        }
      ]
    }
  }
}
```

### 8. 过滤器面板

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "数据过滤器",
          "#content": "在此设置数据过滤条件，按日期范围、类型、状态等进行筛选。"
        }
      ]
    }
  }
}
```

### 9. 表单编辑抽屉

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "编辑记录",
          "#content": "在此编辑记录的详细信息。保存后更改将立即生效。"
        }
      ]
    }
  }
}
```

### 10. 预览抽屉

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "文档预览",
          "#content": "在此预览文档内容，包括文本、图片、表格等元素的最终展示效果。"
        }
      ]
    }
  }
}
```

### 11. 帮助信息抽屉

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "使用帮助",
          "#content": "欢迎使用本系统。以下是一些常见问题的解答：\n\n1. 如何创建新项目？\n2. 如何添加团队成员？\n3. 如何导出数据？"
        }
      ]
    }
  }
}
```

### 12. 历史记录抽屉

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "操作历史",
          "#content": "最近的操作记录：\n\n- 2024-01-15 10:30 创建了新项目\n- 2024-01-15 11:45 更新了项目设置\n- 2024-01-15 14:20 添加了团队成员"
        }
      ]
    }
  }
}
```

### 13. 项目详情抽屉

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "项目详情",
          "#content": "项目名称：ISMP系统\n项目描述：企业安全监控平台\n创建时间：2024-01-01\n状态：进行中\n负责人：李四"
        }
      ]
    }
  }
}
```

### 14. 通知抽屉

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "系统通知",
          "#content": "您有3条未读通知：\n\n1. 新订单已创建\n2. 服务器维护通知\n3. 安全警报：检测到异常登录"
        }
      ]
    }
  }
}
```

### 15. 统计报表抽屉

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_drawer",
          "#header": "月度统计",
          "#content": "本月数据统计：\n\n- 总访问量：12,345\n- 新增用户：234\n- 活跃用户：1,567\n- 系统错误率：0.02%"
        }
      ]
    }
  }
}
```
