**JavaEE开发**

基于JavaWeb层面开发:

使用Java语言开发的基于浏览器（互联网）运行的项目

# **1.** 软件架构

1.   C/S  Client/Server  客户端/服务器

(1) 优点：用户体验好

(2) 缺点：开发、测试、运行、维护.....

2.   B/S  Browser/Server  浏览器/服务器

只需要有浏览器即可运行项目

(1) 优点：开发、测试、运行、维护比较方便

(2) 缺点：用户体验没有C/S架构好，对硬件要求比较高

 

浏览器资源：

静态资源：图片、音频、视频....

动态资源：需要结合服务器来展示

用户访问根据自己的特点，时间看到的效果不同

# **2.** 静态资源

HTML:用来展示文本内容的技术

CSS:用来做样式的技术

JavaScript:用来做特效的技术 （前台验证、前后交互）

# **3.** HTML

见html讲义

# **4.** ***\*JavaScript\***

JavaScript（简称“JS”） 是一种具有函数优先的轻量级，解释型或即时编译型的[编程语言](https://baike.baidu.com/item/编程语言/9845131)。虽然它是作为开发[Web](https://baike.baidu.com/item/Web/150564)页面的[脚本语言](https://baike.baidu.com/item/脚本语言/1379708)而出名，但是它也被用到了很多非[浏览器](https://baike.baidu.com/item/浏览器/213911)环境中，JavaScript 基于原型编程、多范式的动态脚本语言，并且支持面向对象、命令式和声明式（如[函数](https://baike.baidu.com/item/函数/301912)式编程）风格。

## 4.1. **JS功能**

1.嵌入[动态文本](https://baike.baidu.com/item/动态文本)于HTML页面。

2.对浏览器事件做出响应。

3.读写[HTML元素](https://baike.baidu.com/item/HTML元素)。 	

4.在数据被提交到服务器之前验证数据(正则表达式)。

5.检测访客的浏览器信息。 控制[cookies](https://baike.baidu.com/item/cookies/187064)，包括创建和修改等。 

6.基于Java技术进行服务器端编程。

  教程见js讲义

# **5.** ***\*JavaWEB开发入门\****

## 5.1. **web开发入门**

WEB应用程序指供浏览器访问的程序，通常也简称为web应用。

Web应用开发好后，若想供外界访问，需要把web应用所在目录交给***\*web服务器管理\*******\*（Web容器）\****

## 5.2. **web服务器常见服务器简介**

***\*WebLogic\****

WebLogic是用于开发、集成、部署和管理大型分布式Web应用、网络应用和数据库应用的Java应用服务器。

***\*WebSphere\****

WebSphere Application Server 是一种功能完善、开放的Web应用程序服务器，是IBM公司电子商务计划的核心部分，它是基于 Java 的应用环境，用于建立、部署和管理 Internet 和 Intranet Web 应用程序。

***\*Tomcat\****

Tomcat是一个实现了JAVA EE标准的最小的WEB服务器。因为Tomcat 技术先进、性能稳定，而且开源免费，因而深受Java 爱好者的喜爱并得到了部分软件开发商的认可，成为目前比较流行的Web 应用服务器。

***\*IIS\****

Microsoft的Web服务器产品为Internet Information Services （IIS），IIS 是允许在公共Intranet或Internet上发布信息的Web服务器。

 

Web服务器：Web服务器是指驻留于因特网上某种类型计算机的程序，是可以向发出请求的浏览器提供文档的程序。

服务器：安装了web服务器的电脑

 

## 5.3. **Tomcat的安装与启动**

解压apache-tomcat-7.0.40.zip到指定文件夹下面

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps1.jpg) 

 

bin目录:

启动命令：startup.bat

停止命令：shutdown.bat 或者点击cmd窗口的关闭按钮

启动服务器相关问题：

启动报错：端口号被占用（2种解决办法）

1.释放被占用的端口号 netstat -ano  -----> pid  任务管理器

2.改变自己的端口号：

找到tomcat根目录，找到conf文件夹，找到server.xml

<Connector port="8888" protocol="HTTP/1.1"

​        connectionTimeout="20000"

​        redirectPort="8443" />

启动一闪而过：

找到JDK环境变量配置JAVA_HOME 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps2.jpg) 

## 5.4. **http协议简介以及其请求和响应**

HTTP是hypertext transfer protocol（超文本传输协议）的简写，它是TCP/IP协议的一个应用层协议，用于定义WEB浏览器与WEB服务器之间交换数据的过程。客户端连上web服务器后，若想获得web服务器中的某个web资源，需遵守一定的通讯格式，HTTP协议用于定义客户端与web服务器通迅的格式。

 

HTTP协议的版本：HTTP/1.0、HTTP/1.1

​    在HTTP1.0协议中，客户端与web服务器建立连接后，只能获得一个web资源。

　　  在HTTP1.1协议，允许客户端与web服务器建立连接后，在一个连接上获取多个web资源。

 

 

 

请求头：

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps3.jpg) 

请求行：请求方式 请求资源 请求协议

请求（消息）头：描述浏览器信息

请求空行：用来分割请求头与请求正文

 

请求行中的GET称之为请求方式，请求方式有：

​    POST、GET、HEAD、OPTIONS、DELETE、TRACE、PUT

常用的有： GET（默认）、 POST

POST和GET区别

GET方式，则可以在请求的URL地址后以?的形式带上交给服务器的数据，多个数据之间以&进行分隔，在URL地址后附带的参数是有限制的，其数据容量通常不能超过1K。

a链接、form表单默认为get提交、浏览器地址栏刷新、jQuery中ajax也有get请求

POST方式，则可以在请求的实体内容中向服务器发送数据，Post方式的特点：传送的数据量无限制。

form表单post提交、jQuery中ajax也有post请求

请求头各项的含义：

accept:浏览器通过这个头告诉服务器，它所支持的数据类型

​	Accept-Charset: 浏览器通过这个头告诉服务器，它支持哪种字符集

​	Accept-Encoding：浏览器通过这个头告诉服务器，支持的压缩格式

​	Accept-Language：浏览器通过这个头告诉服务器，它的语言环境

Host：浏览器通过这个头告诉服务器，想访问哪台主机

​	If-Modified-Since: 浏览器通过这个头告诉服务器，缓存数据的时间

​	Referer：浏览器通过这个头告诉服务器，客户机是哪个页面来的 防盗链

​	Connection：浏览器通过这个头告诉服务器，请求完后是断开链接还是何持链接

 

 

处理响应；

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps4.jpg) 

响应行：协议版本 响应状态码

响应头：服务器信息

响应空行：用来分割响应头与响应正文

响应头解释：

Location: 服务器通过这个头，来告诉浏览器跳到哪里

·Server：服务器通过这个头，告诉浏览器服务器的型号

·Content-Encoding：服务器通过这个头，告诉浏览器，数据的压缩格式

·Content-Length: 服务器通过这个头，告诉浏览器回送数据的长度

·Content-Language: 服务器通过这个头，告诉浏览器语言环境

·Content-Type：服务器通过这个头，告诉浏览器回送数据的类型

·Refresh：服务器通过这个头，告诉浏览器定时刷新

·Content-Disposition: 服务器通过这个头，告诉浏览器以下载方式打数据

·Transfer-Encoding：服务器通过这个头，告诉浏览器数据是以分块方式回送的

·Expires: -1 控制浏览器不要缓存

 

 

 

 

响应状态码：

1XX：正在连接...

2XX :200 成功状态

3XX：304 转发

4XX：404 目标资源不存在  405 

5XX：500 服务器内部出错

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps5.jpg) 

处理请求，返回响应======控制器 	Servlet  Server Applet

 

## 5.5. **搭建第一个控制器**

控制器是一个标准   Servlet接口

\1. 先创建MyServlet类

***\*public class\**** MyServlet

 

\2. 实现Servlet接口

***\*public class\**** MyServlet ***\*implements\**** Servlet

 

\3. 重写接口中的抽象方法

初始化方法init调用方法service销毁方法destroy

 

\4. 配置控制器

