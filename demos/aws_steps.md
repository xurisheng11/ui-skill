# aws_steps 示例

本文档展示 aws_steps 组件的各种使用场景。

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
          "#type": "aws_steps",
          "#steps": [
            { "status": "success", "header": "步骤1完成", "statusIconAriaLabel": "成功" },
            { "status": "success", "header": "步骤2完成", "statusIconAriaLabel": "成功" },
            { "status": "in-progress", "header": "步骤3进行中", "statusIconAriaLabel": "进行中" },
            { "status": "pending", "header": "步骤4等待中", "statusIconAriaLabel": "等待" }
          ]
        }
      ]
    }
  }
}
```

### 2. 带详情

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
            { "status": "success", "header": "订单已创建", "details": "订单号：ORD-12345" },
            { "status": "success", "header": "支付完成", "details": "支付方式：支付宝" },
            { "status": "in-progress", "header": "商品打包中", "details": "预计完成时间：今天 18:00" },
            { "status": "pending", "header": "等待发货" }
          ]
        }
      ]
    }
  }
}
```

### 3. 全部成功

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
            { "status": "success", "header": "账号注册" },
            { "status": "success", "header": "邮箱验证" },
            { "status": "success", "header": "资料完善" }
          ]
        }
      ]
    }
  }
}
```

### 4. 有错误

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
            { "status": "success", "header": "提交申请" },
            { "status": "error", "header": "审核失败", "details": "材料不符合要求" }
          ]
        }
      ]
    }
  }
}
```

### 5. 部署流程

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
            { "status": "success", "header": "代码构建", "details": "构建完成，耗时 2分30秒" },
            { "status": "success", "header": "单元测试", "details": "测试通过率 98%" },
            { "status": "in-progress", "header": "部署到测试环境" },
            { "status": "pending", "header": "部署到生产环境" }
          ]
        }
      ]
    }
  }
}
```

### 6. 引导向导

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
            { "status": "success", "header": "第一步：基础信息" },
            { "status": "success", "header": "第二步：详细配置" },
            { "status": "success", "header": "第三步：确认提交" }
          ]
        }
      ]
    }
  }
}
```

### 7. 进度追踪

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
            { "status": "success", "header": "已接收" },
            { "status": "success", "header": "处理中" },
            { "status": "success", "header": "已发货" },
            { "status": "in-progress", "header": "运输中" },
            { "status": "pending", "header": "已签收" }
          ]
        }
      ]
    }
  }
}
```

### 8. 开通流程

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
            { "status": "success", "header": "选择服务" },
            { "status": "in-progress", "header": "配置参数" },
            { "status": "pending", "header": "确认订单" },
            { "status": "pending", "header": "完成开通" }
          ]
        }
      ]
    }
  }
}
```

### 9. 注册流程

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
            { "status": "success", "header": "填写信息" },
            { "status": "success", "header": "验证邮箱" },
            { "status": "in-progress", "header": "设置密码" },
            { "status": "pending", "header": "注册完成" }
          ]
        }
      ]
    }
  }
}
```

### 10. 审批流程

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
            { "status": "success", "header": "提交申请", "details": "申请人：张三" },
            { "status": "success", "header": "部门审批", "details": "审批人：李四" },
            { "status": "in-progress", "header": "领导审批" },
            { "status": "pending", "header": "完成" }
          ]
        }
      ]
    }
  }
}
```

### 11. 安装向导

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
            { "status": "success", "header": "同意协议" },
            { "status": "success", "header": "选择安装位置" },
            { "status": "in-progress", "header": "正在安装" },
            { "status": "pending", "header": "安装完成" }
          ]
        }
      ]
    }
  }
}
```

### 12. 登录流程

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
            { "status": "success", "header": "输入用户名" },
            { "status": "success", "header": "输入密码" },
            { "status": "in-progress", "header": "验证中" }
          ]
        }
      ]
    }
  }
}
```

### 13. 备份流程

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
            { "status": "success", "header": "选择备份源" },
            { "status": "in-progress", "header": "创建备份" },
            { "status": "pending", "header": "验证备份" },
            { "status": "pending", "header": "完成" }
          ]
        }
      ]
    }
  }
}
```

### 14. 升级流程

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
            { "status": "success", "header": "检查更新" },
            { "status": "in-progress", "header": "下载更新" },
            { "status": "pending", "header": "安装更新" },
            { "status": "pending", "header": "重启服务" }
          ]
        }
      ]
    }
  }
}
```

### 15. 导出流程

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
            { "status": "success", "header": "选择导出格式" },
            { "status": "success", "header": "选择数据范围" },
            { "status": "in-progress", "header": "导出数据" },
            { "status": "pending", "header": "下载完成" }
          ]
        }
      ]
    }
  }
}
```
