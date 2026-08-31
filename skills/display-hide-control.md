# 显示隐藏控制模式

## 概述

使用 `BaseUI.addSetting()` 添加 `#prefix` 和 `#suffix` 属性，实现条件显示隐藏。

## 基础模式

```typescript
BaseUI.addSetting(field, {
  '#prefix': '{ condition ?',
  '#suffix': ':""}',
})
```

## 条件显示

### 单条件

```typescript
// 当 value_complianceLevel 为 L4 或 L5 时显示
BaseUI.addSetting(
  BaseUI.selectField('isSpotCheckRequired', '是否为抽查必做项', options, selected),
  {
    '#prefix': '{value_complianceLevel.value === "L4" || value_complianceLevel.value === "L5" ?',
    '#suffix': ':""}',
  }
)
```

### 嵌套条件

```typescript
// 当 L4/L5 且检查方式为人工时显示
BaseUI.addSetting(
  BaseUI.textArea('requiredDocuments', 'L4-L5人工所需文档资料', ...),
  {
    '#prefix': '{(value_complianceLevel.value === "L4" || value_complianceLevel.value === "L5") && value_checkMethod.value === "MANUAL" ?',
    '#suffix': ':""}',
  }
)
```

### 选择值条件

```typescript
// 当选择某个值时显示
BaseUI.addSetting(
  BaseUI.selectField('commonValidity', '公共项有效期', options, selected),
  {
    '#prefix': '{value_isCommon.value === "YES" ?',
    '#suffix': ':""}',
  }
)
```

### 工具检查方式

```typescript
// 当检查方式为工具时显示
BaseUI.addSetting(
  BaseUI.selectField('checkSubjectTool', '检查主体', options, selected),
  {
    '#prefix': '{value_checkMethod.value === "TOOL" ?',
    '#suffix': ':""}',
  }
)
```

## 完整示例：检查主体联动

```typescript
const itemContent = {
  // 人工检查主体
  check_subject: BaseUI.addSetting(
    BaseUI.textField(
      'checkSubject',
      '检查主体',
      '人员角色',
      BaseUI.validatePattern.titleNew.message,
      data?.checkSubject,
      {},
      false,
    ),
    {
      '#prefix': '{value_checkMethod.value === "MANUAL" ?',
      '#suffix': ':""}',
    }
  ),
  
  // 工具检查主体 (非 L4/L5)
  check_subject_tool: BaseUI.addSetting(
    BaseUI.selectField('checkSubjectTool', '检查主体', toolOptions, selected),
    {
      '#prefix': '{value_checkMethod.value === "TOOL" && value_complianceLevel.value !== "L4" && value_complianceLevel.value !== "L5" ?',
      '#suffix': ':""}',
    }
  ),
  
  // 工具检查主体 (L4/L5)
  check_subject_tool_L4_L5: BaseUI.addSetting(
    BaseUI.selectField('checkSubjectToolL4OrL5', '检查主体', l4l5Options, selected),
    {
      '#prefix': '{value_checkMethod.value === "TOOL" && (value_complianceLevel.value === "L4" || value_complianceLevel.value === "L5") ?',
      '#suffix': ':""}',
    }
  ),
};
```

## 完整示例：公共项有效期联动

```typescript
const itemContent = {
  is_common: (() => {
    const { options, defaultValue } = this.yesNoOptions();
    return BaseUI.selectField('isCommon', '是否公共项', options, defaultValue);
  })(),

  common_validity: (() => {
    const { options, defaultValue } = this.commonValidityOptions();
    return BaseUI.addSetting(
      BaseUI.selectField('commonValidity', '公共项有效期', options, defaultValue),
      {
        '#prefix': '{value_isCommon.value === "YES" ?',
        '#suffix': ':""}',
      }
    );
  })(),
};
```

## 表单提交时的值处理

```typescript
public async submit(@Body() body: any) {
  body.isCommon = this.selectValue(body.isCommon);
  
  // isCommon=YES 时才传 commonValidity
  if (body.isCommon === 'YES') {
    body.commonValidity = this.selectValue(body.commonValidity);
  } else {
    delete body.commonValidity; // 清除不需要的字段
  }
}
```

## 条件必填验证

```typescript
@Post('/form/validate', {
  summary: '表单参数校验',
})
public async validate(@Body() body: any) {
  const isCommonVal = this.selectValue(body.isCommon);
  const commonValidityVal = this.selectValue(body.commonValidity);
  
  // 公共项有效期联动校验
  if (isCommonVal === 'YES' && !commonValidityVal) {
    return Base.success({
      errors: { commonValidity: '是否公共项为"是"时，公共项有效期为必填项' },
    });
  }
  
  return Base.success(null);
}
```

## 字段前缀验证

```typescript
// 编号前缀验证
BaseUI.textField(
  'uniqueCode',
  '唯一编号',
  '',
  BaseUI.validatePattern.technicalCode.message,
  'JS',
  { pattern: BaseUI.validatePattern.technicalCode.pattern },
  true,
  false,
  undefined,
  undefined,
  undefined,
  undefined,
  "if(!detail.value.startsWith('JS')){setErrorText_uniqueCode('不可删除前缀'); return false;}"
)
```

## 动态样式控制

### display 控制

```typescript
BaseUI.box_display(content, {
  '#markup': '{ display ? "block" : "none" }'
})
```

### 颜色动态

```typescript
BaseUI.markupItem('{color_map[item.level]}')
```

## 批量条件处理

```typescript
const fields = {
  field1: BaseUI.addSetting(BaseUI.textField(...), {
    '#prefix': '{condition1 ?',
    '#suffix': ':""}',
  }),
  field2: BaseUI.addSetting(BaseUI.selectField(...), {
    '#prefix': '{condition2 ?',
    '#suffix': ':""}',
  }),
  field3: BaseUI.addSetting(BaseUI.textArea(...), {
    '#prefix': '{condition3 ?',
    '#suffix': ':""}',
  }),
};
```

## 常用条件表达式

| 条件 | 表达式 |
|------|--------|
| 等于 | `value_field.value === "VALUE"` |
| 不等于 | `value_field.value !== "VALUE"` |
| 或 | `value_a.value === "A" \|\| value_b.value === "B"` |
| 且 | `value_a.value === "A" && value_b.value === "B"` |
| 不为空 | `value_field && value_field.value` |
| 为空 | `!value_field || !value_field.value` |
| L4/L5 | `value_level.value === "L4" \|\| value_level.value === "L5"` |
| 非 L4/L5 | `value_level.value !== "L4" && value_level.value !== "L5"` |
| 值为真 | `condition ?` |

## OffCanvas 条件显示

```typescript
BaseUI.addSetting(
  BaseUI.offCanvas(content, '提示'),
  {
    '#prefix': '{showTip ?',
    '#suffix': ':""}',
  }
)
```

## Tab 切换显示

```typescript
BaseUI.tabs(
  {
    tab1: BaseUI.tabItem('tab1', '标签1', content1),
    tab2: BaseUI.tabItem('tab2', '标签2', content2),
  },
  tab ? tab : 'tab1'  // 默认选中
)
```
