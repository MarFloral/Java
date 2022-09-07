



# HTML

Html是 Hyper text mark language，是超文本标记语言。是用来编写网页的标记语言。最主要的目的是提供网页内容。**不做美化**。

超文本:一个是超越普通文本，电子档，可以通过超链接把不同地域，不同类型的各种资源集合到一起，好像在本地浏览一样。信息共享，信息传递，丰富多彩的效果，比如 flash,视频。

Mark Language：它是一门基于标记（标签、元素）的语言。。

结论:html,学习非常简单，就是学习一些标记和属性。

html的编写用任何文本编辑器都可以，是基于ascii,编码的。后缀名是.html、.htm、xhtml dhtml等

html 是web标准，web标准是一系列的标准，比如html，css，javascript等。

## 常用标签：

### 1、骨架标签：

骨架标签分4个：**html，head，title，body**。基本所有的html网页都应该包含以上4个标签。

注意：

1.  标签一般成对出现

2.  标签可以多重嵌套，但是不能交叉嵌套

3.  所有的html标签都应该出现在<html></html>内部.

4.  html源代码中的效果和网页呈现效果是不一样的。比如在html源代码中换行在网页是没有效果的，道理很简单：html是由浏览器解释执行，浏览器只认识html标签。源代码中敲入的回车换行浏览器不认识。所以在html中想要做事情要找标签，并且要用合适的标签标记合适的内容。

5.  html中的基本概念：标签、属性、元素。

    -   标签分类：单标签(有属性和没属性)，双标签

    -   属性：可以用来附加一些信息给标签，比如颜色、外观，位置等等。

```html
<html>
    <head>
        <title></title>
    </head>
    <body>
        
    </body>
</html>
```

### 2、常见的单标记和双标记

#### 1、文本格式标记

```html
<!--换行标记，单标记-->
	<br/>

<!--粗体文本标记，双标记-->
	<b></b>

<!--倾斜文本标记，双标记-->
	<i></i>

<!--下划线标记，双标记-->
	<u></u>

<!--强调显示标记（斜体），双标记-->
	<em></em>

<!--加强调显示标记（加粗），双标记-->
	<strong></strong>

<!--水平线标记，单标记-->
	<hr />

<!--空格-->
	&nbsp;
<!--小于号-->
	&lt; 
<!--大于号-->
	&gt; 
<!--&-->
	&amp; 
<!--双引号-->
	&quot; 
<!--版权-->
	&copy; 
<!--注册-->
	&reg;

```

#### 2、标题标签

```html
<h1></h1>---<h6></h6>
<!--
其中<h1></h1>代表1级标题，级别最高，字体也最大，
其他标题依次递减，<h6></h6>级别最低。
标题对齐方式属性:align
属性值：left（左对齐）, center（居中对齐）, right（右对齐）
-->

```

#### 3、段落标签

```html
<!--段落标记，双标记，定义网页中的一段文本-->
<p></p>
<!--align：段落对齐方式：left左对齐, center居中, right右对齐-->

```

#### 4、图像标签

```html
<!--插入图像，单标记-->
<img src="图片路径" alt="" width="" height="" border="" title="" />
<!--属性：
（1）src属性
	指定图片源文件的路径

（2）alt属性
当图像非正常显示时，在图像的位置上显示alt中的提示文字

（3）width属性
	图像宽度,默认单位为像素

（4）height属性
	图像高度,默认单位为像素

（5）border属性
	图像的边框，默认单位为像素

（6）title属性
    鼠标滑过时显示的文字提示
-->

```

#### 5、超链接

 是指从一个网页指向一个目标的链接关系，这个目标可以是网页、图片等。

1)   **为什么会有超链接？**

超级链接在本质上属于一个网页的一部分，它是一种允许我们同其他网页或站点之间进行连接的元素。各个网页链接在一起后，才能真正构成一个网站。

2)   **如何使用超链接**

```html
<!--1）超链接的标签-->
<a></a>

<!--2）超链接href属性，用来指定链接的地址-->

<!--3）超链接target属性，目标文件的打开方式-->
	<a href="链接的路径" target="目标窗口或指定值">链接的文本</a>
<!--target属性值可以是_blank、_self、_top、_parent
_self在原窗口中打开，为默认值。_blank在新窗口打开-->

<!--4）使用超链接静态整站的建立-->

<!--5）空连接：#-->
<a href="#">新闻</a>

<!--6） 外部链接地址前要加http:// -->  
<a href="http://www.baidu.com">百度一下</a>
```

#### 6、列表

##### 1）无序列表

1)   **什么是无序列表？**

无序列表就是列表项没有先后顺序的列表形式。

2)   **为什么要有无序列表？**

列表的使用，能从语义上为意义相关的内容分组。

3)   **如何应用无序列表标签？**

