# 实践样例 Skill

## 概述

整合所有模式，形成完整的实践样例。

## 列表页完整示例

```typescript
import { Controller, Get, Post, Query, Body } from '@midwayjs/core';
import { ApiBearerAuth, ApiOperation } from '@midwayjs/swagger';
import { Base } from '../commons/Base';
import { BaseUI } from '../commons/BaseUI';
import { BaseController } from '../commons/BaseController';

@ApiBearerAuth()
@Controller('/example', { tagName: 'example', description: '示例管理' })
export class ExampleController extends BaseController {
  private name = 'example_list';

  @ApiOperation({ operationId: 'buildExampleList' })
  @Get('/list/build', { summary: '示例列表', description: '示例列表' })
  public async build() {
    const linkPrefix = Base.Example.pageMain;
    
    const header = [
      BaseUI.tableHeader('name', '名称'),
      BaseUI.tableHeader('description', '描述'),
      BaseUI.tableHeaderCreated(),
      BaseUI.tableHeaderUpdated(),
    ];

    const url = this.getUrl(`${BaseUI.uiHost()}/example/list/page`);

    return Base.successWrapper(
      BaseUI.tableWithActions(
        this.name,
        '示例管理',
        await this.buttons(this.name, linkPrefix),
        BaseUI.tableAjax(header, url, true, 1, [[3, 'desc']]),
        undefined,
        undefined,
        '示例管理',
        'name',
      ),
      undefined,
      ['text-break'],
    );
  }

  private async buttons(id: string, linkPrefix: string): Promise<object> {
    const idPrefix = id + '_button_';
    const result = {};
    
    result[`${idPrefix}refresh`] = BaseUI.refreshButton();
    result[`${idPrefix}create`] = BaseUI.linkButton('创建', this.getUrl(`${linkPrefix}/create`));
    result[`${idPrefix}edit`] = BaseUI.commonButton('编辑', id, `selected_${id}.length === 0 || selected_${id}.length > 1`);
    result[`${idPrefix}delete`] = BaseUI.deleteButton(id, '删除');
    
    return result;
  }

  @ApiOperation({ operationId: 'submitExampleList' })
  @Post('/list/submit', { summary: '列表提交', description: '列表提交' })
  public async submit(@Body() body: any) {
    const ids = this.tableSelected(body[this.name]);

    if (body.op === `${this.name}_button_edit`) {
      return Base.success(this.getUrl(`${Base.Example.pageMain}/edit/${ids}`));
    } else if (body.op === `${this.name}_button_delete`) {
      await this.delete(`${Base.ROOT}/examples/${ids}`);
    }

    return Base.success(this.getUrl(Base.Example.pageMain));
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

## 表单页完整示例

```typescript
import { Body, Controller, Get, Post, Query } from '@midwayjs/core';
import { ApiBearerAuth, ApiOperation } from '@midwayjs/swagger';
import { Base } from '../commons/Base';
import { BaseUI } from '../commons/BaseUI';
import { BaseController } from '../commons/BaseController';

@ApiBearerAuth()
@Controller('/example', { tagName: 'example', description: '示例表单' })
export class ExampleFormController extends BaseController {
  private name = 'example';

  @ApiOperation({ operationId: 'buildExampleForm' })
  @Get('/form/build', { summary: '示例表单', description: '示例表单' })
  public async build(@Query('id') id: string) {
    const linkPrefix = Base.Example.pageMain;
    const isEdit = !!id;
    let data;

    if (isEdit) {
      data = await this.get(`${Base.ROOT}/examples/{id}`, { data: { id } });
    }

    const buttonContent = {
      button_cancel: BaseUI.linkButtonLight('取消', this.getUrl(`${linkPrefix}/list`)),
      button_save: BaseUI.submitButton(isEdit ? '保存' : '创建'),
    };

    const itemContent = {
      name_field: BaseUI.textField(
        'name',
        '名称',
        '',
        BaseUI.validatePattern.titleNew.message,
        data?.name,
        { pattern: BaseUI.validatePattern.titleNew.pattern },
      ),
      description_field: BaseUI.textArea(
        'description',
        '描述',
        '',
        BaseUI.validatePattern.description.message,
        data?.description,
        { pattern: BaseUI.validatePattern.description.pattern },
      ),
      status_field: (() => {
        const options = [
          BaseUI.cardItem('启用', 'ENABLED'),
          BaseUI.cardItem('禁用', 'DISABLED'),
        ];
        const defaultValue = options[0];
        const selected = data?.status
          ? options.find((o) => o.value === data.status) ?? defaultValue
          : defaultValue;
        return BaseUI.selectField('status', '状态', options, selected);
      })(),
    };

    return Base.successWrapper([
      BaseUI.spaceBetween(
        {
          header: BaseUI.pageTitle('example_title', isEdit ? '编辑示例' : '创建示例'),
          form_content: BaseUI.container(BaseUI.spaceBetween(itemContent), '基本信息'),
        },
        buttonContent,
      ),
    ]);
  }

