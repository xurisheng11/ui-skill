# BaseUI validatePattern 校验规则大全

所有预置正则规则，配合 `textField` / `textArea` / `numberField` 的 `attributes` 参数使用。

## 完整规则列表

| key | 说明 | 规则摘要 |
|---|---|---|
| `identifier` | 标识符 | 小写字母开头，可含小写字母/数字/连字符，1-63位，不可连续连字符，不可连字符结尾 |
| `name` | 名称 | 1-63 个字符，不可全空白 |
| `title` | 标题 | 1-128 个字符 |
| `description` | 描述 | 0-255 个字符 |
| `version` | 版本号 | x.y.z 格式，如 1.0.0，不超过20字符 |
| `number` | 正整数 | 必须是正整数（1起） |
| `minScaleNumber` | 非负整数 | 0 或正整数 |
| `password` | 密码 | 8-32位，必须含大小写字母和数字 |
| `customName` | 自定义名称 | 小写字母开头，只含小写字母和数字，1-24位 |
| `providerName` | 提供者名称 | 同上 |
| `account` | 账号 | 1-63 个字符 |
| `config` | 配置内容 | 0-10000 个字符 |
| `cn30` | 中文/英文30字符内 | 最多30个字符 |
| `cn100` | 中文/英文100字符内 | 最多100个字符 |
| `letter30` | 字母数字下划线30字符内 | 最多30字符，支持字母/数字/下划线 |
| `en20` | 20字符内 | 最多20个字符 |
| `en100` | 100字符内 | 最多100个字符 |
| `appId` | 应用ID | 0-64 个字符 |
| `appSecret` | 应用密钥 | 0-64 个字符 |
| `idsAddress` | URL地址 | 最多128字符，满足URL规范 |
| `domain` | 域名通配符 | *.xxx.xxx 格式 |
| `dockerUrl` | Docker镜像URL | Docker镜像地址格式 |
| `nfs` | NFS挂载地址 | ip:/path 格式 |
| `ip` | IP地址 | IPv4 格式 |
| `expire` | 有效期天数 | 1-365 正整数 |
| `num` | 数字 | 正整数 |
| `icon` | 关键词 | 1-30 个字符 |

## 使用方法

```typescript
// 在 textField 中使用
BaseUI.textField(
  'name', '名称', '',
  BaseUI.validatePattern.identifier.message,  // 约束提示文字
  data.name,
  { pattern: BaseUI.validatePattern.identifier.pattern }, // 正则
)

// 在 numberField 中使用
BaseUI.numberField(
  'port', '端口',
  BaseUI.validatePattern.number.message,
  data.port,
  { pattern: BaseUI.validatePattern.number.pattern },
)

// 在 textArea 中使用
BaseUI.textArea(
  'description', '描述 - 可选', '',
  BaseUI.validatePattern.description.message,
  data.description,
  { pattern: BaseUI.validatePattern.description.pattern },
  false,
)
```

## 自定义校验规则

```typescript
// 自定义 pattern（写在 attributes 对象中）
BaseUI.textField(
  'email', '邮箱', '',
  '请输入正确的邮箱格式',
  data.email,
  {
    pattern: '^[^\\\\s@]+@[^\\\\s@]+\\\\.[^\\\\s@]+$',  // 注意：在 TypeScript 字符串里双重转义
    pattern_err: '邮箱格式不正确',
  },
)
```

**注意转义规则**：
- JSON 中写：`"^[^\\s@]+@[^\\s@]+\\\\.[^\\s@]+$"`
- TypeScript 字符串中写：`'^[^\\\\s@]+@[^\\\\s@]+\\\\.[^\\\\s@]+$'`（因鲁班会对正则进行二次转义）

## 在 validate 接口中校验

```typescript
@Post('/form/validate')
public async validate(@Body() body: any) {
  // 用正则手动校验
  const nameRegex = /^[a-z](?!.*--)[a-z0-9-]{0,62}(?<!-)$/;
  if (body.name && !nameRegex.test(body.name)) {
    return Base.success({ errors: { name: BaseUI.validatePattern.identifier.message } });
  }
  return Base.success(null);
}
```
