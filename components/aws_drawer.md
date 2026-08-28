# aws_drawer

AWS 抽屉组件，用于从页面侧面滑出的面板。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| header | 字符串 | 是 | 抽屉头部内容，应包含唯一的标题文本 |
| content | 字符串 | 否 | 抽屉的主要内容 |
| loading | 布尔值 | 否 | 以加载状态渲染抽屉 |
| i18n_strings | 对象 | 否 | 本地化字符串对象 |

### i18n_strings 结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| loadingText | 字符串 | 加载中文本 |

### header 变量

header 属性支持使用变量，格式为 `${变量名}`。

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
          "#type": "aws_drawer",
          "#header": "抽屉标题",
          "#content": "这是抽屉的内容区域，可以包含任意文本内容。"
        }
      ]
    }
  }
}
```

### 带加载状态

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

### 带国际化字符串

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

### 带变量的 header

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

### 详细设置面板

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

### 用户信息抽屉

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

### 确认对话框

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

### 过滤器面板

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

### 表单编辑抽屉

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

### 预览抽屉

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

### 帮助信息抽屉

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

### 历史记录抽屉

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
