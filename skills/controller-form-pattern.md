# Controller 固定四方法模式

## 概述

每个 Controller 表单页面都遵循固定的四方法模式，这是 Luban 前端框架的标准规范。

## 四个固定方法

### 1. formId 接口 - 表单命名ID

```typescript
@Get('/form', {
  summary: '【固定接口 ①】表单的四个相对接口路径（所有表单都一样）',
  description: '【固定接口 ①】表单的四个相对接口路径（所有表单都一样）',
})
public async getFormUris() {
  return Base.successForm();
}
```

### 2. formId/uri 接口 - 表单ID

```typescript
@Get('/form/formId', {
  summary: '【固定接口 ②】表单的命名ID',
  description: '【固定接口 ②】表单的命名ID',
})
public async formId() {
  return Base.success(this.name + '_form');
}
```

### 3. validate 接口 - 表单参数校验

```typescript
@Post('/form/validate', {
  summary: '【固定接口 ③】表单参数校验',
  description: '【固定接口 ③】表单参数校验',
})
public async validate(@Body() body: any) {
  // 校验逻辑
  return Base.success(null); // 无错误时返回 null
  // 或返回错误
  // return Base.success({ errors: { fieldName: '错误信息' } });
}
```

### 4. build 接口 - 获取页面 JSON

```typescript
@Get('/form/build', { summary: '页面构建', description: '页面构建' })
public async build(@Query('id') id: string) {
  // 构建表单内容
  return Base.successWrapper(
    BaseUI.container(...), // 页面内容
    [],                    // JS 函数数组
    ['class-name'],        // CSS 类名
    []                     // const_define 变量定义
  );
}
```

## submit 接口 - 表单提交

```typescript
@Post('/form/submit', { summary: '表单提交', description: '表单提交' })
public async submit(@Body() body: any) {
  // 处理提交逻辑
  return Base.success(this.getUrl('/redirect/path')); // 重定向到列表页
  // 或返回错误
  // return Base.success({ errors: { error: '错误信息' } });
}
```

## Base.successForm() 方法

定义在 `Base.ts` 中：

```typescript
static successForm(
  formId = 'formId',
  submit = 'submit',
  validate = 'validate',
  build = 'build',
): object {
  return this.success({
    api_list: {
      getFormId: formId,
      submitForm: submit,
      validateForm: validate,
      buildForm: build,
    },
  });
}
```

## 完整示例

```typescript
import { Body, Controller, Get, Post, Query } from '@midwayjs/core';
import { ApiBearerAuth, ApiOperation } from '@midwayjs/swagger';
import { Base } from '../commons/Base';
import { BaseUI } from '../commons/BaseUI';
import { BaseController } from '../commons/BaseController';

@ApiBearerAuth()
@Controller('/example', { tagName: 'example', description: '示例' })
export class ExampleController extends BaseController {
  private name = 'example_list';

  @ApiOperation({ operationId: 'buildExampleList' })
  @Get('/list/build', { summary: '示例列表', description: '示例列表' })
  public async build() {
    const header = [
      BaseUI.tableHeader('name', '名称'),
      BaseUI.tableHeader('createdAt', '创建时间', BaseUI.tableItemTime('item.createdAt')),
    ];
    const url = this.getUrl(`${BaseUI.uiHost()}/example/list/page`);
    return Base.successWrapper(
      BaseUI.tableWithActions(
        this.name,
        '示例列表',
        await this.buttons(this.name),
        BaseUI.tableAjax(header, url, true, 1),
      ),
      undefined,
      ['text-break'],
    );
  }

  private async buttons(id: string): Promise<object> {
    return {
      [`${id}_button_create`]: BaseUI.linkButton('创建', this.getUrl('/example/create')),
      [`${id}_button_edit`]: BaseUI.commonButton('编辑', id),
      [`${id}_button_delete`]: BaseUI.deleteButton(id, '删除'),
    };
  }

  @ApiOperation({ operationId: 'submitExampleList' })
  @Post('/list/submit', { summary: '列表提交', description: '列表列表提交' })
  public async submit(@Body() body: any) {
    const ids = this.tableSelected(body[this.name]);
    if (body.op === `${this.name}_button_edit`) {
      return Base.success(this.getUrl(`/example/edit/${ids}`));
    } else if (body.op === `${this.name}_button_delete`) {
      await this.delete(`${Base.ROOT}/examples/${ids}`);
    }
    return Base.success(this.getUrl('/example/list'));
  }

  // ========== 固定四方法 ==========
  @Get('/list', {
    summary: '【固定接口 ①】表单的四个相对接口路径',
  })
  public async getFormUris() {
    return Base.successForm();
  }

  @Get('/list/formId', {
    summary: '【固定接口 ②】表单的命名ID',
  })
  public async formId() {
    return Base.success(this.name + '_form');
  }

  @Post('/list/validate', {
    summary: '【固定接口 ③】表单参数校验',
  })
  public async validate() {
    return Base.success(null);
  }

  @ApiOperation({ operationId: 'getExamplePageList' })
  @Get('/list/page', {
    summary: '分页列表数据',
  })
  public async pageList(
    @Query('data[page][page]') page: number,
    @Query('data[page][size]') size: number,
    @Query('data[filter][default]') search: string,
  ) {
    const result = await this.get(
      `${Base.ROOT}/examples?page=${page}&size=${size}&search=${search}`
    );
    return Base.success({
      items: result.items,
      counter: result.pagination.totalItems,
      filtered: result.pagination.filterTotal,
      pagesCount: result.pagination.totalPages,
    });
  }
}
```

## 表单提交按钮

使用 `BaseUI.submitButton()` 创建提交按钮：

```typescript
const buttonContent = {
  button_cancel: BaseUI.linkButtonLight('取消', '/list'),
  button_save: BaseUI.submitButton('保存'), // 或 '创建'
};
```

## 页面重定向

```typescript
// 重定向到指定路径
return Base.success(this.getUrl('/example/list'));

// 带查询参数
return Base.success(this.getUrl('/example/list') + '&tab=management');

// 返回错误
return Base.success({ errors: { error: '错误信息' } });
```
