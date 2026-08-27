workflow中有一个很实用的功能就是可以通过workflow.scratchpad.xxx=xxx的形式设置共享变量，设置完成后可以在不同的workflow的模块间进行调用。

在workflow外部，也可以通过以下方法进行获取和修改（只能在服务端调用，Client Sript端无法调用）

  var workflow = new Workflow();
        var context = workflow.getContexts(current); //current为当前执行该workflow的record
         var Item= "";
        
         if (context.next()) {
             Item = context.scratchpad.Item;
context.scratchpad.Item="1";
context.update();

         }