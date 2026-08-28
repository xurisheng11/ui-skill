# aws_steps

步骤指示器组件，用于显示进度步骤。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| steps | 数组 | 是 | 步骤数组 |

### steps 项结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| status | 字符串 | 步骤状态 |
| statusIconAriaLabel | 字符串 | 状态图标aria-label |
| header | 组件/字符串 | 步骤标题 |
| details | 组件/字符串 | 步骤详情 |

### status 可选值

- `success` - 成功
- `stopped` - 停止
- `pending` - 待处理
- `in-progress` - 进行中
- `error` - 错误

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
          "#type": "aws_steps",
          "#steps": [
            {
              "status": "success",
              "header": "步骤1完成",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "success",
              "header": "步骤2完成",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "in-progress",
              "header": "步骤3进行中",
              "statusIconAriaLabel": "进行中"
            },
            {
              "status": "pending",
              "header": "步骤4等待中",
              "statusIconAriaLabel": "等待"
            }
          ]
        }
      ]
    }
  }
}
```

### 带详情

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_steps",
          "#steps": [
            {
              "status": "success",
              "header": "订单已创建",
              "details": "订单号：ORD-12345",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "success",
              "header": "支付完成",
              "details": "支付方式：支付宝",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "in-progress",
              "header": "商品打包中",
              "details": "预计完成时间：今天 18:00",
              "statusIconAriaLabel": "进行中"
            },
            {
              "status": "pending",
              "header": "等待发货",
              "statusIconAriaLabel": "等待"
            }
          ]
        }
      ]
    }
  }
}
```

### 全部成功

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_steps",
          "#steps": [
            {
              "status": "success",
              "header": "账号注册",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "success",
              "header": "邮箱验证",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "success",
              "header": "资料完善",
              "statusIconAriaLabel": "成功"
            }
          ]
        }
      ]
    }
  }
}
```

### 有错误

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_steps",
          "#steps": [
            {
              "status": "success",
              "header": "提交申请",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "error",
              "header": "审核失败",
              "details": "材料不符合要求，请重新上传",
              "statusIconAriaLabel": "错误"
            },
            {
              "status": "pending",
              "header": "等待重新提交",
              "statusIconAriaLabel": "等待"
            }
          ]
        }
      ]
    }
  }
}
```

### 部署流程

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_steps",
          "#steps": [
            {
              "status": "success",
              "header": "代码构建",
              "details": "构建完成，耗时 2分30秒",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "success",
              "header": "单元测试",
              "details": "测试通过率 98%",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "in-progress",
              "header": "部署到测试环境",
              "details": "正在部署...",
              "statusIconAriaLabel": "进行中"
            },
            {
              "status": "pending",
              "header": "部署到生产环境",
              "statusIconAriaLabel": "等待"
            }
          ]
        }
      ]
    }
  }
}
```

### 引导向导

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_steps",
          "#steps": [
            {
              "status": "success",
              "header": "第一步：基础信息",
              "statusIconAriaLabel": "已完成"
            },
            {
              "status": "success",
              "header": "第二步：详细配置",
              "statusIconAriaLabel": "已完成"
            },
            {
              "status": "success",
              "header": "第三步：确认提交",
              "statusIconAriaLabel": "已完成"
            }
          ]
        }
      ]
    }
  }
}
```

### 进度追踪

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_steps",
          "#steps": [
            {
              "status": "success",
              "header": "已接收",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "success",
              "header": "处理中",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "success",
              "header": "已发货",
              "statusIconAriaLabel": "成功"
            },
            {
              "status": "in-progress",
              "header": "运输中",
              "statusIconAriaLabel": "进行中"
            },
            {
              "status": "pending",
              "header": "已签收",
              "statusIconAriaLabel": "等待"
            }
          ]
        }
      ]
    }
  }
}
```
