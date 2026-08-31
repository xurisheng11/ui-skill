# aws_badge

AWS 徽章组件，用于显示简短的信息摘要，如计数、状态标签或分类标识。

## 参数说明

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| color | 字符串 | 否 | 指定徽章的颜色 | blue / grey / green / red / severity-critical / severity-high / severity-medium / severity-low / severity-neutral | "grey" |
| content | 字符串/组件 | 是 | 徽章的显示内容 | - | - |

## color 可选值说明

| 值 | 颜色 | 适用场景 |
| --- | --- | --- |
| blue | 蓝色 | 信息、链接、导航相关 |
| grey | 灰色（默认） | 通用标签、未分类项 |
| green | 绿色 | 成功、在线、可用状态 |
| red | 红色 | 错误、危险、删除 |
| severity-critical | 深红色 | 严重级别：关键问题 |
| severity-high | 橙红色 | 高严重级别：重要问题 |
| severity-medium | 橙色 | 中等严重级别：需要注意 |
| severity-low | 黄色 | 低严重级别：轻微问题 |
| severity-neutral | 中性灰 | 无严重级别或未知 |

## 使用示例

### 基础用法 - 不同颜色

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

### 严重级别徽章

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
          "#content": "严重"
        },
        {
          "#type": "aws_badge",
          "#color": "severity-high",
          "#content": "高"
        },
        {
          "#type": "aws_badge",
          "#color": "severity-medium",
          "#content": "中"
        },
        {
          "#type": "aws_badge",
          "#color": "severity-low",
          "#content": "低"
        },
        {
          "#type": "aws_badge",
          "#color": "severity-neutral",
          "#content": "无"
        }
      ]
    }
  }
}
```

### 数字计数徽章

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
          "#content": "20"
        }
      ]
    }
  }
}
```

### 状态标签

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
          "#color": "green",
          "#content": "运行中"
        },
        {
          "#type": "aws_badge",
          "#color": "grey",
          "#content": "已停止"
        },
        {
          "#type": "aws_badge",
          "#color": "red",
          "#content": "故障"
        }
      ]
    }
  }
}
```

### 分类标识

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
          "#content": "生产环境"
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

### 表格行中的应用

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
          "#content": [
            {
              "#type": "aws_badge",
              "#color": "green",
              "#content": "CPU: 45%"
            },
            {
              "#type": "aws_badge",
              "#color": "blue",
              "#content": "内存: 2.4GB"
            },
            {
              "#type": "aws_badge",
              "#color": "grey",
              "#content": "实例: t3.medium"
            }
          ]
        }
      ]
    }
  }
}
```

### 多个徽章组合

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
            "#content": "服务状态：",
            "#children": [
              {
                "#type": "aws_badge",
                "#color": "green",
                "#content": "Web API"
              },
              {
                "#type": "aws_badge",
                "#color": "green",
                "#content": "Database"
              },
              {
                "#type": "aws_badge",
                "#color": "red",
                "#content": "Cache"
              }
            ]
          }
        }
      ]
    }
  }
}
```
