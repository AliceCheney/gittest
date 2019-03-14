#### Spring是什么？

```
Spring主要用来开发Java应用的轻量级框架
```

#### 使用spring的好处是什么？

轻量：spring是轻量级的

控制反转：spring通过控制反转实现了松散耦合，对象们给出他们的依赖，而不是创建或查找依赖的对象们

面向切面编程（AOP）：spring支持面向切面的编程，并且把应用业务逻辑和系统服务分开。

容器：spring包含并管理应用中对象的生命周期和配置。

mvc框架：spring的web框架是一个精心设计的框架，web框架的一个很好的替代品

事务管理：spring提供一个持续的事务管理接口，可扩展到上至本地事务下至全局事务（JAT）

异常处理：spring提供方便的API技术相关的异常（比如由JDBC，Hibernate or JDO抛出的）转化为一致的unchecked 异常。

##### spring框架的基本信息：或者有哪些模块组成

##### spring的核心容器：

BeanFactory 是 任何以spring为基础的应用的核心。Spring 框架建立在此模块之上，它使Spring成为一个容器

##### Beanfactory实现举例：

Bean 工厂是工厂模式的一个实现，提供了控制反转功能，用来把应用的配置和依赖从正真的应用代码中分离。

最常用的BeanFactory 实现是XmlBeanFactory 类。

##### XMLBeanfactory：

最常用的就是org.springframework.beans.factory.xml.XmlBeanFactory ，它根据XML文件中的定义加载beans。该容器从XML 文件读取配置元数据并用它去创建一个完全配置的系统或应用。

##### 解释AOP模块

AOP模块用于给Spring应用做面向切面的开发， 很多支持由AOP提供，这样就确保了Spring和其他AOP框架的共通性。这个模块将元数据编程引入Spring

##### 解释JDBC抽象和DAO模块：

通过使用jdbc和dao，保证数据库代码的简洁，并能避免数据库资源错误关闭导致的问题，他在各种不同的数据库的错误信息之上，提供了一个统一的异常访问层，他还利用springAOP模块给spring提供事务管理服务

##### 解释对象/关系映射集（ORM)成模块：

spring通过提供ORM模块，支持我们直接在JDBC之上使用一个对象/关系映射工具，spring支持继承主流的ORM框架，如Hiberate,JDO和 iBATIS SQL Maps。spring的事务管理同样支持ORM框架及JDBC

（ORM提供了实现持久化层的另一种模式，它采用映射元数据来描述对象关系的映射，使得ORM中间件能在任何一个应用的业务逻辑层和数据库层之间充当桥梁。Java典型的ORM中间件有:Hibernate,ibatis,speedframework。 ）

##### 解释web模块： 

spring的web模块是构建在application context 模块基础之上，提供一个适合web应用的环境，这个模块也包括支持多种面向web的任务，如透明地处理多个文件上传请求和程序级请求参数绑定到你的业务对象

##### spring配置文件：

spring配置文件是xml文件，这个文件包含了类的信息，描述如何配置它们，和如何相互调用

##### 什么是springIOC 容器：

spring IOC负责创建对象，管理对象（通过依赖注入），装配对象，配置对象，并且管理对象的整个生命周期

##### IOC的优点是什么？

IOC或依赖注入把应用的代码量降到最低，它使应用容易测试，单元测试不再需要单例和JNDI查找机制，最小的代价和最小的侵入性使松散耦合得以实现。IOC容器支持加载服务时的饿汉式初始化和懒加载

##### ApplicationContext通常的实现是什么?

**FileSystemXmlApplicationContext ：**此容器从一个XML文件中加载beans的定义，XML Bean 配置文件的全路径名必须提供给它的构造函数。

**ClassPathXmlApplicationContext：**此容器也从一个XML文件中加载beans的定义，这里，你需要正确设置classpath因为这个容器将在classpath里找bean配置。

**WebXmlApplicationContext：**此容器加载一个XML文件，此文件定义了一个WEB应用的所有bean。

##### （未记住）Bean 工厂和 Application contexts 有什么区别？

Application contexts 提供一种方法处理文本消息，一个通常的做法是加载文件资源（比如镜像），他们可以向注册为监听器的bean发布事件。另外，在容器或容器接口内的对象上执行那些必须由bean工厂以程序化方式处理的操作，可以在application contexts中以声明的方式处理。application contexts实现了message source接口，该接口的实现以可拔插的方式提供获取本地化消息的方法

##### 一个spring的应用看起来像什么？

一个定义了一些功能的接口

实现包括属性，Setter ， gette方法和构造函数

spring AOP

spring XML配置文件

使用以上功能的客户端程序

### 依赖注入

##### 什么是spring的依赖注入？

	依赖注入，是ioc的一个方面，就是说你不用创建对象，只需要描述他们如何让被创建。你不在代码里直接组装你的组件和服务，但是要在配置文件里描述哪些组件需要哪些服务，之后一个容器（ioc容器）负责把他们组装起来

##### 有哪些不同类型的ioc（依赖注入）方式？

**构造器依赖注入**：构造器依赖注入通过容器触发一个类的构造器来实现，该类有一些列参数，每个参数代表一个对其它类的依赖

**Setter方法注入**：setter方法注入是容器通过调用无参构造器或无参static工厂方法实例化bean之后，调用该bean的setter方法，即实现了基于setter的依赖注入




