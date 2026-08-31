# aws_text_content

文本内容组件，用于显示格式化文本。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| class_name | 字符串 | 否 | 添加到根元素的类名（已弃用） |
| id | 字符串 | 否 | 添加到根元素的ID（已弃用） |

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| content (默认) | 组件子元素 | 是 | {variable} |

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

### 段落文本

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

### 列表

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

### 有序列表

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

### 定义列表

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
            "#markup": "<h3>术语解释</h3><dl><dt>API</dt><dd>应用程序编程接口</dd><dt>SDK</dt><dd>软件开发工具包</dd><dt>UI</dt><dd>用户界面</dd></dl>"
          }
        }
      ]
    }
  }
}
```

### 代码块

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

### 强调文本

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
            "#markup": "<p><strong>重要：</strong>请仔细阅读以下条款。</p><p><em>注意：</em>此操作不可撤销。</p><p><b>警告：</b>数据删除后将无法恢复。</p>"
          }
        }
      ]
    }
  }
}
```

### 链接文本

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
            "#markup": "<p>更多信息，请访问：</p><ul><li><a href='#'>官方文档</a></li><li><a href='#'>API 参考</a></li><li><a href='#'>技术支持</a></li></ul>"
          }
        }
      ]
    }
  }
}
```

### 分隔线

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

### 复杂排版

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
            "#markup": "<h2>产品介绍</h2><p>这是一款功能强大的企业级应用系统。</p><h3>主要特性</h3><ul><li><strong>高性能：</strong>采用先进的架构设计</li><li><strong>安全可靠：</strong>多重安全防护机制</li><li><strong>易于使用：</strong>友好的用户界面</li></ul><h3>使用场景</h3><ol><li>企业办公管理</li><li>项目管理协作</li><li>数据统计分析</li></ol><hr/><p><em>如需了解更多，请联系我们的客服团队。</em></p>"
          }
        }
      ]
    }
  }
}
```

### 内联元素

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
            "#markup": "<p>支持<span>内联</span>元素的<span style='color:red'>样式</span>设置。</p>"
          }
        }
      ]
    }
  }
}
```

### 用户协议

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
            "#markup": "<h3>用户协议</h3><p>欢迎使用我们的服务。</p><p><strong>1. 服务条款</strong></p><p>使用本服务即表示您同意以下条款...</p><p><strong>2. 隐私政策</strong></p><p>我们尊重您的隐私...</p><p><strong>3. 免责声明</strong></p><p>服务按\"原样\"提供...</p>"
          }
        }
      ]
    }
  }
}
```
