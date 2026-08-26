
#  多语言自适应Message带参数的实现

## 实现多语言自适应Message的函数

1. 客户端：
```javascript
getMessage();
```

2. 服务端：
```javascript
gs.getMessage();
```

## Message中带参数

1. 客户端：
```javascript
getMessage("Good Morning, {0}!", function(msg) {
	g_form.addInfoMessage(msg.withValues([g_user.getFullName()])); 
 } );
```

2. 服务端：
①在sys_ui_message里创建多语言消息：
System Localization > Message 
key = 'im_notification_msg'
message = 'Message sent to {0} regarding {1}';
②代码里调用：
```javascript
var msgArray = [];
// 将值按顺序添加到数组中
msgArray.push(current.caller_id.getDisplayValue());
msgArray.push(current.number);
var msg = gs.getMessage('im_notification_msg', msgArray);
gs.addInfoMessage(msg);
```