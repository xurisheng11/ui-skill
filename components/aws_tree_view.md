# aws_tree_view

AWS 树视图组件，用于展示层级结构数据，支持展开/折叠子节点。

## 参数说明

| 名称 | 类型 | 描述 | 接受值 | 默认值 | 是否必填 |
|---|---|---|---|---|---|
| aria_describedby | string | 设置树视图上的 aria-describedby 属性。 | - | - | 否 |
| aria_label | string | 为树视图提供一个屏幕阅读器可以读取的 aria-label。不要同时使用 aria_label 和 aria_labelledby。 | - | - | 否 |
| aria_labelledby | string | 设置树视图上的 aria-labelledby 属性。 | - | - | 否 |
| className (deprecated) | string | 已弃用。 | - | - | 否 |
| expanded_items | ReadonlyArray<string> | 提供已展开的树视图项的 ID。控制项是展开还是折叠。 | - | - | 否 |
| get_item_children | (item: T, index: number) => ReadonlyArray<T> | 指定树视图项展开时显示的嵌套项。 | - | - | **是** |
| get_item_id | (item: T, index: number) => string | 为每个树视图项提供唯一标识符。 | - | - | **是** |
| i18n_strings | TreeViewProps.I18nStrings<T> | 包含组件所需的所有必要本地化字符串的对象。 | - | - | 否 |
| id (deprecated) | string | 已弃用。 | - | - | 否 |
| items | ReadonlyArray<T> | 指定要在树视图中显示的顶级项。 | - | - | **是** |
| render_item | (item: T, index: number) => TreeViewProps.TreeItem | 使用此属性将您的数据映射到树视图项。必须返回包含 content、icon（可选）、secondaryContent（可选）、actions（可选）、announcementLabel（可选）的对象。 | - | - | **是** |
| render_item_toggle_icon | function | 在切换按钮中显示自定义图标。 | - | - | 否 |

## 使用示例

```json
{
  "status": 0,
  "message": "操作成功",
  "data": {
    "aws": {
      "#type": "aws_wrapper",
      "#children": {
        "aws_list": {
          "#type": "aws_tree_view",
          "#items": [
            {
              "id": "1",
              "content": "Feature X",
              "iconName": "folder",
              "nestedItems": [
                {
                  "id": "1.1",
                  "content": "tests",
                  "iconName": "folder",
                  "nestedItems": [
                    {"id": "1.1.1", "content": "unit.test.tsx", "iconName": "file"},
                    {"id": "1.1.2", "content": "integ.test.ts", "iconName": "file"}
                  ]
                },
                {"id": "1.2", "iconName": "folder", "content": "assets"},
                {"id": "1.3", "iconName": "file", "content": "index.tsx"}
              ]
            },
            {
              "id": "2",
              "content": "Feature Y",
              "iconName": "folder",
              "nestedItems": [
                {"id": "2.1", "content": "index.tsx", "iconName": "file"}
              ]
            },
            {"id": "3", "content": "package.json", "iconName": "file"}
          ],
          "#render_item": {
            "icon": {"#type": "aws_icon", "#name": {"#markup": "item.iconName"}},
            "content": "item.content"
          }
        }
      }
    }
  }
}
```
