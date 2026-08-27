实现多语言自适应Message的函数：

1、客户端：getMessage()

2、服务端：gs.getMessage()



Message中可带参数，客户端和服务器的实现方式相同，只是函数不同，以下是示例代码：


①使用服务端函数的例子
key = 'im_notification_msg'
message = 'Message sent to {0} regarding {1}';
-----------------------------------------------------
var msgArray = [];

// 将值按顺序添加到数组中
msgArray.push(current.caller_id.getDisplayValue());
msgArray.push(current.number);

var msg = gs.getMessage('im_notification_msg', msgArray);

gs.addInfoMessage(msg);

②使用客户端函数的例子
getMessage("Good Morning, {0}!", function(msg) {
	g_form.addInfoMessage(msg.withValues([g_user.getFullName()])); 
 } );
// Good Morning, Fred Luddy!