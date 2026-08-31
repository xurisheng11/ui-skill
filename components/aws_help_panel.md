# aws_help_panel

帮助面板组件，用于显示帮助信息。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| loading | 布尔值 | 否 | 以加载状态渲染面板 |
| loading_text | 字符串 | 否 | 加载状态显示的文本 |

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| content (默认) | 帮助面板的主要内容 | 是 | {variable} |
| header | 帮助面板的头部（应包含唯一的h2） | 是 | variable |
| footer | 帮助面板的页脚 | 是 | variable |

**content 支持的HTML标签**：p, a, h3, h4, h5, span, div, ul, ol, li, code, pre, dl, dt, dd, hr, br, i, em, b, strong

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
          "#type": "aws_help_panel",
          "#header": {
            "#type": "aws_header",
            "#title": "帮助指南"
          },
          "#content": "欢迎使用本系统帮助文档。"
        }
      ]
    }
  }
}
```

### 带页脚

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_help_panel",
          "#header": {
            "#type": "aws_header",
            "#title": "常见问题"
          },
          "#content": "<h3>如何重置密码？</h3><p>访问登录页面，点击\"忘记密码\"链接。</p><h3>如何联系客服？</h3><p>发送邮件至 support@example.com</p>",
          "#footer": {
            "#markup": "<h5>需要更多帮助？</h5><p>请联系技术支持团队</p>"
          }
        }
      ]
    }
  }
}
```

### 带列表内容

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_help_panel",
          "#header": {
            "#type": "aws_header",
            "#title": "使用指南"
          },
          "#content": "<h3>入门步骤</h3><ol><li>注册账户</li><li>验证邮箱</li><li>完成个人资料</li><li>开始使用</li></ol><h3>提示</h3><ul><li>建议定期更换密码</li><li>开启双因素认证</li></ul>"
        }
      ]
    }
  }
}
```

### 带代码块

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_help_panel",
          "#header": {
            "#type": "aws_header",
            "#title": "API 文档"
          },
          "#content": "<h3>快速开始</h3><p>使用以下代码获取数据：</p><pre><code>GET /api/v1/users</code></pre><h3>认证</h3><p>在请求头中添加您的API密钥。</p>"
        }
      ]
    }
  }
}
```

### 加载状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_help_panel",
          "#loading": true,
          "#loading_text": "正在加载帮助内容..."
        }
      ]
    }
  }
}
```

### 详细文档

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_help_panel",
          "#header": {
            "#type": "aws_header",
            "#title": "用户手册"
          },
          "#content": "<h3>目录</h3><dl><dt>1. 概述</dt><dd>系统简介和主要功能</dd><dt>2. 快速入门</dt><dd>基础操作指南</dd><dt>3. 高级功能</dt><dd>进阶使用技巧</dd><dt>4. 故障排除</dt><dd>常见问题解答</dd></dl>",
          "#footer": {
            "#markup": "<p><strong>版本：</strong> 2.0.0</p><p><strong>更新时间：</strong> 2024-01-15</p>"
          }
        }
      ]
    }
  }
}
```

### 带链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_help_panel",
          "#header": {
            "#type": "aws_header",
            "#title": "相关资源"
          },
          "#content": "<p>查看更多资源：</p><ul><li><a href='#'>官方文档</a></li><li><a href='#'>视频教程</a></li><li><a href='#'>社区论坛</a></li></ul><hr/><p><em>最后更新于 2024年1月</em></p>"
        }
      ]
    }
  }
}
```
