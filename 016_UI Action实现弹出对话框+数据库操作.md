要实现这样的效果，需要同时使用Client（勾选Client）和Service的代码
Client示例代码
```javascript
//Client-side onclick function
function createProblem(){
    if(!confirm("Do you want to continue?")){
        return false;
    }

    // Call the UI action and skip the 'onclick' function

    //gsftSubmit（String control, Object form, String action_name）
    //提交表单，支持在单个UI操作中调用客户端代码和服务器端代码。
    //control：填你想要模拟用户点击的按钮的名字，或者填null
    //form：可选，提交的名单元素，通常通过“ g_form.getFormElement()”来检索其值
    //action_name：该值在[sys_ui_action]表中提供

    gsftSubmit(null, g_form.getFormElement(), 'create_problem'); //MUST call the 'Action name' set in this UI Action
}

// Code that runs without 'onclick' 确保在客户端函数不再运行之前，服务器端函数不会运行
// Ensure call to server-side function with no browser errors
if (typeof window == 'undefined')
serverResolve();
```

Service示例代码
```javascript
// Server-side function
function serverResolve() {
    //对数据库的一系列操作
    var prob = new GlideRecord("problem");
    prob.short_description = current.short_description;
    prob.cmdb_ci = current.cmdb_ci;
    prob.priority = current.priority;
    prob.company = current.company;
    prob.sys_domain = current.sys_domain;
    prob.description = current.description;
    prob.u_incident = current.sys_id;
    var sysID = prob.insert();

    current.problem_id = sysID;
    var mySysID = current.update();

    gs.addInfoMessage("Problem " + prob.number + " created");    //使用addInfoMessage在表单的顶部显示信息消息

    action.setRedirectURL(prob);    //设置用户将看到的下一页
    action.setReturnURL(current);   //设置用户在提交表单后返回的页面，或者在他们看到的下一页点击返回之后显示的页面
}
```
