
Abort action可以用来取消此次检索。
利用current.addquery等，可以修改此次检索结果




例如：在when to run勾选“before”和“Query”

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/030_01.png)



输入以下代码：用户权限为admin时，可以查看incident中所有数据；不为admin时，只能看到状态为“In Progress”（state=2）的数据。

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/030_02.png)



查看incident的list页面，admin用户显示结果

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/030_03.png)



非admin用户显示结果

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/030_04.png)



3. current.getEncodedQuery()(.indexOf("target=order_iten")用来判断检索条件。



例：当检索条件中含有“category=inquiry”时，检索结果只显示“New”(state=1)的数据。

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/030_05.png)



显示结果：

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/030_06.png)