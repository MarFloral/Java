# Java微服务

原名：OAK

Java之父 詹姆斯·高斯林

Oracle（神谕，甲骨文）

## 一、Java三个体系：

SE（平台标准版），桌面应用程序

EE（平台企业版），面向Internet的应用程序

ME（平台微型版），移动端（智能设备）应用程序

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

扶行字节码，例如java HelloWorld

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

空格没有实际意义，可以利用空格无意义，将代码合理缩进，易读0包含的代码称之为代码块，例如类if(){}、方法{}、类(}等等

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

对象：类的抽象

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

### 7、this

概念：代表调用者（类）本身

作用：

1.  区分局部变量和全局变量
2.  调用本类中的其他方法（普通方法和构造方法）
3.  在调用本类中其他构造方法时，必须写在第一行（第一个“;”前）

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

私有化构造方法

```java
public class Person{
    public static Person person = new Person();//在类的内部实例化对象
    
    private Person(){}//私有化构造方法
    
    public static Person getPerson(){//静态方法访问对象，可以让其他类调用Person
        return person;
    }
}

public class Test{
    Person person = Person.gerPerson();
    Person person1 = Person.getPerson();//访问对象方法
    
    System.out.println(person);
    System.out.println(person1);//输出对象地址
    
    System.out.println(person == person1);//判断地址是否相同，其结果应为true
}
```

### 10、static

==static可以用来修饰属性,叫做静态属性，那么可以通过类名直接调用==，

放在静态区一般用public static修饰

如果一个变量被public static修饰，那一般还会有另外一个关键字final配合使用

==static可以用来修饰方法,叫做静态方法，那么可以通过类名直接调用==

static可以用来修饰类：

-   （非）静态的方法可以访问静态的成员
-   静态的方法不能访问非静态的成员

### 11、12、13、14、

## 十二、十三、