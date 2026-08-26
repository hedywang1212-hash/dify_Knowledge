ACL高级功能
使用菜单的Debug Security可以用来调试ACL，当你打开一条记录时，记录下面会输出每一条ACL的判定以及结果。

打开调试之后使用impersonate User后依旧可以看到对应用户的调试结果。

ACL的类型除了Record，还有其他的，这里介绍下常用的。

client_callable_script_include: AJAX调用中对相应的Script Include做权限控制。

REST_Endpoint: REST权限控制。

ui_page: UI Page权限控制，我们平时在内部页面使用的incident_list.do，incident.do也属于UI Page，当Record的ACL通过但依旧无法打开内部form界面时，可以看看这个有没有问题。