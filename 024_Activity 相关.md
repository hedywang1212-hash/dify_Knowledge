1.Activity在画面上点击提交后，会在sys_journal_field表中生成日志
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_01.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_01.png

图片说明：该图对应原文内容：Activity在画面上点击提交后，会在sys_journal_field表中生成日志
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_02.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_02.png

图片说明：该图对应原文内容：历史活动会保存在sys_history_set，sys_history_line表中

2.历史活动会保存在sys_history_set，sys_history_line表中
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_03.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_03.png

图片说明：该图对应原文内容：历史活动会保存在sys_history_set，sys_history_line表中
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_04.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_04.png

图片说明：该图对应原文内容：如果想要修改additional comments的时候，先修改sys_audit中的value值,这时候会发现activity中改过的值没有变

3.如果想要修改additional comments的时候，先修改sys_audit中的value值,这时候会发现activity中改过的值没有变
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_05.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_05.png

图片说明：该图对应原文内容：如果想要修改additional comments的时候，先修改sys_audit中的value值,这时候会发现activity中改过的值没有变

然后把sys_history_set（缓存）中的数据删除后
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_06.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_06.png

图片说明：该图对应原文内容：然后把sys_history_set（缓存）中的数据删除后
![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_07.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/024_07.png

图片说明：该图对应原文内容：Activity的值也改变了,sys_journal_fiel中记录的值还是之前的3333，如果改变成5555，activity中显示为4444。

Activity的值也改变了,sys_journal_fiel中记录的值还是之前的3333，如果改变成5555，activity中显示为4444。