**<!--****配置****MyServlet-->**<***\*servlet\****>  <***\*servlet-name\****>MyServlet</***\*servlet-name\****>  <***\*servlet-class\****>com.zx.servlet.MyServlet</***\*servlet-class\****>**<!--****设置服务器启动时初始化** **-->**  <***\*load-on-startup\****>1</***\*load-on-startup\****></***\*servlet\****><***\*servlet-mapping\****>  <***\*servlet-name\****>MyServlet</***\*servlet-name\****>  <***\*url-pattern\****>/MyServlet</***\*url-pattern\****></***\*servlet-mapping\****>

 

## 5.6. **Servlet运行过程**

Servlet程序是由WEB服务器调用，web服务器收到客户端的Servlet访问请求后：

　　①Web服务器首先检查是否已经装载并创建了该Servlet的实例对象。如果是，则直接执行第④步，否则，执行第②步。

　　②装载并创建该Servlet的一个实例对象。 

　　③调用Servlet实例对象的init()方法。

　　④创建一个用于封装HTTP请求消息的HttpServletRequest对象和一个代表HTTP响应消息的HttpServletResponse对象，然后调用Servlet的service()方法并将请求和响应对象作为参数传递进去。

　　⑤WEB应用程序被停止或重新启动之前，Servlet引擎将卸载Servlet，并在卸载之前调用Servlet的destroy()方法。 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps6.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps7.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps8.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps9.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps10.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps11.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps12.jpg) 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps13.jpg) 

## 5.7. **Servlet生命周期**

服务器上

创建阶段：tomcat根据请求来创建一个servlet对象。

Tomcat会根据URL来找到servlet虚拟路径，通过web.xml找到对应的serlvet类，tomcat会分配一块内存空间作为servlet容器来存放创建出来的这些servlet对象，

（创建是通过Class cla=class.forName(“类名”)，cla.newInstance();创建servlet对象。）

初始阶段：调用init方法初始化servlet对象，且只会被调用一次

调用阶段：自动调用service方法，响应其所有方法，可以被调用多次

销毁阶段：调用destroy方法（通过Tomcat的reload/关闭tomcat/关闭计算机）；

Servlet的每次提供服务实际都是调用service方法。只不过service方法内部会根据客户端的请求方式再决定调用doGet还是doPost。

我们来看一个图:

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps14.png) 

### 5.7.1. **1** **初始化阶段**

在以下时刻Servlet容器装载Servlet

1.Servlet启动时自动装载某些Servlet，实现方法：在web.xml文件中的<Servlet></Servlet>中添加<load-on-startup>1</load-on-startup>

2.在Servlet容器启动后，客户端首次向Servlet发送请求

3.Servlet类文件被更新，重新装载Servlet

Servlet被装载后，Servlet容器创建一个Servlet实例调用Servlet的init方法进行初始化，在整个生命周期中，init方法只会被调用一次

 

例:获取初始化参数及启动服务器就执行的方法的配置(ServletConfig)

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps15.jpg) 

web.xml

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps16.jpg) 

### 5.7.2. **2** **调用****阶段**

对于客户的请求到达Servlet，Servlet容器会创建特定于这个请求的ServletRequest对象和ServletResponse对象，然后会调用Servlet的service方法。然后service方法从ServletRequest对象中获取客户的请求信息，处理该请求，并通过ServletResponse对象向客户端返回响应信息。

### 5.7.3. **3** **销毁****阶段**

当web应用被终止，或者Servlet容器终止运行，或者Servlet容器重新装载Servlet，Servlet容器会调用Servlet的destroy方法，去释放Servlet所占用的资源。

调用destroy方法的三种方式：通过Tomcat的Reload方式调用destroy，关闭Tomcat服务，关闭计算机。

 

 

## 5.8. **Servlet接口实现类**

　　Servlet接口SUN公司定义了两个默认实现类，分别为：GenericServlet、HttpServlet。

HttpServlet指能够处理HTTP请求的servlet，它在原有Servlet接口上添加了一些与HTTP协议处理方法，它比Servlet接口的功能更为强大。因此开发人员在编写Servlet时，通常应继承这个类，而避免直接去实现Servlet接口。

java提供了一个servlet接口，这个接口里面有3个方法：Init()、Service()、Destroy()。

​	GenericServlet抽象类实现了servlet接口，实现了其中Init()和Destroy()，service()没有实现。

　　HttpServlet在实现Servlet接口时，覆写了service方法，该方法体内的代码会自动判断用户的请求方式，如为GET请求，则调用HttpServlet的doGet方法，如为Post请求，则调用doPost方法。因此，开发人员在编写Servlet时，通常只需要覆写doGet或doPost方法，而不要去覆写service方法。

步骤：

\1. 创建web工程

\2. Src下创建类HelloServlet.java,并继承抽象类HttpServlet

\3. 书写doGet方法

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps17.jpg) 

\4. 在web.xml中配置

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps18.jpg) 

\5. 部署项目到tomcat，启动服务器

\6. 在浏览器输入地址来访问到我们项目中的这个方法内打印出语句：

http://localhost:8080/项目名/helloServlet

 

多个servlet配置会繁琐且多变，通常我们不采用web.xml的配置，而是在servlet类上面使用注解的方式配置，简单、高效、快捷、方便。

​	@WebServlet(***\*"/test"\****)

 

### 5.8.1. **5.5、Servlet的线程安全问题****（****选修****）**

　　当多个客户端并发访问同一个Servlet时，web服务器会为每一个客户端的访问请求创建一个线程，并在这个线程上调用Servlet的service方法，因此service方法内如果访问了同一个资源的话，就有可能引发线程安全问题。例如下面的代码：

不存在线程安全问题的代码：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps19.jpg)](javascript:void(0);)

 1 package gacl.servlet.study;

 2 

 3 import java.io.IOException;

 4 

 5 import javax.servlet.ServletException;

 6 import javax.servlet.http.HttpServlet;

 7 import javax.servlet.http.HttpServletRequest;

 8 import javax.servlet.http.HttpServletResponse;

 9 

10 public class ServletDemo3 extends HttpServlet {

11 

12   

13   public void doGet(HttpServletRequest request, HttpServletResponse response)

14       throws ServletException, IOException {

15     

16     /**

17     * 当多线程并发访问这个方法里面的代码时，会存在线程安全问题吗

18     * i变量被多个线程并发访问，但是没有线程安全问题，因为i是doGet方法里面的局部变量，

19     * 当有多个线程并发访问doGet方法时，每一个线程里面都有自己的i变量，

20     * 各个线程操作的都是自己的i变量，所以不存在线程安全问题

21     * 多线程并发访问某一个方法的时候，如果在方法内部定义了一些资源(变量，集合等)

22     * 那么每一个线程都有这些东西，所以就不存在线程安全问题了

23     */

24     int i=1;

25     i++;

26     response.getWriter().write(i);

27   }

28 

29   public void doPost(HttpServletRequest request, HttpServletResponse response)

30       throws ServletException, IOException {

31     doGet(request, response);

32   }

33 

34 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps20.jpg)](javascript:void(0);)

存在线程安全问题的代码：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps21.jpg)](javascript:void(0);)

 1 package gacl.servlet.study;

 2 

 3 import java.io.IOException;

 4 

 5 import javax.servlet.ServletException;

 6 import javax.servlet.http.HttpServlet;

 7 import javax.servlet.http.HttpServletRequest;

 8 import javax.servlet.http.HttpServletResponse;

 9 

10 public class ServletDemo3 extends HttpServlet {

11 

12   int i=1;

13   public void doGet(HttpServletRequest request, HttpServletResponse response)

14       throws ServletException, IOException {

15     

16     i++;

17     try {

18       Thread.sleep(1000*4);

19     } catch (InterruptedException e) {

20       e.printStackTrace();

21     }

22     response.getWriter().write(i+"");

23   }

24 

25   public void doPost(HttpServletRequest request, HttpServletResponse response)

26       throws ServletException, IOException {

27     doGet(request, response);

28   }

29 

30 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps22.jpg)](javascript:void(0);)

　　把i定义成全局变量，当多个线程并发访问变量i时，就会存在线程安全问题了，如下图所示：同时开启两个浏览器模拟并发访问同一个Servlet，本来正常来说，第一个浏览器应该看到2，而第二个浏览器应该看到3的，结果两个浏览器都看到了3，这就不正常。

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps23.jpg)

　　线程安全问题只存在多个线程并发操作同一个资源的情况下，所以在编写Servlet的时候，如果并发访问某一个资源(变量，集合等)，就会存在线程安全问题，那么该如何解决这个问题呢？

先看看下面的代码：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps24.jpg)](javascript:void(0);)

 1 package gacl.servlet.study;

 2 

 3 import java.io.IOException;

 4 

 5 import javax.servlet.ServletException;

 6 import javax.servlet.http.HttpServlet;

 7 import javax.servlet.http.HttpServletRequest;

 8 import javax.servlet.http.HttpServletResponse;

 9 

10 

11 public class ServletDemo3 extends HttpServlet {

12 

13   int i=1;

14   public void doGet(HttpServletRequest request, HttpServletResponse response)

15       throws ServletException, IOException {

16     /**

17     * 加了synchronized后，并发访问i时就不存在线程安全问题了，

18     * 为什么加了synchronized后就没有线程安全问题了呢？

19     * 假如现在有一个线程访问Servlet对象，那么它就先拿到了Servlet对象的那把锁

20     * 等到它执行完之后才会把锁还给Servlet对象，由于是它先拿到了Servlet对象的那把锁，

21     * 所以当有别的线程来访问这个Servlet对象时，由于锁已经被之前的线程拿走了，后面的线程只能排队等候了

22     * 

23     */

24     synchronized (this) {//在java中，每一个对象都有一把锁，这里的this指的就是Servlet对象

25       i++;

26       try {

27         Thread.sleep(1000*4);

28       } catch (InterruptedException e) {

29         e.printStackTrace();

30       }

31       response.getWriter().write(i+"");

32     }

33     

34   }

35 

36   public void doPost(HttpServletRequest request, HttpServletResponse response)

37       throws ServletException, IOException {

38     doGet(request, response);

39   }

40 

41 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps25.jpg)](javascript:void(0);)

