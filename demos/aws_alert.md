# aws_alert 示例

本文档展示 aws_alert 组件的各种使用场景。

## 示例列表

### 1. 基础用法 - 四种消息类型

展示不同类型的警告框：info、success、warning、error。

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
        },
        {
          "#type": "aws_alert",
          "#alert_type": "success",
          "#content": "操作成功完成！"
        },
        {
          "#type": "aws_alert",
          "#alert_type": "warning",
          "#content": "请注意，此操作不可逆。"
        },
        {
          "#type": "aws_alert",
          "#alert_type": "error",
          "#content": "发生错误，请联系管理员。"
        }
      ]
    }
  }
}
```

### 2. 带标题的警告框

使用 header 属性为警告框添加标题。

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
          "#header": "保存成功",
          "#content": "您的更改已成功保存到服务器。"
        }
      ]
    }
  }
}
```

### 3. 可关闭的警告框

设置 dismissible 属性为 true，用户可以手动关闭警告框。

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
          "#dismissible": true,
          "#header": "提示",
          "#content": "这是一条可关闭的提示消息。"
        }
      ]
    }
  }
}
```

### 4. 表单验证失败示例

在表单提交失败时显示多个错误信息。

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
          "#header": "表单验证失败",
          "#content": "请修正以下错误后再提交：\n1. 用户名不能为空\n2. 邮箱格式不正确\n3. 密码长度不足8位"
        }
      ]
    }
  }
}
```

### 5. 业务操作提示

展示实际业务场景中的各种提示信息。

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
          "#header": "订单创建成功",
          "#content": "订单号：ORD-2024-001234，预计 2-3 个工作日送达。"
        },
        {
          "#type": "aws_alert",
          "#alert_type": "warning",
          "#header": "库存不足",
          "#content": "您订购的商品仅剩 3 件，建议尽快完成支付以确保库存。"
        },
        {
          "#type": "aws_alert",
          "#alert_type": "info",
          "#dismissible": true,
          "#content": "新用户首单满 100 元减 20 元优惠已自动生效。"
        }
      ]
    }
  }
}
```

### 6. 复杂内容示例

在警告框中嵌套其他 AWS 组件。

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
          "#header": "系统维护通知",
          "#content": {
            "#type": "aws_box",
            "#padding": "m",
            "#content": {
              "#type": "aws_box",
              "#content": "维护时间：2024-12-25 02:00 - 06:00"
            }
          }
        }
      ]
    }
  }
}
```
