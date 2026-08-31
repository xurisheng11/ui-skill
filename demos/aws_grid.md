# aws_grid 示例

本文档展示 aws_grid 组件的各种使用场景。

## 示例列表

### 1. 基础两列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 2 },
            { "colspan": 10 }
          ],
          "#content": [
            {
              "#markup": "<div>左侧 (2列)</div><div>右侧 (10列)</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 2. 三列等分布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 4 },
            { "colspan": 4 },
            { "colspan": 4 }
          ],
          "#content": [
            {
              "#markup": "<div>第一列</div><div>第二列</div><div>第三列</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 3. 响应式布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": { "default": 3, "xs": 9 } },
            { "colspan": { "default": 9, "xs": 3 } }
          ],
          "#content": [
            {
              "#markup": "<div>块1</div><div>块2</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 4. 四列卡片

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 3 },
            { "colspan": 3 },
            { "colspan": 3 },
            { "colspan": 3 }
          ],
          "#content": [
            {
              "#markup": "<div>卡片1</div><div>卡片2</div><div>卡片3</div><div>卡片4</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 5. 带偏移布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 4, "offset": 4 }
          ],
          "#content": [
            {
              "#markup": "<div>居中内容</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 6. 仪表盘布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [{ "colspan": 12 }],
          "#content": [
            {
              "#markup": "<div>统计卡片区</div>"
            }
          ]
        },
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 8 },
            { "colspan": 4 }
          ],
          "#content": [
            {
              "#markup": "<div>主图表</div><div>侧边栏</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 7. 表单布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 6 },
            { "colspan": 6 }
          ],
          "#content": [
            {
              "#markup": "<div>姓名</div><div>邮箱</div>"
            }
          ]
        },
        {
          "#type": "aws_grid",
          "#grid_definition": [{ "colspan": 12 }],
          "#content": [
            {
              "#markup": "<div>地址（全宽）</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 8. 六列布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 2 },
            { "colspan": 2 },
            { "colspan": 2 },
            { "colspan": 2 },
            { "colspan": 2 },
            { "colspan": 2 }
          ],
          "#content": [
            {
              "#markup": "<div>1</div><div>2</div><div>3</div><div>4</div><div>5</div><div>6</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 9. 无间距布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#disable_gutters": true,
          "#grid_definition": [
            { "colspan": 6 },
            { "colspan": 6 }
          ],
          "#content": [
            {
              "#markup": "<div>无间距内容1</div><div>无间距内容2</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 10. 混合布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 3 },
            { "colspan": 6 },
            { "colspan": 3 }
          ],
          "#content": [
            {
              "#markup": "<div>左</div><div>中</div><div>右</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 11. 大小屏不同

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": { "default": 4, "l": 3, "m": 6, "s": 12 } },
            { "colspan": { "default": 4, "l": 3, "m": 6, "s": 12 } },
            { "colspan": { "default": 4, "l": 6, "m": 12 } }
          ],
          "#content": [
            {
              "#markup": "<div>响应式块1</div><div>响应式块2</div><div>响应式块3</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 12. 列表布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 1 },
            { "colspan": 11 }
          ],
          "#content": [
            {
              "#markup": "<div>图标</div><div>标题和描述</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 13. 详情页布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 2 },
            { "colspan": 4 },
            { "colspan": 2 },
            { "colspan": 4 }
          ],
          "#content": [
            {
              "#markup": "<div>标签1</div><div>值1</div><div>标签2</div><div>值2</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 14. 推送布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 4, "push": 2 }
          ],
          "#content": [
            {
              "#markup": "<div>被推送的内容</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 15. 拉取布局

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 4, "pull": 2 }
          ],
          "#content": [
            {
              "#markup": "<div>被拉取的内容</div>"
            }
          ]
        }
      ]
    }
  }
}
```