　　现在这种做法是给Servlet对象加了一把锁，保证任何时候都只有一个线程在访问该Servlet对象里面的资源，这样就不存在线程安全问题了，如下图所示：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps26.jpg)

　　这种做法虽然解决了线程安全问题，但是编写Servlet却万万不能用这种方式处理线程安全问题，假如有9999个人同时访问这个Servlet，那么这9999个人必须按先后顺序排队轮流访问。

　　针对Servlet的线程安全问题，Sun公司是提供有解决方案的：***\*让Servlet去实现一个SingleThreadModel接口，如果某个Servlet实现了SingleThreadModel接口，那么Servlet引擎将以单线程模式来调用其service方法。\****

　　查看Sevlet的API可以看到，SingleThreadModel接口中没有定义任何方法和常量，***\*在Java中，把没有定义任何方法和常量的接口称之为标记接口\****，经常看到的一个最典型的标记接口就是"***\*Serializable\****"，这个接口也是没有定义任何方法和常量的，标记接口在Java中有什么用呢？主要作用就是给某个对象打上一个标志，告诉JVM，这个对象可以做什么，比如实现了"***\*Serializable\****"接口的类的对象就可以被序列化，还有一个"Cloneable"接口，这个也是一个标记接口，在默认情况下，Java中的对象是不允许被克隆的，就像现实生活中的人一样，不允许克隆，但是只要实现了"Cloneable"接口，那么对象就可以被克隆了。

　　让***\*Servlet实现了SingleThreadModel接口，\****只要在Servlet类的定义中增加实现SingleThreadModel接口的声明即可。  

　　***\*对于实现了SingleThreadModel接口的Servlet，Servlet引擎仍然支持对该Servlet的多线程并发访问，其采用的方式是产生多个Servlet实例对象，并发的每个线程分别调用一个独立的Servlet实例对象\****。

　　实现SingleThreadModel接口并不能真正解决Servlet的线程安全问题，因为Servlet引擎会创建多个Servlet实例对象，而真正意义上解决多线程安全问题是指一个Servlet实例对象被多个线程同时调用的问题。事实上，在Servlet API 2.4中，已经将SingleThreadModel标记为Deprecated（过时的）。 

 

## 5.9. **工具开发Servlet**

Idea  MyEclipse Eclipse 工具不同开发方式步骤不同，先阶段95%以上都是在用idea开发。所以只学idea的方式，若遇上特殊开发工具，自行百度即可。

 

## 5.10. **HttpServletRequest**

　HttpServletRequest对象代表客户端的请求，当客户端通过HTTP协议访问服务器时，HTTP请求头中的所有信息都封装在这个对象中，通过这个对象提供的方法，可以获得客户端请求的所有信息。

 

以下是Request常用方法

### 5.10.1. **获得客户机信息**

　　***\*getRequestURL方法返回客户端发出请求时的完整URL。\****

　　***\*getRequestURI方法返回请求行中的资源名部分。\****

　　***\*getQueryString 方法返回请求行中的参数部分。\****

　　getPathInfo方法返回请求URL中的额外路径信息。额外路径信息是请求URL中的位于Servlet的路径之后和查询参数之前的内容，它以“/”开头。

　　***\*getRemoteAddr方法返回发出请求的客户机的IP地址。\****

　　getRemoteHost方法返回发出请求的客户机的完整主机名。

　　getRemotePort方法返回客户机所使用的网络端口号。

　　getLocalAddr方法返回WEB服务器的IP地址。

　　getLocalName方法返回WEB服务器的主机名。

***\*范例：通过request对象获取客户端请求信息\****

 8 /**

 9 * @author gacl

10 * 通过request对象获取客户端请求信息

11 */

12 public class RequestDemo01 extends HttpServlet {

14   public void doGet(HttpServletRequest request, HttpServletResponse response)

15       throws ServletException, IOException {

16     /**

17     * 1.获得客户机信息

18     */

19     String requestUrl = request.getRequestURL().toString();//得到请求的URL地址

20     String requestUri = request.getRequestURI();//得到请求的资源

21     String queryString = request.getQueryString();//得到请求的URL地址中附带的参数

22     String remoteAddr = request.getRemoteAddr();//得到来访者的IP地址

23     String remoteHost = request.getRemoteHost();//返回发出请求的客户机的完整主机名

24     int remotePort = request.getRemotePort();//返回客户机所使用的网络端口号。

25     String remoteUser = request.getRemoteUser();

26     String method = request.getMethod();//得到请求URL地址时使用的方法

27     String pathInfo = request.getPathInfo();

28     String localAddr = request.getLocalAddr();//获取WEB服务器的IP地址

29     String localName = request.getLocalName();//获取WEB服务器的主机名

30     response.setCharacterEncoding("UTF-8");//设置将字符以"UTF-8"编码输出到客户端浏览器

31     //通过设置响应头控制浏览器以UTF-8的编码显示数据，如果不加这句话，那么浏览器显示的将是乱码

32     response.setHeader("content-type", "text/html;charset=UTF-8");

33     PrintWriter out = response.getWriter();

34     out.write("获取到的客户机信息如下：");

35     out.write("<hr/>");

36     out.write("请求的URL地址："+requestUrl);

37     out.write("<br/>");

38     out.write("请求的资源："+requestUri);

39     out.write("<br/>");

40     out.write("请求的URL地址中附带的参数："+queryString);

41     out.write("<br/>");

42     out.write("来访者的IP地址："+remoteAddr);

43     out.write("<br/>");

44     out.write("来访者的主机名："+remoteHost);

45     out.write("<br/>");

46     out.write("使用的端口号："+remotePort);

47     out.write("<br/>");

48     out.write("remoteUser："+remoteUser);

49     out.write("<br/>");

50     out.write("请求使用的方法："+method);

51     out.write("<br/>");

52     out.write("pathInfo："+pathInfo);

53     out.write("<br/>");

54     out.write("localAddr："+localAddr);

55     out.write("<br/>");

56     out.write("localName："+localName);

57   }

58 

59   public void doPost(HttpServletRequest request, HttpServletResponse response)

60       throws ServletException, IOException {

61     doGet(request, response);

62   }

63 

64 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps27.jpg)](javascript:void(0);)

运行结果：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps28.jpg)

### 5.10.2. **获得客户机请求头**

　　getHeader(string name)方法:String 

　　getHeaders(String name)方法:Enumeration 

　　getHeaderNames()方法 

范例：***\*通过request对象获取客户端请求头信息\****

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps29.jpg)](javascript:void(0);)

 9 /**

10 * @author gacl

11 * 获取客户端请求头信息

12 * 客户端请求头：

13 * 

14 */

15 public class RequestDemo02 extends HttpServlet {

16 

17   public void doGet(HttpServletRequest request, HttpServletResponse response)

18       throws ServletException, IOException {

19     response.setCharacterEncoding("UTF-8");//设置将字符以"UTF-8"编码输出到客户端浏览器

20     //通过设置响应头控制浏览器以UTF-8的编码显示数据

21     response.setHeader("content-type", "text/html;charset=UTF-8");

22     PrintWriter out = response.getWriter();

23     Enumeration<String> reqHeadInfos = request.getHeaderNames();//获取所有的请求头

24     out.write("获取到的客户端所有的请求头信息如下：");

25     out.write("<hr/>");

26     while (reqHeadInfos.hasMoreElements()) {

27       String headName = (String) reqHeadInfos.nextElement();

28       String headValue = request.getHeader(headName);//根据请求头的名字获取对应的请求头的值

29       out.write(headName+":"+headValue);

30       out.write("<br/>");

31     }

32     out.write("<br/>");

33     out.write("获取到的客户端Accept-Encoding请求头的值：");

34     out.write("<hr/>");

35     String value = request.getHeader("Accept-Encoding");//获取Accept-Encoding请求头对应的值

36     out.write(value);

37     

38     Enumeration<String> e = request.getHeaders("Accept-Encoding");

39     while (e.hasMoreElements()) {

40       String string = (String) e.nextElement();

41       System.out.println(string);

42     }

43   }

44 

45   public void doPost(HttpServletRequest request, HttpServletResponse response)

46       throws ServletException, IOException {

47     doGet(request, response);

48   }

49 

50 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps30.jpg)](javascript:void(0);)

运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps31.jpg)

