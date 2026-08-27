具体代码如下:



```javascript
var isChoiceTable = tableGR.getElement(data.selectedKey).getED().isChoiceTable();
var fieldChoices = tableGR.getElement(data.selectedKey).getChoices();
if(isChoiceTable){
//choice list
var fieldChoices = tableGR.getElement(data.selectedKey).getChoices();
var cl = new ChoiceList(data.table, data.selectedKey);
gs.addInfoMessage(cl.getLabel(fieldChoices.get(0))); //label
gs.addInfoMessage(fieldChoices.get(0)); //value
}
```


例：test table中，color字段为choice类型。

![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_01.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_01.png

图片说明：该图对应原文内容：例：test table中，color字段为choice类型。
运行如下代码：

![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_02.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_02.png

图片说明：该图对应原文内容：运行如下代码：
输出结果为：

![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_03.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_03.png

图片说明：该图对应原文内容：输出结果为：
