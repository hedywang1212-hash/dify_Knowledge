var nowTime = new GlideDateTime().getDisplayValueInternal();
nowTime=new GlideDateTime(nowTime);
​
var timeDiffrent=gs.dateDiff(nowTime,new GlideDateTime(),true);