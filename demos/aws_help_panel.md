# aws_help_panel 示例

本文档展示 aws_help_panel 组件的各种使用场景。

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

### 2. 带页脚

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

### 3. 带列表

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
          "#content": "<h3>入门步骤</h3><ol><li>注册账户</li><li>验证邮箱</li><li>完成个人资料</li><li>开始使用</li></ol>"
        }
      ]
    }
  }
}
```

### 4. 带代码块

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
          "#content": "<h3>快速开始</h3><p>使用以下代码获取数据：</p><pre><code>GET /api/v1/users</code></pre>"
        }
      ]
    }
  }
}
```

### 5. 加载状态

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

### 6. 用户手册

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
          "#content": "<h3>目录</h3><dl><dt>1. 概述</dt><dd>系统简介和主要功能</dd><dt>2. 快速入门</dt><dd>基础操作指南</dd><dt>3. 高级功能</dt><dd>进阶使用技巧</dd></dl>",
          "#footer": {
            "#markup": "<p><strong>版本：</strong> 2.0.0</p>"
          }
        }
      ]
    }
  }
}
```

### 7. 功能介绍

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
            "#title": "功能介绍"
          },
          "#content": "<h3>主要功能</h3><ul><li><strong>数据分析</strong>：强大的数据分析和可视化能力</li><li><strong>报表生成</strong>：一键生成各类统计报表</li><li><strong>实时监控</strong>：24小时实时监控系统状态</li><li><strong>告警通知</strong>：多渠道告警通知</li></ul>"
        }
      ]
    }
  }
}
```

### 8. 操作指南

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
            "#title": "操作指南"
          },
          "#content": "<h3>创建项目</h3><ol><li>点击\"新建项目\"按钮</li><li>填写项目基本信息</li><li>配置项目参数</li><li>点击\"创建\"完成</li></ol><hr/><p><em>提示：创建后可在项目设置中修改配置</em></p>"
        }
      ]
    }
  }
}
```

### 9. 术语解释

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
            "#title": "术语解释"
          },
          "#content": "<dl><dt><strong>API</strong></dt><dd>应用程序编程接口，用于系统间通信</dd><dt><strong>SDK</strong></dt><dd>软件开发工具包，包含开发所需的工具和库</dd><dt><strong>Webhook</strong></dt><dd>一种回调机制，用于事件通知</dd></dl>"
        }
      ]
    }
  }
}
```

### 10. 联系支持

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
            "#title": "联系支持"
          },
          "#content": "<p>如果您需要帮助，请通过以下方式联系我们：</p><ul><li><strong>邮箱：</strong>support@example.com</li><li><strong>电话：</strong>400-xxx-xxxx</li><li><strong>在线客服：</strong>工作日 9:00-18:00</li></ul>",
          "#footer": {
            "#markup": "<p><a href='#'>提交工单</a></p>"
          }
        }
      ]
    }
  }
}
```

### 11. 故障排除

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
            "#title": "故障排除"
          },
          "#content": "<h3>常见问题</h3><p><strong>Q: 无法登录怎么办？</strong></p><p>A: 请检查用户名密码是否正确，或尝试重置密码。</p><p><strong>Q: 数据加载失败？</strong></p><p>A: 请检查网络连接，或刷新页面重试。</p>"
        }
      ]
    }
  }
}
```

### 12. 版本说明

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
            "#title": "版本说明"
          },
          "#content": "<h3>v2.0.0 (2024-01)</h3><ul><li>新增数据分析功能</li><li>优化用户界面</li><li>修复已知问题</li></ul><h3>v1.5.0 (2023-12)</h3><ul><li>新增报表导出</li><li>性能优化</li></ul>"
        }
      ]
    }
  }
}
```

### 13. 快捷键

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
            "#title": "快捷键"
          },
          "#content": "<h3>全局快捷键</h3><dl><dt>Ctrl + S</dt><dd>保存当前内容</dd><dt>Ctrl + Z</dt><dd>撤销</dd><dt>Ctrl + Shift + Z</dt><dd>重做</dd><dt>Ctrl + F</dt><dd>搜索</dd></dl>"
        }
      ]
    }
  }
}
```

### 14. 权限说明

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
            "#title": "权限说明"
          },
          "#content": "<h3>角色权限</h3><ul><li><strong>管理员</strong>：拥有所有权限</li><li><strong>编辑者</strong>：可创建、编辑内容</li><li><strong>查看者</strong>：仅可查看内容</li></ul>"
        }
      ]
    }
  }
}
```

### 15. 更新日志

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
            "#title": "更新日志"
          },
          "#content": "<h3>2024-01-15</h3><ul><li>优化了登录页面加载速度</li><li>新增深色模式支持</li><li>修复了若干Bug</li></ul><hr/><p><em>最后更新于 2024年1月</em></p>"
        }
      ]
    }
  }
}
```
