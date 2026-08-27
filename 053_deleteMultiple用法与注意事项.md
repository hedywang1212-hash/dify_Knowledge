deleteMultiple();
删除所有检索到的record

deleteRecord();
删除指定的单条record

如果是在business等有current字段的代码中
使用deleteMultiple()的话
因为current并没有加入检索条件，所有检索范围算作是整个table，
因此会把整个table里的所有record都删除掉

所以想要删除当前record时可以使用current.deleteRecord();