```html
<ul type="">
    
    <li>无序列表项</li>
    
    <li>无序列表项</li>
    
    <li>无序列表项</li>
    
</ul>

<!--默认情况下无序列表的列表符号用圆点表示-->
<!--type规定列表的案例符号的类型：
disc（默认实心圆）
square（小正方形）
circle（空心圆）
-->
```

##### 2）有序列表

1)   **什么是有序列表？**

有序列表的概念：有序列表就是列表项有先后顺序的列表形式

2)   **为什么要有无序列表？**

列表的使用，能从语义上为意义相关的内容分组。

3)   **如何应用有序列表标签？**

```html
<ol type="" reversed="">

    <li>有序列表项</li>

    <li>有序列表项</li>

    <li>有序列表项</li>

    <li>有序列表项</li>

</ol>
<!-- type：规定在列表中使用的标记类型：
值：1（默认）、 a、 A、I、i

reversed：用于指定列表倒序显示

start：用于指定有序列表的起始值（只能是数字）
-->
```

#### 7、自定义列表

```html
<!--语法-->
<dl>
    <dt>上层案例</dt>
    <dd>下层案例</dd>
</dl>
<!--自定义列表标签（定义项<dt></dt>、描述项<dd></dd>）-->
```

#### 8、表格

##### 1）语法

```html
<!--表格基本语法-->
    <table><!--表格标签-->
        <tr><!--行标签-->
            <td></td><!--列标签-->
        </tr>
        <tr><!--行标签-->
            <td></td><!--列标签-->
        </tr>
    </table>
```

##### 2）属性：

```html
<!--table属性-->
	<table width="" height="" align="" border="" bgcolor="" background="" cellspacing="" cellpadding=""></table>

<!--
宽高：width、height（单位是像素或百分比）
对齐：align
外边框：border            
背景色：bgcolor           
背景图片：background        
单元格与单元格间距：cellspacing       
单元格边距：cellpadding（表格边框与内容的间距）
-->

<!--tr属性-->
<tr align="" valign="" bgcolor=""></tr>
<!--
align      水平对齐left/center/ right
valign  垂直对齐Top/middle/bottom
bgcolor 背景色
-->

```





#### 9、10、11、12、13、

```html
<!DOCTYPE html><!--声明标签-->
<html>
    <head>
        <meta charset="utf-8"/>
        <title>sjt2207</title><!--web网页题目-->
        <!--书写css代码-->
        <style>
        	/*行内样式>id选择器>类选择器>标签选择器>全局选择器*/
        	/*全局选择器*/
        	*{
        		/*颜色表示方式：单词 16进制代码 rgb()*/
        		color: #123adf;
        	}
        	/*标签选择器*/
        	a{
        		color: green;
        	}
        	p{
        		color: yellow;
        	}
        	/*class选择器（类选择器）*/
        	.p1{
        		color: purple;
        	}
        	/*id选择器：*/
        	#h1{
        		color: red;
        	}
        	.ss{
        		color:#00FFFF;
        		font:small-caps 30px ;
        		font-style: italic;/*倾斜*/
        		font-size:20px;/*大小*/
        		font-weight: 100;/*粗细*/
        		font-family: "楷体";/*字体*/
        	}
        </style>
    </head>
    
    <body>
        你好网页
        <span>空标签</span>
        <h1 class="ss">标题标签<!--h1到h6--></h1>
        <p>段落&nbsp;标签（文本到页面边换行）</p>
        <p class=p1>段落&nbsp;标签（文本到页面边换行）</p>
        <p>段落&nbsp;标签（文本到页面边换行）</p>
        <br /><!--换行-->
        <!--超链接-->
        <a href = "https://www.baidu.com/">百度一下</a>
        <a target=" parent" href="https://www.taobao.com/">淘宝</a>
        
        <h1 class=p1 align="right">我是标题标签</h1><!--右对齐-->
        <h6 class=p1 id=h1 style = "color: black;"align="center">我是h6标题标签</h6><!--居中-->
        
        <!--图片-->
        <img src = "../img/1658124995753.jpg" width="100px"  alt="海报">
        <!--src：'alt+/'提示路径 width：宽（不写高时默认等比例缩放）height：高 alt：提示文字-->
        
        <hr size="5px" noshade="noshade" width="500px" align="left"/>
        <!--分割线	size：宽度	noshade：重色	width：像素	align：对其方式-->
        
        <!--border：边框	cellpadding：单元格内容与边沿的间距	cellspacing：表格单元格之间的间距-->
        <table class=p1 border= "1px" cellpadding="Opx" cellspacing="0px"><!--表格-->
            <tr>
                <td bgcolor="aquamarine">序号</td>
                <td>姓名</td>
                <td>性别</td>
            </tr>
    		<tr>
                <td bgcolor="darkmagenta">1</td>
                <!--colspan：横向合并-->
                <td>张三</td>
                <!--<td>男</td>-->
        	</tr>
        	<tr>
                <td>1</td>
                <td>张三</td>
                <!--rowsqan：纵向合并-->
                <td >男</td>
        	</tr>
        	<tr>
                <td>1</td>
                <td>张三</td>
                <td>男</td>
        	</tr>
        </table>
        <!--无序列表	type="square"标点-->
        <ul type="square">
        	<li>无序列表内容1</li>
        	<li>无序列表内容2</li>
        	<li>无序列表内容3</li>
        </ul>
        <!--有序列表	reversed：倒序	start：规定起始值		type：排序方式（数字，罗马数字，字母）-->
        <ol reversed="reversed" start="5" type="1">
        	<li>有序列表内容1</li>
        	<li>有序列表内容2</li>
        	<li>有序列表内容3</li>
        </ol>
        
        <!--表单域	action：提交地点	method：提交方式-->
        <form  action="https://www.baidu.com/" method="post">
        	<!--多功能框-->
        	<!--input：输入	type：格式-->
        	姓名：<input type="text" name="name"/><br />
        	
        	<!--password：输入不显示数值-->
        	密码：<input type="password" name="password"/><br />
        	
        	<!--redio：单选框	name：需要限定接收值，限制单选-->
        	性别：<input type="radio" name="sex"/>男
        	<input type="radio" name="sex"/>女<br />
        	
        	<!--checkbox：多选框（没有name限制）-->
        	爱好：<input type="checkbox"/>篮球
        	<input type="checkbox"/>乒乓球
        	<input type="checkbox"/>学习
        	<input type="checkbox"/>睡觉<br />
        	
        	<!--file：文件-->
        	头像上传：<input type="file" /><br />
        	
        	<!--select：下拉框	option：选项-->
        	地址：<select>
        		<option>--请选择--</option>
        		<option>--山西--</option>
        		<option>--山东--</option>
        		<option>--北京--</option>
        	</select><br />
        	
        	<!--date：时间（年月日）-->
        	时间：<input type="date" /><br />
        	
        	<!--textarea：文本域		cols：初始行字	rows：初始行数-->
        	备注：<textarea cols="30" rows="5"></textarea><br />
        	
        	<!--把表单的内容提交到指定的地方url-->
        	<button>按钮</button>
        	<input type="submit" value="提交"/>
        	<!--重置当前表单输入的内容-->
        	<input type="reset" value="重置"/>
        </form>
    </body>
</html>
```

