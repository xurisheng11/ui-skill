# aws_button_dropdown 示例

本文档展示 aws_button_dropdown 组件的各种使用场景。

## 示例列表

### 1. 基础用法

最基本的下拉按钮示例。

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
            { "text": "编辑", "id": "edit" },
            { "text": "复制", "id": "copy" },
            { "text": "删除", "id": "delete" }
          ]
        }
      ]
    }
  }
}
```

### 2. 主要按钮样式

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
          "#text": "新建",
          "#variant": "primary",
          "#items": [
            { "text": "文件夹", "id": "folder" },
            { "text": "文档", "id": "document" },
            { "text": "从模板创建", "id": "from-template" }
          ]
        }
      ]
    }
  }
}
```

### 3. 带禁用选项

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
          "#text": "Short",
          "#items": [
            { "text": "Delete", "id": "rm", "disabled": false },
            { "text": "Move", "id": "mv", "disabled": false },
            { "text": "Rename", "id": "rn", "disabled": true }
          ]
        }
      ]
    }
  }
}
```

### 4. 带外部链接

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
          "#text": "Short",
          "#items": [
            { "text": "Delete", "id": "rm", "disabled": false },
            { "text": "Move", "id": "mv", "disabled": false },
            { "text": "Rename", "id": "rn", "disabled": true },
            {
              "id": "view",
              "text": "View metrics",
              "href": "https://example.com",
              "external": true,
              "externalIconAriaLabel": "(opens in new tab)"
            }
          ]
        }
      ]
    }
  }
}
```

### 5. 带主动作

主动作显示在下拉触发器旁边，适合主次操作分明的场景。

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
            "text": "创建",
            "href": "/create"
          },
          "#items": [
            { "text": "从模板创建", "id": "from-template" },
            { "text": "导入文件", "id": "import" },
            { "text": "批量创建", "id": "batch" }
          ]
        }
      ]
    }
  }
}
```

### 6. 禁用状态

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

### 7. 加载状态

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

### 8. 自定义点击事件

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
          "#text": "Short",
          "#on_item_click": "if(detail.id=='aaa'||detail.id=='bbb'||detail.id=='ccc'){console.log(detail.id + ' Button clicked')}",
          "#items": [
            { "id": "aaa", "text": "aaa text" },
            { "id": "bbb", "text": "bbb text", "form_action": "none" },
            { "id": "ccc", "text": "ccc text", "href": "https://example.com" }
          ]
        }
      ]
    }
  }
}
```

### 9. 图标按钮

无文本的图标按钮下拉菜单。

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

### 10. 排序下拉

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
          "#items": [
            { "text": "按名称排序", "id": "sort-name" },
            { "text": "按创建时间排序", "id": "sort-created" },
            { "text": "按修改时间排序", "id": "sort-modified" },
            { "text": "按大小排序", "id": "sort-size" }
          ]
        }
      ]
    }
  }
}
```

### 11. 筛选下拉

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
          "#text": "筛选",
          "#items": [
            { "text": "全部显示", "id": "show-all" },
            { "text": "仅显示文件夹", "id": "show-folders" },
            { "text": "仅显示文件", "id": "show-files" },
            { "text": "仅显示收藏", "id": "show-favorites" }
          ]
        }
      ]
    }
  }
}
```

### 12. 导出操作

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
          "#text": "导出",
          "#variant": "primary",
          "#items": [
            { "text": "导出为 CSV", "id": "export-csv" },
            { "text": "导出为 Excel", "id": "export-excel" },
            { "text": "导出为 PDF", "id": "export-pdf" }
          ]
        }
      ]
    }
  }
}
```