### 5.10.3. **获得客户机请求参数(客户端提交的数据)**

· getParameter(String)方法***\*(常用)\****

· getParameterValues(String name)方法***\*(常用)\****

· getParameterNames()方法(***\*不常用\****)

· getParameterMap()方法***\*(编写框架时常用)\****

***\*比如现在有如下的form表单\****

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps32.jpg)](javascript:void(0);)

 1 <%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

 2 <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">

 3 <html>

 4 <head>

 5   <title>Html的Form表单元素</title>

 6 </head>

 7 <fieldset style="width:500px;">

 8   <legend>Html的Form表单元素</legend>

 9   <!--form表单的action属性规定当提交表单时，向何处发送表单数据，method属性指明表单的提交方式，分为get和post，默认为get-->

10   <form action="${pageContext.request.contextPath}/servlet/RequestDemo03" method="post">

11   <!--输入文本框，SIZE表示显示长度，maxlength表示最多输入长度-->

12   编 号(文本框)：

13   <input type="text" name="userid" value="NO." size="2" maxlength="2"><br>

14   <!--输入文本框，通过value指定其显示的默认值-->

15   用户名(文本框)：<input type="text" name="username" value="请输入用户名"><br>

16   <!--密码框，其中所有输入的内容都以密文的形式显示-->

17   密 码(密码框)：

18   <!-- 表示的是一个空格-->

19   <input type="password" name="userpass" value="请输入密码"><br>

20   <!--单选按钮，通过checked指定默认选中，名称必须一样，其中value为真正需要的内容-->

21   性 别(单选框)：

22   <input type="radio" name="sex" value="男" checked>男 

23   <input type="radio" name="sex" value="女">女<br>

24   <!--下拉列表框，通过<option>元素指定下拉的选项-->

25   部 门(下拉框)：

26   <select name="dept">

27     <option value="技术部">技术部</option>

28     <option value="销售部" SELECTED>销售部</option>

29     <option value="财务部">财务部</option>

30   </select><br>

31   <!--复选框，可以同时选择多个选项，名称必须一样，其中value为真正需要的内容-->

32   兴 趣(复选框)： 

33   <input type="checkbox" name="inst" value="唱歌">唱歌 

34   <input type="checkbox" name="inst" value="游泳">游泳 

35   <input type="checkbox" name="inst" value="跳舞">跳舞 

36   <input type="checkbox" name="inst" value="编程" checked>编程 

37   <input type="checkbox" name="inst" value="上网">上网

38   <br>

39   <!--大文本输入框，宽度为34列，高度为5行-->

40   说 明(文本域)：

41   <textarea name="note" cols="34" rows="5">

42   </textarea>

43   <br>

44   <!--隐藏域，在页面上无法看到，专门用来传递参数或者保存参数-->

45   <input type="hidden" name="hiddenField" value="hiddenvalue"/>

46   <!--提交表单按钮，当点击提交后，所有填写的表单内容都会被传输到服务器端-->

47   <input type="submit" value="提交(提交按钮)">

48   <!--重置表单按钮，当点击重置后，所有表单恢复原始显示内容-->

49   <input type="reset" value="重置(重置按钮)">

50 </form>

51 <!--表单结束-->

52 </fieldset>

53 </body>

54 <!--完结标记-->

55 </html>

56 <!--完结标记-->

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps33.jpg)](javascript:void(0);)

　　在Form表单中填写数据，然后提交到RequestDemo03这个Servlet进行处理，填写的表单数据如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps34.jpg)

***\*在服务器端使用\*******\*getParameter方法\*******\*和\*******\*getParameterValues方法\*******\*接收表单参数，代码如下：\****

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps35.jpg)](javascript:void(0);)

 8 /**

 9 * @author gacl

10 * 获取客户端通过Form表单提交上来的参数

11 */

12 public class RequestDemo03 extends HttpServlet {

13 

14   public void doGet(HttpServletRequest request, HttpServletResponse response)

15       throws ServletException, IOException {

16     //客户端是以UTF-8编码提交表单数据的，所以需要设置服务器端以UTF-8的编码进行接收，否则对于中文数据就会产生乱码

17     request.setCharacterEncoding("UTF-8");

18     /**

19     * 编 号(文本框)：

20      <input type="text" name="userid" value="NO." size="2" maxlength="2">

21     */

22     String userid = request.***\*getParameter\****("userid");//获取填写的编号，userid是文本框的名字，<input type="text" name="userid">

23     /**

24     * 用户名(文本框)：<input type="text" name="username" value="请输入用户名">

25     */

26     String username = request.getParameter("username");//获取填写的用户名

27     /**

28     * 密 码(密码框)：<input type="password" name="userpass" value="请输入密码">

29     */

30     String userpass = request.getParameter("userpass");//获取填写的密码

31     String sex = request.getParameter("sex");//获取选中的性别

32     String dept = request.getParameter("dept");//获取选中的部门

33     //获取选中的兴趣，因为可以选中多个值，所以获取到的值是一个字符串数组，因此需要使用getParameterValues方法来获取

34     String[] insts = request.***\*getParameterValues\****("inst");

35     String note = request.getParameter("note");//获取填写的说明信息

36     String hiddenField = request.getParameter("hiddenField");//获取隐藏域的内容

37     

38     String instStr="";

39     /**

40     * 获取数组数据的技巧，可以避免insts数组为null时引发的空指针异常错误！

41     */

42     for (int i = 0; insts!=null && i < insts.length; i++) {

43       if (i == insts.length-1) {

44         instStr+=insts[i];

45       }else {

46         instStr+=insts[i]+",";

47       }

48     }

49     

50     String htmlStr = "<table>" +

51               "<tr><td>填写的编号：</td><td>{0}</td></tr>" +

52               "<tr><td>填写的用户名：</td><td>{1}</td></tr>" +

53               "<tr><td>填写的密码：</td><td>{2}</td></tr>" +

54               "<tr><td>选中的性别：</td><td>{3}</td></tr>" +

55               "<tr><td>选中的部门：</td><td>{4}</td></tr>" +

56               "<tr><td>选中的兴趣：</td><td>{5}</td></tr>" +

57               "<tr><td>填写的说明：</td><td>{6}</td></tr>" +

58               "<tr><td>隐藏域的内容：</td><td>{7}</td></tr>" +

59             "</table>";

60     htmlStr = MessageFormat.format(htmlStr, userid,username,userpass,sex,dept,instStr,note,hiddenField);

61     

62     response.setCharacterEncoding("UTF-8");//设置服务器端以UTF-8编码输出数据到客户端

63     response.setContentType("text/html;charset=UTF-8");//设置客户端浏览器以UTF-8编码解析数据

64     response.getWriter().write(htmlStr);//输出htmlStr里面的内容到客户端浏览器显示

65   }

66 

67   public void doPost(HttpServletRequest request, HttpServletResponse response)

68       throws ServletException, IOException {

69     doGet(request, response);

70   }

71 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps36.jpg)](javascript:void(0);)

运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps37.jpg)

***\*在服务器端使用\*******\*getParameterNames方法\*******\*接收表单参数，代码如下：\****

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps38.jpg)](javascript:void(0);)

1 Enumeration<String> paramNames = request.getParameterNames();//获取所有的参数名

2     while (paramNames.hasMoreElements()) {

3       String name = paramNames.nextElement();//得到参数名

4       String value = request.getParameter(name);//通过参数名获取对应的值

5       System.out.println(MessageFormat.format("{0}={1}", name,value));

6     }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps39.jpg)](javascript:void(0);)

运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps40.jpg)

***\*在服务器端使用\*******\*getParameterMap方法\*******\*接收表单参数，代码如下：\****

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps41.jpg)](javascript:void(0);)

 1 //request对象封装的参数是以Map的形式存储的

 2     Map<String, String[]> paramMap = request.getParameterMap();

 3     for(Map.Entry<String, String[]> entry :paramMap.entrySet()){

 4       String paramName = entry.getKey();

 5       String paramValue = "";

 6       String[] paramValueArr = entry.getValue();

 7       for (int i = 0; paramValueArr!=null && i < paramValueArr.length; i++) {

 8         if (i == paramValueArr.length-1) {

 9           paramValue+=paramValueArr[i];

10         }else {

11           paramValue+=paramValueArr[i]+",";

12         }

13       }

14       System.out.println(MessageFormat.format("{0}={1}", paramName,paramValue));

15     }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps42.jpg)](javascript:void(0);)

运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps43.jpg)

### 5.10.4. **以POST方式提交表单中文参数的乱码问题**

例如有如下的form表单页面：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps44.jpg)](javascript:void(0);)

 1 <%@ page language="java" import="java.util.*" pageEncoding="***\*UTF-8\****"%>

 2 

 3 <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">

 4 <html>

 5  <head>

 6   <title>request接收中文参数乱码问题</title>

 7  </head>

 8  

 9  <body>

