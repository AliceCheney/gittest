### 1.说说你对缓存的理解？

1.使用缓存的目的：

2.缓存的介质（缓存的存储位置）

3.缓存的分类

4.缓存什么样的数据？

5.缓存的有效性

6.脏数据

7.刷新缓存的方式

8.缓存的层次（一般我们将缓存加载service中）

9.缓存的清除策略:(缓存空间不足需要进行清理的时候使用)

10.什么时候使用缓存的清除策略？

### **2.**你对Maven是怎么理解的？

### 3.Spring MVC中的注解你都用过哪些，**SpringMVC的运行原理是什么？

### 4.SSM整合的流程？

### 5.谈谈你对Spring的理解？

IOC的作用：

Spring IOC的注入：

Spring IOC 自动绑定模式：

 AOP  主要应用于日志记录，性能统计，安全控制,事务处理（项目中使用的）等方面。

Spring中实现AOP技术：

 在Spring中可以通过代理模式来实现AOP



Spring AOP事务的描述：

在spring-common.xml里通过<aop:config>里面先设定一个表达式，设定对service里那些方法  如：对add* ,delete*,update*等开头的方法进行事务拦截。我们需要配置事务的传播（propagation="REQUIRED"）特性,通常把增,删,改以外的操作需要配置成只读事务（read-only="true"）.只读事务可以提高性能。之后引入tx:advice,在tx:advice引用transactionManager（事务管理）,在事务管理里再引入sessionFactory,sessionFactory注入 dataSource，最后通过<aop:config>引入txAdvice。



Spring实现ioc控制反转描述：

 原来需要我们自己进行bean的创建以及注入，而现在交给

spring容器去完成bean的创建以及注入。

 所谓的“控制反转”就是 对象控制权的转移，

从程序代码本身转移到了外部容器。

### 6.HashMap和HashTable的区别?

.Map是一个以键值对存储的接口。

### 7.HashMap的底层原理?(源代码)

### 8.jre,jdk,jvm的区别？

Jdk【Java Development ToolKit】就是java开发工具箱， JDK是整个JAVA的核心里边包含了jre

Jre【Java  Runtime  Enviromental】是java运行时环境，它只是保证java程序运行，不能用来开发，而jdk才是用来开发的，所有的Java程序都要在JRE下才能运行。

Jre里边包含jvm

Jvm：【Java Virtual Mechinal】因为jre是java运行时环境，java的底层是依赖于jvm，即java虚拟机，java虚拟机用来加载类文件，java中之所以有跨平台的作用，就是因为jvm

关系：

 J2se是基于jdk和jre，

 JDK是整个JAVA的核心里边包含了jre，

 Jre里边包含jvm

### 9.Set,List,Collection,Collections的区别？

### 11.抽象类和接口的区别？

### 12.Get和Post的区别？

### 13.Redirect和Forward的区别？

### 14.Http协议的理解?

### 15.长连接和短连接？



