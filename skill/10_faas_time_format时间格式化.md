# 实践样例：faas_time_format 时间格式化

前端 JS 工具函数，将 UTC 时间字符串转换为北京时间（GMT+8）显示格式。

## 函数实现（resources/js/faas_time_format.js）

```javascript
function faas_time_format(utcTimeString) {
  if (!utcTimeString) return '';

  const date = new Date(utcTimeString);

  const options = {
    timeZone: 'Asia/Shanghai',
    year: 'numeric',
    month: '2-digit',
    day: '2-digit',
    hour: '2-digit',
    minute: '2-digit',
    second: '2-digit',
    hour12: false,
  };
  const beijingTimeString = date.toLocaleString('zh-CN', options);
  return beijingTimeString
    .replace(/年|月/g, '-')
    .replace(/日/g, '')
    .replace(/\//g, '-')
    .replace(/,/g, '');
}
// 输出格式：2024-01-15 14:30:00
```

## 在表格列中使用

```typescript
// TypeScript 中定义时间列头
BaseUI.tableHeaderTime('createdAt', '创建时间')
// 等价于：
BaseUI.tableHeader('createdAt', '创建时间', 'faas_time_format(item.createdAt)', '140px')
```

```json
// JSON 中直接引用
{
  "id": "createdAt",
  "header": "创建时间",
  "cell": "faas_time_format(item.createdAt)",
  "sortingField": "createdAt",
  "minWidth": "140px"
}
```

## 在详情页卡片中使用

```typescript
// TypeScript 中
BaseUI.cardItemTime('创建时间', data.createdAt)
// 等价于：
BaseUI.cardItem(
  '创建时间',
  BaseUI.box({
    '#theme': 'time_format',
    time: data.createdAt,
  })
)
```

```json
// JSON 中
{
  "label": "创建时间",
  "value": {
    "#type": "aws_box",
    "#content": {
      "#theme": "time_format",
      "time": "2024-01-15T06:30:00.000Z"
    }
  }
}
```

## 在 JavaScript 中直接调用

```javascript
// 在 useEffect 注入的 JS 代码中使用
var formattedTime = faas_time_format(item.createdAt);
document.getElementById('time_span').textContent = formattedTime;
```

## 注意事项

- 输入格式：ISO 8601 UTC 时间字符串，如 `2024-01-15T06:30:00.000Z`
- 输出格式：`2024-01-15 14:30:00`（北京时间）
- 空值处理：传入空值时返回空字符串 `''`
- 此函数由框架自动注入前端，无需手动引入
