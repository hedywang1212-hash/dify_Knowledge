1、创建一个Ui Script（字段UI Type和Global分别需要是Desktop和true）

![创建一个Ui Script](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/021_01.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/021_01.png

图片说明：该图对应原文内容：1、创建一个Ui Script（字段UI Type和Global分别需要是Desktop和true）

2、将附件中的UI script.txt中的代码复制到Script中，保存。



3、创建一个Client Script（注意UI Type要为All，且Isolate script为false）

![创建一个Client Script](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/021_02.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/021_02.png

图片说明：该图对应原文内容：3、创建一个Client Script（注意UI Type要为All，且Isolate script为false）
4、将附件中的Client Script.txt里的代码粘贴到Script中。

代码中的：

```javascript
shortcut.add("Ctrl+S",function() {
    gsftSubmit(document.getElementById('sysverb_update_and_stay'));
});
```
其中，第一个参数"Ctrl+S"为组合键，可以自己定义，如“Shift+Ctrl+F”。

第二个参数是当检测到点击了组合键之后将会运行的操作。此处的“document.getElementById('sysverb_update_and_stay')”的意思是查找当前页面上Id名为“sysverb_update_and_stay”的按钮，并执行该按钮操作。
