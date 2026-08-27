

使用sysparm_stack可以指定页面跳转到相应的表。


（如果设定sysparm_stack=no的话，将返回到上一个页面）



例①直接在URL中使用：在新建incident的页面的URL中添加"sysparm_stack=sys_script_list.do"，则提交之后，页面跳转至business rule的list页面。

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/032_01.png)



提交后跳转的页面


​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/032_02.png)


例②用于【Edit Module】：如下图在menu中点击【Edit Module】，【Arguments】中显示"sysparm_stack=incident_list.do"。则提交incident之后，页面跳转至incident这张表。

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/032_033.png)