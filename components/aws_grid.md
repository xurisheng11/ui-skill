# aws_grid

网格组件，用于创建响应式网格布局。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| grid_definition | 数组 | 是 | 网格定义数组 |
| disable_gutters | 布尔值 | 否 | 隐藏水平和垂直间隔 |

### grid_definition 结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| colspan | 数字/对象 | 列跨越的网格元素数量 (1-12) |
| offset | 数字/对象 | 列偏移的网格元素数量 (0-11) |
| pull | 数字/对象 | 向左拉动的网格元素数量 (0-12) |
| push | 数字/对象 | 向右推动的网格元素数量 (0-12) |

**响应式断点**：`xxs`, `xs`, `s`, `m`, `l`, `xl`, `default`

### 插槽

| 插槽名 | 描述 | 可使用变量 | 使用方法 |
| --- | --- | --- | --- |
| content (默认) | 网格对齐的元素 | 是 | {variable} |

## 使用示例

### 基础两列布局

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
              "#markup": "<div>左侧边栏 (2列)</div><div>右侧内容 (10列)</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 三列等分布局

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

### 响应式布局（大屏4+8，小屏9+3）

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

### 带偏移的布局

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
            { "colspan": 4, "offset": 4 },
            { "colspan": 3, "offset": 1 }
          ],
          "#content": [
            {
              "#markup": "<div>居中内容</div><div>偏移内容</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 四列卡片布局

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

### 仪表盘布局

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
            { "colspan": 12 }
          ],
          "#content": [
            {
              "#markup": "<div>顶部统计卡片区</div>"
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
              "#markup": "<div>主图表区域 (8列)</div><div>侧边栏 (4列)</div>"
            }
          ]
        },
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 4 },
            { "colspan": 4 },
            { "colspan": 4 }
          ],
          "#content": [
            {
              "#markup": "<div>统计项1</div><div>统计项2</div><div>统计项3</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 无间距布局

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
              "#markup": "<div>左侧内容</div><div>右侧内容</div>"
            }
          ]
        }
      ]
    }
  }
}
```

### 表单布局

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
              "#markup": "<div>姓名输入框</div><div>邮箱输入框</div>"
            }
          ]
        },
        {
          "#type": "aws_grid",
          "#grid_definition": [
            { "colspan": 12 }
          ],
          "#content": [
            {
              "#markup": "<div>地址输入框（全宽）</div>"
            }
          ]
        }
      ]
    }
  }
}
```
