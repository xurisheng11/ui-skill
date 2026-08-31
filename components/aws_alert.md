# aws_alert

AWS 警告框组件，用于向用户显示重要的通知消息。支持不同的消息类型（成功、错误、警告、信息），并可配置可关闭的警告框。

## 参数说明

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| alert_type | 字符串 | 否 | 指定要显示的消息类型 | success / error / warning / info | 'info' |
| dismissible | 布尔值 | 否 | 设置为 true 时，在提醒信息中添加一个关闭按钮。当用户点击按钮时触发 on_dismiss 事件 | - | false |
| dismiss_aria_label | 字符串 | 否 | 向关闭按钮添加一个 aria-label | 注意：该属性是内置国际化的一部分。如果应用程序使用 Cloudscape 的 I18nProvider，此属性将自动提供 | - | false |
| status_icon_aria_label | 字符串 | 否 | 为图标提供文字替代方案 | - | - |
| header | 字符串/组件 | 否 | 警告框的标题内容 | - | - |
| content | 字符串/组件 | 否 | 警告框的主体内容 | - | - |

## 使用示例

### 基础用法 - 不同类型

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_alert",
          "#alert_type": "info",
          "#content": "这是一条普通的信息提示"
        }
      ]
    }
  }
}
```

### 成功提示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_alert",
          "#alert_type": "success",
          "#header": "操作成功",
          "#content": "您的请求已成功处理，数据已保存。"
        }
      ]
    }
  }
}
```

### 错误提示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_alert",
          "#alert_type": "error",
          "#header": "操作失败",
          "#content": "系统发生错误，请稍后重试。如果问题持续存在，请联系管理员。"
        }
      ]
    }
  }
}
```

### 警告提示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_alert",
          "#alert_type": "warning",
          "#header": "注意",
          "#content": "您的会话即将过期，请及时保存重要数据。"
        }
      ]
    }
  }
}
```

### 可关闭的警告框

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_alert",
          "#alert_type": "error",
          "#dismissible": true,
          "#header": "操作失败",
          "#content": "您的请求处理失败，点击关闭按钮可隐藏此消息。"
        }
      ]
    }
  }
}
```

### 带组件内容

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_alert",
          "#alert_type": "warning",
          "#header": "配置变更提醒",
          "#content": {
            "#type": "aws_box",
            "#padding": "m",
            "#content": "检测到以下配置变更：\n1. 数据库连接池大小已更新\n2. 缓存策略已调整"
          }
        }
      ]
    }
  }
}
```

### 多个警告框组合

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_alert",
          "#alert_type": "success",
          "#content": "主要配置已保存成功"
        },
        {
          "#type": "aws_alert",
          "#alert_type": "warning",
          "#content": "部分设置需要重启服务后生效"
        },
        {
          "#type": "aws_alert",
          "#alert_type": "info",
          "#dismissible": true,
          "#content": "系统将在凌晨 2:00 进行例行维护"
        }
      ]
    }
  }
}
```
