# aws_button_dropdown

AWS 下拉按钮组件，带有下拉菜单的按钮组件，用于展示多个可选操作。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| variant | 字符串 | 否 | 确定按钮下拉的整体样式 | primary / normal / icon / inline-icon | 'normal' |
| text | 字符串 | 是 | 按钮元素中显示的文本 | - | - |
| disabled | 布尔值 | 否 | 决定按钮下拉是否被禁用 | - | false |
| disabled_reason | 字符串 | 否 | 提供按钮下拉被禁用的原因（仅在 disabled 为 true 时有效） | - | - |
| loading | 布尔值 | 否 | 将按钮渲染为加载状态 | - | false |
| loading_text | 字符串 | 否 | 加载状态时屏幕阅读器播报的文本 | - | - |
| expandable_groups | 布尔值 | 否 | 控制项目组的可扩展性 | - | false |
| expand_to_viewport | 布尔值 | 允许下拉菜单扩展到容器外 | - | false |

### 功能属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| main_action | 对象 | 否 | 在下拉触发器之前显示的独立动作（仅与 primary 和 normal 变体一起使用） | MainAction 对象 | - |
| on_item_click | 函数 | 否 | 自定义点击事件 | - | - |

### main_action 子属性

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| text | 字符串 | 显示在主动作中的文字 |
| external | 布尔值 | 标记主动作作为外部链接 |
| href | 字符串 | 链接地址 |

### 无障碍属性

| 属性名 | 类型 | 必填 | 描述 | 可接受值 | 默认值 |
| --- | --- | --- | --- | --- | --- |
| aria_label | 字符串 | 否 | 向按钮下拉触发器添加 aria-label（当按钮没有可见文本时使用） | - | - |

### variant 可选值说明

| 值 | 描述 |
| --- | --- |
| primary | 主要按钮样式 |
| normal | 次要按钮样式（默认） |
| icon | 图标按钮样式 |
| inline-icon | 无外边距的图标按钮样式 |

## items 子属性说明

下拉菜单中的每个选项有以下属性：

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| id | 字符串 | 选项的唯一标识符 |
| text | 字符串 | 选项显示的文本 |
| disabled | 布尔值 | 是否禁用该选项 |
| href | 字符串 | 链接地址（可选） |
| external | 布尔值 | 是否为外部链接 |
| externalIconAriaLabel | 字符串 | 外部链接图标的 aria-label |
| form_action | 字符串 | 表单动作类型 |

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
          "#type": "aws_button_dropdown",
          "#text": "操作",
          "#items": [
            { "text": "删除", "id": "delete" },
            { "text": "移动", "id": "move" },
            { "text": "重命名", "id": "rename" }
          ]
        }
      ]
    }
  }
}
```

### 不同变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_dropdown",
          "#text": "主要按钮",
          "#variant": "primary",
          "#items": [
            { "text": "选项1", "id": "opt1" },
            { "text": "选项2", "id": "opt2" }
          ]
        },
        {
          "#type": "aws_button_dropdown",
          "#text": "普通按钮",
          "#variant": "normal",
          "#items": [
            { "text": "选项1", "id": "opt1" },
            { "text": "选项2", "id": "opt2" }
          ]
        }
      ]
    }
  }
}
```

### 带禁用选项

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_dropdown",
          "#text": "文件操作",
          "#items": [
            { "text": "删除", "id": "rm", "disabled": false },
            { "text": "移动", "id": "mv", "disabled": false },
            { "text": "重命名", "id": "rn", "disabled": true }
          ]
        }
      ]
    }
  }
}
```

### 带外部链接

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_dropdown",
          "#text": "更多操作",
          "#items": [
            { "text": "编辑", "id": "edit" },
            {
              "id": "view",
              "text": "查看详情",
              "href": "https://example.com",
              "external": true,
              "externalIconAriaLabel": "（在新标签页打开）"
            }
          ]
        }
      ]
    }
  }
}
```

### 带主动作

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_dropdown",
          "#text": "更多",
          "#variant": "primary",
          "#main_action": {
            "text": "新建",
            "href": "/create"
          },
          "#items": [
            { "text": "从模板创建", "id": "from-template" },
            { "text": "导入", "id": "import" }
          ]
        }
      ]
    }
  }
}
```

### 禁用状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_dropdown",
          "#text": "操作",
          "#disabled": true,
          "#disabled_reason": "该功能已暂时禁用",
          "#items": [
            { "text": "选项1", "id": "opt1" }
          ]
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
          "#type": "aws_button_dropdown",
          "#text": "加载中",
          "#loading": true,
          "#loading_text": "正在加载选项...",
          "#items": [
            { "text": "选项1", "id": "opt1" }
          ]
        }
      ]
    }
  }
}
```

### 自定义点击事件

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_dropdown",
          "#text": "快捷操作",
          "#on_item_click": "if(detail.id=='aaa'||detail.id=='bbb'){console.log(detail.id + ' clicked')}",
          "#items": [
            { "id": "aaa", "text": "操作A" },
            { "id": "bbb", "text": "操作B" },
            { "id": "ccc", "text": "操作C", "href": "https://example.com" }
          ]
        }
      ]
    }
  }
}
```

### 图标按钮变体

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_dropdown",
          "#variant": "icon",
          "#aria_label": "更多操作",
          "#items": [
            { "text": "编辑", "id": "edit" },
            { "text": "删除", "id": "delete" },
            { "text": "复制", "id": "copy" }
          ]
        }
      ]
    }
  }
}
```

### 工具栏操作

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_button_dropdown",
          "#text": "排序",
          "#variant": "normal",
          "#items": [
            { "text": "按名称排序", "id": "sort-name" },
            { "text": "按日期排序", "id": "sort-date" },
            { "text": "按大小排序", "id": "sort-size" }
          ]
        },
        {
          "#type": "aws_button_dropdown",
          "#text": "筛选",
          "#variant": "normal",
          "#items": [
            { "text": "全部显示", "id": "show-all" },
            { "text": "仅显示文件夹", "id": "show-folders" },
            { "text": "仅显示文件", "id": "show-files" }
          ]
        }
      ]
    }
  }
}
```
