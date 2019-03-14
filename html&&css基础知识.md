### 1.XHTML和HTML有什么区别

HTML是一种基本的WEB网页设计语言，XHTML是一个基于XMl的置标语言

最主要的不同

XHTML元素必须被正确地嵌套。

XHTML元素必须被关闭

标签名必须用小写字母

XHTMl文档必须拥有根元素

### 2.什么是语义化的HTML？

直观的认识标签对于搜索引擎的抓取有好处，用正确的标签做正确的事情！

HTML语义化就是让页面的内容结构化，便于对浏览器，搜索引擎解析；

在没有样式css情况下也以一种文档格式显示，并且是容易阅读。搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重，利于SEO。

在阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

### 2（1）、简述一下你对HTML语义化的理解？

1、用正确的标签做正确的事情。

2、html语义化让页面的内容结构化，结构更清晰，便于对浏览器，搜索引擎解析；

3、即使在没有样式CSS情况下也以一种文档格式显示，并且是容易阅读的；

4、搜索引擎的爬虫也依赖于HTML标记确定上下文和各个关键字的权重，利用SEO;

5、使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

### 3.常见的浏览器内核有哪些？

Trident（踹den特）内核：IE,MaxThon,TT,The Word,360,搜狗浏览器等。[又称为MSHTML]

Gecko（该gou)内核：Netscape6及以上版本，FF,MozillaSuite/SeaMonkey等；

