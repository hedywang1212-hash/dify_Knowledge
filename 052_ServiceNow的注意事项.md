#### ServiceNow常用表
 
| 表 | 内部地址 |
| -------- | -------- |
| User表 | sys_user |
| Tables表 | sys_db_object |
| 附件表 | sys_attachment |
| 属性表 | sys_properties |
| Group的权限表 | sys_group_has_role |
| 部门表 | cmn_department |
| 公司表 | core_company |
| Group表| sys_user_group |
| Group和User的对应关系表 | sys_user_grmember |

&nbsp;
&nbsp;
&nbsp;

#### 如何查看当前使用的ServiceNow版本号
 在搜索栏输入stats.do
 可以看到返回的数据，找到【Build tag】，可以看到当前的版本类型以及补丁版本
 ![](http://139.224.210.26:82/pro/file-read-5125.html)
 
&nbsp;
&nbsp;
&nbsp;

#### 如何查看当前的Application和Update Set
点击画面右上角⚙齿轮图标，打开System Setting
Developer中，启用“Show application picker in header” 和 “Show update set picker in header”
<img src="http://139.224.210.26:82/pro/file-read-5137.html" style="zoom:50%;" />
 
&nbsp;
&nbsp;
&nbsp;

#### 常用的命令
运行测试代码：sys.scripts.do
清缓存：cache.do

&nbsp;
&nbsp;
&nbsp;

#### 各种区别
**Business Rule**：对表直接操作，例如：当表1的a字段被修改时，进行xx操作
**UI policy**：当在画面上勾选了/选择了xxx选项，画面会如何变化
**Client Script**：onSubmit、onChange、onLoad
**Script Include**：写通用函数
**Email Script**：在写email邮件的时候会运行的代码

&nbsp;
&nbsp;
&nbsp;

#### 安装插件
菜单栏：
【System Definition】
->【Plugin】
语言包：I18N
esc：Employee Service Center (记得勾选Load demo data)

&nbsp;
&nbsp;
&nbsp;

#### Q：系统自带的Button如何换成自己的？例如通用的new、update按钮（global）中要写入自己的设定
A：
找到该Button的Action Name，复制到自己写的Button的Action Name里

&nbsp;
&nbsp;
&nbsp;

#### Q：Record Producer是如何构建的？
A：
※Record Producer是没有Workflow的，可以使用Lifecycle Event连接实际申请流程
※下载esc的plugin之后，可以通过网址后加esc进行访问

&nbsp;
&nbsp;
&nbsp;

#### Q：创建了Record Producer，但是没有在Portal界面中找到
A：
1、在Record Producer中找到该画面的记录，打开
2、网址栏复制它的sys_id
3、在portal中随意发开一个申请画面
4、在网址栏中替换sys_id

&nbsp;
&nbsp;
&nbsp;

#### Service Portal
例如下面的链接????，以sp结尾，就能进入Service Portal了
https://dev115900.service-now.com/sp

&nbsp;
&nbsp;
&nbsp;

#### 关于Announcement的调查
官方相关文档：https://docs.servicenow.com/bundle/orlando-servicenow-platform/page/build/service-portal/concept/announcements-widget.html

1、新建Announcement