10    <form action="<%=request.getContextPath()%>/servlet/RequestDemo04" method="***\*post\****">

11      用户名：<input type="text" name="userName"/>

12      <input type="submit" value="post方式提交表单"> 

13    </form>

14  </body>

15 </html>

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps45.jpg)](javascript:void(0);)

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps46.jpg)

　　此时在服务器端接收中文参数时就会出现中文乱码，如下所示：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps47.jpg)

### 5.10.5. **post方式提交中文数据乱码产生的原因和解决办法**

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps48.jpg)

　　可以看到，***\*之所以会产生乱码，就是因为服务器和客户端沟通的编码不一致造成的，因此解决的办法是：在客户端和服务器之间设置一个统一的编码，之后就按照此编码进行数据的传输和接收。\****

　　由于客户端是以UTF-8字符编码将表单数据传输到服务器端的，因此服务器也需要设置以UTF-8字符编码进行接收，要想完成此操作，服务器可以直接使用从ServletRequest接口继承而来的"setCharacterEncoding(charset)"方法进行统一的编码设置。修改后的代码如下：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps49.jpg)](javascript:void(0);)

1 public void doPost(HttpServletRequest request, HttpServletResponse response)

2       throws ServletException, IOException {

3     /**

4     * 客户端是以UTF-8编码传输数据到服务器端的，所以需要设置服务器端以UTF-8的编码进行接收，否则对于中文数据就会产生乱码

5     */

6     ***\*request.setCharacterEncoding("UTF-8");\****

7     String userName = request.getParameter("userName");

8     System.out.println("userName："+userName);

9 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps50.jpg)](javascript:void(0);)

　　使用***\*request.setCharacterEncoding("UTF-8");\****设置服务器以UTF-8的编码接收数据后，此时就不会产生中文乱码问题了，如下所示：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps51.jpg)

### 5.10.6. **以GET方式提交表单中文参数的乱码问题**

例如有如下的form表单页面：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps52.jpg)](javascript:void(0);)

 1 <%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

 2 

 3 <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">

 4 <html>

 5  <head>

 6   <title>request接收中文参数乱码问题</title>

 7  </head>

 8  

 9  <body>

10     <form action="${pageContext.request.contextPath}/servlet/RequestDemo04" method="***\*get\****">

11      姓名：<input type="text" name="name"/>

12      <input type="submit" value="get方式提交表单"> 

13    </form>

14  </body>

15 </html>

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps53.jpg)](javascript:void(0);)

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps54.jpg)

　　此时在服务器端接收中文参数时就会出现中文乱码，如下所示：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps55.jpg)

　　那么这个中文乱码问题又该如何解决呢，是否可以通过request.setCharacterEncoding("UTF-8");设置服务器以UTF-8的编码进行接收这种方式来解决中文乱码问题呢，注意，对于以get方式传输的中文数据，通过request.setCharacterEncoding("UTF-8");这种方式是解决不了中文乱码问题，如下所示：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps56.jpg)

### 5.10.7. **get方式提交中文数据乱码产生的原因和解决办法**

　　对于以get方式传输的数据，request即使设置了以指定的编码接收数据也是无效的(至于为什么无效我也没有弄明白)，默认的还是使用ISO8859-1这个字符编码来接收数据，客户端以UTF-8的编码传输数据到服务器端，而服务器端的request对象使用的是ISO8859-1这个字符编码来接收数据，***\*服务器和客户端沟通的编码不一致\****因此才会产生中文乱码的。解决办法：***\*在接收到数据后，先获取request对象以ISO8859-1字符编码接收到的原始数据的字节数组，然后通过字节数组以指定的编码构建字符串，解决乱码问题。\****代码如下：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps57.jpg)](javascript:void(0);)

 1 public void doGet(HttpServletRequest request, HttpServletResponse response)

 2       throws ServletException, IOException {

 3     /**

 4     *

 5     * 对于以get方式传输的数据，request即使设置了以指定的编码接收数据也是无效的，默认的还是使用ISO8859-1这个字符编码来接收数据

 6     */

 7     String name = request.getParameter("name");//***\*接收数据\****

 8     name =new String(name.getBytes("ISO8859-1"), "UTF-8") ;//***\*获取request对象以ISO8859-1字符编码接收到的原始数据的字节数组，然后通过字节数组以指定的编码构建字符串，解决乱码问题\****

 9     System.out.println("name："+name);   

10 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps58.jpg)](javascript:void(0);)

运行结果如下：

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps59.jpg) 

### 5.10.8. **以超链接形式传递中文参数的乱码问题**

　　客户端想传输数据到服务器，可以通过表单提交的形式，也可以通过超链接后面加参数的形式，例如：

1 <a href="${pageContext.request.contextPath}/servlet/RequestDemo05***\*?userName=gacl&name=徐达沛\****">点击</a>

　　点击超链接，数据是以get的方式传输到服务器的，所以接收中文数据时也会产生中文乱码问题，而解决中文乱码问题的方式与上述的以get方式提交表单中文数据乱码处理问题的方式一致，如下所示：

1 String name = request.getParameter("name");

2 name =new String(name.getBytes("ISO8859-1"), "UTF-8");

　　另外，需要提的一点就是***\*URL地址后面如果跟了中文数据，那么中文参数最好使用URL编码进行处理\****，如下所示：

1 <a href="${pageContext.request.contextPath}/servlet/RequestDemo05?userName=gacl&name=***\*<%=URLEncoder.encode("徐达沛", "UTF-8")\****%>">点击</a>

### 5.10.9. **提交中文数据乱码问题总结**

　　1、如果提交方式为post，想不乱码，只需要在服务器端设置request对象的编码即可，客户端以哪种编码提交的，服务器端的request对象就以对应的编码接收，比如客户端是以UTF-8编码提交的，那么服务器端request对象就以UTF-8编码接收(***\*request.setCharacterEncoding("UTF-8")\****)

　　2、如果提交方式为get，设置request对象的编码是无效的，request对象还是以默认的ISO8859-1编码接收数据，因此要想不乱码，只能在接收到数据后再手工转换，步骤如下：

　　1).获取获取客户端提交上来的数据，得到的是乱码字符串,data="???è?????"

　　 String data = request.getParameter("paramName"); 

　　2).查找ISO8859-1码表，得到客户机提交的原始数据的字节数组

　　 byte[] source = data.getBytes("ISO8859-1"); 

　　3).通过字节数组以指定的编码构建字符串，解决乱码

　　 data = new String(source, "UTF-8"); 

通过字节数组以***\*指定的编码\****构建字符串，这里***\*指定的编码\****是根据客户端那边提交数据时使用的字符编码来定的，如果是GB2312，那么就设置成data = new String(source, "GB2312")，如果是UTF-8，那么就设置成data = new String(source, "UTF-8")

也可以修改配置方式（解决长远）

在server.xml中配置

​	![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps60.jpg)

## 5.11. **Request对象实现请求转发**

### 5.11.1. **4.1、请求转发的基本概念**

　　***\*请求转发：指一个web资源收到客户端请求后，通知服务器去调用另外一个web资源进行处理。\****

　　请求转发的应用场景：MVC设计模式

　　在Servlet中实现请求转发的两种方式：

　　***\*1、通过ServletContext的getRequestDispatcher(String path)方法，该方法返回一个RequestDispatcher对象，调用这个对象的forward方法可以实现请求转发。\****

***\*例如：将请求转发的test.jsp页面\****

1 RequestDispatcher reqDispatcher =this.getServletContext().***\*getRequestDispatcher\****("/test.jsp");

2 reqDispatcher.forward(request, response);

　　***\*2、通过request对象提供的getRequestDispatche(String path)方法，该方法返回一个RequestDispatcher对象，调用这个对象的forward方法可以实现请求转发。\****

***\*例如：将请求转发的test.jsp页面\****

1 request.***\*getRequestDispatcher\****("/test.jsp").forward(request, response);

　　request对象同时也是一个域对象(Map容器)，开发人员通过request对象在实现转发时，把数据通过request对象带给其它web资源处理。

***\*例如：请求RequestDemo06 Servlet，RequestDemo06将请求转发到test.jsp页面\****

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps61.jpg)](javascript:void(0);)

 1 package gacl.request.study;

 2 

 3 import java.io.IOException;

 4 import javax.servlet.ServletException;

 5 import javax.servlet.http.HttpServlet;

 6 import javax.servlet.http.HttpServletRequest;

 7 import javax.servlet.http.HttpServletResponse;

 8 

 9 public class RequestDemo06 extends HttpServlet {

10 

11   public void doGet(HttpServletRequest request, HttpServletResponse response)

12       throws ServletException, IOException {

13 

14     String data="大家好，我是孤傲苍狼，我正在总结JavaWeb";

15     /**

16     * 将数据存放到request对象中,此时把request对象当作一个Map容器来使用

17     */

18     request.setAttribute("data", data);

19     //客户端访问RequestDemo06这个Servlet后，RequestDemo06通知服务器将请求转发(forward)到test.jsp页面进行处理

20     request.getRequestDispatcher("/test.jsp").forward(request, response);

21   }

22 

23   public void doPost(HttpServletRequest request, HttpServletResponse response)

24       throws ServletException, IOException {

25     doGet(request, response);

26   }

27 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps62.jpg)](javascript:void(0);)

