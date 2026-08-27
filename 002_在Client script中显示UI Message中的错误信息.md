在Client script中无法调用gs函数，所以不能直接通过gs.getMessage()来获取，但也不用大费周章调用GlideAjax，通过服务端来调用gs.getMessage()。

可以通过以下方法进行调用

```javascript
getMessage("UI Message Key", function(msg) {
    g_form.showFieldMsg('field',msg, "error"); //在执行onChange Client script的时候
g_form.addErrorMessage(msg); //在执行onSubmit Client script的时候
});
```

但调用的UI Message需要参数时，可以通过以下方法进行调用

```javascript
getMessage("The number is exceeds the  {0} stock count({1})!", function(msg) { 
    g_form.showFieldMsg('individual',msg.withValues([参数1,参数2]), "error");
} );
```
