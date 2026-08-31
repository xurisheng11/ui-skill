# aws_breadcrumb_group 示例

本文档展示 aws_breadcrumb_group 组件的各种使用场景。

## 示例列表

### 1. 基础导航

最基本的两级导航示例。

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
            { "text": "当前页面" }
          ]
        }
      ]
    }
  }
}
```

### 2. 管理系统导航

典型的后台管理系统的面包屑导航。

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
            { "text": "首页", "href": "/dashboard" },
            { "text": "系统管理", "href": "/admin" },
            { "text": "用户管理", "href": "/admin/users" },
            { "text": "编辑用户" }
          ]
        }
      ]
    }
  }
}
```

### 3. 订单流程导航

电商订单详情页面的面包屑。

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
            { "text": "我的订单", "href": "#/orders" },
            { "text": "订单详情" }
          ]
        }
      ]
    }
  }
}
```

### 4. 云资源管理导航

云控制台常见的多层级资源导航。

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
            { "text": "计算", "href": "#compute" },
            { "text": "EC2", "href": "#compute/ec2" },
            { "text": "实例", "href": "#compute/ec2/instances" },
            { "text": "i-0abc123def456" }
          ]
        }
      ]
    }
  }
}
```

### 5. 文档页面导航

帮助文档或知识库的面包屑。

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
            { "text": "帮助中心", "href": "#help" },
            { "text": "快速入门", "href": "#help/getting-started" },
            { "text": "创建第一个应用" }
          ]
        }
      ]
    }
  }
}
```

### 6. 文件管理导航

模拟文件系统的层级导航。

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
            { "text": "我的文件", "href": "#" },
            { "text": "项目", "href": "#projects" },
            { "text": "前端项目", "href": "#projects/frontend" },
            { "text": "src", "href": "#projects/frontend/src" },
            { "text": "components" }
          ]
        }
      ]
    }
  }
}
```

### 7. 带无障碍标签

强调无障碍访问的面包屑示例。

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
          "#aria_label": "页面位置导航",
          "#expand_aria_label": "显示完整路径",
          "#items": [
            { "text": "首页", "href": "#" },
            { "text": "配置", "href": "#config" },
            { "text": "当前配置" }
          ]
        }
      ]
    }
  }
}
```

### 8. 分类导航

电商产品分类页面的面包屑。

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
            { "text": "服装", "href": "#clothing" },
            { "text": "男装", "href": "#clothing/men" },
            { "text": "外套", "href": "#clothing/men/outerwear" },
            { "text": "羽绒服" }
          ]
        }
      ]
    }
  }
}
```
