
方法一：服务器端使用以下代码
```javascript
gs.action.getGlideURI().getMap().get('sysparm_id')
```


Scope下直接使用



```javascript
gs.action.getGlideURI().get('sysparm_id')
```


例：在Business Rule中编写代码，获取URL中的sys_id
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_01.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_01.png
图片说明：该图对应原文内容：例：在Business Rule中编写代码，获取URL中的sys_id

获取到当前页面的sys_id
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_02.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_02.png
图片说明：该图对应原文内容：获取到当前页面的sys_id

在日志中验证取值是否正确
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_03.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_03.png
图片说明：该图对应原文内容：在日志中验证取值是否正确

**注意：获取URL或URL内的参数时，如果发生页面刷新则无法获取正确的值。

比如说，在Business rule中设定when to run 为when update，则更新时页面发生刷新，无法取到正确的值。





方法二：在Client Script中使用以下代码获取URL




top.location.href;
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_04.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_04.png
图片说明：该图对应原文内容：top.location.href;

![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_05.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_05.png
图片说明：该图对应原文内容：补充：在widget的服务器端通过方法一获取URL后，可以通过以下代码修改正则表达式来获取URL中的所需参数。

补充：在widget的服务器端通过方法一获取URL后，可以通过以下代码修改正则表达式来获取URL中的所需参数。


```javascript
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
```
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_06.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_06.png
图片说明：该图对应原文内容：}

输出sys_id
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_07.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/029_07.png
图片说明：该图对应原文内容：输出sys_id