test.jsp页面代码如下：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps63.jpg)](javascript:void(0);)

 1 <%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

 2 

 3 <!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN">

 4 <html>

 5  <head>

 6   <title>Request对象实现请求转发</title>

 7  </head>

 8  

 9  <body>

10    使用普通方式取出存储在request对象中的数据：

11    <h3 style="color:red;"><%=(String)request.getAttribute("data")%></h3>

12   使用EL表达式取出存储在request对象中的数据：

13   <h3 style="color:red;">${data}</h3>

14  </body>

15 </html>

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps64.jpg)](javascript:void(0);)

运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps65.jpg)

　　request对象作为一个域对象(Map容器)使用时，主要是通过以下的四个方法来操作

· setAttribute(String name,Object o)方法，将数据作为request对象的一个属性存放到request对象中，例如：request.setAttribute("data", data);

· getAttribute(String name)方法，获取request对象的name属性的属性值，例如：request.getAttribute("data")

· removeAttribute(String name)方法，移除request对象的name属性，例如：request.removeAttribute("data")

· getAttributeNames方法，获取request对象的所有属性名，返回的是一个，例如：Enumeration<String> attrNames = request.getAttributeNames();

### 5.11.2. **4.2、请求重定向和请求转发的区别**

一个web资源收到客户端请求后，***\*通知服务器去调用另外一个web资源\****进行处理，称之为请求转发/307。

　　一个web资源收到客户端请求后，***\*通知浏览器去访问另外一个web资源\****进行处理，称之为请求重定

 

## 5.12. **1、HttpServletResponse对象介绍**

Web服务器收到客户端的http请求，会针对每一次请求，分别创建一个用于代表请求的request对象、和代表响应的response对象。

request和response对象即然代表请求和响应，那我们要获取客户机提交过来的数据，只需要找request对象就行了。要向客户机输出数据，只需要找response对象就行了。

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps66.jpg) 

HttpServletResponse对象代表服务器的响应。这个对象中封装了向客户端发送数据、发送响应头，发送响应状态码的方法。查看HttpServletResponse的API，可以看到这些相关的方法。

### 5.12.1. **负责向客户端(浏览器)发送数据的相关方法**

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps67.jpg)

### 5.12.2. **负责向客户端(浏览器)发送响应头的相关方法**

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps68.jpg)

　　

### 5.12.3. **负责向客户端(浏览器)发送响应状态码的相关方法**

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps69.jpg)

### 5.12.4. **响应状态码的常量**

　　HttpServletResponse定义了很多状态码的常量(具体可以查看Servlet的API)，当需要向客户端发送响应状态码时，可以使用这些常量，避免了直接写数字，常见的状态码对应的常量：

### 5.12.5. **使用OutputStream流向客户端浏览器输出中文数据**

***\*使用OutputStream流输出中文注意问题：\****

　　在服务器端，数据是以哪个码表输出的，那么就要控制客户端浏览器以相应的码表打开，比如：outputStream.write("中国".getBytes("UTF-8"));使用OutputStream流向客户端浏览器输出中文，以UTF-8的编码进行输出，此时就要控制客户端浏览器以UTF-8的编码打开，否则显示的时候就会出现中文乱码，那么在服务器端如何控制客户端浏览器以以UTF-8的编码显示数据呢？可以通过设置响应头控制浏览器的行为，例如：response.setHeader("content-type", "text/html;charset=UTF-8");通过设置响应头控制浏览器以UTF-8的编码显示数据。

***\*范例：使用OutputStream流向客户端浏览器输出"中国"这两个汉字\****

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps70.jpg)](javascript:void(0);) 

10 public class ResponseDemo01 extends HttpServlet {

11 

12   private static final long serialVersionUID = 4312868947607181532L;

13 

14   public void doGet(HttpServletRequest request, HttpServletResponse response)

15       throws ServletException, IOException {

16     outputChineseByOutputStream(response);//使用OutputStream流输出中文

17   }

18   

19   /**

20   * 使用OutputStream流输出中文

21   * @param request

22   * @param response

23   * @throws IOException 

24   */

25   public void outputChineseByOutputStream(HttpServletResponse response) throws IOException{

26     /**使用OutputStream输出中文注意问题：

27     * 在服务器端，数据是以哪个码表输出的，那么就要控制客户端浏览器以相应的码表打开，

28     * 比如：outputStream.write("中国".getBytes("UTF-8"));//使用OutputStream流向客户端浏览器输出中文，以UTF-8的编码进行输出

29     * 此时就要控制客户端浏览器以UTF-8的编码打开，否则显示的时候就会出现中文乱码，那么在服务器端如何控制客户端浏览器以以UTF-8的编码显示数据呢？

30     * 可以通过设置响应头控制浏览器的行为，例如：

31     * response.setHeader("content-type", "text/html;charset=UTF-8");//通过设置响应头控制浏览器以UTF-8的编码显示数据

32     */

33     String data = "中国";

34     OutputStream outputStream = response.getOutputStream();//获取OutputStream输出流

35     response.setHeader("content-type", "text/html;charset=UTF-8");//通过设置响应头控制浏览器以UTF-8的编码显示数据，如果不加这句话，那么浏览器显示的将是乱码

36     /**

37     * data.getBytes()是一个将字符转换成字节数组的过程，这个过程中一定会去查码表，

38     * 如果是中文的操作系统环境，默认就是查找查GB2312的码表，

39     * 将字符转换成字节数组的过程就是将中文字符转换成GB2312的码表上对应的数字

40     * 比如： "中"在GB2312的码表上对应的数字是98

41     *     "国"在GB2312的码表上对应的数字是99

42     */

43     /**

44     * getBytes()方法如果不带参数，那么就会根据操作系统的语言环境来选择转换码表，如果是中文操作系统，那么就使用GB2312的码表

45     */

46     byte[] dataByteArr = data.getBytes("UTF-8");//将字符转换成字节数组，指定以UTF-8编码进行转换

47     outputStream.write(dataByteArr);//使用OutputStream流向客户端输出字节数组

48   }

49 

50   public void doPost(HttpServletRequest request, HttpServletResponse response)

51       throws ServletException, IOException {

52     doGet(request, response);

53   }

54 

55 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps71.jpg)](javascript:void(0);)

 运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps72.jpg)

　　客户端浏览器接收到数据后，就按照响应头上设置的字符编码来解析数据，如下所示：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps73.jpg)

### 5.12.6. **使用PrintWriter流向客户端浏览器输出中文数据**

***\*使用PrintWriter流输出中文注意问题：\****

　　在获取PrintWriter输出流之前首先使用"response.setCharacterEncoding(charset)"设置字符以什么样的编码输出到浏览器，如：response.setCharacterEncoding("UTF-8");设置将字符以"UTF-8"编码输出到客户端浏览器，然后再使用response.getWriter();获取PrintWriter输出流，这两个步骤不能颠倒，如下：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps74.jpg)](javascript:void(0);)

1 response.setCharacterEncoding("UTF-8");//设置将字符以"UTF-8"编码输出到客户端浏览器

2 /**

3 * PrintWriter out = response.getWriter();这句代码必须放在response.setCharacterEncoding("UTF-8");之后

4 * 否则response.setCharacterEncoding("UTF-8")这行代码的设置将无效，浏览器显示的时候还是乱码

5 */

6 PrintWriter out = response.getWriter();//获取PrintWriter输出流

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps75.jpg)](javascript:void(0);)

　　然后再使用response.setHeader("content-type", "text/html;charset=字符编码");设置响应头，控制浏览器以指定的字符编码编码进行显示，例如：

1 //通过设置响应头控制浏览器以UTF-8的编码显示数据，如果不加这句话，那么浏览器显示的将是乱码

2 response.setHeader("content-type", "text/html;charset=UTF-8");

　　除了可以使用response.setHeader("content-type", "text/html;charset=字符编码");设置响应头来控制浏览器以指定的字符编码编码进行显示这种方式之外，还可以用如下的方式来模拟响应头的作用

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps76.jpg)](javascript:void(0);)

1 /**

2 * 多学一招：使用HTML语言里面的<meta>标签来控制浏览器行为，模拟通过设置响应头控制浏览器行为

3 *response.getWriter().write("<meta http-equiv='content-type' content='text/html;charset=UTF-8'/>");

4 * 等同于response.setHeader("content-type", "text/html;charset=UTF-8");

5 */

