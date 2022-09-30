# Java微服务

原名：OAK

Java之父 詹姆斯·高斯林

Oracle（神谕，甲骨文）

## 一、Java三个体系：

SE（平台标准版），桌面应用程序

EE（平台企业版），面向Internet的应用程序

ME（平台微型版），移动端（智能设备）应用程序

### JavaEE开发

基于JavaWeb层面开发

使用Java语言开发的基于浏览器（互联网）运行的项目

#### 软件架构：

1.  C/S	Client/Server客户端/服务器

    -   优点:用户体验好
    -   缺点:开发、测试、运行、维护..…

2.  B/S	Browser/Server浏览器/服务器

    ​		只需要有浏览器即可运行项目

    -   优点;开发、测试、运行、维护比较方便

    -   缺点:用户体验没有C/S架构好，对硬件要求比较高

浏览器资源：

-   静态资源：图片、音频、视频….
-   动态资源：需要结合服务器来展示

​		用户访问根据自己的特点，时间看到的效果不同

## 二、Java特点：

面向对象（OOP）

跨平台

安全健壮

没有指针操作

垃圾自动回收装置

多线程

分布式

## 三、Java程序的运行机制

### 	JVM与跨平台

Java程序不是直接在操作系统之上运行，而是运行于JVM (java虚拟机)之上

![img](Typora图片\JVM与跨平台.png)

Java源代码（java文件)经编译器编译成字节码(.class文件)，JVM本质上就是一个负责解释执行Java字节码的程序。

JVM执行Java程序的过程:

-   加载.class文件
-   管理并分配内存
-   执行垃圾收集

### 	JVM，JRE，JDK

JVM：Java虚拟机

JRE：Java运行时环境（JVM+类库）

JDK：Java开发工具包（JRE+编译工具）

JDK里面包含JRE包含JVM

运行Java程序只需要安装JRE,开发Java程序则需要安装JDK

### 	JAVA开发环境安装，配置

#### 		安装JDK

​	==注意:安装路径不要有空格和中文!==

​	安装完成后需要关闭原来的命令窗口，重新打开一个薪的窗口

查看java版本:

-   java -version
-   javac -version

#### 		配置环境变量

JAVA_HOME：C:\Program Files\Java\jdk1.6.0

PATH：%JAVA_HOME%\bin;  或

C:\Program Files\Java\jdk1.6.0\bin;

### 	Java开发流程

#### 结构化编程与面向对象编程

结构化编程：函数

面向对象编程：类

java类的基本结构：变量 + 方法

#### 编写和运行Java程序的三个步骤

编写源代码，保存到源代码文件中，例如HelloWorld.java

编译源代码，例如 javas HelloWorld.java

执行字节码，例如java HelloWorld

#### 			案例

```java
修饰符 关键字 类名{
	修饰符 关键字 方法修饰 方法名（参数）{
		输出语句
}
}

public class 类名{
    public static void main(String[] args){
        System.out.println("");
    }
}

```

#### 	源文件与class文件

在Java 中源文件的名称必须是文件中主类的名称，扩展名必须为.java。源文件中可以包含多个类，但是最多只能有一个类使用 public修饰，使用public修饰的类就是主类。在Java 中，源文件还被作为编译单元,即一个源文件就是一个编译单元

编译器会为源代码中的每个类生成一个.class文件，.class文件的名称是类的名称，扩展名为.class 

#### 	main()方法

方法名:只能是main，不能是Main等形式。
==修饰符:public static void三个缺一不可，多一个不行==

参数：

-   参数类型为字符串数组

-   参数名称只要符合Java中标识符命名要求即可

-   参数声明的两种方式: String[] args ，或Sting args[]

    dos命令：

1.  切换盘符：盘:
2.  切换目录：cd
3.  清屏：cls
4.  上级目录：cd ..
5.  退出：exit





## 四、标识符、关键字、数据类型

###  1、注释

-   单行注释：//
-   多行注释：/* 注释内容 */
-   文档注释：/** 文档内容 */		可以生成文档内容			javadoc -d(指定生成文档的目录) Java源文件

### 2、分隔符、代码块

每行功能代码以  “**;**”  作为结束符号

空格没有实际意义，可以利用空格无意义，将代码合理缩进，易读{}包含的代码称之为代码块，例如类if(){}、方法{}、类(}等等

### 3、标识符

#### 	概念：

java中类名、方法名以及变量名都叶做标识符

#### 	标识符规则：

-   由字母、数字、下划线(_)以及美元符号($)组成
-   不能以数字开头
-   不能使用关键字和保留字

==注意：==

-   标识符的长度没有限制
-   Java是大小写敏感的，所有标识符区分大小写

#### 	标识符规范：（驼峰）

##### 大驼峰

第一个单词的首字母大写。以大写字母开头（用于类名、接口名）

```java
class Helloworld{…}//类名
    
interface AccountBase {…}//接口名
```

##### 小驼峰

第一个单词的首字母是小写，其他单词的首字母大写。以小写字母或单词开头（用于方法名，变量名）

```java
String studentName;//变量名

String getStudentName(){…}//方法名
```

#### 常量命名规范

常量是使用final 修饰的存储单元。(最终的)

全部为大写字母表示
			final public int DAYS_WEEK=7;

​	final public double PI=3.1415926;

#### 关键字和保留字

| abstract | continue | for        | new       | switch       |
| -------- | -------- | ---------- | --------- | ------------ |
| assert   | default  | goto       | package   | synchronized |
| boolean  | do       | if         | private   | this         |
| break    | double   | implements | protected | throw        |
| byte     | else     | import     | public    | throws       |
| case     | enum     | instanceof | return    | transient    |
| catch    | extends  | int        | short     | try          |
| char     | final    | interface  | static    | void         |
| class    | finally  | long       | strictfp  | volatile     |
| const    | float    | native     | super     | while        |

Java保留了const和goto关键字，但是没有使用。Java还保留了下面这些关键字：true、 false和null。这些关键字是Java定义的数值





## 五、基本数据类型

### 	1、分类

![](Typora图片\Java数据类型.png)

### 	2、整型(long,int,short,byte)

​		==Java不支持无符号的、只是正值的整数==

####  类型宽度范围

| **名 称** | **宽 度** | **范   围**                                           |
| --------- | --------- | ----------------------------------------------------- |
| long      | 64/8      | -9 223 372 036 854 775 808至9 223 372 036 854 775 807 |
| int       | 32/4      | -2 147 483 648至2 147 483 647   大约21亿              |
| short     | 16/2      | -32 768至32 767                                       |
| byte      | 8/1       | -128至127                                             |

#### 		字面值

1.  整数字面值默认是int类型
2.  将字面值赋给byte或 short变量时,如果字面值位于目标类型的范围之内，就不产生错误。
3.  ==大写或小写的L明确地标识其类型为long（一般为大写）==
4.  在字面值可以包含下划线，例如1_000_000_000
5.  各进制开头：十进制、八进制（0)、十六进制（0X/0x)、二进制（0B/0b)

### 3、浮点型(float,double)

浮点数，也称为实数(real number)，当计算需要小数精度的表达式时使用

#### 	类型宽度范围

| 名称           | 高度（位） | 大致范围          |
| -------------- | ---------- | ----------------- |
| double(双精度) | 64/8       | 4.9e-324~1.8e+308 |
| float(单精度)  | 32/4       | 1.4e-045~3.4e+038 |

#### 	浮点数字面值

1.  默认为double类型，为了指定float字面值，需要使用后缀F或f
2.  科学计数法。例如6.022E23、314159E-5、2e+100==（e：幂的缩写）==

### 4、字符型(char)

#### 	char类型与字符编码

