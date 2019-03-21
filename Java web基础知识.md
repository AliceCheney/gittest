##### 1.编码问题？

```
html页面：浏览器会根据<http header:content-type=text/html;  charset="UTF-8">的值来决定用什么encoding(编码)，离线的本地html要在meta中指定，不指定会采用默认的编码<meta http-equiv="Content-Type" content="text/html”; charset="UTF-8">。
```

```
Request ：request.setCharacterEncoding(“UTF-8”)应用于通过getParameter()获取字符串，只对POST有效。必须设置在servlet中getParameter()方法被调用之前，原因是：只有在第一次调用getParameter()方法时会查询encoding编码格式，后续的getParameter将不再查询编码格式。
```

```
对于GET提交，get提交的内容存在URL中，需在Tomcat的server.xml设置，在Connector标签中设置生成URI时的编码格式URIEncoding=”UTF-8”。(个人理解为 针对URI这一特殊类型数据，在server中统一设置编码格式，不管是在JSP还是Servlet中出现，都使用统一的解码方式，避免了乱码的发生)。默认为ISO8859-1。
```

```
Resopnse ：response.setContentType(“text/html”;charset=”UTF-8”)是指定HTTP响应的编码，同时指定浏览器(JSP)的显示编码，显示编码不一定在JSP中有效果，因为JSP中设置的编码格式优先级更高。
```

```
response.setCharacterEncoding(“UTF-8”)的作用是设置HTTP的响应编码，设置应在getWriter和response被提交之前。(个人理解为 此编码的设置是针对要返回的数据进行编码生成response，再返回)。
```

```
 JSP：<%@page ContentType=”text/html;charset=UTF-8”%>

<%@page pageEncoding=”charset=UTF-8”%>

以上两种编码只有一种有效，用于设置 页面的显示编码。

如果页面中使用include标签导入了其他的JSP，<%@ include file=”BB.jsp”%>设置的BB.jsp中不能再设置编码，<jsp:include page=”BB.jsp”/>设置，BB.jsp中还可以设置编码集。
```

##### 2.集合（map）list有序（存取），set无序

集合主要有vector，hashtable，array list，hashmap，stack

	vector 默认初始化容量为10，扩容为一倍扩容。比Arraylist多了同步机制，效率低，线程安全，在内存中占用连续的空间，当数据量更大时，会分配更大的空间。如果将vector定义为object类型，则可以存放任意类型，已弃用。
	
	hashtable默认初始化容量为11，也是同步的，所以线程是安全的，对整张哈希表加锁，key,value都不能为null,存储的key为对象的hashcode,已弃用。
	
	hashmap，默认初始化容量为16，不是同步的，所以线程是不安全的，key和value都可以为null

```
判断key=null;的键是否存在，应该用containsKey方法，并不能用get方法。因为get返回null，即可表示null键也可表示不存在。存储的key重新计算hash值(+salt?).

采用快速失败机制(Fail-Fast)，
```

	hashset内部使用map保存数据，即将hashset的数据hashcode做key，添加一次需要比较两次，hashcode、equals
	
	**ArrayList** 实现了List接口，内部基于数组结构实现存储，**随机访问速度快**。默认初始化容量为10，扩容为1.5倍扩容。
	
	ArrayList在删除元素后，剩余的元素会向前移动，所以下标会变

**LinkedList**实现了List接口，内部基于链表结构实现存储，**增删快。**

remove()方法调用的是remove(int index)；而不是remove(Object o); 因此删除index索引出元素。

AbstractSet类实现了set接口，HashSet继承AbstractSet类，同时实现set接口

###### HashTable 和 HashMap的区别：

1.继承不同和：

HashTable 继承 Dictionary

HashMap 继承 AbstractMap

2.同步问题

HashTable 中方法是同步的，而HashMap中方法在缺省的情况下是同步的，需要自己添加同步

3) null 的问题：

HashTable中，key、value都不允许出现null值，

 HashMap中，null可以作为键，这样的键只有一个，可以有多个value=null,需要自己增加同步。

 4.遍历方式不同：

 HashTable、HashMap都使用了Iterator，而由于历史原因，HashTable还使用了Enumeration（例举）的方式，

5) 哈希值不同：

HashTable直接使用对象的hashcode，而HashMap重新计算hash值。

6) 初始化和扩容：

   HashTable和HashMap内部实现都是数组初始化大小和扩容方式。

   HashTable的Hash数组默认为11，扩容为old*2+1;

   HashMap的hash数组默认值为16，而且一定是2的指数扩容。

##### 3.异常分类：

异常指程序运行时(非编译)所发生的错误，jvm将错误以异常形式抛出。

error类主要是运行时，逻辑错误导致的，jvm停止，

exception表示可恢复异常，包括检查性异常和运行性异常

检查性异常多包括IO异常、SQl异常，多发生在编译期，通过try/catch捕捉。

运行性异常一般都上抛，直到遇到处理代码，多线程用run()抛出，单线程用main()抛出。



##### String类是final类，

成员方法默认为final方法，底层是char()数组来保存，没有“/0”

对String对象的任何改变都不会影响到原对象。

当代码中出现字面量形式创建字符串对象时，JVM首先会对字面量进行检查，如果常量池存在相同内容引用，则将引用返回，否则新的字符串对象被创建，然后将对象放到字符串常量池，并返回此引用。

方法：

(1) String.toUpperCase();==>转换为大写，有返回值

(2) string.replace(‘f’,’F’); ==>用F替代f,无返回值(参数为char和charSequence)

(3) string.replaceAll(‘regex’,’’);==>all 匹配的是正则表达式(.匹配各个字符)

(4) string.equals()==>String 重写了Object类的方法

##### Servlet 相关：

service 方法是在servlet生命周期中的服务器，默认在HttpServlet类中实现，根据Http请求方法，将请求分发到doGet、doPost等方法实现。

##### 4.request、response

 request.getParameter(“xxx”);获取http提交的数据，返回值为字符串。

  response.getAttibute(“xxx”);获取request域中存在的对象，返回对象。

##### 5.转发与重定向

  forward(请求转发):发送一次请求，将表单数据或封装到url中的数据一并转发到新页面。

 

  redirect(重定向)：发送两次请求，一次请求会收到302状态码，第二次请求收到新地址。

1)response.setStatus(302);response.addHeader("Location","URL");

2)response.sendRedirect("URL");

###### 1)从地址栏显示看：

forward是服务器请求资源，服务器直接访问目标中的URI获取响应，经响应发送给浏览器。

redirect服务器发送一个状态码302，告诉浏览器去请求地址(location)，url可以是其他应用。

###### 2)从数据共享来说：

  forward转发页面和转发到的页面可以共享request中的内容。redirect不能共享

###### 3)从运用应用方面：

 forward 用于登录注册页面

redirect 用于注销登录返回主页面或跳转其他网站，不再使用response输出数据，否则会异常。

###### 4)从效率看

forward 效率高

redirect 效率低

##### 6.参数传递

  基本类型传递值，引用类型传递地址，在方法中，可根据地址改变引用类型的成员变量值。  

值传递不可以改变原变量的内容和地址(仅副本做局部变量)。

  引用传递不可以改变原变量地址，但可通过引用改变值。