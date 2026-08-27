kb_article_view的文章页面自带有很多组件，如果不需要这些想把它去掉时，有两个地方可以进行设置。

1.比如想去掉文章中的作者信息
打开kb_article_view的Instance Options
在css栏中填入
.author{display: none;}语句保存

刷新页面后组件就会被去掉

2.去掉评论功能
在Knowledge>Administration>Properties中
在Article View Properties中的
Show user comments on knowledge articles:
把选项改为Never并保存