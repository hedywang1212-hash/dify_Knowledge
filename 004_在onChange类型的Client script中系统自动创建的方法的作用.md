在新建一个onChange类型的Client script时，系统会自动创建一个if (isLoading || newValue == '') { return;  }方法。

这个方法的作用有两个，

第一个是在界面载入时，系统默认会对field进行赋值，这时候不加这个方法，则也算是会触发这个onChange。

第二个是当该onChange的对象的新值为空时也不触发这个onChange，因为很多对象如果值为空会产生bug。
