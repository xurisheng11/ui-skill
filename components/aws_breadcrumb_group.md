# aws_breadcrumb_group

AWS 面包屑组组件，用于显示用户当前位置的路径导航，帮助用户在层级结构中快速返回上级页面。

## 参数说明

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| aria_label | 字符串 | 否 | 提供一个面包屑组的 aria-label，屏幕阅读器可以读取（为了无障碍访问） | - | - |
| expand_aria_label | 字符串 | 否 | 提供给省略号按钮一个 aria-label，屏幕阅读器可以读取（为了无障碍访问） | 注意：该属性是内置国际化的一部分。如果应用程序使用 Cloudscape 的 I18nProvider，此属性将自动提供 | - |
| items | 数组 | 是 | 描述此导航链接层次结构的面包屑项数组 | 数组中的每个对象包含 text 和 href 属性 | [] |

### items 子属性

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| text | 字符串 | 指定面包屑项的标题文本 |
| href | 字符串 | 指定面包屑项链接的 URL。即使为面包屑项设置了点击处理程序，也应指定链接以确保生成有效的标记 |

**注意**：数组中的最后一个面包屑项自动被视为当前项，并且不是一个链接。

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
          "#type": "aws_breadcrumb_group",
          "#items": [
            { "text": "System", "href": "#" },
            { "text": "Components", "href": "#components" },
            {
              "text": "Breadcrumb group",
              "href": "#components/breadcrumb-group"
            }
          ]
        }
      ]
    }
  }
}
```

### 简化导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_breadcrumb_group",
          "#items": [
            { "text": "首页", "href": "/" },
            { "text": "用户管理", "href": "/users" }
          ]
        }
      ]
    }
  }
}
```

### 多层级导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_breadcrumb_group",
          "#items": [
            { "text": "首页", "href": "/" },
            { "text": "订单管理", "href": "/orders" },
            { "text": "订单详情", "href": "/orders/123" },
            { "text": "物流信息", "href": "/orders/123/shipping" }
          ]
        }
      ]
    }
  }
}
```

### 带中文文本

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_breadcrumb_group",
          "#items": [
            { "text": "首页", "href": "#" },
            { "text": "系统设置", "href": "#settings" },
            { "text": "用户管理", "href": "#settings/users" },
            { "text": "编辑用户" }
          ]
        }
      ]
    }
  }
}
```

### 产品目录导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_breadcrumb_group",
          "#items": [
            { "text": "首页", "href": "#" },
            { "text": "电子产品", "href": "#electronics" },
            { "text": "电脑", "href": "#electronics/computers" },
            { "text": "笔记本电脑", "href": "#electronics/computers/laptops" },
            { "text": "MacBook Pro 14" }
          ]
        }
      ]
    }
  }
}
```

### 文件系统导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_breadcrumb_group",
          "#items": [
            { "text": "我的文档", "href": "#" },
            { "text": "项目文件", "href": "#projects" },
            { "text": "2024年度报告", "href": "#projects/annual-report-2024" },
            { "text": "财务报表", "href": "#projects/annual-report-2024/financial" },
            { "text": "Q4季度报告" }
          ]
        }
      ]
    }
  }
}
```

### 带无障碍标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_breadcrumb_group",
          "#aria_label": "您当前的位置",
          "#expand_aria_label": "展开更多面包屑",
          "#items": [
            { "text": "首页", "href": "#" },
            { "text": "分类", "href": "#category" },
            { "text": "当前页面" }
          ]
        }
      ]
    }
  }
}
```

### 两级导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_breadcrumb_group",
          "#items": [
            { "text": "首页", "href": "#" },
            { "text": "设置页面" }
          ]
        }
      ]
    }
  }
}
```
