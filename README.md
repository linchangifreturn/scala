# scala
### 1.匿名函数
（1）没有名字的函数就是匿名函数
```(x: Int) => {The function}```
（2）Example1
```
二元运算函数，只操作1和2两个数，但是具体运算通过参数传入
def dualFunctionOneAndTwo(fun: (Int, Int) => Int): Int ={
    fun(1,2)
}