1.  char是16位，Java在内部使用16位的整数表示字符(Unicode编码）,char类型的范围0~65536。<!--char是无符号类型-->//全世界基本的语言符号基本都包含了
2.  char也可以用作整数类型，可以将整型字面值赋给char类型的变量，可以在char类型上执行算术运算。
3.  26个小写字母、26个大写字母、以及10个数字0-9，其编码是连续的
4.  ASCII：65=’A’    97=‘a’

#### char类型字面值

字符型字面值使用单引号中的字符表示,例如'a'。

​				字符型==有且仅有==一个字符

##### 				转义字符

| **转义序列** | **描   述**               |
| ------------ | ------------------------- |
| \ddd         | 八进制字符(ddd)           |
| \uxxxx       | 十六进制Unicode字符(xxxx) |
| \’           | 单引号                    |
| \”           | 双引号                    |
| \\           | 反斜杠                    |
| \r           | 回车符                    |
| \n           | 新行符(也称为换行符)      |
| \f           | 换页符                    |
| \t           | 制表符                    |
| \b           | 回格符                    |

#### 字符串类型

字符串类型是 String，==String是类==，所以是引用类型。字符串字面值是使用双引号包围起来的内容。

### 5、布尔型（boolean	一般用于判断）

1.  boolean类型表示逻辑值,==它只能是true或false==
2.  boolean类型的值与整数0和1没有任何关系





## 六、变量常量与方法

### 1、变量的声明与赋值

==说明==:变量表示存储单元，变量名就是存储单元的名称，变量初始化之后就可以通过变量名访问存储单元

1.  变量声明	int i;	String str;		//还没有分配存储空间
2.  初始化（赋初值）	i=10;     str="abc";	//初始化之后就分配了存储空间
3.  声明并赋值	inti=10;      String st="abc";	//声明的同时进行初始化

==注意:变量在使用之前必须先初始化(赋初值)==

### 2、常量的声明和赋值（final）

-   
    声明常量需要使用final关键字，如：final double PI=3.1415926
-   常量通常在声明时赋值,并且**==赋值之后其值不能改变==**
-   常量标识符通常全部为大写。



### 3、实例变量与局部变量

根据变量声明的位置,变量可以分为实例变量和局部变量

#### 	实例变量及作用范围

-   在类的内直接定义的变量，称为实例变量或成员变量
-   作用范围:整个类中都可以使用
-   实例变量在创建对象时会自劫初始化，并有初始值(默认值)

byte/short/int：0

long：0L

float：0.0f

double：0.0

boolean：false

引用类型：null

#### 	局部变量及作用范围

-   在方法中或代码块(中定义的变量，称之为局部变量
-   作用范围:直接包含它的{}内有效
-   局部变量不会自动初始化,没有默认值，使用之前必须要初始化



### 4、类型转换

#### 	自动转换

类型兼容、小类型转换为大类型

​	==double>float>long>int>short>byte==

#### 	强制转换

大类型转换为小类型

```java
类型 变量=(类型)变量;（类型兼容）
```



## 七、运算符

### 1、 赋值运算符（=）

赋值运算符有一个有趣的特性：它允许创建赋值链。例如，分析下面的代码段：

```java
int x, y, z;
x = y = z = 100;  // set x, y, and z to 100 
//赋值给z为100，把z赋给y，又把y赋给x
```



### 2、 算术运算符（+	-	*	/	%）

1.  整型数字之间运算时，没有long类型参与时，结果是整型数字(int)
2.  在有long类型参与的整数运算式中，结果是long类型
3.  在有浮点型数字参与运算时，结果是浮点型数字(默认double类型)
4.  在有字符串参与运算时，执行的是字符串拼接操作

### 3 、组合运算符（+=	-=	*=	/=	%=	++	--）

1.符号在前  先自增1  再运算

2.符号在后  先运算  再自增1

### 4、 逻辑运算符（&	|	^	！	&&	||）

&(与)  |(或)  ^(异或)  !(非)  &&(短路与)  ||(短路或)

布尔逻辑运算符，只能操作boolean型操作数。

| 运算符 | 结  果             |
| ------ | ------------------ |
| &&     | 逻辑与（短路形式） |
| \|\|   | 逻辑或（短路形式） |
| ^      | 逻辑异或           |
| !      | 逻辑一元非         |
| &      | 逻辑与             |
| \|     | 逻辑或             |

布尔逻辑运算规则：

| 操作数 | 逻辑运算及结果 |          |        |       |       |
| ------ | -------------- | -------- | ------ | ----- | ----- |
| A      | B              | A \|\| B | A && B | !A    | A ^ B |
| false  | false          | false    | false  | true  | false |
| true   | false          | true     | false  | false | true  |
| false  | true           | true     | false  | true  | true  |
| true   | true           | true     | true   | false | false |

&(与)  两边都为真  则真 否则为假  结果是布尔类型

|(或)  两边都为假  则假 否则为真

^(异或) 两边不一样为真  两边一样为假

!(非)  真为假  假为真  只能操作布尔类型

&&(短路与)  左边为假 右边不再判断(执行)

||(短路或)  左边为真 右边不再判断(执行)

### 5 、关系运算符（>	>=	<	<=	==	!=）

（1）关系运算的结果为==**boolean**==型数值。

（2）关系运算符最常用于if语句和各种循环语句中的控制表达式。

### 6 、位运算符(适用于二进制)（<<	>>	>>>）

####  左移和右移

<<(左移)  左移之后右边空出来的位数补0(左移一位结果乘以2)

\>>(右移)  右移之后右边多出来的位数直接砍掉(右移一位结果除以2) 

\>>>(无符号右移)

####  位逻辑运算符

| **运算符** | **结  果**   |
| ---------- | ------------ |
| ~          | 按位一元取反 |
| &          | 按位与       |
| \|         | 按位或       |
| ^          | 按位异或     |

运算规则：

| **操作数** | **位运算及结果** |                |               |           |         |
| ---------- | ---------------- | -------------- | ------------- | --------- | ------- |
| **A**      | **B**            | **A** **\| B** | **A** **& B** | **A ^ B** | **～A** |
| 0          | 0                | 0              | 0             | 0         | 1       |
| 1          | 0                | 1              | 0             | 1         | 0       |
| 0          | 1                | 1              | 0             | 1         | 1       |
| 1          | 1                | 1              | 1             | 0         | 0       |

==注意：==

&和|，如果操作数为boolean类型，则为逻辑运算符，如果操作数为整数则为位运算符。通常将&和|作为位运算符。

### 7、 三目运算符

语法：表达式1?表达式2:表达式3

运算规则：表达式1成立  执行表达式2  否则执行表达式3





## 八、分支结构

选择结构是通过分支语句实现的，分支语句有两种

### 1、if...else

```java
if(条件表达式){
	代码结构
}

if(条件表达式){
	满足条件执行的代码结构
}else{
	不满足条件执行的代码结构
}

if(条件表达式1){
	满足条件1执行的代码结构
}else if(条件表达式2){
	满足条件2执行的代码结构
}else{
	都不满足  执行的代码结构
}
```

==注意：==

-   if可以单独使用 else只能配合if使用  不能单独使用
-   当满足了一个条件之后  就不会再满足后面的其他条件

### 2、switch

```java
switch(变量){
    case 值1:
        代码块;
        break;
    case 值2:
        代码块;
        break;
    case 值3:
        代码块;
        break;
    case 值4:
        代码块;
        break;
    default:
        代码块;//不满足所有条件后执行
        break;
}
```

==**注意：**==

1.  default一般放在最后也可以放在开头或者中间

2.  case分支的值不能相等

3.  switch条件必须是一个变量不能是一个表达式

4.  switch条件变量数据类型只能使用byte、short、int、 char

    新增字符串枚举

### 3、if和switch的区别

1.   switch 语句**只能进行相等性测试**，这一点与if语句不同,if语句可以对任何类型的布尔表达式进行求值。即，switch只查看表达式的值是否和某个case常量相匹配
2.  相对于一系列嵌套的if语句，switch语句通常效率更高





## 九、循环结构

### 1、while

```java
while(表达式){
    循环代码块;
}
```

### 2、do{...}while

```java
do{
    循环代码块;
}while(表达式);
```

### 3、while 和do{...}while区别:

1.  while先判断条件，条件为真，执行循环
2.  do{}while先执行一次循环，再判断条件
3.  无论如何do{}while都会先执行一次循环(输出一条语句)

### 4、for

```java
for(初始化语句（默认初始值）;循环条件(boolean 值（不写默认true）);迭代语句（boolean值的控制条件）){
    循环代码块;
}

for(;;){
    死循环;
}
```

**注：**

循环结构中布尔条件不能直接写false（导致废代码块），但可以写boolean类型变量

### 5、循环嵌套

```java
for(int i=0;i<10;i++){
    for(int j=0;j<10;j++){
        System.out.println(i+"-"+j);
    }
}
```

运行逻辑：内循环执行结束后才执行外循环

### 6、break，continue

break:终止直接包含的循环体，结束(本层）循环

continue:终止本次循环，直接执行循环的下一次

```java
for(int i=0;i<10;i++){
    for(int j=0;j<10;j++){
        System.out.println(i+"-"+j);
        if(j==4){
            break;
        }
        System.out.println(j);
    }	
}
// i=0    j=0,1,2,3,4
//i=1
```





## 十、数组

### 1、概念

一组相同数据的**集合**

### 2、数组的声明

```java

类型[] 数组名 = new 类型[数组长度];
//静态声明
int[] 数组名 = new int[数组长度];//最常用的方法
int 数组名[] = new int[数组长度];//不推荐
//动态声明
int[] 数组名 = new int[]{初始值1,初始值2...};
int[] 数组名 = {初始值1,初始值2...};

int[] arr = new int[10];
int arr2[] = new int[5];
int[] arr3 = new int[]{};
int[] arr4 ={};
System.out.println(arr2.length);//对象.属性（方法）  获取数组的长度

//赋值
arr[0]=5;
arr[9]=19;
System.out.println(arr[5]);

long[] arr1 = new long[5];
arr1[0] = 5;//不用加L
arr1[1] = 6;
arr1[2] = 7;
arr1[3] = 8;
arr1[4] = 9;
```

==注：==

1.  数组声明之后，不能再改变数组长度
2.  数组中只能存储同类型的值

不同类型在数组中的默认值：

-   byte，short，int，long：0
-   float，double：0.0
-   boolean：false

### 3、变量的内存（了解）

![](Typora图片\变量内存.png)

栈内存：局部变量，数组或者对象的名称		由虚拟机自动清除数据

堆内存：全局变量，数组或者对象的实例		由垃圾回收机制（**==CG==**）定期扫描

### 4、数组的最值与排序

#### 	1、==冒泡排序==

```java
int[] arr = {12,78,5,9,34,1,8,6,35,101,5,75,65,-7};//14
int temp;
for (int i = 0; i < arr.length; i++) {//排序比较次数
    for (int j = 1; j < arr.length-i; j++) {//下标
        if (arr[j-1] > arr[j]) {
            temp = arr[j-1];
            arr[j-1] = arr[j];
            arr[j] = temp;
        }
    }
}
```

#### 	2、二分折半法

```java
int[] arr = {-7,1,5,5,6,8,9,12,34,35,65,75,78,101};
int key = 12;
int max = arr.length-1;
int min = 0;
int mid = (max+min)/2;
boolean b = true;
while(b){
    if (key > arr[mid]) {
        min = mid+1;
        mid = (max+min)/2;
    }else if (key < arr[mid]) {
        max = mid-1;
        mid = (max+min)/2;
    }else if (key == arr[mid]) {
        System.out.println("存在该数字，下标为"+mid);
        break;
    }
    if (max < min) {
        System.out.println("不存在该数字");
        break;
    }
}
```

### 5、二维数组

包含了多个一维数组

```java
int[][] arr = new int[][]{{1,2,3,5},{4,6},{7,8,9},{7}};
int[][] arr2 = new int[3][4];	//二维数组长度为3，其中的一维数组长度为4，共计12个元素
int arr3[][] = new int[3][];

//赋值
arr2[0][0] = 12;
arr2[0][3] = 15;

//查找输出
System.out.println(arr[0][0]);
for(int i = 0; i < arr.length; i++){
    for(int i = 0; i < arr[i].length; i++){
        System.out.print(arr[i][j]+" ");
    }
    System.out.println();
}
```

### 6、快捷方法

```java
//排序方法（从小到大）
Arrays.sort(arr);

//以字符串形式输出
System.out.println(Arrays.toString(arr));

//获取随机数
Random r = new Random();
int a = r.nextInt(5);//包前不包后（在0-5之间随机取值，包括0但不包括5）
int a2 = r.nextInt(900)+100;//随机三位数

//查找(先排序)
int a = Arrays.binarySearch(arr,7);//在数组arr中查找数字7，存在则输出下标，输出负值表示不存在
```

### 7、8、9、





## 十一、==[面向对象](https://bbs.csdn.net/topics/392567100)==

### 理解“万事万物皆对象”

1.  在Java语言范畴中，我们都将功能、结构等封装到类中，通过类的实例化，来调用具体的功能结构
    -   Scanner ,String等
    -   文件:File
    -   网络资源:URL
2.  涉及到Java语言与前端Html、后端的数据库交互时，前后端的结构在Java层面交互时，都体现为类、对象。

### 1、概念

#### 面向对象(Object Oriented)

是软件开发方法，一种编程范式。面向对象的概念和应用已超越了程序设计和软件开发，扩展到如数据库系统、交互式界面、应用结构、应用平台、分布式系统、网络管理结构、CAD技术、人工智能等领域。面向对象是一种对现实世界理解和抽象的方法，是计算机编程技术发展到一定阶段后的产物

面向对象是相对于面向过程来讲的，面向对象方法，把相关的数据和方法组织为一个整体来看待，从更高的层次来进行系统建模，更贴近事物的自然运行模式

#### 对象：

是指具体的某一个事物，郎在现实生活中能够省得见携得着的事物。在疏向对象程序设计中，对象所指的是计算机系统中的某一个成分。在面向对象程序设计中，对象包含两个合义，其中一个是数据，另外一个是动作，对象则是数据和动作的结合体。对象不仅能够进行操作，同时还蜕够及时记录下换作结果

协助理解：

![](Typora图片\面向对象协助理解.png)

对象来源：

1.  官方底层代码（常见的）
2.  第三方寻找（社区）
3.  自己实现  类中创建

### 2、类和对象

类：是具有相同特性(数据元素)和行为(功能)的对象的抽象

对象：类的实例

### 3、类和对象的创建

==<u>**先创建类，才能创建对象！**</u>==

```java
类的成员属性：
    修饰符 类型 属性名;
对象类型 名称 = new 类;


//写在实体类中，在main中调用：
public class Person{		//创建类
    public int id;			//编号（属性）
    public String name;		//姓名（属性）
    public int chinese;		//语文成绩（属性）
    public int math;		//数学成绩（属性）
    public int sum(){		//总成绩（方法）
        return chinese+sum;
    }
}
public class Test{
    public static void main(String[] args){
        Person p = new Person();//创建对象
        p.id;//调用属性
        p.sum();//调用方法
    }
}
```

#### Java编程分层结构：

实体类：com.abc.beans

测试类：com.abc.test

接口类：com.abc.dao

接口实现包：com.abc.dao.impl

工具类：com.abc.util

<img src="Typora图片\Java分层结构.png" style="zoom:67%;" />

### 4、方法

#### 1）语法

```java
修饰符 返回类型 方法名(形参列表){
    方法体;
}

public void userName(){
    System.out.println(name)
}
public int avg(){
    return (chinese+math)/2
}
```

==注：==

-   方法中定义变量称为局部变量。
-   如果没有返回值，则方法的返回类型必须为void
-   当方法有具体的返回类型时，则必须使用return语句返回一种值。
-   **==设计方法时，只需要抓住两个要素:==**

​						==**是否有返回值**==

​						==**是否需要参数**==

#### 2）方法的重载

在一个类中允许出现相同的方法名，但是<u>同名方法的参数类型或者参数个数不能一样</u>



1.  方法名相同
2.  参数类型与个数相同

解决方法：

1.  参数类型
2.  参数个数
3.  一般功能类似的方法方法名相同

#### 3）方法的可变参数列表

```java
修饰符 返回类型 方法名(数组类型[] 参数名){// 必须先声明数组
    方法体;
}

修饰符 返回类型 方法名(数组类型... 参数名){// 可以输入数组或数字
    方法体;
}

public class Student{//实体类
	public int sum(int... a){
        int sum = 0;
        for (int i = 0; i < a.length; i++) {
            sum += a[i];
        }
        return sum;
	}
}
public class Test {//测试类
    public static void main(String[] args) {
        Student student = new Student();
		int[] arr = {1,2,3,4,5,6};
		System.out.println(student.sum(arr));
		System.out.println(student.sum(1,2,3,4,5,6));
    }
}
```

### 5、标准实体类

private	私有化	私有的

1.  私有属性

2.  公有方法
    -   set属性名（首字母大写）——设置成员值，有参数 没有返回值（命名规范）
    -   get属性名（首字母大写）——获取成员值，没有参数 有返回值（命名规范）

3.  构造方法

    1.  空参构造方法
    2.  全参构造方法

4.  toString方法【具体见 13：1）】

    建议所有子类重写此方法（@Override）【11：3）及11：4）】

5.  

```java
public class Book {
    private int id;//编号
    private String name;//书名
    private String author;//作者
    private double price;//价格

    public void setPrice(double pri) {//设置方法
        price = pri;
    }
    public double getPrice() {//获取方法
        return price;
    }
}
```

### 6、构造方法（==<u>方法名和类名相同</u>==）

是用来初始化对象内部状态的特殊方法

#### 1）==<u>特征</u>==

1.  在Java语言中，每个类都至少有一个构造方法
2.  虚拟机为每一个类默认提供一个空参构造方法，如果程序的设计者手动提供带参构造方法，那么原来默认提供的空参构造方法失效
3.  构造方法的主要作用是完成对类对象的初始化工作
4.  构造方法不能由编程人员显式地直接调用
5.  构造方法没有返回类型
6.  构造方法的方法名与类名相同

#### 2）语法

```java
/*三种需要有的构造方法：
带所有属性的构造方法
除id外的构造方法
空参构造方法*/

访问修饰符 方法名(){}
//说明：访问修饰符一般用public     方法名固定，都是类名

快捷键：Alt+insert--Constructor
    右键--Generate
```

### 7、关键字：this

概念：代表调用者（类）本身（不是实体类本身）

作用：

1.  区分局部变量和全局变量
2.  调用本类中的其他方法（普通方法和构造方法）
3.  在调用本类中其他构造方法时，必须写在**第一行**（第一个“;”前）

```java
public class Person {
    private int id;
    private String userName;
    private String passWord;
    private int age;

    public Person() {
    }

    public Person(int id, String userName, String passWord, int age) {
        this (userName,passWord,age);//调用构造方法
//        this.id = id;
//        this.userName = userName;
//        this.passWord = passWord;
        this.age = age;
    }

    public Person(String userName, String passWord, int age) {
        this.userName = userName;
        this.passWord = passWord;
        this.age = age;
    }

    public int setId(int id) {
        return this.id = id;
    }
    public void setUserName(int id) {
        int a = this.setId(id);//调用普通方法
        System.out.println(a);
    }
}
```

### 8、==特征==：封装

私有的：private

private 数据类型 属性名称

需要set/get公有方法访问：

-   set属性名首字母大写	无返回值	有参数
-   get属性名首字母大写    有返回值    无参数

### 9、单例设计模式

**私有化构造方法**

```java
public class Person{
    public static Person person = new Person();//在类的内部实例化对象
    
    private Person(){}//私有化构造方法
    
    public static Person getPerson(){//静态方法访问对象，可以让其他类调用Person
        return person;
    }
}

public class Test{
    public static void main(String[] args){
        Person person = Person.gerPerson();
    	Person person1 = Person.getPerson();//访问对象方法
    
    	System.out.println(person);
    	System.out.println(person1);//输出对象地址
    
    	System.out.println(person == person1);//判断地址是否相同，其结果应为true
    }
}
```

### 10、关键字：static

==static可以用来修饰属性,叫做静态属性，那么可以通过类名直接调用==，

放在静态区一般用public static修饰

如果一个变量被public static修饰，那一般还会有另外一个关键字final配合使用

==static可以用来修饰方法,叫做静态方法，那么可以通过类名直接调用==

static可以用来修饰内部类：

-   （非）静态的方法可以访问静态的成员
-   静态的方法不能访问非静态的成员

静态代码块

**<u>优先于任何代码执行，而且只执行一次</u>**

```java
static{
    代码块;
}
```

### 11、==特征==：继承（extends）

使用继承可以为一系列相关对象定义共同特征的一般类，然后其他类(更特殊的类)可以继承这个一般类，每个进行继承的类都可以添加其特有的内容

==**<u>被继承的类称为超类(super class）/父类,继承的类称为派生类/子类(subclass）</u>**==

#### 	1）语法

**<u><!--继承内默认以语法内代码为例，包括super关键字--></u>**

```java
子类 extends 父类
    
public class person{//父类
    private int id;//编号
    private String name;//姓名
    private String phone;//电话

    public Person() {
    }

    public Person(int id, String name, String phone) {
        this.id = id;
        this.name = name;
        this.phone = phone;
    }

    public Person(String name, String phone) {
        this.name = name;
        this.phone = phone;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }
    
    public void study(){
        System.out.println("父类学习");
    }
}

public class Student extends Person {//子类
    public void n(){
        setName("阿斯顿");
        System.out.println(getName());
    }
}

public class Test {
    public static void main(String[] args) {
        Student student = new Student();
        student.n();
    }
}
```

#### 	2）注：

一旦创建了一个定义一系列对象共同特征的超类，就可以使用该超类创建任意数量的更特殊的子类

子类可以使用父类中的==非私有类型==（除了private）的方法或属性

Java只支持单继承，不支持多继承（一个子类只能有一个父类，一个父类能有多个子类）

Java支持多重继承（继承体系）

<u>**不要仅为了获取其他类中某个功能而去继承**</u>

==**继承时自动继承父类的构造方法**==

如果一个类想要使用另外一个类的成员，有两种办法：继承，传参

#### 3）方法的重写

当子类出现和父类一模一样（包括方法名，参数类型，参数个数）的方法时，出现方法的覆盖操作或者重写或者复写

当有重写现象发生时，子类执行方法则执行重写之后的方法，且不能再调用父类被重写的方法

重写的修饰符访问权限不能比被重写方法更高

#### 4）注解（@Override）

==**<u>注解不是注释</u>**==

表示这个方法是一个重写方法（父类中有这个方法）

==限制==：这个方法跟父类中的方法一模一样（包括方法名和参数）

```java
public class Student extends Person {//子类
    @Override//注解，表示下一个方法为重写方法
    public void study() {
        super.study();
    }
}
```

### 12、关键字：super

调用父类中的（非私有）方法或（非私有）属性，使用方法和this类似

==**子类继承父类时自动继承父类的构造方法**==

==调用构造方法时super与this不能同时使用==

```java
super.父类成员非私有属性
super.父类中的非私有方法
super()//调用构造方法，隐式存在且只能在第一行
    
public class Student extends Person {
    @Override//注解
    public void study() {
        System.out.println(super.getName() + "学习");
        super.study();
    }
    
    public Student(){
        super();//不写默认隐藏存在
    }
}
```

### 13、Object类（所有类的基类）

类0bject 是类层次结构的根类。每个类都使用0bject作为超类。所有对象（包括数组）都实现这个类的方法。

下面的方法都为Object类中的方法

#### 1）toString

返回该对象的字符串表示

通常，toString方法会回一个“以文本方式表示”此对象的字符率。结果应是一个简明但易于读懂的信息表达式

==建议所有子类都重写此方法==

```java
Student student = new Student();
System.out.println(student.toString());
System.out.println(student);//直接输出对象时默认调用toString方法输出其地址
```

### 14、修饰符

|           | 本类   | 本包   | 继承子类 | 公共   |
| --------- | ------ | ------ | -------- | ------ |
| private   | 可访问 |        |          |        |
| (default) | 可访问 | 可访问 |          |        |
| protected | 可访问 | 可访问 | 可访问   |        |
| public    | 可访问 | 可访问 | 可访问   | 可访问 |

**定义default方法时不能写修饰符**

```java
void aaa(){//default修饰的方法
}
```

### 15、关键字：final

修饰类：修饰后<u>不能被继承</u>（一般不修饰类）

修饰成员属性：需要初始化成员属性，一般用public static final 修饰，被当作常量，属性名建议用大写

修饰方法：被修饰的方法不能被重写

```java
public final class 类名
public static final 数据类型 属性名;
public final void 方法名(){}
```

### 16、对象的传参

```java
public class Person(){
    public int a;
}
public class Student(){
    public void aaa(Person person){
        System.out.println(Person.a);
    }
}
```

### 17、抽象类和抽象方法（==<u>abstract</u>==）

抽象类的作用类似于“<u>模版</u>”,其目的是方便开发人员根据抽象类的格式来修改和创建新类

Java中可以定义<u>没有方法体</u>的方法，该方法的具体实现由<u>子类</u>完成，该方法称为抽象方法，包含抽象方法的类就是抽象类

抽象类和抽象方法必须用**abstract**关键字来修饰。

抽象方法只有方法声明,没有方法体，定义在抽象类中。**抽象类不可以被实例化**，也就是不可以用new创建对象

抽象类是不具体的，**没有对应的实例**

而且抽象类即使创建了对象，调用抽象方法也没有意义

抽象类通过其子类实例化,而**子类需要覆盖掉抽象类中<u>所有</u>的抽象方法**后才可以创建对象，否则该子类也是抽象类

**抽象类不一定有抽象方法，有抽象方法的类一定是抽象类**

==**抽象方法不能用private、final、static修饰**==

```java
public abstract class Animal {//构造抽象类
    public abstract void a();
    public abstract int c();
}
public class cat extends Animal{//实体类继承抽象类（必须重写抽象类的抽象方法）
    @Override
    public void a() {
    }

    @Override
    public int c() {
        return 0;
    }
}
```

### 18、模板设计模式

在模板模式中，父抽象类公开几个抽象方法供子类实现。在父抽象类中有另一个方法或几个方法使用抽象方法来实现业务逻辑

```java
public abstract class RunCodeModel {
    public long runTime(){//运行时间（模板代码）
        long begin = System.currentTimeMillis();//返回以毫秒为单位的当前时间（时间戳）
        runCode();//调用运行代码
        long end = System.currentTimeMillis();
        long time = end - begin;
        return time;
    }
    public abstract void runCode();//运行代码抽象方法
}

public class RunCode extends RunCodeModel {
    @Override
    public void runCode() {//重写运行代码
        for (int i = 0; i < 100; i++) {
            System.out.println("i = " + i);
        }
    }
}

public class Test extends RunCodeModel {//测试类继承
    @Override
    public void runCode() {//重写运行代码
        for (int i = 0; i < 100; i++) {
            System.out.println("i = " + i);
        }
    }
    
    public static void main(String[] args) {
        RunCode runCode = new RunCode();//实例化子类
        Test test = new Test();
        System.out.println(runCode.runTime());
    }
}


//官方文档例子：
abstract class Software {
   abstract void initialize();
   abstract void start();
   abstract void end();
   //模板方法
   public final void play(){
      //initialize
      initialize();
      //start
      start();
      //end
      end();
   }
}
class Browser extends Software {
   @Override
   void end() {
      System.out.println("Browser Finished!");
   }

   @Override
   void initialize() {
      System.out.println("Browser Initialized!.");
   }

   @Override
   void start() {
      System.out.println("Browser Started.");
   }
}
class Editor extends Software {

   @Override
   void end() {
      System.out.println("Editor Finished!");
   }

   @Override
   void initialize() {
      System.out.println("Editor Initialized!");
   }

   @Override
   void start() {
      System.out.println("Editor Started!");
   }
}
public class Main {
   public static void main(String[] args) {
      Software s1 = new Browser();//利用子类构造方法实例化父类，但父类不能调用子类中的属性和方法（包括重写方法）
      s1.play();
      s1 = new Editor();
      s1.play();
   }
}
```

### 19、==<u>*接口*</u>==

#### 1）概念

接口是java中最重要的概念,接口可以理解为一种特殊的类，里面全部是由<u>**全局常量和公共的抽象方法**</u>所组成。

当抽象类中的所有方法全部是抽象方法的时候，那么这个类是一个特殊的抽象类，叫接口

```Java
interface 接口名{//【】中代表可以不写
    【 public static final 】 数据类型 属性名 = 值;//全局常量
    【 public abstract 】 返回值类型 方法名();//抽象方法
    default void 返回值类型 方法名(){
        方法体;
    }
}

interface Person{
    public static final int AGE = 0;
    public abstract void study();
    public abstract void eat();
    public abstract void play();
    default void add(){

    }
}
public class Admin implements Person{
    @Override
    public void study() {
        System.out.println("学习管理");
    }

    @Override
    public void eat() {

    }

    @Override
    public void play() {

    }
}
```

==**注**==：

1.  接口中的成员修饰符是**<u>固定</u>**的（public abstract修饰成员函数  和  public static final修饰成员常量）

2.  接口中的方法这只能是==抽象方法==

3.  接口中<u>不存在public修饰的带方法体的方法</u>，需要用default修饰（**这里的default不能省略**）（jdk1.8版本之后可用）

4.  接口的出现将“多继承”通过另一种方式体现出来，即“多实现”

#### 2）特点

1.  对外暴露原则
2.  是程序的功能拓展
3.  接口的出现会降低耦合性（==**高内聚，低耦合**==）
4.  可以多实现
5.  类和接口之间为实现关系，类在继承一个类的同时还能实现多个接口（继承在前，接口实现在后）
6.  接口与接口之间可以继承

#### 3）面向接口编程

```java
public interface BookDao{
    //增加方法：
    void addBook(参数);
    //删除方法
    void deleteBook(参数);
    //修改方法
    void updateBook(参数);
    //查询方法
    Book[] getBook();//返回值为数组类型
}
```

### 20、==特征==：多态

#### 1）概念

一个对象具有多种形态，

向同一父类的不同子类对象发送一条消息（执行同一个方法），行为不同

==**<u>如果想要发生对象的向下转型，必须现有对象的向上转型</u>**==

```java
public class Animal {
    public void eat(){
        System.out.println("吃饭");
    }
}

public class Cat extends Animal {
    @Override
    public void eat() {
        System.out.println("吃鱼");
    }
    public void a(){
        System.out.println("a");
    }
}

public class Dog extends Animal{
    @Override
    public void eat() {
        System.out.println("吃骨头");
    }
}

public class AnimalTest {
    public static void main(String[] args) {
        Cat cat = new Cat();
        cat.eat();//输出吃鱼


        //编译看左，执行看右
        Animal animal = new Cat();
        animal.eat();//输出吃鱼

        Animal animal1 = new Dog();
        animal1.eat();//输出吃骨头
        
        //如果想要发生对象的向下转型，必须现有对象的向上转型
        Cat cat1 = (Cat) animal1;//编译正常，运行报错

        Cat cat2 = (Cat) animal;
        cat2.eat();//输出吃鱼
        cat2.a();//输出a，子类（Cat）有而父类（animal）没有的方法不能用父类（animal）直接调用
    }
}
```

#### 2）类型：

1.  向上转型：子类对象 → 父类对象	

    对于向上转型，程序会自动完成

2.  向下转型：父类对象 → 子类对象

    对于向下转型，必须明确指明要转换的子类类型

```java
//向上转型
父类 父类引用 = 子类实例			

//向下转型
子类 子类引用 = (子类) 父类实例		
```

### 21、关键字：instanceof （了解）

是 Java 的保留关键字。

作用：测试它左边的对象是否是它右边的类（其子类，或是其接口的实现类）的实例，返回 boolean 的数据类型。

### 22、内部类

类的内部可以定义另一个类，如果在类Outer的内部再定义一个Inner，此时Inner称为内部类，Outer称为外部类。

#### 1）成员内部类

可以使用修饰符修饰

Ⅰ、访问方法：

外部方法中创建内部类对象，调用内部类方法

外部类.内部类 内部类对象 = 外部类实例.内部类实例

```java
package com.Mar.beans3;

public class Outer01 {
    private int age;
    public void out_method(){
        System.out.println("外部类方法");
        Inner inner = new Inner();  //创建内部类对象
        inner.in_method();
    }
    public class Inner{//内部类
        private int id;
        public void in_method(){
            System.out.println("内部类方法");
        }
    }

    public class Inner2{

    }
}


package com.Mar.test;

import com.Mar.beans3.Outer01;

public class OuterTest {
    public static void main(String[] args) {
        Outer01 outer01 = new Outer01();
        //outer01.out_method();

        //直接找内部类：外部类.内部类 内部类对象 = 外部类实例.内部类实例;
        Outer01.Inner outerIn01 = new Outer01().new Inner();
        outerIn01.in_method();
        Outer01.Inner outerIn02 = outer01.new Inner();
        outerIn02.in_method();
    }
}

```

#### 变量调用

成员内部类中方法中的局部变量，调用外部类或内部类中重名的成员变量：

```java
//方法中的局部变量:变量
//内部类中的成员变量:this.变量
//外部类中的成员变量:外部类类名.this.变量

package com.Mar.beans3;

public class Outer01 {
    private int age = 30;
    public void out_method(){
        System.out.println("外部类方法");
        Inner inner = new Inner();  //创建内部类对象
        inner.in_method();
    }
    public class Inner{//内部类
        private int id;
        private int age = 20;
        public void in_method(){
            int age = 30;
            System.out.println("内部类方法" + age + " " + this.age + " " + Outer01.this.age);
            //输出顺序：30 20 18
        }
    }

    public class Inner2{

    }
}

```

#### 2）静态内部类

Ⅰ、访问方法：

```java
package com.Mar.beans3;

public class Outer02 {
    private int id;
    public void out_method(){
        System.out.println("外部类方法");
    }
    public static class Inner02{
        public void in_method(){
            System.out.println("内部类方法");
        }
    }
}

package com.Mar.test;

import com.Mar.beans3.Outer02;

public class Outer02Test {
    public static void main(String[] args) {
        //外部类.内部类 内部类对象= new 外部类名称.内部类名称();
        Outer02.Inner02 inner02 = new Outer02.Inner02();
        inner02.in_method();
    }
}

```

#### 3）方法内部类（认识）

```java
package com.Mar.beans3;

public class Outer03 {
    private int id;
    
    public void out_method(){
        System.out.println("外部类方法");
        class Inner03{
            private int id;
            
            public void in_method(){
                System.out.println("内部类方法");
            }
        }
    }
}
```

#### 4）<u>匿名内部类</u>（匿名子类）

是一次性内部类

```java
package com.Mar.beans3;

public class Outer04 {
    private int id;
    public void out_method(){
        System.out.println("外部类");
    }
}



package com.Mar.test;

import com.Mar.beans3.Outer04;

public class Outer04Test {
    public static void main(String[] args) {
        new Outer04().out_method();
        
        //新建类继承Outer04，内部可以重写方法
        //匿名重写
        new Outer04(){
            @Override
            public void out_method() {
                System.out.println("HelloWorld");
            }
        }.out_method();//输出HelloWorld
        
        //非匿名重写
        Outer04 outer04 = new Outer04(){
            @Override
            public void out_method() {
                System.out.println("HE");
            }
        };
        outer04.out_method();//输出HE
    }
}

```

### 23、常用类

在Java中，除lang包不需要手动引入（例：lang包下的Object类）外，其他包都需要手动引入

Random	随机数

Scanner	动态输入

String类	字符串类：

```java
package com.Mar.test;

public class Test {
    public static void main(String[] args) {
        //直接指向字符串常量区
        String name1 = "admin";
        String name2 = "admin";

        //通过创建堆指向字符串常量区
        String name3 = new String("admin");
        String name4 = new String("admin");
        
        //比较String对象的地址：
        System.out.println(name1 == name2);//true
        System.out.println(name3 == name4);//false
        System.out.println(name1 == name3);//false
    }
}
```

**String类在内存中的储存方式**：

<img src="Typora图片\String类储存方式.png" style="zoom: 80%;" />

String常用方法：

```java
package com.Mar.test;

public class Test02 {
    public static void main(String[] args) {
        //charAt(int index)     返回指定索引处的字符
        String str = "adfdvb123fes";
        char c = str.charAt(5);
        System.out.println(c);

        int i = str.codePointCount(5, 7);
        System.out.println(i);

        //compareTo(yuans)
        //如果参数字符串等于此字符串，则返回值0;
        //如果此字符串按字典顺序小于字符串参数，则返回一个小于0的值;
        //如果此字符串按字典顺序大于字符串参数，则返回一个大于0的值。
        //区分大小写
        String s = "abcdefghigklmnopqrstuvwxyz";
        int b = s.compareTo("am");//以括号中参数为参照物（0）
        System.out.println(b);
        //不区分大小写
        String s2 = "abcF";
        int a = s2.compareToIgnoreCase("abF");
        System.out.println(a);

        //	concat(字符串)		将指定字符串连接到此字符串的结尾
        String s = "admin";
        String concat = s.concat("");
        System.out.println(concat);

        //	contains(字符串)	当且仅当此字符串包含指定的 char 值序列时，返回 true
        String s = "abcdr";
        boolean a = s.contains("abc");
        System.out.println(a);

        //	copyValueOf(数组)		字符数组转化成字符串
        char[] c = new char[]{'a','b','c','d','f','g'};
        String s = String.copyValueOf(c);
        System.out.println(s);
        //	copyValueOf(数组,数字1,数字2)		返回初始位置（数字1）开始的定长（数字2）字符串
        String s1 = String.copyValueOf(c, 3/*数字1*/, 2/*数字2*/);
        System.out.println(s1);
        
            //	endsWith(指定后缀)		测试此字符串是否以指定的后缀结束,参数为空字符串或其本身时返回true
        String s = "admin";
        boolean n = s.endsWith("");
        System.out.println(n);

        //	equals(字符串)		比较字符串,只有完全相等时返回true
        //区分大小写
        String s = "admin";
        boolean admin = s.equals("admin");
        System.out.println(admin);
        //区分大小写
        boolean admIn = s.equalsIgnoreCase("AdmIn");
        System.out.println(admIn);

        //	format(格式,添加的值)		格式化字符串
        //使用指定的语言环境、格式字符串和参数返回一个格式化字符串
        //%s    字符串转换符  符号先占位   添加的内容在后面
      	String s = "admin";
        String format = String.format(s+"%n%s","feilong");
        System.out.println(format);

        //	getBytes(编码格式)	转换成ASCII编码
        String s = "123456admin";
        byte[] bytes = s.getBytes();
        System.out.println(Arrays.toString(bytes));
        byte[] bytes1 = s.getBytes("Utf-16");
        System.out.println(Arrays.toString(bytes1));

        //	getChar将字符从此字符串复制到目标字符数组
        String s = "123456admin";
        char[] c = new char[10];
        s.getChars(2,5,c,1);
        System.out.println(Arrays.toString(c));
        
        //返回指定字符在此字符串中第一次出现处的索引，找不到则返回-1
        //参数为int类型（Unicode编码,起始位置）起始位置不写默认从头
        //参数为String类型（"字符串",起始位置）起始位置不写默认从头
        String s = "123456admin";
        int i = s.indexOf(54,5);
        System.out.println(i);
        int i1 = s.indexOf("ad",4);
        System.out.println(i1);

        //返回字符串对象的规范化表示形式
        //可以规范有堆地址的字符串直接引用
        String s = "a";
        String s2 = new String("a");
        System.out.println(s == s2);
        System.out.println(s == s2.intern());
        
        //当且仅当 length() 为 0 时返回 true
        String s = "";
        boolean empty = s.isEmpty();
        System.out.println(empty);

        //返回指定子字符串在此字符串中最后一次出现处的索引，从指定的索引开始反向搜索
        String s = "ad1ada";
        int ad = s.lastIndexOf("ad");
        System.out.println(ad);

        //字符串长度
        String s = "admin";
        int length = s.length();
        System.out.println(length);

        //测试两个字符串区域是否相等
        //toffset - 此字符串中子区域的起始偏移量。
        //other - 字符串参数。
        //toffset - 字符串参数中子区域的起始偏移量。
        //len - 要比较的字符数。
        String s = "admin";
        boolean mi = s.regionMatches(3, "mi", 1, 2);
        System.out.println(mi);

        //指定的字面值替换序列替换此字符串所有匹配字面值目标序列的子字符串
        String s = "Admin";
        String replace = s.replace('A', 'a');
        String replace2 = s.replace("A", "a");
        System.out.println(replace);
        System.out.println(replace2);

        //给定的值替换此字符串所有匹配给定值的字符串
        String s = "adminadmin";
        String s1 = s.replaceAll("ad", "kk");
        System.out.println(s1);

        //返回一个新字符串，它是此字符串的一个子字符串
        String s = "admin";
        String substring = s.substring(2);
        System.out.println(substring);
        String substring1 = s.substring(2, 4);
        System.out.println(substring1);

        //将此字符串转换为一个新的字符数组,它的内容被初始化为包含此字符串表示的字符序列
        String s = "admin";
        char[] chars = s.toCharArray();
        System.out.println(chars);

        //清除首尾的空格
        String s = " admin ";
        int length = s.length();
        System.out.println(length);
        String trim = s.trim();
        System.out.println(trim.length());
    }
}
```

### 24、包装类

| 基本数据类型     | 对应包装类           |
| ---------------- | -------------------- |
| `byte`           | `Byte`               |
| `short`          | `Short`              |
| <u>**`int`**</u> | <u>**`Integer`**</u> |
| `long`           | `Long`               |
| `float`          | `Float`              |
| `double`         | `Double`             |
| `char`           | `Character`          |
| `boolean`        | `Boolean`            |

```java
package com.Mar.test;

public class IntegerTest {
    public static void main(String[] args) {
        int a = 15;
        int b = 15;
        Integer x = new Integer(15);
        Integer y = new Integer(15);
        Integer i = 15;
        Integer j = 15;

        Integer a1 = Integer.valueOf(128);
        Integer b1 = Integer.valueOf(128);
        Integer a2 = Integer.valueOf(127);
        Integer b2 = Integer.valueOf(127);
        System.out.println(x == y);//false，对象地址
        System.out.println(i == j);//true，隐式调用valueOf()方法
        System.out.println(a1 == b1);//false，128开始换地址
        System.out.println(a2 == b2);//true
    }
}
```



### 25、日期类，日历类

#### 1）日期类：（Date, SimpleDateFormat）

```java
package com.Mar.test;

import java.text.SimpleDateFormat;
import java.util.Date;

public class DateText {
    public static void main(String[] args) {
        Date date = new Date();
        System.out.println(date);
        //已过时方法
//        System.out.println((date.getYear() + 1900) + "-" + (date.getMonth() + 1) + "-" + date.getDate() + " " + date.getHours() + ":" + date.getMinutes() + ":" + date.getSeconds());
//        System.out.println(date.getYear() + 1900);
//        System.out.println(date.getMonth() + 1);
//        System.out.println(date.getDate());

        //日期格式化类
        SimpleDateFormat sf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        String format = sf.format(date);
        System.out.println(format);


    }
}
```

SimpleDateFormat：日期格式化类格式标准：

>   | 字母 | 日期或时间元素           | 表示              | 示例                                        |
>   | ---- | ------------------------ | ----------------- | ------------------------------------------- |
>   | `G`  | Era 标志符               | Text              | `AD`                                        |
>   | `y`  | 年                       | Year              | `1996`; `96`                                |
>   | `M`  | 年中的月份               | Month             | `July`; `Jul`; `07`                         |
>   | `w`  | 年中的周数               | Number            | `27`                                        |
>   | `W`  | 月份中的周数             | Number            | `2`                                         |
>   | `D`  | 年中的天数               | Number            | `189`                                       |
>   | `d`  | 月份中的天数             | Number            | `10`                                        |
>   | `F`  | 月份中的星期             | Number            | `2`                                         |
>   | `E`  | 星期中的天数             | Text              | `Tuesday`; `Tue`                            |
>   | `a`  | Am/pm 标记               | Text              | `PM`                                        |
>   | `H`  | 一天中的小时数（0-23）   | Number            | `0`                                         |
>   | `k`  | 一天中的小时数（1-24）   | Number            | `24`                                        |
>   | `K`  | am/pm 中的小时数（0-11） | Number            | `0`                                         |
>   | `h`  | am/pm 中的小时数（1-12） | Number            | `12`                                        |
>   | `m`  | 小时中的分钟数           | Number            | `30`                                        |
>   | `s`  | 分钟中的秒数             | Number            | `55`                                        |
>   | `S`  | 毫秒数                   | Number            | `978`                                       |
>   | `z`  | 时区                     | General time zone | `Pacific Standard Time`; `PST`; `GMT-08:00` |
>   | `Z`  | 时区                     | RFC 822 time zone | `-0800`                                     |

#### 2）日历类：（Calendar抽象类）

```java
package com.Mar.test;

import java.util.Calendar;

public class CalendarTest {
    public static void main(String[] args) {
        Calendar calendar = Calendar.getInstance();

        System.out.println(calendar.get(Calendar.YEAR));
        System.out.println(calendar.get(calendar.MONTH));
        int year = calendar.get(Calendar.YEAR);
        int month = calendar.get(Calendar.MONTH) + 1;
        int day = calendar.get(Calendar.DAY_OF_MONTH);
        int hour = calendar.get(Calendar.HOUR);
        int minute = calendar.get(Calendar.MINUTE);
        int second = calendar.get(Calendar.SECOND);
        System.out.println(year + "-" + month + "-" + day + " " + hour + ":" + minute + ":" + second);
    }
}
```



### 26

## 十二、集合

 数组	可变长数组	集合

<img src="Typora图片\接口Collection.png" style="zoom:100%;" />

```java
//加强版for循环：foreach
/*for(集合类型 输出变量 : 循环对象){
    循环体;
}*/
package com.Mar.test;

import java.util.ArrayList;

public class ArrayListTest {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList();
        list.add("admin1");
        list.add("admin2");
        list.add("admin3");
        list.add("admin4");

        System.out.println(list);
        //普通
        for (int i = 0; i < list.size(); i++) {
            System.out.println(list.get(i));
        }
        //foreach
        for (String name : list) {
            System.out.println(name);
        }
        //迭代器
        Iterator<String> iterator = list.iterator();
        while(iterator.hasNext()) {
            System.out.println(iterator.next());
        }
    }
}
```



### 1、List接口

存取顺序一致

元素可以重复



在自定义类中重写equals方法，在equals方法中自定义比较规则

**<u>\<E>：泛型，E为规范的数据类型，指定E后，该列表只能存储E类型的元素</u>**

#### 	1）Arraylist\<E>

以数组形式存在

```java
package com.Mar.test;

import com.Mar.beans.Book;

import java.util.ArrayList;
import java.util.Arrays;

public class Test {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();//初始容量为10
        list.add("admin");
        list.add("fbb");
        list.add("fbb1");
        list.add("fbb2");
        ArrayList<String> list1 = new ArrayList<>();
        list1.add("fbb3");
        list1.add("fbb4");
        list1.add("fbb5");
        list1.add("fbb6");

        //	add(位置,元素)	集合的添加操作：
        System.out.println(list);
        System.out.println(list1);
        list.addAll(list1);
        list.addAll(2,list1);//（位置，添加的元素）
        System.out.println(list);

        //	clear()		清空集合
        list.clear();
        System.out.println(list);

        //	contains(元素)	元素是否在集合中，返回值为boolean类型
        boolean admin = list.contains("admin");
		System.out.println(admin);

        //	get(位置索引)	根据索引获取对应的值
        String s = list.get(2);
        System.out.println(s);

        //	indexOf(元素)		获取元素在集合中第一次出现的位置
        int fbb1 = list.indexOf("fbb1");
        System.out.println(fbb1);

        //	isEmpty()	检测集合是否非空，返回boolean值
        boolean empty = list.isEmpty();
        System.out.println(empty);

        //	remove(元素)	移除指定元素
        list.remove("admin");
        System.out.println(list);

        //	set(位置索引,元素)	修改集合中指定位置的元素
        System.out.println(list);
        String abc = list.set(2, "abc");
        System.out.println(list);
        System.out.println(abc);

        //	size()	获取集合的长度
        int size = list.size();
        System.out.println(size);//区分：数组：array. Length    字符串：string. Length()    集合：list.size()

        //	toArray()	将集合转换成数组
        Object[] array = list.toArray();//自动新建一个Object类型的数组
        System.out.println(Arrays.toString(array));
        String[] array1 = list.toArray(new String[10]);//将集合转换成指定的**足够长**的数组，
        System.out.println(Arrays.toString(array1));

        
//        list.add(new Book(1,"笑傲江湖","金庸"));
//        list.add(new Book(2,"倚天屠龙记","金庸"));
//        list.add(new Book(3,"鹿鼎记","金庸"));
//        list.add(new Book(4,"神雕侠侣","金庸"));
//        list.add(new Book(5,"连城诀","金庸"));
        //打印值
//        System.out.println(list.toString());
    }
}

```

判断在集合中是否存在某一对象（**重写equals方法**）

```java
package com.Mar.test;

import com.Mar.beans.Book;

import java.util.ArrayList;

public class Test02 {
    public static void main(String[] args) {
        ArrayList list = new ArrayList();
        Book book = new Book(1,"笑傲江湖","金庸");
        Book book2 = new Book(2,"倚天屠龙记","金庸");
        list.add(book);
        list.add(book2);
        list.add(new Book(3,"鹿鼎记","金庸"));

        System.out.println(list.contains(new Book(5,"倚天屠龙记","金庸")));
        System.out.println(list.equals(new Book(3,"鹿鼎记","金庸")));
        list.remove(new Book(2,"倚天屠龙记","金庸"));
        System.out.println(list);
    }
}
```



#### 	2）LinkedList

列表形式存在

```java
package com.Mar.test;

import com.Mar.beans.Book;

import java.util.Iterator;
import java.util.LinkedList;

public class LinkedListTest01 {
    public static void main(String[] args) {
        LinkedList list = new LinkedList();
        list.add(1);
        list.add(5);
        list.add(0,4);
        list.addFirst(5);
        list.addFirst(6);
        list.add(0,7);
        list.addLast(8);
        list.add(5);


        list.add(new Book(1,"笑傲江湖","金庸"));
        list.add(new Book(2,"倚天屠龙记","金庸"));
        list.add(new Book(3,"天龙八部","金庸"));


        System.out.println(list.contains(new Book(3,"天龙八部","金庸")));
        System.out.println(list);

        Iterator iterator = list.descendingIterator();
        System.out.println(iterator.getClass());

        //	clone()		返回浅表的副本
        Object o = list.clone();
        System.out.println(o);

        //	element(),getFirst(),getLast(),get(位置索引)	返回列表的头,尾，或指定位置
        Object o1 = list.element();//头
        System.out.println(o1);
        Object o2 = list.getFirst();//头
        Object o3 = list.getLast();//尾
        Object o4 = list.get(5);//指定位置
        System.out.println(o2 + "\n" + o3 + "\n" + o4);

        //	offerFirst(元素),offer(元素),offerLast(元素)	在头，尾插入指定元素
        list.offerFirst("ad");//头
        list.offer("be");//尾
        list.offerLast("cf");//尾
        System.out.println(list);

        //	peek(),peekFirst(),peekLast()	返回头，尾
        Object o5 = list.peek();//头
        Object o6 = list.peekFirst();//头
        Object o7 = list.peekLast();//尾
        System.out.println(o5 + "\n" + o6 + "\n" + o7);

        //	poll(),pollFirst(),pollLast()	获取且移除头，尾
        Object o8 = list.poll();//头
        Object o9 = list.pollFirst();//头
        Object o10 = list.pollLast();//尾
        System.out.println(list);

        //	pop()	查询并删除头
        Object o11 = list.pop();
        System.out.println(o11);
        System.out.println(list);

        //	push(元素)	添加头
        list.push(123);
        System.out.println(list);

        //	removeFirstOccurrence(元素)	删除第一次出现的指定元素
        list.removeFirstOccurrence(5);
        System.out.println(list);
        
        //	removeLastOccurrence(元素)	删除最后一次出现的指定元素
        list.removeLastOccurrence(5);
        System.out.println(list);

    }
}
```



### 2、Set接口

存取顺序不一致

元素不可以重复



现在自定义中重写hashCode方法，保证hasCode的返回值一致，然后在自定义中重写equals方法，在equals方法中自定义比较规则

#### 	1）HashSet

先在自定义对象中重写hashCode方法,保证hashCode,的返回值是一致的，然后在自定义类中重写equals方法，在equals方法中自定义比较规则

```java
package com.Mar.test;

import com.Mar.beans.Person;

import java.util.ArrayList;
import java.util.HashSet;

public class HashSetTest {
    public static void main(String[] args) {
        HashSet<Person> hashSet = new HashSet();
//        hashSet.add(1);
//        hashSet.add(2);
//        hashSet.add(2);
//        hashSet.add("admin");
//        hashSet.add(new Person(1,15,"sas"));
//        hashSet.add(new Person(1,15,"sas"));
//        System.out.println(hashSet);

        hashSet.add(new Person(1,15,"zhangsan"));
        hashSet.add(new Person(1,15,"admin"));
        hashSet.add(new Person(1,15,"lisi"));
        hashSet.add(new Person(1,15,"wangwu"));
        hashSet.add(new Person(1,15,"wangwu"));
        ArrayList<Person> list = new ArrayList<>();
        list.add(new Person(2,15,"asd"));
        list.add(new Person(2,15,"fad"));
        list.add(new Person(2,15,"fad"));

        hashSet.addAll(list);
        System.out.println(hashSet);

        boolean fad = hashSet.contains(new Person(2, 15, "fad"));
        System.out.println(fad);

        //hashSet是否有list中的所有元素
        boolean b = hashSet.containsAll(list);
        System.out.println(b);

        boolean fad1 = hashSet.equals(new Person(2, 15, "fad"));//比较地址
        System.out.println(fad1);

        //是否为空
        boolean empty = hashSet.isEmpty();
        System.out.println(empty);
    }
}
```

#### 	2）TreeSet

同一TreeSet添加的类型必须为同种类型

能放入Treeset集合中的元素必须具备排序规则,所以自定义对象如果想要放入集合中，必须实现Compareable接口，重写compareTo方法，在compareTo中自定义排序规则

```java
package com.Mar.test;

import com.Mar.beans.Book;
import com.Mar.beans.Person;

import java.util.TreeSet;

public class TreeSetTest {
    public static void main(String[] args) {
//        TreeSet set = new TreeSet();
//        set.add(1);
//        set.add(7);
//        set.add(2);

//        set.add("zhangsan");
//        set.add("admin");
//        set.add("wangwu");
//        set.add("k");
//        set.add("123456");
//        set.add("5454");
//        set.add("5232");
//        set.add("张三");
//        set.add("王五");
//        set.add("李四");
//        System.out.println(set);

        TreeSet<Person> set = new TreeSet();
        //先加三个，然后以中间的数为根进行二叉树比较
        //排序的判断依据为自定义对象中的compareTo方法
        set.add(new Person(1,12,"admin"));
        set.add(new Person(1,5,"admin"));
        set.add(new Person(1,2,"admin2"));
        set.add(new Person(1,1,"admin2"));
        set.add(new Person(1,15,"admin"));
        set.add(new Person(1,14,"admin"));
        set.add(new Person(1,13,"admin"));
        set.add(new Person(1,13,"admin"));
        set.add(new Person(1,17,"admin"));
        set.add(new Person(1,107,"admin"));
        System.out.println(set);

        //返回大于等于给定值的最小数，不存在则null
        Person admin2 = set.ceiling(new Person(5, 2, "a"));
        System.out.println(admin2);

        //判断元素是否存在，判断依据为自定义对象中的compareTo方法
        boolean a = set.contains(new Person(1, 2, "a"));
        System.out.println(a);
    }
}
```

### 3、Map接口

#### 	1）HashMap

```java
package com.Mar.test;

import com.Mar.beans.Animal;

import java.util.HashMap;
import java.util.Iterator;

public class HashMapTest01 {
    public static void main(String[] args) {
//        HashMap map = new HashMap();
//        map.put("1","admin");
//        map.put("a","admin");
//        map.put("5","admin");
//        map.put("b","admin");
//        map.put("3","admin");
//        map.put("1",new Animal(1,"cat"));
//        map.put("2",new Animal(1,"cat"));
//        System.out.println(map);
//        System.out.println(map.containsValue(new Animal(1,"cat")));

        HashMap<String,Animal> map = new HashMap();
        map.put("1",new Animal(1,"cat"));
        map.put("2",new Animal(1,"dog"));
        map.put("3",new Animal(1,"snake"));
        map.put("4",new Animal(1,"tiger"));
        map.put("5",new Animal(1,"pig"));
        map.put("6",new Animal(1,"sheep"));

        System.out.println(map.size());
        
        System.out.println(map.remove("1"));
        
        //指定键所映射的值
        System.out.println(map.get("2"));
        
        //映射中所包含的键的Set视图。
        System.out.println(map.keySet());
        
        //返回此映射所包含的值的Collection视图
        System.out.println(map.values());
        
        //循环遍历
        for (String key : map.keySet()){
            System.out.println(key);
            System.out.println(map.get(key));
        }
        
        Iterator<String> iterator = map.keySet().iterator();
        while (iterator.hasNext()){
            String next = iterator.next();
            System.out.println(next);
            System.out.println(map.get(next));
        }
    }
}

```



#### 	2）TreeMap

```java
package com.Mar.test;

import com.Mar.beans.Dog;

import java.util.Iterator;
import java.util.TreeMap;

public class TreeMapTest01 {
    public static void main(String[] args) {
//        TreeMap<String, String> map = new TreeMap<>();
//        map.put("1","admin");
//        map.put("2","admin");
//        System.out.println(map);

        TreeMap<String, Dog> map = new TreeMap<>();
        map.put("1",new Dog(1,"tom"));
        map.put("2",new Dog(2,"jerry"));
        map.put("7",new Dog(2,"jerry"));
        map.put("5",new Dog(2,"jerry"));
        map.put("8",new Dog(2,"jerry"));
        map.put("23",new Dog(2,"jerry"));
        map.put("20",new Dog(2,"jerry"));
        
        System.out.println(map);
        
        // 返回对此映射中的键进行排序的比较器
        System.out.println(map.comparator());
        
        // 返回小于等于给定键的最大键
        System.out.println(map.floorKey("111"));
        
        // 返回此映射的部分视图，键值小于toKey,true:小于等于toKey
        System.out.println(map.headMap("5"));
        System.out.println(map.headMap("5",true));

        //返回小于给定键的最大值
        System.out.println(map.lowerKey("5"));
        
        //循环遍历
        for (String key : map.keySet()){
            System.out.println(key);
            System.out.println(map.get(key));
        }
        
        Iterator<String> iterator = map.keySet().iterator();
        while (iterator.hasNext()){
            String next = iterator.next();
            System.out.println(next);
            System.out.println(map.get(next));
        }
    }
}

```



## 十三、反射

### 1、概念

Java反射就是在运行状态中，

​			对于任意一个类，都能够知道这个类的所有属性和方法；

​			对于任意一个对象，都能够调用它的任意方法和属性；并且能改变它的属性

### 2、反射的创建

-   对象.getClass()
-   类名.class
-   Class.forName("com.zx.beans.User")

```java
package com.Mar.test;

import com.Mar.beans.User;

public class UserTest {
    public static void main(String[] args) throws ClassNotFoundException {
        //正常创建： 自己的引用 = 自己的实例
        User user = new User();

        //多态创建： 父类的引用 = 自己的实例
        Animal animal = new Cat();

        //反射创建的三种方式：
        //对象.getClass();
        Class c1 = user.getClass();

        //类名.class;
        Class c2 = User.class;

        //Class.forName("com.Mar.beans.User")（地址全称）
        //常用
        Class c3 = Class.forName("com.Mar.beans.User");//需要抛出异常
        System.out.println(c1);//class com.Mar.beans.User
        System.out.println(c2);//class com.Mar.beans.User
        System.out.println(c3);//class com.Mar.beans.User
    }
}
```

### 3、获取（名）及修改属性

-   获取类中的所有的公有属性			getFields()
-   获取类中指定的一个公有属性		getField()
-   获取类中所有的任意属性				getDeclaredFields()
-   获取类中指定的一个任意属性		getDeclaredField()
-   暴力访问属性   								setAccessible(true)

```java
package com.Mar.test;

import com.Mar.beans.User;
import com.sun.org.apache.xalan.internal.xsltc.compiler.util.MatchGenerator;

import java.lang.reflect.Field;
import java.lang.reflect.Method;
import java.util.Arrays;

public class UserTest01 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchFieldException, IllegalAccessException, NoSuchMethodException {
        User user = new User();
        user.age = 12;
        System.out.println(user.age);

        Class c = Class.forName("com.Mar.beans.User");
        //获取类中所有公有属性（权限，数据类型，具体地址）
        Field[] fields = c.getFields();
        System.out.println(Arrays.toString(fields));//[public int com.Mar.beans.User.age, public java.lang.String com.Mar.beans.User.gender]
        for (Field field : fields){
            System.out.println(field);
        }

        //获取类中指定公有属性，需要抛出找不到属性的异常
        Field fieldage = c.getField("age");
        System.out.println(fieldage);//public int com.Mar.beans.User.age

        fieldage.set(user,15);//属性.set(对象,值)
        System.out.println(fieldage.get(user));//15     属性.get(对象)

        //获取类中所有属性（包括私有）
        Field[] fields1 = c.getDeclaredFields();
        System.out.println(Arrays.toString(fields1));
        //[private int com.Mar.beans.User.id, private java.lang.String com.Mar.beans.User.name, public int com.Mar.beans.User.age, public java.lang.String com.Mar.beans.User.gender]
        for (Field field : fields1){
            System.out.println(field);
        }

        //获取类中的任意属性
        Field fieldId = c.getDeclaredField("id");
        //暴力访问（不推荐使用）
        fieldId.setAccessible(true);
        fieldId.set(user,5);
        System.out.println(fieldId);//private java.lang.String com.Mar.beans.User.name
        System.out.println(fieldId.get(user));//5

    }
}
```

### 4、获取（名）及运行方法

-   获取类中的所有的公有方法包含父类公共方法		getMethods()
-   获取类中指定的一个公有方法									getMethod()
-   获取类中所有的任意方法 						getDeclaredMethods()
-   获取类中指定的一个任意方法  				getDeclaredMethod()
-   暴力访问属性   											setAccessible(true)

```Java
package com.Mar.test;

import com.Mar.beans.User;

import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;

public class UserTest02 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException, InvocationTargetException, IllegalAccessException {
        User user = new User();
        //user.eat();

        Class c = Class.forName("com.Mar.beans.User");

        //获取所有包括本类及父类（默认继承Object）的公有方法
        Method[] methods = c.getMethods();
        for (Method method : methods){
            System.out.println(method);
        }

        //获取指定的公有方法（包括父类公有方法）
        Method setId = c.getMethod("eat");//无参
        System.out.println(setId);

        //获取本类（不包括父类）的所有方法
        Method[] declaredMethods = c.getDeclaredMethods();
        for (Method method : declaredMethods){
            System.out.println(method);
        }

        //获取指定的任意方法
        Method methodstudy = c.getDeclaredMethod("study");
        System.out.println(methodstudy);

        //调用公共方法
        Method methodeat = c.getMethod("eat",String.class);//有参
        methodeat.invoke(user, "123");

        Method methodstudy = c.getDeclaredMethod("study", int.class);
        //暴力访问
        methodstudy.setAccessible(true);
        methodstudy.invoke(user,100);

    }
}
```

### 5、获取get/set方法

```java
package com.Mar.test;

import com.Mar.beans.User;

import java.lang.reflect.Field;
import java.lang.reflect.InvocationTargetException;
import java.lang.reflect.Method;

public class UserTest03 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException, InvocationTargetException, IllegalAccessException {
        User user = new User();
        Class<?> c = Class.forName("com.Mar.beans.User");
        //有返回值的方法
//        Method methodaa = c.getMethod("aa", int.class, int.class);
//        int o = (int)methodaa.invoke(user, 15, 20);
//        System.out.println(o);
//
//        Method methodsetId = c.getMethod("setId", int.class);
//        methodsetId.invoke(user, 144);
//
//        Method methodgetId = c.getMethod("getId");
//        int id = (int) methodgetId.invoke(user);
//        System.out.println(id);
        
        
        Field[] fields = c.getDeclaredFields();
        for (Field field : fields){
            System.out.println(field);
            String fieldName = field.getName();
            System.out.println(fieldName);
            String getMethodName = "get" + fieldName.substring(0,1).toUpperCase() + fieldName.substring(1);
            String setMethodName = "set" + fieldName.substring(0,1).toUpperCase() + fieldName.substring(1);
            Method getMethod = c.getMethod(getMethodName);
            Method setMethod = c.getMethod(setMethodName, field.getType());
            System.out.println(field.getType());
            Object invoke = getMethod.invoke(user);
            System.out.println(invoke);
        }
    }
}
```

### 6、获取构造器

-   获取全部构造方法					getConstructors()
-   获取指定的带参数的构造器	getConstructor(int.class,String.class)

```java
package com.Mar.test;

import java.lang.reflect.Constructor;

public class UserTest04 {
    public static void main(String[] args) throws ClassNotFoundException, NoSuchMethodException {
        Class c = Class.forName("com.Mar.beans.User");

        //获取全部的构造方法
        Constructor[] constructors = c.getConstructors();
        for (Constructor constructor : constructors){
            System.out.println(constructor);
        }

        //获取指定构造器
        Constructor constructor = c.getConstructor(int.class, String.class);
        System.out.println(constructor);
    }
}
```

### 7、

## 十四、异常体系

### 1、Error（错误）

是Throwable的子类，用于指示合理的应用程序不应该试图捕获的严重问题

### 2、Exception（异常）

Exception类及其子类是Throwable的一种形式,它指出了合理的应用程序想要捕获的条件

#### 1）非运行异常

编译时报错

#### 2）运行异常（RuntimeException）

编译可通过，运行过程中可能出现问题

#### 3）异常捕获

```Java
package com.Mar.test;

import java.util.Arrays;

public class Test {
    public static void main(String[] args) {
        int[] arr = new int[10];
        int a = 10;
        int i = 0;
        try {
            arr[a] = 10;
            int b = a / i;
            System.out.println(Arrays.toString(arr));
        }catch (Exception e){
            e.printStackTrace();
            System.out.println("下标越界");
        }finally {
            System.out.println("永远都会执行的代码块");
        }

    }
}
```

## 十五、泛型<>

```java
package com.Mar.beans;

public class Demo<E> {
    public void aTest(E e){
        System.out.println(e);
    }
}

package com.Mar.beans;

public class User extends Person {
}

package com.Mar.beans;

public class Person {
    public void add(Demo<? extends Person> o){//限制Demo类型的泛型必须时Person的子类或本身
        									//extend——>super 必须时Person的父类或本身
        System.out.println(125);
    }
}

package com.Mar.test;

import com.Mar.beans.Demo;
import com.Mar.beans.Person;
import com.Mar.beans.User;

public class DemoTest {
    public static void main(String[] args) {
        //任意
        Demo demo = new Demo();
        demo.aTest(123);
        //单一
        Demo<String> demo1 = new Demo<>();
        demo1.aTest("abc");
        //自定义类
        Demo<User> demo2 = new Demo<>();
        demo2.aTest(new User());

        //
        Person person = new Person();
        person.add(demo2);


    }
}

```

## 十六、枚举（Enum）

```java
package com.Mar.beans;

import com.Mar.dao.Dao;

public enum Color01 implements Dao {
    RED("红色"){
        @Override
        public void run() {
            System.out.println("红色");
        }
    },GREEN("绿色") {
        @Override
        public void run() {
            System.out.println("绿色");
        }
    },BLUE("蓝色") {
        @Override
        public void run() {
            System.out.println("蓝色");
        }
    },OTHER{
        public void run(){
            System.out.println();
        }
    };

    private String name;
    private Color01(){

    }
    private Color01(String name){
        this.name = name;
    }

    public void run(){
        System.out.println("");
    }
    @Override
    public String toString() {
        return "Color01{" +
                "name='" + name + '\'' +
                '}';
    }
}
```

## 十七、数据库

### 1、数据库

#### 1）关系型数据库

RDBMS（Relational Database Management System，关系数据库管理系统）

**MySql**	Oracle	sqlServer

#### 2）非关系型数据库

Redis	MongoDB

### 2、MySql

MySQL是一个**关系型数据库管理系统**，在 WEB 应用方面，MySQL是最好的 **RDBMS** (Relational Database Management System，关系数据库管理系统) 应用软件之一。

MySQL是一种关系型数据库管理系统，关系数据库将数据保存在不同的表中，而不是将所有数据放在一个大仓库内，这样就增加了速度并提高了灵活性。



### 3、SQL语言

结构化查询语言（Structured Query Language）简称SQL，是一种特殊目的的编程语言，是一种数据库查询和程序设计语言，用于存取数据以及查询、更新和管理关系数据库系统。

1、数据查询语言（**DQL**: Data Query Language）：

​	其语句，也称为“数据检索语句”，用以从表中获得数据，确定数据怎样在应用程序给出。保留字select是DQL（也是所有SQL）用得最多的动词，其他DQL常用的保留字有where，order by，groupBY和having。这些DQL保留字常与其它类型的SQL语句一起使用。 

2、数据操作语言（**DML**：Data Manipulation Language）：

​	其语句包括动词insert、update和delect。它们分别用于添加、修改和删除。 

3、事务控制语言（**TCL**）：

​	它的语句能确保被DML语句影响的表的所有行及时得以更新。包括commit（提交）命令、savepoint（保存点）命令、rollback（回滚）命令。

4、数据控制语言（**DCL**）：

​	它的语句通过grant或revoke实现权限控制，确定单个用户和用户组对数据库对象的访问。某些RDBMS可用grant或revoke控制对表单个列的访问。 

5、数据定义语言（**DDL**）：

​	其语句包括动词create，alter和drop。在数据库中创建新表或修改、删除表（create，alter或drop table）；为表加入索引等。

6、指针控制语言（CCL）（Java用不到）：

​	它的语句，像DECLARE CURSOR，FETCH INTO和UPDATE WHERE CURRENT用于对一个或多个表单独行的操作。

### 4、登录数据库

```mysql
mysql -uroot -proot 
```

### 5、简单数据库

```mysql
查看数据库:
show databases;

查看数据库的编码:
show create database 数据库名;

使用数据库:
use 数据库名;

新建数据库:
create database 数据库名;

删除数据库:
drop database 数据库名;

查看表格:
show tables;

查看表结构:
desc 表名;

创建表格:
create table 表名(字段名类型(长度),….)

删除表格:
drop table表名;

```



### 6、增删改查

```mysql
添加数据:
insert into 表名 values(值1,值2,...);
insert into 表名(字段1,字段2,...) values(值1,值2,...)

查询数据:
select * from 表名;

删除数据:
delete from 表名 【where 条件】;
```



### 7、8、9、

## 十八、I/O流

1、

**输入：外部源——>程序**

**输出：程序——>输出目标（文件)**

外部源和输出目标:磁盘文件、网络连接、内存缓存

Java程序通过流执行I/O。流(stream)是一种抽象，它要么产生信息，要么使用信息。流通过Java的IO系统链接到物理设备。

所有流的行为方式是相同的，尽管与它们链接的设备是不同的。因此，可以为任意类型的设备应用相同的IO类和方法。这意味着可以将许多不同类型的输入:磁盘文件、键盘或网络socket，抽象为一个输入流。反之，一个输出流可以引用控制台、磁盘文件或网络连接。流是一种处理输入/输出的清晰方式，例如，代码中的所有部分都不需要理解健盘和网络之间的区别。

流是Java在由java.io包定义的类层次中实现的。

-   System.in标准输入流对象：接收键盘输入
-   System.out标准输出流对象：直接输出到控制台

### 2、流

#### 1）



#### 2）流的分类

Java中的流可以从不同的角度进行分类:

-   按照流的方向不同：分为输入流和输出流。
-   按照处理数据单位的不同：分为字节流（8位）和字符流（16位）。
-   按照功能不同：分为节点流和处理流。

节点流:是可以从一个特定的数据源〈节点）读写数据的流（例如文件，内存)。就像是一条单一的管子接到水龙头上开始放水。

处理流:是“连接”在已经存在的流（节点流或处理流）之上，通过对数据的处理为程序提供更为强大的读写功能。

##### 字节流

```java
package com.Mar.test;

import java.io.*;

public class Test {
    public static void main(String[] args) throws IOException {
        //字节流输出流
        //创建好输出流对象，指定好文件，加true追加到后面，不写默认覆写
        OutputStream os = new FileOutputStream("D:\\aaa.text",true);
        //要写入的字符串
        String string = "123松下问童子，言师采药去。只在此山中，云深不知处。";//写入文件吧字符串转换成字节数组
        os.write(string.getBytes());
        //关闭流
        os.close();

        //字节流输入流
        InputStream in = new FileInputStream("D:\\aaa.text");
        //一次性取多少个字节
        byte[] bytes = new byte[1024];
        //用来接收读取的字节数组
        StringBuilder sb = new StringBuilder();
        //读取到的字节数组长度，为-1时表示没有数据
        int length = 0;
        //循环取数据
        while ((length = in.read(bytes)) != -1) {
            //将读取的内容转换成字符串
            sb.append(new String(bytes, 0, length));
        }
        //关闭流
        in.close();
        System.out.println(sb);
    }
}
```

##### 字符流

```java
package com.Mar.test;

import java.io.*;

public class Test02 {
    public static void main(String[] args) throws IOException {
        //字符输出流
        //创建好输出流对象，指定好文件，加true追加到后面，不写默认覆写
        FileWriter fileWriter = new FileWriter("D:\\bbb.text",true);
        String string = "123松下问童子，言师采药去。只在此山中，云深不知处。";
        fileWriter.write(string);
        fileWriter.close();


        //字符输入流
//        InputStreamReader isr = new InputStreamReader (new FileInputStream(file),"UTF-8");
        FileReader isr = new FileReader(  "D:\\bbb.text");
        //字符数组:一次读取多少个字符
        char[] chars = new char [1024];
        //每次读取的字符数组先append到StringBui lder中
        StringBuilder sb = new StringBuilder ();
        //读取到的字符数组长度，为-1时表示没有数据
        int length;
        //循环取数据
        while ((length = isr.read(chars)) !=-1) {
            System.out.println(length);
            //将读取的内容转换成字符串
            sb.append(chars, 0, length);
        }
        isr.close();
        System.out.println(sb);
    }
}
```

##### 字节流字符流转换

```java
package com.Mar.test;

import java.io.*;

public class Test02 {
    public static void main(String[] args) throws IOException {
        //字节流转换字符流
        //输出
        //字节流
        OutputStream outputStream = new FileOutputStream( "D:\\ccc.txt", true);
        //转换字符流
        OutputStreamWriter outputStreamWriter = new OutputStreamWriter(outputStream);
        String string = "123松下问童子，言师采药去。只在此山中，云深不知处。";
        outputStreamWriter.write(string);

        //输入
        FileInputStream filelnputStream = new FileInputStream( "D:\\a1.txt");
        InputStreamReader inputStreamReader = new InputStreamReader(filelnputStream) ;
    }
}
```

##### 缓冲流

```java
package com.Mar.test;

import java.io.*;

public class Test02 {
    public static void main(String[] args) throws IOException {
        //缓冲流
                Writer writer = new FileWriter("D:\\ddd.text");
                BufferedWriter bufferedWriter = new BufferedWriter(writer);
                bufferedWriter.write("12松下问童子");
                bufferedWriter.newLine();//换行
                bufferedWriter.write("123松下问童子");
                bufferedWriter.newLine();
                bufferedWriter.close();
                writer.close();

                BufferedReader bufferedReader = new BufferedReader(new FileReader("D:\\ddd.text"));
                String str = null;
                while ((str=bufferedReader.readLine()) != null){
                    System.out. println(str);
                }
        //        String s = bufferedReader.readLine();
        //        System.out.println(s);
        //        String s1 = bufferedReader.readLine();
        //        System.out.println(s1);
        //        String s2 = bufferedReader.readLine();
        //        System.out.println(s2);
                bufferedReader.close();
    }
}
```

##### 读写图片

```java
package com.Mar.test;

import java.io.*;

public class Test02 {
    public static void main(String[] args) throws IOException {
        //读写图片
        FileInputStream fileInputStream = new FileInputStream("D:\\123.jpg");
        File file = new File("D:\\123.jpg");
        int length =(int) file.length();
        System.out.println(file.length());
        byte[] bytes = new byte[length];
        System.out.println(bytes.toString());
        int read = fileInputStream.read(bytes);
        System.out.println(read);
        fileInputStream.read(bytes);
        System.out.println(bytes. toString());
        FileOutputStream fileOutputStream = new FileOutputStream( "D:\\12.jpg");
        fileOutputStream.write(bytes,0,read);
        fileOutputStream.close();
        fileInputStream. close();
    }
}
```

## 十九、多线程

### 1、线程

-   进程：执行的程序，是==重量级==的任务，多任务的一种形式
-   线程：是进程中某个单一顺序的执行流，是==轻量级==的多任务
-   多进程：在操作系统中同时运行多个任务（程序）
-   多线程：在同意应用程序（进程）中有多个执行流同时执行
-   线程的生命周期：一个线程从创建到执行完的整个过程



## 二十
