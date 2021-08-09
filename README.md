# scala
### 1.匿名函数
（1）没有名字的函数就是匿名函数
```(x: Int) => {The function}```

Example1
```scala
二元运算函数，只操作1和2两个数，但是具体运算通过参数传入
def dualFunctionOneAndTwo(fun: (Int, Int) => Int): Int ={
  fun(1,2)
}
val add = (a: Int, b: Int) => a + b
val minus = (a: Int, b: Int) => a - b
println(dualFunctionOneAndTwo(add)) // 3
println(dualFunctionOneAndTwo(minus)) // -1
```

（2）匿名函数的简化
```scala
println(dualFunctionOneAndTwo((a,b) => a + b))
println(dualFunctionOneAndTwo(_ + _) ) 
```
###2.高阶函数
```scala
object TestFunction {
  def main(args: Array[String]): Unit = {
    def f(n: Int): Int = {
      println("f调用")
      n + 1 //  return 
    }

    val result: Int = f(125)
    println(result)// 126
  }
}
```
（1）函数作为值进行传递
```scala
// same object
val f1: Int=> Int = f // 
val f2 = f _ // When using _,  it's simple 

println(f1) // An object
println(f1(12))// 13
println(f2(35))// 36
```

（2）函数作为参数进行传递

定义一个二元计算函数
```scala
def dualEval(op: (Int, Int) => Int, a :Int, b: Int): Int = {
  op(a,b)
}

def add(a: Int, b: Int): Int = {
  a + b
}

println(dualEval(add, 10, 95)) // 105
println(dualEval((a, b) => a + b, 10, 95)) // 105

```

（3）函数作为函数得返回值返回

函数式编程中，关心的是映射关系
```scala
def f5(): Int => Unit={
  def f6(a: Int): Unit = {
    println("f6调用"+a)
  }
  f6 // return function f6
 }
 println(f5()) // object
 val f6 = f5()
 println(f6) // object 
 println(f6(25)) // "f6调用"+a ()
 println(f5()(25)) // "f6调用"+a ()
```















