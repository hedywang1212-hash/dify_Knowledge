一、如果ACL中type选择UI PAGE，name设置为XXX_list，可以用来禁用相关list的列表访问，如果是直接table名的话则是禁用form访问


例：禁止访问test table表的list界面

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/040_01.png)



则用户无法访问list界面

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/040_02.png)



二、ACL的type为record时，部分或全部内容不显示
例：显示字段“trueorfalse”为“true”的record

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/040_03.png)



显示结果如下：

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/040_04.png)