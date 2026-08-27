方法：新建一个script include并使用GlideAjax，或者使用REST APIs。
​

例：在client script中将用户设置为 Fred Luddy，然后调用script include以获取他们的经理。

client script中代码如下：

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/039_01.png)



script include中代码如下:

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/039_02.png)

运行结果如下：

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/039_03.png)



注意：getXMLWait()也不能再scope application中使用。

