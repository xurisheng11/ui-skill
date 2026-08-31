# aws_tag_editor 示例

本文档展示 aws_tag_editor 组件的各种使用场景。

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
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "Environment", "value": "Production", "existing": true },
            { "key": "Project", "value": "ISMP", "existing": false }
          ]
        }
      ]
    }
  }
}
```

### 2. 空标签列表

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": []
        }
      ]
    }
  }
}
```

### 3. 带标签限制

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#tag_limit": 5,
          "#default_value": [
            { "key": "Tag1", "value": "Value1" },
            { "key": "Tag2", "value": "Value2" }
          ]
        }
      ]
    }
  }
}
```

### 4. 现有标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "Environment", "value": "Production", "existing": true },
            { "key": "Application", "value": "WebApp", "existing": true },
            { "key": "CostCenter", "value": "CC-001", "existing": true }
          ]
        }
      ]
    }
  }
}
```

### 5. 标记删除的标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "Keep", "value": "This", "existing": true, "marked_for_removal": false },
            { "key": "Remove", "value": "This", "existing": true, "marked_for_removal": true }
          ]
        }
      ]
    }
  }
}
```

### 6. 资源标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "Name", "value": "Production Server", "existing": true },
            { "key": "Environment", "value": "prod", "existing": true },
            { "key": "Team", "value": "Infrastructure", "existing": true },
            { "key": "Backup", "value": "enabled", "existing": false }
          ]
        }
      ]
    }
  }
}
```

### 7. 新建标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "Department", "value": "IT", "existing": false },
            { "key": "ProjectCode", "value": "P2024", "existing": false }
          ]
        }
      ]
    }
  }
}
```

### 8. 混合标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "CreatedBy", "value": "admin", "existing": true, "marked_for_removal": false },
            { "key": "Status", "value": "active", "existing": true, "marked_for_removal": false },
            { "key": "Monitored", "value": "true", "existing": false }
          ]
        }
      ]
    }
  }
}
```

### 9. 产品标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "Product", "value": "ISMP", "existing": true },
            { "key": "Version", "value": "2.0", "existing": false },
            { "key": "Owner", "value": "DevOps", "existing": true }
          ]
        }
      ]
    }
  }
}
```

### 10. 环境标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "Env", "value": "production", "existing": true },
            { "key": "Region", "value": "us-east-1", "existing": true },
            { "key": "Cluster", "value": "main", "existing": false }
          ]
        }
      ]
    }
  }
}
```

### 11. 合规标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "Compliance", "value": "SOC2", "existing": true },
            { "key": "DataClassification", "value": "Internal", "existing": true },
            { "key": "Retention", "value": "90days", "existing": false }
          ]
        }
      ]
    }
  }
}
```

### 12. 成本标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "CostCenter", "value": "CC-001", "existing": true },
            { "key": "Project", "value": "CloudMigration", "existing": true },
            { "key": "Billable", "value": "Yes", "existing": false }
          ]
        }
      ]
    }
  }
}
```

### 13. 安全标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "SecurityLevel", "value": "High", "existing": true },
            { "key": "Encryption", "value": "Required", "existing": true },
            { "key": "BackupRequired", "value": "true", "existing": false }
          ]
        }
      ]
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
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "CustomTag1", "value": "Value1", "existing": false },
            { "key": "CustomTag2", "value": "Value2", "existing": false }
          ]
        }
      ]
    }
  }
}
```

### 15. 运维标签

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_tag_editor",
          "#default_value": [
            { "key": "ManagedBy", "value": "Terraform", "existing": true },
            { "key": "Environment", "value": "staging", "existing": true },
            { "key": "DeployedAt", "value": "2024-01-15", "existing": false },
            { "key": "OwnerTeam", "value": "Platform", "existing": true }
          ]
        }
      ]
    }
  }
}
```
