# BaseUI 按钮方法详解

## 按钮类型总览

| 方法 | 用途 | variant | form_action |
|---|---|---|---|
| `button()` | 通用按钮，可跳转 | 任意 | 提交（默认） |
| `clickButton()` | 点击触发 JS，不提交表单 | 任意 | none |
| `submitButton()` | 表单提交按钮 | primary | 提交 |
| `refreshButton()` | 刷新页面 | icon | none |
| `linkButton()` | 跳转主按钮（primary） | primary | — |
| `linkButtonLight()` | 跳转链接按钮（无边框） | link | — |
| `linkCommonButton()` | 跳转普通按钮（有边框） | normal | — |
| `deleteButton()` | 删除（触发弹窗） | normal | none |
| `commonButton()` | 普通提交（按表格选中置灰） | normal | 提交 |
| `commonButtonCopy()` | 复制（仅选1个时可用） | normal | 提交 |

## button — 通用按钮

```typescript
BaseUI.button(
  title,              // 按钮文字
  variant?,           // 'primary' | 'normal' | 'link' | 'icon'
  href?,              // 跳转 URL（有则变成链接按钮）
  disable_definition?,// 置灰条件（JS 表达式字符串）
  on_click?,          // 点击事件 JS
  icon_name?,         // 图标名称（如 'settings', 'add-plus'）
  classes?,           // CSS 类名
)

// 置灰示例
BaseUI.button('删除', 'normal', undefined, 'selected_table.length === 0')
// → #disabled: { '#markup': 'selected_table.length === 0' }
```

## clickButton — 不提交表单的点击按钮

```typescript
BaseUI.clickButton(
  title,
  click,              // 点击时执行的 JS 代码
  variant?,
  disable_definition?,
  classes?,
)

// 常见用法
BaseUI.clickButton('刷新',  'window.location.href = window.location.href;')
BaseUI.clickButton('取消',  'setValue_modal(false)')
BaseUI.clickButton('打开弹窗', 'setValue_delete_modal(true)',
  'normal', 'selected_table.length === 0')
BaseUI.clickButton('触发上传', 'setValue_upload_trigger(v => v + 1)')
```

## deleteButton — 删除按钮（自动绑定弹窗）

```typescript
BaseUI.deleteButton(
  tableId,       // 对应 tableWithActions 的 tableId
  title,         // 按钮文字，如 '删除'
  disable_when?, // 自定义置灰条件，默认 'selected_{tableId}.length === 0'
)
// 点击时自动执行 setValue_{tableId}_modal(true)
// 按钮 id 必须以 _delete 结尾才能被 tableWithActions 自动检测到
```

## 常见按钮命名约定

`tableWithActions` 会自动扫描按钮 id，以 `_delete` 结尾的自动生成删除弹窗：

```typescript
private async buttons(tableId: string, linkPrefix: string) {
  const prefix = tableId + '_button_';
  return {
    [`${prefix}refresh`]: BaseUI.refreshButton(),
    [`${prefix}delete`]:  this.canDelete && BaseUI.deleteButton(tableId, '删除'),
    [`${prefix}create`]:  BaseUI.linkButton('创建', this.getUrl(`${linkPrefix}/create`)),
    [`${prefix}edit`]:    BaseUI.commonButton('编辑', tableId),  // 选中1个才可用
    [`${prefix}copy`]:    BaseUI.commonButtonCopy('复制', tableId), // 选中1个才可用
  };
}
```

## 按钮内的权限控制

```typescript
// 方式1：权限为 false 时整个按钮不渲染
result[`${prefix}delete`] = this.currentAuth().admin && BaseUI.deleteButton(tableId, '删除')
// admin=false → result 的值为 false，框架忽略

// 方式2：动态置灰（前端条件）
BaseUI.button('发布', 'primary', undefined, 'selected_table.length === 0')

// 方式3：组合（后端权限 + 前端置灰）
result[`${prefix}publish`] = this.currentAuth().admin && 
  BaseUI.button('发布', 'primary', undefined, 'selected_table.length === 0')
```

## 带 icon 的按钮

```typescript
// 只有图标（icon按钮）
BaseUI.refreshButton()
// 等价于：
{
  '#type': 'aws_button',
  '#icon_name': 'refresh',
  '#form_action': 'none',
  '#on_click': 'window.location.href = window.location.href;'
}

// 文字+图标
BaseUI.button('添加', 'primary', url, undefined, undefined, 'add-plus')

// 带 icon 的点击按钮
BaseUI.addSetting(
  BaseUI.clickButton('上传', 'setValue_upload_modal(true)'),
  { '#icon_name': 'upload' }
)
```

## 表单取消/提交按钮固定模式

```typescript
const buttonContent = {
  button_cancel: BaseUI.linkButtonLight('取消', this.getUrl(backUrl)),
  button_save: BaseUI.submitButton(isEdit ? '保存' : '创建'),
};
// 通过 spaceBetween 第二参数传入，自动放到右下角
return Base.successWrapper([
  BaseUI.spaceBetween({ ... }, buttonContent)
]);
```

## button_dropdown 下拉按钮

```typescript
// 直接用 aws_button_dropdown（推荐）
{
  '#type': 'aws_button_dropdown',
  '#text': '更多操作',
  '#items': [
    { id: 'view',   text: '查看',   href: '/path' },
    { id: 'edit',   text: '编辑',   href: '/edit' },
    { id: 'delete', text: '删除',
      form_action: 'none',
      on_click: 'setValue_delete_modal(true)',
      disabled: { '#markup': 'selected_table.length === 0' },
    },
    { id: 'export', text: '导出到新标签',
      href: 'https://example.com',
      external: true,
      externalIconAriaLabel: '(opens in new tab)',
    },
  ],
}

// 通过 groupButtons 方法（从按钮对象转换）
BaseUI.groupButtons('操作', {
  btn_edit:   BaseUI.button('编辑', 'link', editUrl),
  btn_delete: BaseUI.deleteButton(tableId, '删除'),
})
```

## getUrl — URL 构建（必须用）

```typescript
// 所有页面内部跳转 URL 都必须通过 getUrl 包装
// 自动追加 ?cp=currentProject&cl=currentCluster
this.getUrl('/module/create')           // → '/module/create?cp=xxx&cl=xxx'
this.getUrl(linkPrefix + '/edit')        // → '/path/edit?cp=xxx&cl=xxx'
this.getUrl(linkPrefix) + '&tab=env_tab' // → '/path?cp=xxx&cl=xxx&tab=env_tab'
```
