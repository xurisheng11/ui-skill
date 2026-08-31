# aws_badge 示例

本文档展示 aws_badge 组件的各种使用场景。

## 示例列表

### 1. 基础用法 - 四种基本颜色

展示蓝色、灰色、绿色、红色四种基本颜色的徽章。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_badge",
          "#color": "blue",
          "#content": "信息"
        },
        {
          "#type": "aws_badge",
          "#color": "grey",
          "#content": "默认"
        },
        {
          "#type": "aws_badge",
          "#color": "green",
          "#content": "成功"
        },
        {
          "#type": "aws_badge",
          "#color": "red",
          "#content": "错误"
        }
      ]
    }
  }
}
```

### 2. 严重级别徽章

用于安全告警、漏洞扫描等场景的严重程度展示。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_badge",
          "#color": "severity-critical",
          "#content": "严重 - 3"
        },
        {
          "#type": "aws_badge",
          "#color": "severity-high",
          "#content": "高 - 7"
        },
        {
          "#type": "aws_badge",
          "#color": "severity-medium",
          "#content": "中 - 12"
        },
        {
          "#type": "aws_badge",
          "#color": "severity-low",
          "#content": "低 - 25"
        },
        {
          "#type": "aws_badge",
          "#color": "severity-neutral",
          "#content": "无 - 0"
        }
      ]
    }
  }
}
```

### 3. 数字计数徽章

常用于未读消息数、待处理任务数等场景。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_badge",
          "#color": "red",
          "#content": "99+"
        },
        {
          "#type": "aws_badge",
          "#color": "red",
          "#content": "20"
        },
        {
          "#type": "aws_badge",
          "#color": "blue",
          "#content": "5"
        },
        {
          "#type": "aws_badge",
          "#color": "green",
          "#content": "0"
        }
      ]
    }
  }
}
```

### 4. 资源状态标签

展示云资源（如EC2实例）的运行状态。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#content": "EC2 实例状态："
        },
        {
          "#type": "aws_badge",
          "#color": "green",
          "#content": "running"
        }
      ]
    }
  }
}
```

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#content": "RDS 数据库状态："
        },
        {
          "#type": "aws_badge",
          "#color": "red",
          "#content": "stopped"
        }
      ]
    }
  }
}
```

### 5. 环境标识

区分生产、测试、开发等不同环境。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_badge",
          "#color": "red",
          "#content": "生产环境"
        },
        {
          "#type": "aws_badge",
          "#color": "blue",
          "#content": "预发环境"
        },
        {
          "#type": "aws_badge",
          "#color": "grey",
          "#content": "测试环境"
        },
        {
          "#type": "aws_badge",
          "#color": "green",
          "#content": "开发环境"
        }
      ]
    }
  }
}
```

### 6. 资源标签组合

在资源列表中同时展示多个维度的信息。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#padding": "m",
          "#content": {
            "#type": "aws_box",
            "#content": "服务器配置",
            "#children": [
              {
                "#type": "aws_badge",
                "#color": "blue",
                "#content": "CPU: 45%"
              },
              {
                "#type": "aws_badge",
                "#color": "green",
                "#content": "内存: 2.4GB"
              },
              {
                "#type": "aws_badge",
                "#color": "grey",
                "#content": "t3.medium"
              }
            ]
          }
        }
      ]
    }
  }
}
```

### 7. 服务健康状态

展示多个服务的运行状态。

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_box",
          "#padding": "m",
          "#content": {
            "#type": "aws_box",
            "#content": "服务健康状态：",
            "#children": [
              {
                "#type": "aws_badge",
                "#color": "green",
                "#content": "Web API: 正常"
              },
              {
                "#type": "aws_badge",
                "#color": "green",
                "#content": "Database: 正常"
              },
              {
                "#type": "aws_badge",
                "#color": "red",
                "#content": "Cache: 异常"
              }
            ]
          }
        }
      ]
    }
  }
}
```

### 8. 版本和类型标识

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_badge",
          "#color": "blue",
          "#content": "v2.0"
        },
        {
          "#type": "aws_badge",
          "#color": "grey",
          "#content": "主版本"
        },
        {
          "#type": "aws_badge",
          "#color": "green",
          "#content": "LTS"
        }
      ]
    }
  }
}
```
