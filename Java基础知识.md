##### 1.Anonymous Inner Class (匿名内部类) 是否可以extends(继承)其它类，是否可以implements(实现)interface(接口)？

不能继承其它类，但是可以作为一个接口，由另一个内部类实现

##### 2.Static Nested Class 和 Inner Class的不同

nested是c++的说法，inner是Java的说法。Java内部类和c++嵌套类最大的不同就是在于是否有指向外部的引用上

##### 3.&和&&的区别？

&是位运算符，表示按位与运算，&&是逻辑运算符，表示逻辑与（and）

##### 4.Collection 和 Collections的区别？

collection是集合类的上级接口，collections是集合类的一个帮助类

##### 5.在 Spring中如何注入一个java集合？

Spring提供以下几种集合的配置元素：

```
<list>类型用于注入一列值，值可以相同
<set>类型用于注入一组值，值不能相同
<map>注入一组键值对，键值对可以为任意类型
<props>注入一组键值对，键和值只能为String类型
```

##### 6.什么时候使用assert断言？

	测试用的。

它对一个boolean表达式进行检查，一个正确程序必须保证这个boolean表达式的值为true；如果该值为false，说明程序已经处于不正确的状态下，系统将给出警告或退出。

##### 7.Java有没有goto？

	有，但是不用了

##### 8.数组有没有length（）这个方法？String有没有？

	数组没有length（）方法，但有length（）属性，string有length（）这个方法

##### 9.Overload和Override的区别。Overloaded的方法是否可以改变返回值的类型

	Overloaded的方法是可以改变返回值的类型。

如果在子类中定义某方法与其父类有相同的名称和参数，我们说该方法被重写 (Overriding)。

如果在一个类中定义了多个同名的方法，它们或有不同的参数个数或有不同的参数类型，则称为方法的重载(Overloading)。

重写Overriding是父类与子类之间多态性的一种表现，重载Overloading是一个类中多态性的一种表现。

##### 10.给我一个你最常见到的runtime exception

数组越界（IndexOutOfBoundsException）

空指针（NullPointerException）

##### 11.Set里的元素是不能重复的，那么用什么方法来区分重复与否呢? 是用==还是equals()? 它们有何区别

用（迭代器）iterator()方法来区分重复与否。

用==方法

equals()是判读两个Set是否相等 

##### 12.error和exception有什么区别？

 error 表示一种严重问题。比如说内存溢出。不可能指望程序能处理这样的情况 exception 表示一种设计或实现问题。也就是说，它表示如果程序运行正常，从不会发生的情况

##### 13.List, Set, Map是否继承自Collection接口

list，set继承，map不继承

##### 14.abstract class（抽象类）和interface（接口）有什么区别?

抽象类只能继承一个，接口能实现多个

##### 15.abstract（抽象类）的method（方法）是否可同时是static（静态的）,是否可同时是native（本地的），是否可同时是synchronized（同步）？

都不能

##### 16.接口是否可继承接口? 抽象类是否可实现(implements)接口? 抽象类是否可继承实体类(concrete class)

接口能继承接口，抽象类可以实现接口，抽象类能继承实体类，但是实体类要有明确的构造函数

##### 17.构造器Constructor是否可被override（重写）？

构造器不能被继承，所以不能被重写，但是可以被重载

##### 18.是否可以继承String类？

string类是final类，final类一旦被定义就不能更改，所以不能被继承

##### 19.try {}里有一个return语句，那么紧跟在这个try后的finally {}里的code会不会被执行，什么时候被执行，在return前还是后

会执行，在return结束之前

##### 20.两个对象值相同(x.equals(y) == true)，但却可有不同的hash code，这句话对不对

不对，有相同的我hash code

##### 21.当一个对象被当作参数传递到一个方法后，此方法可改变这个对象的属性，并可返回变化后的结果，那么这里到底是值传递还是引用传递

是值传递，Java编程语言只有值传递参数

##### 22.swtich是否能作用在byte上，是否能作用在long上，是否能作用在String上

long不能作用于swtich上

 switch（expr1）中，expr1是一个整数表达式

##### 23.ArrayList和Vector的区别,HashMap和Hashtable的区别

Vector是线程安全的，而ArrayList是线程序不安全的，Hashtable是线程安全的，也就是说是同步的

##### 24.char型变量中能不能存贮一个中文汉字?为什么?

能存，因为一个char占16个字节

##### 25.GC是什么? 为什么要有GC？

GC是垃圾收集的意思（Garbage Collection）

java提供GC功能可以自动监测对象是否超过作用域从而达到自动回收内存的目的

##### 26.抽象类与接口？

抽象类有自己的部分实现，而接口则完全是一个标识，同时又多重继承功能

27.string与stringbuffer的区别？

string长度是不可变得，string buffer长度是可变得

##### 28.谈谈final, finally, finalize的区别

**答：** final—修饰符（关键字）如果一个类被声明为final，意味着它不能再派生出新的子类，不能作为父类被继承。因此一个类不能既被声明为 abstract的，又被声明为final的。将变量或方法声明为final，可以保证它们在使用中不被改变。被声明为final的变量必须在声明时给定初值，而在以后的引用中只能读取，不可修改。被声明为final的方法也同样只能使用，不能重载finally—再异常处理时提供 finally 块来执行任何清除操作。如果抛出一个异常，那么相匹配的 catch 子句就会执行，然后控制就会进入 finally 块（如果有的话）finalize—方法名。Java 技术允许使用 finalize() 方法在垃圾收集器将对象从内存中清除出去之前做必要的清理工作。这个方法是由垃圾收集器在确定这个对象没有被引用时对这个对象调用的。它是在 Object 类中定义的，因此所有的类都继承了它。子类覆盖 finalize() 方法以整理系统资源或者执行其他清理工作。finalize() 方法是在垃圾收集器删除对象之前对这个对象调用的

##### 29.面向对象的特征有哪些方面？

1.抽象 2.继承 3.封装  4. 多态

##### 30.String是最基本的数据类型吗？

基本数据类型包括byte、int、char、long、float、double、boolean和short。string类是final类型的，不能被继承不能修改为这个类

##### 31.int 和 Integer 有什么区别

Int是java的原始数据类型，Integer是java为int提供的封装类

##### 32.说出ArrayList,Vector, LinkedList的存储性能和特性？

array list线程不安全，取的快，vector是同步的，线程安全，但是存取慢，linked list 是双线连接，存的快，不安全

##### 33.HashMap和Hashtable的区别

hashmap允许空键值，因为线程是非安全的，所以效率上高于hashtable

##### 34.heap（堆）和stack（栈）有什么区别？

栈是一种线性集合。堆是栈的一个组成元素

##### 35.你所知道的集合类都有哪些？主要方法？

最常用的的集合类是List和map。

##### 36一个".java"源文件中是否可以包括多个类（不是内部类）？有什么限制？

可以。必须只有一个类名与文件名相同

##### 37.（未掌握）描述一下JVM加载class文件的原理机制?

虚拟机中装载的都是由classloader和它的子类来实现的Java ClassLoader 是一个重要的Java运行时系统组件。它负责在运行时查找和装入类文件的类

##### 38.在JAVA中，如何跳出当前的多重嵌套循环？

用break或return 方法。

##### 39.是否可以从一个static方法内部发出对非static方法的调用？

不可以。如果其中包含对对象的method（），不能保证对象初始化

