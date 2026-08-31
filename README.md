# UI-Skill 项目

## 概述

这是一个整理企业前端 UI 开发规范和实践样例的项目，基于 Luban/AWS 前端框架。

## 目录结构

```
skills/
├── controller-form-pattern.md   # Controller 固定四方法模式
├── baseui-components.md         # BaseUI 组件封装
├── js-useeffect-ajax.md        # JavaScript useEffect 和 ajax-callback 模式
├── display-hide-control.md     # 显示隐藏控制模式
├── const-define-pattern.md     # const_define 变量定义模式
└── practice-examples.md         # 实践样例
```

## 核心概念

### 1. Controller 四方法模式

每个表单页面都遵循固定的四方法规范：

- `GET /form` - 返回表单接口路径配置
- `GET /form/formId` - 返回表单命名 ID
- `POST /form/validate` - 表单参数校验
- `GET /form/build` - 构建页面 JSON

### 2. Base.successWrapper 返回结构

```typescript
Base.successWrapper(
  content,           // 页面内容（BaseUI 组件）
  [jsFunctions],     // JS 函数数组（useEffect 等）
  ['className'],     // CSS 类名
  [const_define]    // 变量定义数组
)
```

### 3. 变量定义 const_define

用于前端状态管理：

```typescript
{
  value: 'variableName',      // 变量名
  set_value: 'set_variableName', // 设置函数
  default: defaultValue       // 默认值
}
```

### 4. JS useEffect + ajax-callback

实现动态数据加载和交互：

```javascript
useEffect(() => {
  $.ajax({
    url: '/ajax-callback',
    data: { method: 'get', url: 'API_URL' },
    success: function(response) {
      set_variable(response);
    }
  });
}, [dependency])
```

### 5. 显示隐藏控制

使用 `#prefix` 和 `#suffix` 实现条件显示：

```typescript
BaseUI.addSetting(field, {
  '#prefix': '{condition ?',
  '#suffix': ':""}',
})
```

## 常用 BaseUI 组件

| 组件 | 用途 |
|------|------|
| `button` | 普通按钮 |
| `clickButton` | 带点击事件的按钮 |
| `submitButton` | 提交按钮 |
| `textField` | 文本输入框 |
| `textArea` | 多行文本框 |
| `selectField` | 下拉选择框 |
| `tableWithActions` | 带操作栏的表格 |
| `tableAjax` | 动态翻页表格 |
| `tabs/tabItem` | Tab 页签 |
| `cardPanel` | 卡片容器 |
| `spaceBetween` | 布局容器 |
| `markupItem` | 标记内容 |
| `statusIndicator` | 状态指示器 |

## AWS 组件列表

| 组件 | 名称 | 描述 |
| --- | --- | --- |
| [[aws_wrapper]] | AWS 包装器 | 用于渲染aws组件，所有aws组件必须包裹在其中 |
| [[aws_input]] | AWS 输入框 | 用于创建输入字段的组件 |
| [[aws_box]] | AWS 盒子 | 用于创建具有边界和背景色的容器 |
| [[aws_alert]] | AWS 警告框 | 用于显示通知消息 |
| [[aws_badge]] | AWS 徽章 | 用于显示简短的信息摘要 |
| [[aws_button]] | AWS 按钮 | 用于触发动作的标准按钮组件 |
| [[aws_checkbox]] | AWS 复选框 | 复选框允许用户选择选项 |
| [[aws_column_layout]] | AWS 列布局 | 列布局组件 |
| [[aws_container]] | AWS 容器 | 呈现一组内容片段 |
| [[aws_date_picker]] | AWS 日期选择器 | 用户可以选择日期 |
| [[aws_form_field]] | AWS 表单字段 | 在表单中创建样式正确的控件 |
| [[aws_header]] | AWS 头 | 总结显示在它下面的内容 |
| [[aws_link]] | AWS 链接 | 链接组件 |
| [[aws_modal]] | AWS 模态框 | 模态窗口组件 |
| [[aws_select]] | AWS 下拉框 | 从列表中选择单个项目 |
| [[aws_multi_select]] | AWS 多选下拉框 | 从列表中选择多个项目 |
| [[aws_text_area]] | AWS 多行文本框 | 多行纯文本输入控件 |
| [[aws_tabs]] | AWS 选项卡 | 在不同类别信息之间切换 |
| [[aws_toggle]] | AWS 开关 | 打开或关闭选项 |
| [[aws_table]] | AWS 表格 | 以二维表格格式显示数据 |
| [[aws_cards]] | AWS 卡片 | 以卡片格式显示数据 |
| [[aws_offcanvas]] | AWS 弹出框 | 页面右侧弹出信息 |
| [[aws_attribute_editor]] | AWS 属性编辑器 | 创建、编辑和删除资源属性 |
| [[aws_progress_bar]] | AWS 进度条 | 显示操作进度 |
| [[aws_status_indicator]] | AWS 状态指示器 | 传达资源的状态 |

## 开发流程

### 1. 创建列表页

1. 定义 `name` 属性
2. 实现 `build()` 方法构建表格
3. 实现 `buttons()` 方法定义操作按钮
4. 实现 `submit()` 方法处理操作
5. 实现固定四方法

### 2. 创建表单页

1. 定义 `name` 属性
2. 实现 `build()` 方法构建表单
3. 实现 `submit()` 方法处理提交
4. 实现 `validate()` 方法进行校验
5. 实现固定四方法

### 3. 添加动态交互

1. 在 `build()` 中添加 `const_define` 变量
2. 编写 `useEffect` JS 函数
3. 通过 `ajax-callback` 调用后端接口
4. 更新变量状态

### 4. 实现联动逻辑

1. 使用 `BaseUI.addSetting()` 包装字段
2. 设置 `#prefix` 和 `#suffix` 条件
3. 在 `submit()` 中处理条件值
4. 在 `validate()` 中添加联动校验

## 示例代码

参考 `skills/practice-examples.md` 获取完整的实践样例。

## 资源链接

- Luban 框架文档：https://kb.fzyun.net/projects/luban-support/wiki/
- Drupal Render API：https://api.drupal.org/api/drupal/namespace/Drupal!Core!Render!Element
