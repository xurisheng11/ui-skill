# aws_side_navigation 示例

本文档展示 aws_side_navigation 组件的各种使用场景。

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
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "页面 1", "href": "#/page1" },
            { "type": "link", "text": "页面 2", "href": "#/page2" },
            { "type": "link", "text": "页面 3", "href": "#/page3" }
          ]
        }
      ]
    }
  }
}
```

### 2. 带激活状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#const_define": [
        { "value": "nav", "set_value": "set_nav", "default": "/page2" }
      ],
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#active_href": "nav",
          "#items": [
            { "type": "link", "text": "页面 1", "href": "/page1" },
            { "type": "link", "text": "页面 2", "href": "/page2" },
            { "type": "link", "text": "页面 3", "href": "/page3" }
          ]
        }
      ]
    }
  }
}
```

### 3. 带分隔线

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "首页", "href": "/home" },
            { "type": "link", "text": "仪表盘", "href": "/dashboard" },
            { "type": "divider" },
            { "type": "link", "text": "用户管理", "href": "/users" },
            { "type": "link", "text": "订单管理", "href": "/orders" }
          ]
        }
      ]
    }
  }
}
```

### 4. 带Section

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "首页", "href": "/" },
            {
              "type": "section",
              "text": "内容管理",
              "items": [
                { "type": "link", "text": "文章列表", "href": "/articles" },
                { "type": "link", "text": "分类管理", "href": "/categories" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 5. LinkGroup

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            {
              "type": "link-group",
              "text": "文档",
              "href": "/docs",
              "items": [
                { "type": "link", "text": "快速开始", "href": "/docs/quickstart" },
                { "type": "link", "text": "API参考", "href": "/docs/api" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 6. ExpandableLinkGroup

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "首页", "href": "/" },
            {
              "type": "expandable-link-group",
              "text": "产品中心",
              "href": "/products",
              "defaultExpanded": true,
              "items": [
                { "type": "link", "text": "产品A", "href": "/products/a" },
                { "type": "link", "text": "产品B", "href": "/products/b" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 7. 外部链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "首页", "href": "/" },
            { "type": "link", "text": "官方文档", "href": "https://docs.example.com", "external": true },
            { "type": "link", "text": "GitHub", "href": "https://github.com", "external": true }
          ]
        }
      ]
    }
  }
}
```

### 8. 带标题

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#header": { "text": "我的应用", "href": "/" },
          "#items": [
            { "type": "link", "text": "概览", "href": "/overview" },
            { "type": "link", "text": "分析", "href": "/analytics" }
          ]
        }
      ]
    }
  }
}
```

### 9. 完整导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#header": { "text": "企业管理后台", "href": "/" },
          "#items": [
            { "type": "link", "text": "仪表盘", "href": "/dashboard" },
            { "type": "divider" },
            {
              "type": "section",
              "text": "业务管理",
              "items": [
                { "type": "link", "text": "订单管理", "href": "/orders" },
                { "type": "link", "text": "客户管理", "href": "/customers" }
              ]
            },
            {
              "type": "section",
              "text": "系统管理",
              "items": [
                { "type": "link", "text": "用户管理", "href": "/users" },
                { "type": "link", "text": "角色权限", "href": "/roles" }
              ]
            },
            { "type": "divider" },
            { "type": "link", "text": "系统设置", "href": "/settings" }
          ]
        }
      ]
    }
  }
}
```

### 10. 默认折叠Section

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "首页", "href": "/" },
            {
              "type": "section",
              "text": "默认折叠",
              "defaultExpanded": false,
              "items": [
                { "type": "link", "text": "子页面 1", "href": "/sub1" },
                { "type": "link", "text": "子页面 2", "href": "/sub2" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 11. 电子商务导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "首页", "href": "/" },
            { "type": "link", "text": "商品列表", "href": "/products" },
            { "type": "link", "text": "购物车", "href": "/cart" },
            { "type": "link", "text": "订单列表", "href": "/orders" },
            { "type": "link", "text": "用户中心", "href": "/profile" }
          ]
        }
      ]
    }
  }
}
```

### 12. 内容管理

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "仪表盘", "href": "/" },
            { "type": "divider" },
            { "type": "link", "text": "文章管理", "href": "/articles" },
            { "type": "link", "text": "页面管理", "href": "/pages" },
            { "type": "link", "text": "媒体库", "href": "/media" },
            { "type": "link", "text": "评论管理", "href": "/comments" }
          ]
        }
      ]
    }
  }
}
```

### 13. 设置导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "常规设置", "href": "/settings/general" },
            { "type": "link", "text": "外观", "href": "/settings/appearance" },
            { "type": "link", "text": "通知", "href": "/settings/notifications" },
            { "type": "link", "text": "安全", "href": "/settings/security" },
            { "type": "link", "text": "高级", "href": "/settings/advanced" }
          ]
        }
      ]
    }
  }
}
```

### 14. 多级导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "首页", "href": "/" },
            {
              "type": "section",
              "text": "模块A",
              "items": [
                { "type": "link", "text": "功能1", "href": "/module-a/feature1" },
                { "type": "link", "text": "功能2", "href": "/module-a/feature2" }
              ]
            },
            {
              "type": "section",
              "text": "模块B",
              "items": [
                { "type": "link", "text": "功能3", "href": "/module-b/feature3" },
                { "type": "link", "text": "功能4", "href": "/module-b/feature4" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 15. 管理员导航

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#header": { "text": "管理后台", "href": "/" },
          "#items": [
            { "type": "link", "text": "概览", "href": "/" },
            { "type": "divider" },
            { "type": "link", "text": "用户", "href": "/admin/users" },
            { "type": "link", "text": "角色", "href": "/admin/roles" },
            { "type": "link", "text": "权限", "href": "/admin/permissions" },
            { "type": "divider" },
            { "type": "link", "text": "系统日志", "href": "/admin/logs" },
            { "type": "link", "text": "系统设置", "href": "/admin/settings" }
          ]
        }
      ]
    }
  }
}
```
