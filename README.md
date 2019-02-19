##### 1.spring mvc的配置：

    1.建立一个普通法的web项目
    
    2.引入相关jar包
    
    3.在web的配置文件web.xml中配置mvc的相关配置和dispatchServlet

##### 2.springboot的配置

    1.在spring官网start.spring.io快速创建一个项目
    
    2.在maven引入相关的依赖
    
    3.在application文件中管理springboot配置

##### 3.nosql：

NoSQL，泛指非关系型的数据库。

##### nosql的特点

    1.不需要预定义模式
    
    2.无共享架构
    
    3.弹性可扩展
    
    4.分区
    
    5.异步复制

##### nosql的使用场景

    1、数据模型比较简单；
    
    2、需要灵活性更强的IT系统；
    
    3、对数据库性能要求较高；
    
    4、不需要高度的数据一致性；
    
    5、对于给定key，比较容易映射复杂值的环境。

##### 4.GitHub上传的命令

1).初次上传的时候:

```
1.git init

2.git add . 

3.git commit -m "起个名字"

4.git remote add origin 你的网址

5.git push -u origin master
```

2).二次上传的时候

```
1.git add .

2.git commit -m "起个名字“

3.git push -u origin master
```

   git回退:

	本地:git reset --hard 版本号
	
	同步回退:git push --force

   git分支:

	1.创建并切换分支 :git checkout -b 名字
	
	2.创建分支 ： git branch 名字
	
	3.查看分支：git branch
	
	4.选择分支：git checkout 名字
	
	5.合并分支：git merge 分支名字
	
	6.删除分支：git branch -d 名字

##### Maven常见的依赖范围有哪些?

compile:编译依赖，默认的依赖方式，在编译（编译项目和编译测试用例），运行测试用例，运行（项目实际运行）三个阶段都有效，典型地有spring-core等jar。

	test:测试依赖，只在编译测试用例和运行测试用例有效，典型地有JUnit。
	
	provided:对于编译和测试有效，不会打包进发布包中，典型的例子为servlet-api,一般的web工程运行时都使用容器的servlet-api。
	
	runtime:只在运行测试用例和实际运行时有效，典型地是jdbc驱动jar包。
	
	system: 不从maven仓库获取该jar,而是通过systemPath指定该jar的路径。
	
	import: 用于一个dependencyManagement对另一个dependencyManagement的继承。

##### “Mvn Clean Package”命令进行项目打包，请问该命令执行了哪些动作来完成该任务？

```
maven-clean-plugin:clean

maven-resources-plugin:resources

maven-compile-plugin:compile

mavne-resources-plugin:testResources

maven-compile-plugin:testCompile

maven-jar-plugin:jar
```

##### Java设计原则：

```
1.不要把所有的逻辑代码写到单独的方法中，把小的逻辑代码独立出来，要易读，可复用

2.写类，写方法，写功能时，应考虑其移植性，复用性：防止一次性代码！

3.找出应用中相同之处，且不容易发生变化的东西，把它们抽取到抽象类中，让子类去继承它们；
```

##### Java设计模式：

1.单例模式

```
是一种常用的软件设计模式，在它的核心结构中值包含一个被称为单例的特殊类。一个类只有一个实例，即一个类只有一个对象实例。
```

2.工厂模式

```
根据需要返回我们的对象。应用比较熟悉的场景就是spring配置文件了。
```

3.适配器模式

```
将一个类的接口转换成客户希望的另外一个接口。通俗地讲，就是在2个类之间做了一个衔接。比如你在调用A类的doSomething方法，实际上内部实现调用了B类的doSomething方法。
```

4.代理模式

```
它的定义是：代理模式给某一个对象提供一个代理对象，并由代理对象控制对原对象的引用。Java的反射机制，很多地方就用了代理模式来实现。
```

5.监听模式

```
当事件源触发某种行为，会自动执行事件监听器里面相应的方法。
Java监听模式右三个部分组成：事件源、事件对象、事件监听器。
```

6.装饰器模式

```
简单说就是不改变现有类的结构前提下，扩展它的功能。用别的类来增加原有类的功能。
```

##### 数据库各种连接：

1.内连接

内连接就是两张表中都包含的数据，因为部门表包含了员工表，所以内连接就是上图中绿色部分

```
SELECT * FROM tbl_dept a INNER JOIN tbl_emp b ON a.id = b.deptId;
```

2.左外连接

左外连接就是查询join左边表中的所有数据，并且把join右边表中对应的数据查询出来

```
SELECT * FROM tbl_dept a LEFT JOIN tbl_emp b ON a.id=b.deptId;
```

3.左连接

其实就是在左外连接在后面加了一个where条件，查询只存在于join左边表的内容

```
SELECT * FROM tbl_dept a LEFT JOIN tbl_emp b ON a.id=b.deptId WHERE b.deptId IS NULL;
```

4.全连接

```
SELECT * FROM tbl_dept a RIGHT JOIN tbl_emp b ON a.id=b.deptId 
UNION 
SELECT * FROM tbl_dept a LEFT JOIN tbl_emp b ON a.id=b.deptId;
```

5.--两张表中都没有同时出现的数据集

```
SELECT * FROM tbl_dept a RIGHT JOIN tbl_emp b ON a.id=b.deptId WHERE a.id IS NULL
UNION 
SELECT * FROM tbl_dept a LEFT JOIN tbl_emp b ON a.id=b.deptId  WHERE b.deptId IS NULL;
```

##### 三个范式(通俗地理解是够用的理解，并不是最科学最准确的理解)： 

   	

```
   第一范式：1NF是对属性的原子性约束，要求属性具有原子性，不可再分解；

　　第二范式：2NF是对记录的惟一性约束，要求记录有惟一标识，即实体的惟一性

　　第三范式：3NF是对字段冗余性的约束，即任何字段不能由其他字段派生出来，它要求字段没有冗余
```



##### 范式优点

```
1）范式化的数据库更新起来更加快；

2）范式化之后，只有很少的重复数据，只需要修改更少的数据；

3）范式化的表更小，可以在内存中执行；

4）很少的冗余数据，在查询的时候需要更少的distinct或者group by语句。
```



##### 范式缺点

```
1）范式化的表，在查询的时候经常需要很多的关联，因为单独一个表内不存在冗余和重复数据。这导致，稍微复杂一些的查询语句在查询范式的schema上都可能需要较多次的关联。这会增加让查询的代价，也可能使一些索引策略无效。因为范式化将列存放在不同的表中，而这些列在一个表中本可以属于同一个索引。
```



##### 反范式的优点：

```
1）可以避免关联，因为所有的数据几乎都可以在一张表上显示；
2）可以设计有效的索引；
```



##### 反范式的缺点：

```
表格内的冗余较多，删除数据时候会造成表有些有用的信息丢失。
所以在设计数据库时，要注意混用范式化和反范式化。
```

##### 数据库设计原则

```
1.适度冗余， 让query尽量减少join

2.大字段垂直分拆

3.大表水平分拆

4.选择合适的数据类型
```

