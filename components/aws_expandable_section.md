# aws_expandable_section

可展开区域组件，用于折叠/展开内容。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| header_text | 字符串 | 是 | 标题文本 |
| default_expanded | 布尔值 | 否 | 初始是否为展开状态 |
| expanded | 布尔值 | 否 | 受控模式下的展开状态 |
| disable_content_paddings | 布尔值 | 否 | 移除内容区域的默认内边距 |
| header_counter | 字符串 | 否 | 标题右侧的次要文本 |
| header_description | 字符串 | 否 | 标题下方的补充文本 |
| heading_tag_override | 字符串 | 否 | 覆盖默认HTML标题标签 (h1-h5) |
| variant | 字符串 | 否 | 变体类型 |

### variant 可选值

- `default` - 默认样式
- `footer` - 用于容器页脚
- `container` - 用于详细页面容器
- `navigation` - 用于导航面板
- `stacked` - 用于堆叠容器
- `inline` - 减少内边距

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| content (默认) | 主要内容区域 | 否 | - |
| header_actions | 标题操作按钮区域 | 是 | variable |
| header_info | 标题旁边的信息链接 | 是 | variable |

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
          "#type": "aws_expandable_section",
          "#header_text": "点击展开",
          "#content": "这是展开后的内容区域。"
        }
      ]
    }
  }
}
```

### 带操作按钮

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

### 容器变体

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

### 默认展开

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

### 导航变体

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

### FAQ 场景

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
          "#content": "访问登录页面，点击\"忘记密码\"链接，按照提示输入注册邮箱，系统将发送重置链接到您的邮箱。"
        },
        {
          "#type": "aws_expandable_section",
          "#header_text": "如何联系客服？",
          "#content": "您可以通过以下方式联系客服：\n1. 拨打客服热线：400-xxx-xxxx\n2. 发送邮件至：support@example.com\n3. 在线客服聊天（工作日 9:00-18:00）"
        },
        {
          "#type": "aws_expandable_section",
          "#header_text": "如何升级会员？",
          "#content": "登录后进入\"账户设置\"页面，选择\"会员升级\"选项，选择您需要的会员类型并完成支付即可。"
        }
      ]
    }
  }
}
```

### 配置面板

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
          "#header_description": "配置应用程序的基本设置",
          "#content": "基础配置的具体选项..."
        },
        {
          "#type": "aws_expandable_section",
          "#variant": "container",
          "#header_text": "高级配置",
          "#header_description": "配置高级选项和调试功能",
          "#content": "高级配置的具体选项..."
        },
        {
          "#type": "aws_expandable_section",
          "#variant": "container",
          "#header_text": "安全设置",
          "#header_description": "配置安全相关选项",
          "#content": "安全设置的具体选项..."
        }
      ]
    }
  }
}
```
