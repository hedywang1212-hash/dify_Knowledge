Business Rule：在Business Rule中进行页面重定向：


//action.setRedirectURL('https://www.google.com');
//gs.setRedirect("https://www.google.com");
上面两种方法都可行，




创建了这种Business Rule后，当触发Business Rule时，页面自动跳转到指定的URL。





Script Include：在Script Include中进行页面重定向：

//action.setRedirectURL("https://www.google.com");
//gs.setRedirect("https://www.google.com");
上面两种方法都可行，




创建了这种Script Include后，当触发Script Include时，页面自动跳转到指定的URL。







Client Script：在Script Include中进行页面重定向：

//top.window.location = ("https://www.google.com");
//window.open = ("https://www.google.com");
//g_navigation.openPopup("https://www.google.com");
以上方法都可行，


创建了这种Client Script后，当触发Client Script时，页面自动跳转到指定的URL。





UI Action：在UI Action中进行页面重定向：
//action.setRedirectURL('https://www.google.com');
//gs.setRedirect('https://www.google.com');
以上两种方法都可行，
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_01.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_01.png
图片说明：该图对应原文内容：以上两种方法都可行，

创建了这种UI Action后，当触发UI Action时，页面自动跳转到指定的URL。





UI Page: 在UI Page中进行页面重定向：

```javascript
response.sendRedirect("<url>");
```
可以使用上面的方法在UI Page中的Processing script中进行页面的重定向
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_02.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_02.png
图片说明：该图对应原文内容：可以使用上面的方法在UI Page中的Processing script中进行页面的重定向

在这个例子中，如果我点击了Accept按钮页面就会跳转
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_03.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_03.png
图片说明：该图对应原文内容：在这个例子中，如果我点击了Accept按钮页面就会跳转

==========⇒
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_04.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_04.png
图片说明：该图对应原文内容：==========⇒

Widget：在Widget中进行页面重定向：

只能在Client Script中运用

```javascript
window.location = <url>;
```
window.open(<url>,'_blank');//在新的标签页或窗口中打开 URL。如果浏览器设置阻止弹出窗口，可能会在新的标签页中打开 URL。
window.open(<url>,'_self');//在执行 JavaScript 代码的同一窗口或标签页中打开 URL。如果没有指定目标属性，这是默认行为。 
window.open(<url>,'_parent');//在父窗口或包含框架的窗口中打开 URL。 
window.open(<url>,'_top');//在顶层窗口中打开 URL，忽略嵌套的框架。
```javascript
top.window.location = <url>;
```
//还有使用$location的方法，写在下方
例：

1、创建一个按钮，并设置点击事件
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_05.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_05.png
图片说明：该图对应原文内容：1、创建一个按钮，并设置点击事件

![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_06.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_06.png
图片说明：该图对应原文内容：2、点击对应按钮后页面跳转

2、点击对应按钮后页面跳转





$location方法
例：假设当前URL为'http://localhost/$location/21.1%20$location.html#/foo?name=bunny#myhash'


$location.url('/foo2?name=bunny2&age=12#myhash2');//修改URL的子路径（也就是当前url#后面的内容，包括参数）
例子的URL运行后跳转到的URL为'http://localhost/$location/21.1%20$location.html#/foo2?name=bunny2&age=12#myhash2'


$location.path('/foo2/foo3');//修改URL的子路径部分（也就是当前url#后面的内容，不包括参数）
例子的URL运行后跳转到的URL为‘http://localhost/$location/21.1%20$location.html#/foo2/foo3/?name=bunny#myhash’





```javascript
$location.hash('myhash3');//修改URL的哈希值部分
```
例子的URL运行后跳转到的URL为‘http://localhost/$location/21.1%20$location.html#/foo?name=bunny#myhash3’




①第二个参数的格式也是字符串
```javascript
$location.search('name','code_bunny');// 第一个参数表示url参数的属性名,第二个参数是该属性名的属性值,如果是已有属性名,则修改,如果不是已有属性,则新增
```
测试URL中有name字段，所以会将name的值更新，得到'http://localhost/$location/21.1%20$location.html#/foo?name=code_bunny#myhash'


②第二个参数的格式为数组,数组中的各个值也是字符串或者布尔值 
```javascript
$location.search('love',['zxg','mitu']);// 第一个参数表示url参数的属性名,第二个参数是该属性名的值,有多少个值,url中就会依次重复出现多少个.
```
例子的URL运行后跳转到的URL为'http://localhost/$location/21.1%20$location.html#/foo?name=bunnylove=zxg&love=mitu#myhash'

 ③传入两个参数,第一个参数为字符串,第二个参数为null

```javascript
$location.search('age',null);// 第一个值表示url参数的属性名,如果是已有属性名,则删除该属性,如果不是已有属性,那就等于没改过
```
由于例子的URL中没有age属性，所以URL不变

④传入一个参数,格式为json对象
```javascript
$location.search({name:'papamibunny',age:16,love:'zxg'});// 直接用这个json对象里的键值对替换整个url的参数部分
```
例子的URL运行后跳转到的URL为’http://localhost/$location/21.1%20$location.html#/foo?name=papamibunny&age=16&love=zxg#myhash‘

```javascript
$location.search({name['code_bunny','white_bunny','hua_bunny'],age:16,love:'zxg'});
```
例子的URL运行后跳转到的URL为‘http://localhost/$location/21.1%20$location.html#/foo?name=code_bunny&name=white_bunny&name=hua_bunny&age=16&love=zxg#myhash’

⑤传入一个参数,格式为字符串:
```javascript
$location.search('bunnybaobao');// 直接用这个字符串替换整个url的参数部分(没有键值对,参数部分就是一个属性名,但转换成json对象的话,这个属性的值就是true,但是在url里没有体现
```
例子的URL运行后跳转到的URL为’http://localhost/$location/21.1%20$location.html#/foo?bunnybaobao#myhash‘

{"bunnybaobao":true}





$location方法使用示例
在widget中创建一个测试按钮
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_07.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_07.png
图片说明：该图对应原文内容：在widget中创建一个测试按钮

在页面上点击测试按钮
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_08.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_08.png
图片说明：该图对应原文内容：在页面上点击测试按钮

页面跳转到指定的sys_id画面
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_09.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/035_09.png
图片说明：该图对应原文内容：页面跳转到指定的sys_id画面
