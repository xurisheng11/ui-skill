# aws_side_navigation

侧边导航组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| items | 数组 | 否 | 导航项数组 |
| active_href | 字符串 | 否 | 当前激活链接的href |
| header | 对象 | 否 | 导航顶部标题 |

### header 结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| text | 字符串 | 标题文本 |
| href | 字符串 | 标题链接 |
| logo | 对象 | 标志图像 |

### logo 结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| alt | 字符串 | 替代文本 |
| src | 字符串 | 图片URL |

### items 项类型

**Link**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| type | 字符串 | 'link' |
| text | 字符串 | 链接文本 |
| href | 字符串 | 链接地址 |
| external | 布尔值 | 是否外部链接 |
| info | 组件 | 信息内容 |

**Divider**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| type | 字符串 | 'divider' |

**Section**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| type | 字符串 | 'section' |
| text | 字符串 | 部分标题 |
| defaultExpanded | 布尔值 | 是否默认展开 |
| items | 数组 | 部分内容 |

**SectionGroup**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| type | 字符串 | 'section-group' |
| title | 字符串 | 组标题 |
| items | 数组 | 组内容 |

**LinkGroup**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| type | 字符串 | 'link-group' |
| text | 字符串 | 组链接文本 |
| href | 字符串 | 组链接地址 |
| info | 组件 | 信息内容 |
| items | 数组 | 组内容 |

**ExpandableLinkGroup**
| 属性 | 类型 | 描述 |
| --- | --- | --- |
| type | 字符串 | 'expandable-link-group' |
| text | 字符串 | 组链接文本 |
| href | 字符串 | 组链接地址 |
| defaultExpanded | 布尔值 | 是否默认展开 |
| items | 数组 | 组内容 |

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
          "#type": "aws_side_navigation",
          "#items": [
            { "type": "link", "text": "页面 1", "href": "#/page1" },
            { "type": "link", "text": "页面 2", "href": "#/page2" },
            { "type": "link", "text": "页面 3", "href": "#/page3" },
            { "type": "link", "text": "页面 4", "href": "#/page4" }
          ],
          "#header": {
            "href": "#/page1",
            "logo": { "alt": "logo", "src": "/core/misc/logo.svg" }
          }
        }
      ]
    }
  }
}
```

### 带激活状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#const_define": [
        {
          "value": "nav",
          "set_value": "set_nav",
          "default": "/page2"
        }
      ],
      "#children": [
        {
          "#type": "aws_side_navigation",
          "#active_href": "nav",
          "#items": [
            { "type": "link", "text": "页面 1", "href": "/page1" },
            { "type": "link", "text": "页面 2", "href": "/page2" },
            { "type": "link", "text": "页面 3", "href": "/page3" },
            { "type": "link", "text": "页面 4", "href": "/page4" }
          ]
        }
      ]
    }
  }
}
```

### 带分隔线

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
            { "type": "link", "text": "订单管理", "href": "/orders" },
            { "type": "divider" },
            { "type": "link", "text": "系统设置", "href": "/settings" }
          ]
        }
      ]
    }
  }
}
```

### 带Section

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
                { "type": "link", "text": "分类管理", "href": "/categories" },
                { "type": "link", "text": "标签管理", "href": "/tags" }
              ]
            },
            {
              "type": "section",
              "text": "用户中心",
              "items": [
                { "type": "link", "text": "用户列表", "href": "/users" },
                { "type": "link", "text": "权限设置", "href": "/permissions" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### Section默认折叠

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

### LinkGroup

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
            },
            {
              "type": "link-group",
              "text": "教程",
              "href": "/tutorials",
              "items": [
                { "type": "link", "text": "基础教程", "href": "/tutorials/basic" },
                { "type": "link", "text": "高级教程", "href": "/tutorials/advanced" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### ExpandableLinkGroup

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
                { "type": "link", "text": "产品B", "href": "/products/b" },
                { "type": "link", "text": "产品C", "href": "/products/c" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 外部链接

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

### 带标题

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
          "#header": {
            "text": "我的应用",
            "href": "/"
          },
          "#items": [
            { "type": "link", "text": "概览", "href": "/overview" },
            { "type": "link", "text": "分析", "href": "/analytics" },
            { "type": "link", "text": "报告", "href": "/reports" }
          ]
        }
      ]
    }
  }
}
```

### SectionGroup

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
              "type": "section-group",
              "title": "管理",
              "items": [
                {
                  "type": "section",
                  "text": "用户管理",
                  "items": [
                    { "type": "link", "text": "用户列表", "href": "/users" }
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 完整导航示例

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
          "#header": {
            "text": "企业管理后台",
            "href": "/"
          },
          "#items": [
            { "type": "link", "text": "仪表盘", "href": "/dashboard" },
            { "type": "divider" },
            {
              "type": "section",
              "text": "业务管理",
              "items": [
                { "type": "link", "text": "订单管理", "href": "/orders" },
                { "type": "link", "text": "客户管理", "href": "/customers" },
                { "type": "link", "text": "产品管理", "href": "/products" }
              ]
            },
            {
              "type": "section",
              "text": "系统管理",
              "items": [
                { "type": "link", "text": "用户管理", "href": "/users" },
                { "type": "link", "text": "角色权限", "href": "/roles" },
                { "type": "link", "text": "操作日志", "href": "/logs" }
              ]
            },
            { "type": "divider" },
            { "type": "link", "text": "系统设置", "href": "/settings" },
            { "type": "link", "text": "帮助文档", "href": "/help", "external": true }
          ]
        }
      ]
    }
  }
}
```
