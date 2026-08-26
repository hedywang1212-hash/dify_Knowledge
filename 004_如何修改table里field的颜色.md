# ServiceNow 根据字段值修改字段显示样式

## 概述

ServiceNow 可以通过字段的 `Configure Styles` 功能，根据记录中的字段值或条件动态应用 CSS 样式。例如，可在字段满足特定条件时修改背景颜色或显示背景图标。

## 适用场景

- 根据状态字段的值突出显示记录。
- 为需要关注的字段设置背景颜色。
- 根据条件为字段添加背景图标或其他 CSS 样式。

## 操作步骤

### 1. 打开目标字段的右键菜单

打开目标表（Table）的表单（Form）。可以打开已有记录（Record），也可以新建记录。找到需要修改样式的字段（Field），右键单击字段标签，然后选择 `Configure Styles`。

图片地址：[https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/004_01.png](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/004_01.png)

图片说明：在表单中右键单击目标字段的标签，从上下文菜单中选择 `Configure Styles`，进入该字段对应的样式配置列表。

### 2. 查看字段对应的 Styles 列表

选择 `Configure Styles` 后，系统会打开 Styles 列表，并自动使用当前表和字段作为筛选条件。列表中会显示该字段已有的样式规则。

图片地址：[https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/004_02.png](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/004_02.png)

图片说明：Styles 列表按 `Table` 和 `Field name` 定位目标字段；`Value` 定义样式生效条件，`Style` 定义满足条件后应用的 CSS 样式，例如背景颜色或背景图标。

### 3. 新建或修改样式规则

在 Styles 列表中新建记录，或打开已有记录进行修改。配置规则的匹配条件和 CSS 样式后保存。当目标字段满足 `Value` 中定义的条件时，系统会应用 `Style` 中的样式。

## Styles 配置字段

- `Table`：样式规则所属的表。
- `Field name`：需要应用样式的字段。
- `Value`：样式生效的字段值或条件。截图中包含以 `javascript:` 开头的条件表达式。
- `Style`：满足条件时应用的 CSS 样式，例如 `background-color: Tomato` 或背景图标。

## 配置逻辑

样式规则可以概括为：

1. 系统定位 `Table` 和 `Field name` 指定的字段。
2. 系统判断当前记录是否满足 `Value` 中的条件。
3. 条件成立时，将 `Style` 中配置的 CSS 应用于该字段。

## 注意事项

- 创建规则前先确认 `Table` 和 `Field name` 是否指向正确字段。
- `Value` 中的条件应与字段类型和实际值保持一致。
- `Style` 中应填写有效的 CSS 属性和值。
- 多条规则作用于同一字段时，应检查条件是否重叠以及最终显示效果是否符合预期。
