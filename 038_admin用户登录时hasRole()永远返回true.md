hasRole(String role, Boolean includeDefaults)

如果当前用户具有指定role或为admin，则返回 true。

​

因为admin具有所有的role，所以永远返回true。

例如：用户为admin时，验证是否具有“snc_internal”
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/038_01.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/038_01.png
图片说明：该图对应原文内容：例如：用户为admin时，验证是否具有“snc_internal”

返回结果为true
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/038_02.png)
图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/038_02.png
图片说明：该图对应原文内容：返回结果为true