Presto(破ruai四逃）内核：Opera7及以上。[Opera内核原为：Presto，现为：Blink]

Webkit内核：Safari,Chrome等。[Chrome的:Blink(Webkit的分支)]

### 3(1).常见哪几种浏览器测试？有哪些内核（Layout Engine）？

浏览器：IE、Chrome、FireFox、Safari、Opera

内核：Trident、Gecko、Presto、Webkit

### 5.请描述一下cookies,sessionStorage（会话存储）和localStrorage（本地存储）的区别？

cookie在浏览器和服务器间来回传递。sessionStorage和localStorage不会；

sessionStorage和localStorage的存储空间更大；

sessionStorage和localStorage有更多丰富易用的接口；

sessionStorage和localStorage各自独立的存储空间；

### 5、（1）请描述一下cookies、sessionStorage和localStorage区别？

cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）。

cookie数据始终在同源的http请求中携带（即使不需要），即会在浏览器和服务器间来回传递。

sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存
`存储大小：`

cookie数据大小不能超过4K。

sessionStorage和localStorage虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。
`有期时间：`

localStorage：存储持久数据，浏览器关闭后数据不丢失除非主动删除数据；

sessionStorage：数据在当前浏览器窗口关闭后自动删除

cookie：设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭

### 6.如何实现浏览器内多个标签页之间的通信？

调用localstorage,cookies等本地存储方式

WebSocket、SharedWorker

localstroge另一个浏览器上下文被添加、删除或修改时，它都会触发一个事件，我们通过监听事件，控制它的值来进行页面信息通信。

注意quirks:Safari在无痕迹模式下设置localstorge值抛出QuotExceededError的异常。

### 7.HTML5为什么只需要写！DOCTYPE HTML？

HTMl5不基于SGML,因此不需要对DTD进行引用，但是需要doctype来规范浏览器的行为(让浏览器按照它们应该的方式来运行)；

### 8.Doctype作用？标准模式与兼容模式各种什么区别？

告知浏览器的解析器用什么文档标准解析这个文档。doctype不存在或格式不正确会导致文档以兼容模式呈现。

标准模式的排版和JS运作模式都是该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式来显示，模拟老式浏览器的行为以防止站点无法工作

### 9.Doctype？严格模式与混杂模式如何触发这两种模式，区分它们有何意义？

用于声明文档使用哪种规范（html/Xhtml）一般为严格过渡基于框架的html文档。

加入XML声明可触发

### html document是干嘛的？

HTML即：超文本标记语言，标准通用标记语言的一个应用，“超文本”就是指页面内可以包含图片、链接、甚至音乐、程序等非文字元素。

HTML Document即：HTML Document对象，每个载入浏览器的HTML文档都会成为Document对象

由于Document对象是window对象的一部分，所以可通过window.document属性对其进行访问。

### html5哪些操作可以SEO优化

title标签；meta标签；header标签；footer标签

元标签（meta标签）；导航标签（nav标签）；文章标签（article标签）；左或右侧标签（aside标签）

### 12、css盒模型有哪些及区别content-box border-box padding-box

#### Q1

IE盒子模型box-sizing:border-box;（怪异模式）

W3C标准盒子模型 box-sizing:content-box;（标准模式）默认模式

#### Q2

content-box:这是默认样式指定CSS标准。测量width和height属性只包括的内容，但不是border, margin, 或者 padding。

padding-box:width和height属性包括padding的大小，不包括border和margin

border-box:width和height属性包括padding和border，但不是margin。这是盒模型的文档时，Internet Explorer使用Quirks模式。

content-box不包含padding，border-box包含padding。所以如果你设置的大小是一样的，content-box看起来，会比border-box大

### 13、行内元素和块状元素的区别？行内快元素的兼容性使用？（IE8以下）

行内元素：会在水平方向排列，不能包含快级元素，设置width无效，height无效（可以设置line-height），margin上下无效，padding上下无效

块级元素：各占据一行，垂直方向排列。从新行开始结束接着一个断行

兼容性：display:inline-block;*display:inline;*zoom:1;

### 14.页面导入样式时，使用link和@import有什么区别？

1.link属于HTML标签，除了加载CSS外，还能用于定义RSS，定义rel连接属性等作用；而@import是CSS提供，只能加载CSS;

2.页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载；import是CSS2.1提出的，只在IE5以上才能被识别，而link是HTML标签，无兼容问题

### 14(1).css引入的方式有哪些？link和@import的区别是？

内联，内嵌，外链，导入

区别：同时加载，

前者无兼容性，后者css2.1以下浏览器不支持

link支持使用javascript改变样式，后者不可。

### 15、介绍以下你对浏览器内核的理解？

1、主要分成两部分：渲染引擎（layout engineer或Rendering Engine）和JS引擎。

2、渲染引擎：负责取得网页的内容（HTML、XML、图像等等）、整理讯息（例如加入CSS等）、以及计算网页的显示方式、然后会输出至显示器或打印机。浏览器的内核的不同对于网页的语法解释会有不同、所以渲染的效果也不相同。所有网页浏览器、电子邮件客户端以及其他需要编辑、显示网络内容的应用程序都需要内核

3、JS引擎则：解析和执行javascript来实现网页的动态效果。

### 16、box-sizing常用的属性有哪些？分别有什么作用？

box-sizing：content-box|border-box|inherit

content-box：宽度和高度分别应用到元素的内容框。

### 17、清楚浮动有哪些方式？比较好的方式是哪一种

1、父级div定义height。

2、结尾处加空div标签clear：both。

3、父级div定义伪类：after和zoom。

4、父级div定义overflow：hidden。

5、父级div定义overflow：auto。

6、父级div也浮动，需要定义宽度。

7、父级div定义display：table。

8、结尾处加br标签clear:both。

比较好的是第3种，好多网站都这样用

### 19、iframe的作用？

#### 用法

1、iframe是用来在网页中插入第三方页面，早期的页面使用iframe主要是用于导航栏这种很多页面都相同的部分，这样在切换页面的时候避免重复下载。

#### 优点

1、便于修改，模拟分离，像一些信息管理系统会用到。

2、但现在基本不推荐使用。除非特殊需要，一般不推荐使用。

### 缺点

1、iframe的创建比一般的DOM元素慢了1-2个数量级

2、iframe标签会阻塞页面的的加载，如果页面的onload事件不能及时触发，会让用户觉得网页加载很慢，用户体验不好，在Safari和Chrome中可以通过js动态设置iframe的src属性来避免阻塞。

3、iframe对于SEO不友好，替换方案一般就是动态语言的Incude机制和ajax动态填充内容等。

### 20、box-sizing、transition、translate分别是什么？

1、box-sizing:用来指定模型的大小的计算方式。主要分为border-box(从边框固定盒子大小)、content-box(从内容固定盒子大小)两种计算方式。

2、transition:当前元素只要有"属性"发生变化时，可以平滑的进行过渡。通过transition-propety设置过渡属性；transition-duration设置过渡时间；transition-timing-function设置过渡速度；transition-delay设置过渡延时。

3、translate：通过移动改变元素的位置；有x,y,z三个属性

### 21、选择器优先级是怎样的？

1、！important>行内样式>id选择器>类选择器>标签选择器>通配符>继承

### 22、有一个导航栏在Chrome里面样式完好？在IE里文字都聚到一起了，是哪个兼容性问题？

用了display：flex属性，在IE10以下都是无效的。

### 23.CSS实现垂直水平居中

```
HTML结构：
<div class="wrapper">
    <div class="content"></div>
</div>
CSS：
.wrapper{position:relative;}
.content{
    background-color:#6699FF;
    width:200px;
    height:200px;
    position: absolute;        //父元素需要相对定位
    top: 50%;
    left: 50%;
    margin-top:-100px ;   //二分之一的height，width
    margin-left: -100px;
}
```

### 24.display有哪些值？说明它们的作用。

block 块类型。默认宽度为父元素宽度，可设置宽高，换行显示。

none 缺省值。像行内元素类型一样显示。

inline 行内元素类型。默认宽度为内容宽度，不可设置宽高，同行显示。

inline-block 默认宽度为内容宽度，可以设置宽高，同行显示。

list-item 像块类型元素一样显示，并添加样式列表标记。

table 此元素会作为块级表格来显示。

inherit 规定应该从父元素继承display属性的值。

### 25.行内元素有哪些？块级元素有哪些？css的盒模型？

块级元素：div ,p,h1,form,ul,li

行内元素：span,a,label,input,img,strong,em;

css盒模型：内容，border,margin,padding;

### 26.写一下audio（奥迪哦）标签中，如何实现音乐的暂停和播放

play()开始,pause()（袍子）暂停

### 26（1）、写出video标签中预加载视频用到的属性是什么

preload（普瑞楼的）

### 27.css选择符有哪些？哪些属性可以继承？优先级算法如何计算？内联和important哪个优先级高？

标签选择符；类选择符；id选择符

id>class>标签选择

important优先级高

### 30、CSS3新特性有哪些？

1、颜色：新增RGBA、HSLA模式

2、文字阴影(text-shadow)

3、边框：圆角（border-radius）边框阴影：box-shadow

4、盒子模型：box-sizing

5、背景：background-size设置背景图片的尺寸，background-origin设置背景图片的原点，background-clip设置背景图片的裁剪区域，以“，”分隔可以设置多背景，用于自适应布局

6、渐变：linear-gradient、radial-gradient

7、过渡：transition可实现动画

8、自定义动画

9、在CSS3中唯一引入的伪元素是::selection

10、多媒体查询、多栏布局

11、border-image

12、2D转换：transform:translate(x,y)rotate(x,y)skew(x,y)scale(x,y)

13、3D转换

### 标签上title与alt属性的区别是什么？

Alt当图片不显示时，用文字代表

Title为该属性提供信息

### 32、描述css reset的作用和用途？

Reset重置浏览器的css默认属性，浏览器的品种不同，样式不同，然后重置，让他们统一。

### 33（1）、为什么要使用css sprites

css精灵 把一堆小的图片整合到一张大的图片上，减轻服务器对图片的请求数量

css sprites其实就是把网页中一些背景图片整合到一张图片文件中，再利用css的"background-image","background-position"的组合进行背景定位，这样可以减少。

很多图片请求的开销，因为请求耗时比较长；请求虽然可以并发，但是如果请求太多会给服务器增加很大的压力

### 34、在新窗口打开链接的方法是？

target:_blank

### 35、合理的页面布局中常听过结构与表现分离，那么结构是什么？表现是什么？

结构是html,表现是css

### 36、简述对Web语义化的理解？

就是让浏览器更好的读懂你写的代码，在进行HTML结构、表现、行为设计时，尽量使用语义化的标签，使程序代码简洁明了，易于进行web操作和网站SEO，方便团队的一种标准，以图实现一种“无障碍”的web开发。

### 38、请用css定义p标签，要求实现以下效果；字体颜色在IE6下为黑色（#000000）；IE7下为红色（#ff0000）;而其他浏览器下为绿色（#00ff00）

```
p{
    color:green;
    *color:blue;
    _color:black;
}
```

### 39、前端页面有哪三层构成，分别是什么？作用是什么？

结构层、表示层、行为层

结构层（structural layer）：由HTML或XHTML之类的标记语言负责创建。

表示层（presentation layer）:由css负责创建。

行为层（behaviorlayer）:负责回答“内容应该如何对事件做出反应”这一问题。这是 Javascript 语言和 DOM主宰的领域。

### 40、实现布局中间自适应宽度，左右两栏固定宽度

```
    <style>
        .box{
            display:flex;
        }
        .left{
            width: 200px;
            height: 600px;
            background:red;
        }
        .right{
            width: 200px;
            height: 600px;
            background:red;
        }
        .center{
            width: 100%;
            height:600px;
            background:green;
        }
    </style>
</head>
<body>
    <div class="box" >
        <div class="left"></div>
        <div class="center"></div>
        <div class="right"></div>
    </div>
```

### 41、如何在页面上实现一个圆形的可点击区域？

1、map+area或者svg

2、border+radius

3、纯js实现需要求一个点在不在圆上简单算法，获取鼠标坐标等等

### 42、介绍一下标准css的盒子模型？低版本IE的盒子模型有什么不同的？

1、有两种：IE盒子模型、W3c盒子模型

2、盒模型：内容(content)、填充(padding)、边界(margin)、边框(border)。

3、区别：IE的content部分把border和padding计算了进去

### 43、你如何对网站的文件和资源进行优化？期待的解决方案包括：

文件合并

文件最小化/文件压缩

使用CDN托管

缓存的使用

### 44、IE8以下版本的浏览器中盒模型有什么不同？

IE8以下浏览器的盒模型中定义的元素的宽高不包括内边剧和边距

### 45、写出几种IE6 BUG的解决方法

1、双边距BUG float引起的 使用display

2、3像素问题使用float引用的使用display:inline -3px;

3、超链接hover后点击失效，使用正确的书写顺序 link visited hover active

4、le z-index问题给父级添加position:relative

5、png 透明使用js代码改

6、min-height最小高度 ！important解决

7、select 在ie6下遮盖 使用iframe嵌套

8、为什么没有办法定义1px左右的宽度器（IE6默认的行高造成的，使用over:hidden,zoom:0.08,line-height:1px）

### 46、css选择符有哪些？哪些属性可以继承？优先级算法如何计算？内联和important哪个优先级高？

css选择符：类选择器、标签选择器、ID选择器、后代选择器（派生选择器）、群组选择器

可以继承：类选择器、标签名选择器、后代选择器（派生选择器）、群组选择器

优先级算法：

标签内直接定义：1000

ID选择器：100

类选择器：1

内联和important中，important优先级高

### 47、css的基本语句构成是？

- 选择符、属性、值