6 response.getWriter().write("<meta http-equiv='content-type' content='text/html;charset=UTF-8'/>");

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps77.jpg)](javascript:void(0);)

***\*范例：使用PrintWriter流向客户端浏览器输出"中国"这两个汉字\****

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps78.jpg)](javascript:void(0);)10 

11 public class ResponseDemo01 extends HttpServlet {

12 

13   private static final long serialVersionUID = 4312868947607181532L;

14 

15   public void doGet(HttpServletRequest request, HttpServletResponse response)

16       throws ServletException, IOException {

17     outputChineseByPrintWriter(response);//使用PrintWriter流输出中文

18   }

19 

20   /**

21   * 使用PrintWriter流输出中文

22   * @param request

23   * @param response

24   * @throws IOException 

25   */

26   public void outputChineseByPrintWriter(HttpServletResponse response) throws IOException{

27     String data = "中国";

28     

29     //通过设置响应头控制浏览器以UTF-8的编码显示数据，如果不加这句话，那么浏览器显示的将是乱码

30     //response.setHeader("content-type", "text/html;charset=UTF-8");

31     

32     response.setCharacterEncoding("UTF-8");//设置将字符以"UTF-8"编码输出到客户端浏览器

33     /**

34     * PrintWriter out = response.getWriter();这句代码必须放在response.setCharacterEncoding("UTF-8");之后

35     * 否则response.setCharacterEncoding("UTF-8")这行代码的设置将无效，浏览器显示的时候还是乱码

36     */

37     PrintWriter out = response.getWriter();//获取PrintWriter输出流

38     /**

39     * 多学一招：使用HTML语言里面的<meta>标签来控制浏览器行为，模拟通过设置响应头控制浏览器行为

40     * out.write("<meta http-equiv='content-type' content='text/html;charset=UTF-8'/>");

41     * 等同于response.setHeader("content-type", "text/html;charset=UTF-8");

42     */

43     out.write("<meta http-equiv='content-type' content='text/html;charset=UTF-8'/>");

44     out.write(data);//使用PrintWriter流向客户端输出字符

45   }

46   

47   public void doPost(HttpServletRequest request, HttpServletResponse response)

48       throws ServletException, IOException {

49     doGet(request, response);

50   }

51 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps79.jpg)](javascript:void(0);)

 　当需要向浏览器输出字符数据时，使用PrintWriter比较方便，省去了将字符转换成字节数组那一步。

### 5.12.7. **使用OutputStream或者PrintWriter向客户端浏览器输出数字**

***\*比如有如下的代码：\****

11 

12 public class ResponseDemo01 extends HttpServlet {

13 

14   private static final long serialVersionUID = 4312868947607181532L;

15 

16   public void doGet(HttpServletRequest request, HttpServletResponse response)

17       throws ServletException, IOException {

18     

19     outputOneByOutputStream(response);//使用OutputStream输出1到客户端浏览器

20     

21   }

22 

23   /**

24   * 使用OutputStream流输出数字1

25   * @param request

26   * @param response

27   * @throws IOException 

28   */

29   public void outputOneByOutputStream(HttpServletResponse response) throws IOException{

30     response.setHeader("content-type", "text/html;charset=UTF-8");

31     OutputStream outputStream = response.getOutputStream();

32     outputStream.write("使用OutputStream流输出数字1：".getBytes("UTF-8"));

33     ***\*outputStream.write(1);\****

34   }

35   

36 }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps80.jpg)](javascript:void(0);)

　　运行上面代码显示的结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps81.jpg)

　　运行的结果和我们想象中的不一样，数字1没有输出来，下面我们修改一下上面的outputOneByOutputStream方法的代码，修改后的代码如下：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps82.jpg)](javascript:void(0);)

 1   /**

 2   * 使用OutputStream流输出数字1

 3   * @param request

 4   * @param response

 5   * @throws IOException 

 6   */

 7   public void outputOneByOutputStream(HttpServletResponse response) throws IOException{

 8     response.setHeader("content-type", "text/html;charset=UTF-8");

 9     OutputStream outputStream = response.getOutputStream();

10     outputStream.write("使用OutputStream流输出数字1：".getBytes("UTF-8"));

11     //outputStream.write(1);

12     ***\*outputStream.write((1+"").getBytes());\****

13   }

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps83.jpg)](javascript:void(0);)

　　***\*1+""\****这一步是将数字1和一个空字符串相加，这样处理之后，数字1就变成了字符串1了，然后再将字符串1转换成字节数组使用OutputStream进行输出，此时看到的结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps84.jpg)

　　这次可以看到输出来的1了，这说明了一个问题：***\*在开发过程中，如果希望服务器输出什么浏览器就能看到什么，那么在服务器端都要以字符串的形式进行输出\****。

　　如果使用PrintWriter流输出数字，那么也要先将数字转换成字符串后再输出，如下：

[![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps85.jpg)](javascript:void(0);)

 1   /**

 2   * 使用PrintWriter流输出数字1

 3   * @param request

 4   * @param response

 5   * @throws IOException 

 6   */

 7   public void outputOneByPrintWriter(HttpServletResponse response) throws IOException{

 8     response.setHeader("content-type", "text/html;charset=UTF-8");

 9     response.setCharacterEncoding("UTF-8");

10     PrintWriter out = response.getWriter();//获取PrintWriter输出流

11     out.write("使用PrintWriter流输出数字1：");

12     out.write(1+"");

13   }

 

 

## 5.13. **JSP(Java Server Page)**

动态页面  解读后台数据库中的数据

JSP页面，必须经过tomcat解析之后进行展示

其实jsp就是java代码，后期还是会被java编译的

### 5.13.1. **JSP组成：**

JSP指令  <%@ 指令名称 属性%>

page

contentType 设置JSP页面响应MIME格式以及响应编码

language 解析语言  目前只支持Java

Extends  设置jsp页面继承的java类，jsp页面在执行之前都会被服务器解析成Servlet，而Servlet是由java类定义的，所以jsp和Servlet都可以继承指定的父类，该属性不常用，可能影响服务器的性能优化。

Import  设置JSP导入的类包，嵌入的java代码片段需要导入相应的类包。

pageEncoding  指定页面编码格式，如果设置为ISO-8859-1，则页面不支持中文，通常设置为GBK或者UTF-8

Session  指定页面是否使用HTTP的session会话对象，默认值为true

Buffer  设置页面out输出对象的缓冲区大小，默认为8KB，单位只能使用KB，建议使用8的倍数作为属性值

autoFlush  设置页面缓存满时，是否自动刷新缓存，默认为true，如果设置成false，则缓存满时会抛出异常

***\*isErrorPage  可以将当前页面设置成错误处理页面来处理另一个JSP页面的错误，也就是作为异常处理页面\****

***\*errorPage  设置当前页面的异常处理页面，对应的异常处理页面isErrorPage必须设置为true，如果设置该属性，那么在web.xml文件中定义的任何错误处理页面都将被忽略，优先使用该属性定义的异常处理页面。\****

​	

​	include 包含指令

<%@ ***\*include\**** ***\*file\****="***\*add.jsp\****"%>

taglib  引入标签库的指令

Java代码

<% Java代码 %>

<% ! Java代码 %>

<% =Java代码 %>

HTML代码

 

### 5.13.2. **JSP的九大内置对象**

pageContext ,request，session，application，

response,  

out，page，config，exception。

request：请求对象，触发服务调用的请求。

response：服务响应对象，对请求的应答。

session：session会话对象，为请求的客户创建一个session对象。

application：从servlet配置对象中获得servlet上下文。

out：输出流对象。

pageContext：页面的上下文。

page：实现处理本页当前请求的类的实例。

config：配置对象。

exception：异常对象。（***\*isErrorPage\****="***\*true\****"）

### 5.13.3. **JSP动作标签**

· <jsp:include>标签  

<jsp:include>标签用于把另外一个资源的输出内容插入进当前JSP页面的输出内容之中，这种在JSP页面执行时的引入方式称之为动态引入。

语法：

   ***\*<jsp:include page="relativeURL | <%=expression%>" flush="true|false" />\****

　　page属性用于指定被引入资源的相对路径，它也可以通过执行一个表达式来获得。

　　flush属性指定在插入其他资源的输出内容时，是否先将当前JSP页面的已输出的内容刷新到客户端。

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps86.jpg) 

一般用于引入头部或者尾部

· <jsp:forward>标签  

<jsp:forward>标签用于把请求转发给另外一个资源。

​		***\*<jsp:forward page="relativeURL | <%=expression%>" />\**** 

　　page属性用于指定请求转发到的资源的相对路径，它也可以通过执行一个表达式来获得。

 

***\*范例：使用<jsp:forward>标签跳转页面\****

***\*forwarddemo01.jsp\****

1 <%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

2 <%--使用<jsp:forward>标签跳转到forwarddemo02.jsp--%>

