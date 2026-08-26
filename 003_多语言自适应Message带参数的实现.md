# ServiceNow 多语言 Message 参数化实现

## 概述

ServiceNow 可通过 Message 机制根据用户语言显示本地化文本。客户端使用 `getMessage()`，服务端使用 `gs.getMessage()`；消息中的动态内容可通过 `{0}`、`{1}` 等占位符按顺序替换。

## 核心 API

- 客户端：`getMessage()`
- 服务端：`gs.getMessage()`
- 多语言消息记录表：`sys_ui_message`
- 客户端占位符替换：`withValues()`

## 获取无参数多语言消息

### 客户端

```javascript
getMessage('message_key', function (message) {
  g_form.addInfoMessage(message);
});
```

客户端通过回调函数接收本地化后的消息文本。

### 服务端

```javascript
var message = gs.getMessage('message_key');
gs.addInfoMessage(message);
```

服务端直接通过 `gs.getMessage()` 获取当前用户语言对应的消息。

## 客户端带参数的 Message

消息文本可以包含索引占位符。例如：

```text
Good Morning, {0}!
```

客户端调用示例：

```javascript
getMessage('Good Morning, {0}!', function (message) {
  var localizedMessage = message.withValues([
    g_user.getFullName()
  ]);

  g_form.addInfoMessage(localizedMessage);
});
```

`withValues()` 按数组顺序替换占位符：数组第一个元素替换 `{0}`，第二个元素替换 `{1}`，依此类推。

## 服务端带参数的 Message

### 第一步：创建多语言消息记录

打开：

`System Localization > Messages`

在 `sys_ui_message` 表中创建消息记录，例如：

- `Key`：`im_notification_msg`
- `Message`：`Message sent to {0} regarding {1}`

为不同语言创建相同 Key 的消息记录，并填写对应语言的文本。

### 第二步：准备参数并获取消息

```javascript
var messageParameters = [];

messageParameters.push(current.caller_id.getDisplayValue());
messageParameters.push(current.number);

var message = gs.getMessage(
  'im_notification_msg',
  messageParameters
);

gs.addInfoMessage(message);
```

参数数组中的顺序必须与消息占位符一致：

- `messageParameters[0]` 替换 `{0}`。
- `messageParameters[1]` 替换 `{1}`。

## 占位符规则

- 占位符索引从 `0` 开始。
- 参数数量应覆盖消息中使用的全部占位符。
- 参数顺序应与占位符语义一致。
- 不同语言的消息记录应使用相同的占位符索引，避免翻译后参数错位。

## 注意事项

- 客户端和服务端 API 不可混用：客户端使用 `getMessage()`，服务端使用 `gs.getMessage()`。
- 建议使用稳定、可读的 Message Key，避免直接把长文本作为长期维护的键值。
- 修改消息文本时，应同时检查所有语言版本的占位符数量与索引。
