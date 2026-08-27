调用script includes时application默认为global，即使调用出处本身为其他scope。

也就是说，用new xxxxx()的形式调用的时候默认是global的，如果要调用scope的时候需要new scope.xxxx() 。