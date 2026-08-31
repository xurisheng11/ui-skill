# const_define 变量定义模式

## 概述

`const_define` 是 `Base.successWrapper()` 的第四个参数，用于定义前端状态变量（相当于 React 的 useState）。

## 基础结构

```typescript
return Base.successWrapper(
  content,          // 页面内容
  [jsFunction],     // JS 函数数组
  ['class-name'],   // CSS 类名
  [                  // const_define 变量定义
    {
      value: 'variableName',
      set_value: 'set_variableName',
      default: defaultValue
    }
  ]
);
```

## 变量定义格式

```typescript
const_define = [
  {
    value: 'variableName',      // 变量名（用于 JS 中访问 value_variableName
    set_value: 'set_variableName', // 设置函数名（用于 JS 中调用 set_variableName(value)
    default: defaultValue       // 默认值
  }
]
```

## 常用变量类型

### 字符串

```typescript
{
  value: 'configured_level',
  set_value: 'set_configured_level',
  default: '未设置'
}
```

### 数字

```typescript
{
  value: 'num',
  set_value: 'set_num',
  default: 0
}
```

### 布尔值

```typescript
{
  value: 'hasVersion',
  set_value: 'set_hasVersion',
  default: true
}
```

### 对象

```typescript
{
  value: 'spotCheckOpinion',
  set_value: 'set_spotCheckOpinion',
  default: null
}
```

### 数组

```typescript
{
  value: 'version',
  set_value: 'set_version',
  default: []
}
```

### 复杂数组

```typescript
{
  value: 'items_list',
  set_value: 'set_items_list',
  default: [
    { field1: 'value1', field2: 'value2' }
  ]
}
```

## 完整示例

```typescript
return Base.successWrapper(
  BaseUI.spaceBetween({
    info: BaseUI.cardPanelWithEdit(
      '基本信息',
      '',
      {
        level: BaseUI.cardItem('等级', BaseUI.markupItem('configured_level')),
        result: BaseUI.cardItem('结果', BaseUI.statusIndicator(
          BaseUI.markupItem('result_type'),
          BaseUI.markupItem('{result_text}')
        )),
      },
      false,
    ),
    list: BaseUI.tableWithActions(
      'list',
      '列表',
      buttons,
      BaseUI.tableSelect(headers, 'items_list', -1)
    ),
  }),
  [this.getDataJs],
  ['mb-4'],
  [
    {
      value: 'configured_level',
      set_value: 'set_configured_level',
      default: '未设置',
    },
    {
      value: 'result_type',
      set_value: 'set_result_type',
      default: 'pending',
    },
    {
      value: 'result_text',
      set_value: 'set_result_text',
      default: '--',
    },
    {
      value: 'items_list',
      set_value: 'set_items_list',
      default: [],
    },
    {
      value: 'num',
      set_value: 'set_num',
      default: 0,
    },
  ],
);
```

## JS 中使用变量

### 获取值

```javascript
// 获取变量值
value_configured_level
value_items_list
value_num
```

### 设置值

```javascript
// 设置字符串/数字
set_configured_level('L1');
set_num(1);

// 设置布尔值
set_hasVersion(true);

// 设置数组
set_version([{ value: '1', label: '选项1' }]);
set_items_list([{ id: 1, name: '项目' }]);

// 设置对象
set_spotCheckOpinion({ opinion: '通过', status: 'PASSED' });
```

## 监听与联动

### 基础监听

```javascript
useEffect(() => {
  // 逻辑
}, [value_version, value_num])
```

### 条件更新

```javascript
useEffect(() => {
  if (num !== 2) {
    set_num(2);
  }
  // 其他逻辑
}, [value_app, value_version, num])
```

### 初始化检查

```javascript
useEffect(() => {
  if (!value_app || !value_app.value) return;
  
  if (value_app.value === 'all') {
    set_version([]);
    setValue_version(null);
    set_hasVersion(false);
    return;
  }
  
  set_hasVersion(true);
  // 请求数据
}, [value_app])
```

## 状态类型映射

### result_type 值

| 值 | 含义 | 颜色 |
|----|------|------|
| `'loading'` | 加载中 | 蓝色 |
| `'success'` | 成功/通过 | 绿色 |
| `'error'` | 失败/不通过 | 红色 |
| `'pending'` | 待处理/未评定 | 灰色 |
| `'warning'` | 警告 | 黄色 |
| `'stopped'` | 停止 | 灰色 |

```typescript
// 评定结果映射
if (result === '通过') {
  set_result_type('success');
  set_result_text('通过');
} else if (result === '不通过') {
  set_result_type('error');
  set_result_text('不通过');
} else {
  set_result_type('pending');
  set_result_text('未评定');
}
```

## 表格数据变量

```typescript
{
  value: 'items_table_list',
  set_value: 'set_items_table_list',
  default: []
}
```

```javascript
// 更新表格数据
set_items_table_list(data.items || []);

// 设置表格初始数据（用于 tableSelect）
set_init_items_table_list(initialItems);
set_table_data_table_list();
```

## 版本选择变量

```typescript
{
  value: 'app',
  set_value: 'set_app',
  default: null  // 或 { label: '全部应用', value: 'all' }
},
{
  value: 'version',
  set_value: 'set_version',
  default: []
},
{
  value: 'hasVersion',
  set_value: 'set_hasVersion',
  default: true
}
```

## 时间选择变量

```typescript
{
  value: 'year',
  set_value: 'set_year',
  default: { label: '2026年', value: '2026' }
},
{
  value: 'month',
  set_value: 'set_month',
  default: { label: '8月', value: '8' }
},
{
  value: 'month_options',
  set_value: 'set_month_options',
  default: []
}
```

## 批量定义模板

```typescript
const buildConstDefine = (
  configuredLevel: string,
  defaultItems: any[],
  versionOptions: any[],
  defaultVersion: any,
  isAll: boolean
) => {
  return [
    { value: 'version', set_value: 'set_version', default: versionOptions },
    { value: 'configured_level', set_value: 'set_configured_level', default: configuredLevel },
    { value: 'current_level', set_value: 'set_current_level', default: '--' },
    { value: 'num', set_value: 'set_num', default: 0 },
    { value: 'hasVersion', set_value: 'set_hasVersion', default: !isAll },
    { value: 'result_type', set_value: 'set_result_type', default: 'pending' },
    { value: 'result_text', set_value: 'set_result_text', default: '--' },
    { value: 'items_list', set_value: 'set_items_list', default: defaultItems },
  ];
};
```

## JS 中使用表格变量

```javascript
// 设置表格初始数据
set_init_items_table_list(items);

// 更新表格
set_table_data_table_list();

// 在 markup 中访问
BaseUI.markupItem('{items_list.length} 个项目')
```

## setValue vs set_

| 函数 | 用途 | 示例 |
|------|------|------|
| `set_value(arr)` | 设置选项数组 | `set_version([{label: 'A', value: '1'}])` |
| `setValue_value(obj)` | 设置单个值 | `setValue_version({label: 'A', value: '1'})` |
| `set_value(val)` | 通用设置 | `set_num(1)`, `set_flag(true)` |