  @ApiOperation({ operationId: 'submitExampleForm' })
  @Post('/form/submit', { summary: '表单提交', description: '表单提交' })
  public async submit(@Body() body: any) {
    const id = body.id;
    body = this.trimBody(body);
    body.status = this.selectValue(body.status);

    if (id) {
      await this.put(`${Base.ROOT}/examples/${id}`, { data: body });
    } else {
      await this.post(`${Base.ROOT}/examples`, { data: body });
    }

    return Base.success(this.getUrl(Base.Example.pageMain));
  }

  // ========== 固定四方法 ==========
  @Get('/form', {
    summary: '【固定接口 ①】表单的四个相对接口路径',
  })
  public async getFormUris() {
    return Base.successForm();
  }

  @Get('/form/formId', {
    summary: '【固定接口 ②】表单的命名ID',
  })
  public async formId() {
    return Base.success(this.name + '_form');
  }

  @Post('/form/validate', {
    summary: '【固定接口 ③】表单参数校验',
  })
  public async validate(@Body() body: any) {
    body = this.trimBody(body);

    // 名称重复校验（创建时）
    if (!body.id) {
      const existing = await this.get(`${Base.ROOT}/examples?name=${body.name}`);
      if (existing && existing.length > 0) {
        return Base.success({ errors: { name: '名称已存在' } });
      }
    }

    return Base.success(null);
  }
}
```

## 动态数据页完整示例（带 JS）

```typescript
import { Controller, Get, Query } from '@midwayjs/core';
import { ApiBearerAuth, ApiOperation } from '@midwayjs/swagger';
import { Base } from '../commons/Base';
import { BaseUI } from '../commons/BaseUI';
import { BaseController } from '../commons/BaseController';

@ApiBearerAuth()
@Controller('/overview', { tagName: 'overview', description: '综览' })
export class OverviewController extends BaseController {
  private name = 'overview';

  @ApiOperation({ operationId: 'buildOverview' })
  @Get('/build', { summary: '综览页面', description: '综览页面' })
  public async build() {
    // 获取初始数据
    const { select_options, default_value } = await this.appGroupOptions();
    const configuredLevel = '未设置';
    const defaultItems = [];

    return Base.successWrapper(
      BaseUI.spaceBetween({
        basic_info: BaseUI.cardPanelWithEdit(
          '基本信息',
          '',
          {
            level: BaseUI.cardItem('等级', BaseUI.markupItem('configured_level')),
            result: BaseUI.cardItem(
              '结果',
              BaseUI.statusIndicator(
                BaseUI.markupItem('result_type'),
                BaseUI.markupItem('{result_text}'),
              ),
            ),
          },
          false,
        ),
        app_version: BaseUI.spaceBetween(
          {
            app: BaseUI.selectField('app', '', select_options, default_value),
            version: BaseUI.addSetting(
              BaseUI.selectField('version', '', 'version', null, '', 'auto', undefined, undefined, '请选择版本'),
              {
                '#prefix': '{hasVersion ?',
                '#suffix': ':""}',
              }
            ),
          },
          undefined,
          'horizontal',
        ),
        list: BaseUI.container(
          BaseUI.tableSelect(
            [
              BaseUI.tableHeader('name', '名称'),
              BaseUI.tableHeader('level', '等级'),
            ],
            'items_list',
            -1,
            [[1, 'desc']]
          ),
          '列表',
          {
            refresh: Object.assign(BaseUI.clickButton('', 'set_num(1);'), {
              '#icon_name': 'refresh',
            }),
          }
        ),
      }),
      [this.getVersionsJs, this.getDataJs()],
      ['mb-4'],
      [
        { value: 'version', set_value: 'set_version', default: [] },
        { value: 'configured_level', set_value: 'set_configured_level', default: configuredLevel },
        { value: 'hasVersion', set_value: 'set_hasVersion', default: true },
        { value: 'result_type', set_value: 'set_result_type', default: 'pending' },
        { value: 'result_text', set_value: 'set_result_text', default: '--' },
        { value: 'items_list', set_value: 'set_items_list', default: defaultItems },
        { value: 'num', set_value: 'set_num', default: 0 },
      ],
    );
  }

