具体代码如下:



var isChoiceTable = tableGR.getElement(data.selectedKey).getED().isChoiceTable();
var fieldChoices = tableGR.getElement(data.selectedKey).getChoices();
if(isChoiceTable){
//choice list
var fieldChoices = tableGR.getElement(data.selectedKey).getChoices();
var cl = new ChoiceList(data.table, data.selectedKey);
gs.addInfoMessage(cl.getLabel(fieldChoices.get(0))); //label
gs.addInfoMessage(fieldChoices.get(0)); //value
}


例：test table中，color字段为choice类型。

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_01.png)



运行如下代码：

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_02.png)



输出结果为：

​![](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/041_03.png)