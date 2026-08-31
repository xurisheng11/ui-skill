# aws_top_navigation

AWS 顶部导航组件，用于展示产品身份信息和顶部工具栏（按钮、下拉菜单、搜索框等）。

## 参数说明

| 名称 | 类型 | 描述 | 接受的值 | 默认值 | 是否必需 | 可使用变量 | 使用方法 |
|---|---|---|---|---|---|---|---|
| className (已弃用) | string | 将指定的类添加到组件的根元素。已弃用。 | - | - | 否 | | |
| i18n_strings | TopNavigationProps.I18nStrings | 包含组件所需的所有本地化字符串的对象。 | - | - | 否 | | |
| id (已弃用) | string | 将指定的ID添加到组件的根元素。已弃用。 | - | - | 否 | | |
| identity | TopNavigationProps.Identity | 描述产品身份的属性。包括：title、logo（src/alt）、href、onFollow。 | - | - | 是 | | |
| utilities | ReadonlyArray<TopNavigationProps.Utility> | 一系列工具导航元素。支持 button 和 menu-dropdown 两种类型。 | - | - | 否 | | |
| search | - | 与输入或自动建议控件一起用于全局搜索查询。 | - | - | 否 | true | variable |

### i18n_strings 属性

- `overflow_menu_back_icon_aria_label` (可选, string)
- `overflow_menu_dismiss_icon_aria_label` (可选, string)
- `overflow_menu_title_text` (可选, string)
- `overflow_menu_trigger_text` (可选, string)
- `search_dismiss_icon_aria_label` (可选, string)
- `search_icon_aria_label` (可选, string)

### identity 属性

- `href`: string - 指定头链接指向的URL。
- `logo` (可选): 包括 `src` 和 `alt` 属性，指定产品的标志。
- `on_follow` (可选): 当身份被点击且未按修饰键时调用的事件处理器。
- `title` (可选, string): 指定标题文本。

### utilities - button 属性

- `variant` ('primary-button' | 'link') - 按钮的视觉外观，默认值为 'link'。
- `href` (string) - 链接的href。
- `target` (string) - 打开链接的窗口。
- `external` (boolean) - 标记链接为外部链接。
- `on_click` (() => void) - 点击工具时调用的事件处理器。
- `on_follow` (() => void) - 当工具被点击且未按下修饰键时调用的事件处理器。

### utilities - menu-dropdown 属性

- `description` (string) - 下拉菜单内显示的描述。
- `items` (ButtonDropdownProps.Items) - 下拉项数组。
- `on_item_click` - 下拉项被选中时调用的事件处理器。
- `on_item_follow` - 当下拉项被选中且未按下修饰键时调用的事件处理器。
- `expandable_groups` (boolean) - 控制项目组的可扩展性。

## 使用示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": [
        {
          "#type": "aws_top_navigation",
          "#identity": {
            "href": "#",
            "title": "Service",
            "logo": {"src": "/core/misc/logo.svg", "alt": "Service"}
          },
          "#utilities": [
            {
              "type": "button",
              "iconName": "notification",
              "title": "Notifications",
              "ariaLabel": "Notifications (unread)",
              "badge": true,
              "disableUtilityCollapse": false
            },
            {
              "type": "menu-dropdown",
              "iconName": "settings",
              "ariaLabel": "Settings",
              "title": "Settings",
              "items": [
                {"id": "settings-org", "text": "Organizational settings"},
                {"id": "settings-project", "text": "Project settings"}
              ]
            },
            {
              "type": "menu-dropdown",
              "text": "Customer Name",
              "description": "email@example.com",
              "iconName": "user-profile",
              "items": [
                {"id": "profile", "text": "Profile"},
                {"id": "preferences", "text": "Preferences"},
                {"id": "signout", "text": "Sign out"}
              ]
            }
          ],
          "#search": {"input": {"#type": "aws_input"}}
        }
      ]
    }
  }
}
```