  private getVersionsJs = `
useEffect(() => {
  if (!value_app || !value_app.value) return;
  
  if (value_app.value === 'all') {
    set_version([]);
    setValue_version(null);
    set_hasVersion(false);
    return;
  }
  
  set_hasVersion(true);
  
  $.ajax({
    url: '/ajax-callback',
    type: 'get',
    data: {
      method: 'get',
      url: '${BaseUI.uiHost()}/common/versions?app=' + value_app.value
    },
    dataType: 'json',
    success: function(response) {
      if (response && response.length > 0) {
        set_version(response);
        setValue_version(response[0]);
      } else {
        set_version([]);
        setValue_version(null);
      }
    }
  });
}, [value_app])
`;

  private getDataJs() {
    return `
useEffect(() => {
  if (num !== 2) {
    set_num(2);
  }
  if (!value_app || !value_app.value) return;
  if (!value_version || !value_version.value) return;

  var parts = value_version.value.split(':');
  var id = parts[0] || '';
  if (!id) return;

  $.ajax({
    url: '/ajax-callback',
    type: 'get',
    data: {
      method: 'get',
      url: '${BaseUI.uiHost()}/overview/result?id=' + id
    },
    dataType: 'json',
    success: function(response) {
      if (!response) return;
      
      set_configured_level(response.level || '未设置');
      
      if (response.result === '通过') {
        set_result_type('success');
        set_result_text('通过');
      } else if (response.result === '不通过') {
        set_result_type('error');
        set_result_text('不通过');
      } else {
        set_result_type('pending');
        set_result_text('未评定');
      }
      
      if (Array.isArray(response.items)) {
        set_items_list(response.items);
      }
    },
    error: function() {
      set_result_type('pending');
      set_result_text('--');
    }
  });
}, [value_app, value_version, num])
`;
  }

  // ========== 固定接口 ==========
  @Get('', {
    summary: '【固定接口 ①】表单的四个相对接口路径',
  })
  public async getFormUris() {
    return Base.successForm();
  }