3 <jsp:forward page="/forwarddemo02.jsp"/>

***\*forwarddemo02.jsp\****

1 <%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

2 <h1>跳转之后的页面！！</h1>

运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps87.jpg)

　　从页面的显示效果来看，页面已经完成了跳转，但地址栏没有变化，地址栏中显示的地址还是forwarddemo01.jsp，但页面显示的内容却是forwardemo02.jsp中的内容。因为此跳转属于服务器端跳转。只要是服务器端跳转，则地址栏永远没有变化。

 

· <jsp:param>标签

当使用<jsp:include>和<jsp:forward>标签引入或将请求转发给其它资源时，可以使用<jsp:param>标签向这个资源传递参数。

<jsp:param>标签的name属性用于指定参数名，value属性用于指定参数值。在<jsp:include>和<jsp:forward>标签中可以使用多个<jsp:param>标签来传递多个参数。 

***\*范例：使用<jsp:param>标签向被包含的页面传递参数\****

***\*JspIncludeTagDemo03.jsp\****

1 <%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

2 <h1>JspIncludeTagDemo03.jsp</h1>

3 <hr/>

4 <jsp:include page="/jspfragments/Inc.jsp">

5   <jsp:param name="parm1" value="hello" />

6   <jsp:param name="parm2" value="gacl" />

7 </jsp:include>

***\*Inc.jsp\****

1 <%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

2 <h1>接收从JspIncludeTagDemo03.jsp页面中传递过来的参数：</h1>

3 <h2><%=request.getParameter("parm1")%></h2>

4 <h2><%=request.getParameter("parm2")%></h2>

　　在***\*JspIncludeTagDemo03.jsp\****页面中使用<jsp:include>标签将Inc.jsp页面包含进来，使用<jsp:param/>标签向Inc.jsp页面传递了两个参数parm1和parm2

　　***\*JspIncludeTagDemo03.jsp\****页面运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps88.jpg)

 ***\*范例：使用<jsp:param>标签向要跳转的页面传递参数\****

***\*forwarddemo03.jsp\****

1<%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

2\<%--使用\<jsp:forward>标签跳转到forwarddemo04.jsp--%>

3\<%--使用\<jsp:param>标签向forwarddemo04.jsp传递参数--%>

4<jsp:forward page="/forwarddemo04.jsp">

5<jsp:param name="ref1" value="hello" />

6<jsp:param name="ref2" value="gacl" />

7\</jsp:forward>

***\*forwarddemo04.jsp\****

1<%@ page language="java" import="java.util.*" pageEncoding="UTF-8"%>

2\<h1>跳转之后的页面！！\</h1>

3\<h1>接收从forwarddemo03.jsp传递过来的参数：\</h1>

4\<h1>ref1：<%=request.getParameter("ref1")%>\</h1>

5\<h1>ref2：<%=request.getParameter("ref2")%>\</h1>

运行结果如下：

　　![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps91.jpg)

 

 

## ==5.14. **EL表达式**==

语法： ${目标参数}

如果EL表达式接收到的是集合，EL表达式+taglib标签库的形式循环遍历

EL表达式4中内置对象

pageScope  requestScope  sessionScope  applicationScope

## 5.15. **JSP标准标签库 JSTL**

JSTL标签库的使用是为弥补html标签的不足，规范自定义标签的使用而诞生的。使用JSLT标签的目的就是不希望在jsp页面中出现java逻辑代码

### 5.15.1. **JSTL标签库的分类**

核心标签(用得最多)

国际化标签(I18N格式化标签)

数据库标签(SQL标签，很少使用)

XML标签(几乎不用)

JSTL函数(EL函数)

#### 5.15.1.1. **\<c:out>标签的功能**

　　\<c:out>标签主要是**用来输出数据对象（字符串、表达式）的内容或结果**。

在使用Java脚本输出时常使用的方式为： <% out.println(“字符串”)%> 或者 <%=表达式%> ，在web开发中，为了避免暴露逻辑代码会尽量减少页面中的Java脚本，使用\<c:out>标签就可以实现以上功能。

-    <c:out value=”字符串”>
-    <c:out value=”EL表达式”>

JSTL的使用是和EL表达式分不开的，EL表达式虽然可以直接将结果返回给页面，但有时得到的结果为空，\<c:out>有特定的结果处理功能，EL的单独使用会降低程序的易读性，建议把EL的结果输入放入\<c:out>标签中。

 

\<c:out>标签的使用范例

<%--引入JSTL核心标签库 --%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>

<c:out value="下面的代码演示了c:out的使用，以及在不同属性值状态下的结果。"/>

<c:out value="\<a href='http://www.cnblogs.com/'>点击链接到博客园</a>" />

<c:out value="<未使用字符转义>" />

#### 5.15.1.2. \<c:set>标签的功能

\<c:set>标签用于把某一个对象存在指定的域范围内，或者将某一个对象存储到Map或者JavaBean对象中。

\<c:set>标签的使用范例

<%--引入JSTL核心标签库 --%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>

\<%--通过<c:set>标签将data1的值放入page范围中。--%>

\<li>把一个值放入page域中:<c:set var="data1" value="xdp" scope="page"/>\</li>

 <%--使用EL表达式从pageScope得到data1的值。--%>

\<li>从page域中得到值：${pageScope.data1}\</li>  

#### 5.15.1.3. **<c:if>标签的语法**

<%--引入JSTL核心标签库 --%>

```html
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
<c:if test="${param.uname=='admin'}">
  	输出语句（类似java，表达式test成立则输出，不成立则不输出，多用于权限控制等）
  	 </c:if>
```

#### 5.15.1.4. **循环标签——forEach标签使用总结**

该标签根据循环条件遍历集合（Collection）中的元素。

```html
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
    <c:forEach var=”name” items=”Collection” varStatus=”StatusName” begin=”begin” end=”end” step=”step”>

  <!--本体内容-->

    </c:forEach>
    
    <c:forEach var="fuwa" items="${list}">
        ${fuwa}//输出list里面的值，若是对象则 var是对象名，输出是对象.属性名
    </c:forEach>
```

【参数解析】：

1.  var设定变量名用于存储从集合中取出元素。
2.  items指定要遍历的集合。
3.  varStatus设定变量名，该变量用于存放集合中元素的信息（可选）。   
4.  begin、end用于指定遍历的起始位置和终止位置（可选）。
5.  step指定循环的步长（可选）

<%--引入JSTL核心标签库 --%>

<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>

集合 List\<String> list = new ArrayList\<String>();

List.add(“a”);

List.add(“b”);

List.add(“c”);



​	 <c:forEach var="fuwa" items="${list}">

​       ${fuwa}//输出list里面的值，若是对象则 var是对象名，输出是对象.属性名

  </c:forEach>

#### 5.15.1.5. **使用相对路径，和绝对路径导入外部文件。**

绝对路劲

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps92.jpg) 

通过jsp或许绝对路径的方式 ${pageContext.request.contextPath} 引入js文件 我的引入路径 如下图

 

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps93.jpg) 

 

 

```html
<!--相对路径-->

<%

  String path = request.getContextPath();

  String basePath = request.getScheme() + "://" + 
   request.getServerName() + ":" + request.getServerPort() + path + "/";%>

<!--头部添加-->

<base href="<%=basePath%>"></base>

<!--可以写个单独的页面同过jsp导入-->

<%@include file="taglib.jsp"%>
```

 



 

## 5.16. **Servlet中的作用域**

pageContext 局限于当前页面  

request  请求一次实效  

session  当前会话有效

ServletContext  全局有效

Session获取ServletContext  对象

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps94.jpg) 

jsp页面

![img](file:///C:\Users\ADMINI~1\AppData\Local\Temp\ksohtml9684\wps95.jpg) 

当输入http://localhost:8080/test 

三个属性都能看的到

同浏览器再次 输入http://localhost:8080/list.jsp（我们跳回了list。Jsp页面）

发现name不见了，其他的都还在，

换个浏览器输入http://localhost:8080/list.jsp

发现只有sex

 

## 5.17. **Session与Cookie**

详见session与cookie的讲义

## 5.18. **项目阶段**

整合之前的所有开始写项目，

管理项目。电商项目。

选择模板。修改模板。需求，开发，分页技术

## 5.19. **过滤器**

\1. 先创建类

\2. 实现Filter接口

\3. 重写方法  初始化方法  过滤方法  销毁方法

\4. 在过滤方法中自定义过滤器业务逻辑

\5. 过滤器配置

(1) Web.xml配置

```html
<filter>
    <filter-name>BookFilter</filter-name>
    <filter-class>com.zx.filter.BookFilter</filter-class>
</filter>
<filter-mapping>
    <filter-name>BookFilter</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>
```

(2) 注解  @WebFilter(过滤的路径)

## 5.20. **监听器**

 

## 5.21. **Redis**

## 5.22. **图片上传**

 

 