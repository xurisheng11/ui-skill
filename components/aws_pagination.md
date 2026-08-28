# aws_pagination

分页组件。

## 参数说明

### 主要属性

| 属性名 | 类型 | 必填 | 描述 |
| --- | --- | --- | --- |
| pages_count | 数字 | 是 | 总页数 |
| default_value | 数字 | 是 | 当前页索引（从1开始） |
| disabled | 布尔值 | 否 | 是否禁用 |
| open_end | 布尔值 | 否 | 开放结尾分页 |
| aria_labels | 对象 | 否 | aria标签 |

### aria_labels 结构

| 属性 | 类型 | 描述 |
| --- | --- | --- |
| pagination_label | 字符串 | 分页组件标签 |
| previous_page_label | 字符串 | 上一页按钮标签 |
| page_label | 函数 | 单个页面按钮标签函数 |
| next_page_label | 字符串 | 下一页按钮标签 |

## 使用示例

### 基础用法

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "pagination": {
          "#type": "aws_pagination",
          "#pages_count": 10,
          "#default_value": 1
        }
      }
    }
  }
}
```

### 带中文标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "pagination": {
          "#type": "aws_pagination",
          "#pages_count": 20,
          "#default_value": 5,
          "#aria_labels": {
            "pagination_label": "表格分页",
            "previous_page_label": "上一页",
            "next_page_label": "下一页",
            "page_label": "第 ${pageNumber} 页"
          }
        }
      }
    }
  }
}
```

### 开放结尾分页

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "pagination": {
          "#type": "aws_pagination",
          "#open_end": true,
          "#default_value": 1
        }
      }
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
      "#children": {
        "pagination": {
          "#type": "aws_pagination",
          "#pages_count": 5,
          "#default_value": 1,
          "#disabled": true
        }
      }
    }
  }
}
```

### 少页数分页

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "pagination": {
          "#type": "aws_pagination",
          "#pages_count": 3,
          "#default_value": 2
        }
      }
    }
  }
}
```

### 大页数分页

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "pagination": {
          "#type": "aws_pagination",
          "#pages_count": 100,
          "#default_value": 50,
          "#aria_labels": {
            "pagination_label": "列表分页"
          }
        }
      }
    }
  }
}
```