  @Get('/formId', {
    summary: '【固定接口 ②】表单的命名ID',
  })
  public async formId() {
    return Base.success(this.name + '_form');
  }
}
```

## 联动表单完整示例

```typescript
// 检查主体联动
const itemContent = {
  check_method: (() => {
    const options = [
      BaseUI.cardItem('工具', 'TOOL'),
      BaseUI.cardItem('人工', 'MANUAL'),
    ];
    return BaseUI.selectField('checkMethod', '检查方式', options, options[0]);
  })(),

  check_subject_manual: BaseUI.addSetting(
    BaseUI.textField('checkSubject', '检查主体', '人员角色', '', '', {}),
    {
      '#prefix': '{value_checkMethod.value === "MANUAL" ?',
      '#suffix': ':""}',
    }
  ),

  check_subject_tool: BaseUI.addSetting(
    BaseUI.selectField('checkSubjectTool', '检查主体', toolOptions, toolOptions[0]),
    {
      '#prefix': '{value_checkMethod.value === "TOOL" && value_complianceLevel.value !== "L4" && value_complianceLevel.value !== "L5" ?',
      '#suffix': ':""}',
    }
  ),

  compliance_level: (() => {
    const options = [
      BaseUI.cardItem('L1', 'L1'),
      BaseUI.cardItem('L2', 'L2'),
      BaseUI.cardItem('L3', 'L3'),
      BaseUI.cardItem('L4', 'L4'),
      BaseUI.cardItem('L5', 'L5'),
    ];
    return BaseUI.selectField('complianceLevel', '合规等级', options, options[0]);
  })(),

  spot_check: BaseUI.addSetting(
    BaseUI.selectField('isSpotCheckRequired', '抽查必做', yesNoOptions, yesNoOptions[0]),
    {
      '#prefix': '{value_complianceLevel.value === "L4" || value_complianceLevel.value === "L5" ?',
      '#suffix': ':""}',
    }
  ),

  required_documents: BaseUI.addSetting(
    BaseUI.textArea('requiredDocuments', 'L4-L5所需文档', '', '', '', {}),
    {
      '#prefix': '{(value_complianceLevel.value === "L4" || value_complianceLevel.value === "L5") && value_checkMethod.value === "MANUAL" ?',
      '#suffix': ':""}',
    }
  ),
};
```

## Tab 页签完整示例

```typescript
BaseUI.tabs(
  {
    technical_tab: BaseUI.tabItem(
      'technical',
      '技术类',
      BaseUI.tableWithActions(
        'technical_list',
        '技术类列表',
        await this.buttons('technical_list'),
        BaseUI.tableAjax(technicalHeader, technicalUrl, true, 1, [[1, 'asc']], undefined, selects),
      )
    ),
    management_tab: BaseUI.tabItem(
      'management',
      '管理类',
      BaseUI.tableWithActions(
        'management_list',
        '管理类列表',
        await this.buttons('management_list'),
        BaseUI.tableAjax(managementHeader, managementUrl, true, 1, [[1, 'asc']], undefined, managementSelects),
      )
    ),
  },
  tab ? tab : 'technical'
)
```

## 表格带删除确认完整示例

```typescript
// 按钮定义
private async buttons(id: string): Promise<object> {
  return {
    [`${id}_button_refresh`]: BaseUI.refreshButton(),
    [`${id}_button_edit`]: BaseUI.commonButton('编辑', id),
    [`${id}_button_delete`]: BaseUI.deleteButton(id, '删除'),
  };
}

// 表格定义
BaseUI.tableWithActions(
  id,
  '列表',
  buttons,
  BaseUI.tableAjax(header, url, true, 1),
  undefined,      // description
  undefined,      // noCheck
  '列表标题',     // headerContent
  'name',         // properties
)

// 提交处理
@Post('/list/submit')
public async submit(@Body() body: any) {
  const ids = this.tableSelected(body[id]);
  
  if (body.op === `${id}_button_edit`) {
    return Base.success(this.getUrl(`/edit/${ids}`));
  } else if (body.op === `${id}_button_delete`) {
    for (const id of ids.split(',')) {
      await this.delete(`${Base.ROOT}/items/${id}`);
    }
  }
  
  return Base.success(this.getUrl('/list'));
}
```

## 时间格式化工具

```javascript
// faas_time_format.js
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
```

## 字典翻译方法

```typescript
protected dictLabel(dictType: string, key: string): string {
  if (!key) return key;
  const dict: Record<string, Record<string, string>> = {
    checkLevel: {
      NETWORK_SECURITY: '网络安全',
      DATA_SECURITY: '数据安全',
      HOST_SECURITY: '主机安全',
    },
    checkScope: {
      EXTERNAL: '外网',
      INTERNAL: '内网',
      CLUSTER: '集群',
    },
    checkMethod: {
      MANUAL: '人工',
      TOOL: '工具',
    },
    checkSubject: {
      WEB_VULN_SCAN: 'Web漏扫',
      CODE_AUDIT: '代码审计',
    },
    complianceLevel: {
      L1: 'L1',
      L2: 'L2',
      L3: 'L3',
    },
    isSpotCheckRequired: {
      YES: '是',
      NO: '否',
    },
  };
  return dict[dictType]?.[key] ?? key;
}

// 使用示例
items.map((item: any) => ({
  ...item,
  checkLevel: this.dictLabel('checkLevel', item.checkLevel),
  checkScope: this.dictLabel('checkScope', item.checkScope),
}))
```
