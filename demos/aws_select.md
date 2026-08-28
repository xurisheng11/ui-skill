# aws_select 示例

本文档展示 aws_select 组件的各种使用场景。

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
          "#type": "aws_select",
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" }
          ]
        }
      ]
    }
  }
}
```

### 2. 带占位符

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#placeholder": "请选择一个选项",
          "#select_options": [
            { "label": "北京", "value": "bj" },
            { "label": "上海", "value": "sh" },
            { "label": "广州", "value": "gz" },
            { "label": "深圳", "value": "sz" }
          ]
        }
      ]
    }
  }
}
```

### 3. 带描述

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#select_options": [
            { "label": "通用型", "value": "general", "description": "适用于通用计算场景" },
            { "label": "计算型", "value": "compute", "description": "适用于计算密集型场景" },
            { "label": "内存型", "value": "memory", "description": "适用于内存密集型场景" }
          ]
        }
      ]
    }
  }
}
```

### 4. 分组选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#select_options": [
            {
              "label": "计算服务",
              "options": [
                { "label": "EC2", "value": "ec2" },
                { "label": "Lambda", "value": "lambda" }
              ]
            },
            {
              "label": "存储服务",
              "options": [
                { "label": "S3", "value": "s3" },
                { "label": "EBS", "value": "ebs" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 5. 带图标

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#select_options": [
            { "label": "文件夹", "value": "folder", "icon_name": "folder" },
            { "label": "文件", "value": "file", "icon_name": "file" }
          ]
        }
      ]
    }
  }
}
```

### 6. 禁用选项

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#select_options": [
            { "label": "运行中", "value": "running" },
            { "label": "已停止", "value": "stopped", "disabled": true },
            { "label": "已删除", "value": "deleted", "disabled": true }
          ]
        }
      ]
    }
  }
}
```

### 7. 带标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#select_options": [
            { "label": "开发环境", "value": "dev", "label_tag": "推荐" },
            { "label": "测试环境", "value": "test", "label_tag": "常用" },
            { "label": "生产环境", "value": "prod", "label_tag": "重要" }
          ]
        }
      ]
    }
  }
}
```

### 8. 自动过滤

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#filtering_type": "auto",
          "#filtering_placeholder": "搜索...",
          "#select_options": [
            { "label": "Apple 苹果", "value": "apple" },
            { "label": "Banana 香蕉", "value": "banana" },
            { "label": "Cherry 樱桃", "value": "cherry" }
          ]
        }
      ]
    }
  }
}
```

### 9. 带默认值

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" },
            { "label": "选项 3", "value": "3" }
          ],
          "#default_value": { "label": "选项 2", "value": "2" }
        }
      ]
    }
  }
}
```

### 10. 禁用状态

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#disabled": true,
          "#select_options": [
            { "label": "选项 1", "value": "1" },
            { "label": "选项 2", "value": "2" }
          ]
        }
      ]
    }
  }
}
```

### 11. 显示完整选项

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#trigger_variant": "option",
          "#select_options": [
            { "label": "北京", "value": "bj", "icon_name": "location-pin" },
            { "label": "上海", "value": "sh", "icon_name": "location-pin" },
            { "label": "广州", "value": "gz", "icon_name": "location-pin" }
          ]
        }
      ]
    }
  }
}
```

### 12. 无匹配提示

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#filtering_type": "auto",
          "#no_match": "未找到匹配的选项",
          "#select_options": [
            { "label": "选项 A", "value": "a" },
            { "label": "选项 B", "value": "b" }
          ]
        }
      ]
    }
  }
}
```

### 13. 国家选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#placeholder": "选择国家",
          "#select_options": [
            { "label": "中国", "value": "cn" },
            { "label": "美国", "value": "us" },
            { "label": "日本", "value": "jp" },
            { "label": "韩国", "value": "kr" },
            { "label": "英国", "value": "uk" },
            { "label": "德国", "value": "de" }
          ]
        }
      ]
    }
  }
}
```

### 14. 禁用整组

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#select_options": [
            {
              "label": "可用组",
              "options": [
                { "label": "选项1", "value": "1" },
                { "label": "选项2", "value": "2" }
              ]
            },
            {
              "label": "禁用组",
              "disabled": true,
              "options": [
                { "label": "选项3", "value": "3" },
                { "label": "选项4", "value": "4" }
              ]
            }
          ]
        }
      ]
    }
  }
}
```

### 15. 状态选择

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_select",
          "#placeholder": "选择状态",
          "#select_options": [
            { "label": "待处理", "value": "pending" },
            { "label": "进行中", "value": "processing" },
            { "label": "已完成", "value": "completed" },
            { "label": "已取消", "value": "cancelled" }
          ]
        }
      ]
    }
  }
}
```