### 3、4、5、6、

# css

## css选择器

```html
<style>
        	/*行内样式>id选择器>类选择器>标签选择器>全局选择器*/
        	/*全局选择器*/
        	*{
        		/*颜色表示方式：单词 16进制代码 rgb()*/
        		color: #123adf;
        	}
        	/*标签选择器*/
        	a{
        		color: green;
        	}
        	p{
        		color: yellow;
        	}
        	/*class选择器（类选择器）*/
        	.p1{
        		color: purple;
        	}
        	/*id选择器：*/
        	#h1{
        		color: red;
        	}
        	.ss{
        		color:#00FFFF;
        		font:small-caps 30px ;
        		font-style: italic;/*倾斜*/
        		font-size:20px;/*大小*/
        		font-weight: 100;/*粗细*/
        		font-family: "楷体";/*字体*/
        	}
        </style>
```




```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title>css</title>
        <!--外联样式-->
        <!--<link href="../css/css.css" rel="stylesheet" type="text/css" />-->
        <style>
            table {
                /*background-image: url(../img/1658124995753.jpg);*/

                /*不重复，repeat-x：横向重复repeat-y：纵向重复*/
                /*background-repeat: no-repeat;*/

                /*position定位：水平 垂直移动距离，可写百分值*/
                /*background-position: 100px 200px;*/

                /*图片固定*/
                /*background-attachment: fixed;*/

                /*background简写属性：*/
                opacity: 0.5;
                background: url(../img/1658124995753.jpg) no-repeat right top;
                width: 1000px;
                height: 1000px;
            }
            p{
                color: #00FFFF;
                text-align:justify;
                direction: rtl;
                unicode-bidi: bidi-override;
            }
        </style>
    </head>

    <body>
        <img src="../img/1658124995753.jpg" >
        <table border="1px" cellpadding="Opx" cellspacing="0px">
            <!--表格-->
            <tr>
                <td>序号</td>
                <td>姓名</td>
                <td>性别</td>
            </tr>
            <tr>
                <td>1</td>
                <td>张三</td>
                <td>男</td>
            </tr>
            <tr>
                <td>1</td>
                <td>张三</td>
                <td>男</td>
            </tr>
            <tr>
                <td>1</td>
                <td>张三</td>
                <td>男</td>
            </tr>
        </table>
    </body>
</html>
```
