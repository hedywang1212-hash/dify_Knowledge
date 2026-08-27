通过update set来记录view的设定有⼀定危险性，element的sys_id在重新添加后会发⽣变化，导致view界⾯不⼀致

如下：

1、创建一个测试用的view

![创建一个view](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/022_01.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/022_01.png

图片说明：创建一个view；对应原文内容：1、创建一个测试用的view
此时，在Form Section中查到，price字段的sys_id为：8f5310d397bee51016803756f053af7c
![Form Section Elements](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/022_02.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/022_02.png

图片说明：Form Section Elements；对应原文内容：此时，在Form Section中查到，price字段的sys_id为：8f5310d397bee51016803756f053af7c
2、将View中的price字段删去之后保存，再添加之后保存。

此时，在Form Section中查到，price字段的sys_id为：edc4545797bee51016803756f053af4d



结论：两次的sys_id并不相同，如果用Update set来记录的话，sys_id不同的两个数据却代表同一个效果会出现问题。
