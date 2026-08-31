# aws_pagination 示例

本文档展示 aws_pagination 组件的各种使用场景。

## 示例列表

### 1. 基础用法

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

### 2. 带中文标签

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

### 3. 开放结尾分页

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

### 4. 少页数

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

### 5. 大页数

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
          "#default_value": 50
        }
      }
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

### 7. 从第5页开始

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
          "#pages_count": 15,
          "#default_value": 5
        }
      }
    }
  }
}
```

### 8. 最后一页

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
          "#default_value": 10
        }
      }
    }
  }
}
```

### 9. 英文标签

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
          "#default_value": 3,
          "#aria_labels": {
            "pagination_label": "Table pagination",
            "previous_page_label": "Previous page",
            "next_page_label": "Next page"
          }
        }
      }
    }
  }
}
```

### 10. 默认起始页

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
          "#pages_count": 8,
          "#default_value": 1
        }
      }
    }
  }
}
```

### 11. 中间页

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
          "#default_value": 10
        }
      }
    }
  }
}
```

### 12. 大量数据

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
          "#pages_count": 500,
          "#default_value": 1
        }
      }
    }
  }
}
```

### 13. 少量数据

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
          "#pages_count": 2,
          "#default_value": 1
        }
      }
    }
  }
}
```

### 14. 自定义标签

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
          "#pages_count": 12,
          "#default_value": 7,
          "#aria_labels": {
            "pagination_label": "评论分页",
            "previous_page_label": "上一页",
            "next_page_label": "下一页",
            "page_label": "第 ${pageNumber} 页，共 ${totalPages} 页"
          }
        }
      }
    }
  }
}
```

### 15. 两页数据

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
          "#pages_count": 2,
          "#default_value": 1
        }
      }
    }
  }
}
```
