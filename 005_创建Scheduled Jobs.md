### 1.使用场景：
需要在特定时间或者重复计划中执行的自动化操作

### 2.创建方式
**①点击菜单中的System Definition>Scheduled Jobs**（**注意：**不要使用System Scheduler中的Scheduled Jobs来新建项目，一些现有的 scheduled jobs已经在Schedule Item [sys_trigger] 表中(System Scheduler > Scheduled Jobs)。

**②点击"NEW",选择Scheduled Jobs的类型**
![选择 Scheduled Jobs 类型](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/005_01.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/005_01.png
图片说明：点击 `NEW` 后，在 Scheduled Jobs 类型选择界面中选择需要创建的任务类型。

**③填写表单，提交**
通常会先在script include中写好代码，在Run this script调用
![填写 Scheduled Job 表单](https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/005_02.png)

图片地址：https://raw.githubusercontent.com/hedywang1212-hash/dify_Knowledge/main/images/005_02.png
图片说明：填写 Scheduled Job 表单并提交；通常先在 `script include` 中编写代码，再通过 `Run this script` 调用。
