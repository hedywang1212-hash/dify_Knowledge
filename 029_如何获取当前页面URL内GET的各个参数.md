
方法一：服务器端使用以下代码
gs.action.getGlideURI().getMap().get('sysparm_id')


Scope下直接使用



gs.action.getGlideURI().get('sysparm_id')


例：在Business Rule中编写代码，获取URL中的sys_id

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_01.png)

获取到当前页面的sys_id

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_02.png)



在日志中验证取值是否正确

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_03.png)

**注意：获取URL或URL内的参数时，如果发生页面刷新则无法获取正确的值。

比如说，在Business rule中设定when to run 为when update，则更新时页面发生刷新，无法取到正确的值。





方法二：在Client Script中使用以下代码获取URL




top.location.href;

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_04.png)

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_05.png)







补充：在widget的服务器端通过方法一获取URL后，可以通过以下代码修改正则表达式来获取URL中的所需参数。


function getCurrentURI() {
var exg = /^(\/[^\?]+\?id=)/gm;
var requestURI = gs.action.getGlideURI().get("request_uri");//这里取到的是object类型
requestURI = String(requestURI);//转化成string
if(requestURI == null){
requestURI = decodeURIComponent(gs.action.getGlideURI());
requestURI = String(requestURI);
exg=/^api\/now\/sp\/widget\/[0-9a-z]{32}\?api=api&id=/g;
}
var subst = '';
var result = requestURI.replace(exg, subst);
return result;
}

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_06.png)






输出sys_id


​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_07.png)
