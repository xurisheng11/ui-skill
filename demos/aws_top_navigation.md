# aws_top_navigation demo

此组件的示例请参考 [组件文档](../components/aws_top_navigation.md)。

## 示例

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
