##### 1.javac命令和java命令做什么事情呢？

  	javac是编译，java是运行。

 javac：负责的是编译的部分，当执行javac时，会启动java的编译器程序。对指定扩展名的.java文件进行编译。生成了jvm可以识别的字节码文件。也就是class文件，也就是java的运行程序。

 java：负责运行的部分.会启动jvm.加载运行时所需的类库,并对class文件进行执行.  一个文件要被执行,必须要有一个执行的起始点,这个起始点就是main函数.

##### java语法基础

###### 1.(了解）关键字：

其实就是某种语言赋予了特殊含义的单词。 

###### 保留字：

其实就是还没有赋予特殊含义，但是准备日后要使用过的单词。

###### 标示符：

其实就是在程序中自定义的名词。比如类名，变量名，函数名。包含 0-9、a-z、$、_ ； 
注意： 
   1），数字不可以开头。 
   2），不可以使用关键字。

###### 常量：

是在程序中的不会变化的数据。

###### 变量：

其实就是内存中的一个存储空间，用于存储常量数据。
   作用：方便于运算。因为有些数据不确定。所以确定该数据的名词和存储空间。
   特点：变量空间可以重复使用。

###### 什么时候定义变量？

只要是数据不确定的时候，就定义变量。

###### 变量空间的开辟需要什么要素呢？

  1，这个空间要存储什么数据？数据类型。
  2，这个空间叫什么名字啊？变量名称。
  3，这个空间的第一次的数据是什么？ 变量的初始化值。

###### 变量的作用域和生存期:

变量的作用域： 
  作用域从变量定义的位置开始，到该变量所在的那对大括号结束；

生命周期： 
  变量从定义的位置开始就在内存中活了；
  变量到达它所在的作用域的时候就在内存中消失了；

###### 数据类型： 

1）：基本数据类型：byte、short、int、long、float、double、char、boolean
2）：引用数据类型: 数组、类、接口。

**级别从低到高为：**byte,char,short(这三个平级)–>int–>float–>long–>double

自动类型转换：从低级别到高级别，系统自动转的；

强制类型转换：什么情况下使用?把一个高级别的数赋给一个别该数的级别低的变量；

###### 运算符号： 

1）、算术运算符。

   + - * / % %:任何整数模2不是0就是1，所以只要改变被模数就可以实现开关运算。
   +:连接符。
   ++,–

2）、赋值运算符。
   = += -= *= /= %=

3）、比较运算符。
  特点：该运算符的特点是：运算完的结果，要么是true，要么是false。

4）、逻辑运算符。

  & | ^ ! && ||

  逻辑运算符除了 ! 外都是用于连接两个boolean类型表达式。

  &: 只有两边都为true结果是true。否则就是false。

  |:只要两边都为false结果是false，否则就是true

   ^:异或：和或有点不一样。
    两边结果一样，就为false。
    两边结果不一样，就为true.
  & 和 &&区别： & ：无论左边结果是什么，右边都参与运算。
       &&：短路与，如果左边为false，那么右边不参数与运算。
  | 和|| 区别：|：两边都运算。
       ||：短路或，如果左边为true，那么右边不参与运算。
5）、位运算符:用于操作二进制位的运算符。

##### 2.关键字

修饰符：  abstract、class、final、private、protected、public、static、7

数据类型：boolean、byte、char、double、float、int、long、short、void、9

语句组成：break、case、catch、continue、default、do、else、extends、finally、 for、if、implements、import、instanceof、interface、new、package、 return、super、switch、sychronized、this、throw、throws、try、while26

特殊含义关键字：assert、const、goto、enum、native、strictfp、transient、volatile、7

assert: 断言，用于调试，多被junit代替，IDE默认不开启。

const：预留关键字。

goto：预留关键字。

enum: 枚举。

native: 本地方法。

strictfp: 精确浮点，可用于类、接口、方法。

transient: 免除变量序列化。

volatile: 被设计用来修饰被不同线程访问和修改的变量。

非java关键字：

true、false、sizeof、null、serilizable、



