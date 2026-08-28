# aws_text_content 示例

本文档展示 aws_text_content 组件的各种使用场景。

## 示例列表

### 1. 基础标题

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h1>Heading 1</h1><h2>Heading 2</h2><h3>Heading 3</h3>"
          }
        }
      ]
    }
  }
}
```

### 2. 段落文本

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<p>这是一个段落文本，用于展示普通文本内容。</p><p>这是第二个段落，包含更多详细信息。</p>"
          }
        }
      ]
    }
  }
}
```

### 3. 列表

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>功能列表</h3><ul><li>用户管理</li><li>权限控制</li><li>数据统计</li><li>系统设置</li></ul>"
          }
        }
      ]
    }
  }
}
```

### 4. 代码块

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>代码示例</h3><pre><code>const greeting = 'Hello World';\nconsole.log(greeting);</code></pre>"
          }
        }
      ]
    }
  }
}
```

### 5. 定义列表

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>术语解释</h3><dl><dt>API</dt><dd>应用程序编程接口</dd><dt>SDK</dt><dd>软件开发工具包</dd></dl>"
          }
        }
      ]
    }
  }
}
```

### 6. 强调文本

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<p><strong>重要：</strong>请仔细阅读以下条款。</p><p><em>注意：</em>此操作不可撤销。</p>"
          }
        }
      ]
    }
  }
}
```

### 7. 链接文本

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<p>更多信息，请访问：</p><ul><li><a href='#'>官方文档</a></li><li><a href='#'>API 参考</a></li></ul>"
          }
        }
      ]
    }
  }
}
```

### 8. 分隔线

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<p>第一部分内容...</p><hr/><p>第二部分内容...</p>"
          }
        }
      ]
    }
  }
}
```

### 9. 产品介绍

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h2>产品介绍</h2><p>这是一款功能强大的企业级应用系统。</p><h3>主要特性</h3><ul><li><strong>高性能：</strong>采用先进的架构设计</li><li><strong>安全可靠：</strong>多重安全防护机制</li></ul>"
          }
        }
      ]
    }
  }
}
```

### 10. 操作步骤

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>操作步骤</h3><ol><li>登录系统</li><li>选择功能模块</li><li>填写表单</li><li>提交保存</li></ol>"
          }
        }
      ]
    }
  }
}
```

### 11. 用户协议

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>用户协议</h3><p><strong>1. 服务条款</strong></p><p>使用本服务即表示您同意以下条款...</p><p><strong>2. 隐私政策</strong></p><p>我们尊重您的隐私...</p>"
          }
        }
      ]
    }
  }
}
```

### 12. 常见问题

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>常见问题</h3><p><strong>Q: 如何重置密码？</strong></p><p>A: 请访问登录页面，点击\"忘记密码\"链接。</p><p><strong>Q: 如何联系客服？</strong></p><p>A: 发送邮件至 support@example.com</p>"
          }
        }
      ]
    }
  }
}
```

### 13. 版本说明

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>更新日志</h3><h4>v2.0.0 (2024-01)</h4><ul><li>新增数据分析功能</li><li>优化用户界面</li><li>修复已知问题</li></ul>"
          }
        }
      ]
    }
  }
}
```

### 14. 技术文档

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>快速开始</h3><p>使用以下代码获取数据：</p><pre><code>GET /api/v1/users</code></pre><h4>参数说明</h4><ul><li>page - 页码</li><li>limit - 每页数量</li></ul>"
          }
        }
      ]
    }
  }
}
```

### 15. 联系信息

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_text_content",
          "#content": {
            "#markup": "<h3>联系我们</h3><p><strong>电话：</strong>400-xxx-xxxx</p><p><strong>邮箱：</strong>contact@example.com</p><p><strong>地址：</strong>北京市朝阳区xxx路xxx号</p><hr/><p><em>工作时间：周一至周五 9:00-18:00</em></p>"
          }
        }
      ]
    }
  }
}
```
