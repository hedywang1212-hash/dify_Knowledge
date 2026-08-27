### 一、parseInt()
```
 parseInt(string.radix)
 
| 参数 | 说明 | 
| -------- | -------- |
| string     | 要被解析的字符串 （必填）   |
| radix     | 要解析的数字的基数，范围在2~36之间（可选，不在此范围内将返回NaN），如果省略该参数或者其值为0，则数字将以10为基础解析，如果它以“0x”或“0X”开头，将以16为基数   | 


示例
parseInt("123abcd")   //123
parseInt("1.55")   //1
parseInt(".123")  //NaN
parseInt(10)    //10
parseInt("19",10)   //19(10+9)
parseInt("11",2)    //3(2+1)
parseInt("17",8)   //15(8+7)

注意：parseInt("17",6) 当解析时，1属于6进制范围，7不属于6进制范围，当string的数字大于radix时（7>6),它只会解析到它的上一位
 所以parseInt("17",6) = parseInt("1",6)=1
```
