# JavaScript

## 一、功能：

1.  嵌入动态文本于HTML页面。
2.  对浏览器事件做出响应
3.  读写HTML元素
4.  在数据被提交到服务器之前验证数据
5.  检测访客的浏览器信息。 控制cookies，包括创建和修改等
6.  基于Node.js技术进行服务器端编程

## 二、基本语法：

HTML 中的JavaScript 脚本必须位于\<script>\</script>标签之间。\<script>标签可被放置在 HTML 页面的\<body>和\<head>部分中。

```html
<script>
    //标识标签
	alert( "我的第一个JavaScript");//脚本语句
</script>
    //也可以使用外部脚本
<script src="mySssipt·is"></script>
```

### 1、输出语句

```html
<!--window.alert()-->
<!DOCTYPE html>
<html>
    <body>
        <h1>页面</h1>
        <p>段落</p>
        <script>
            //弹出警告框
            window.alert(5 + 6);
            
            //将内容写到HTML文件中
            document.write(Date());
            //请使用document.write()仅仅向文档输出写内容
            //如果在文档已完成加载后执行document.write，整个HTML页面将被覆盖
            
            //写入到浏览器的控制台 （类似日志功能）
            console.log("日志");
            
            //输出带有判断的弹出框
            window.confirm();
            //如果⽤户单击“确定”，该框返回 true。如果⽤户单击“取消”，该框返回 false
            
            //输出提示框
            window.prompt("请输入姓名");
            //如果⽤户单击“确定”，该框返回输⼊值。如果⽤户单击“取消”，该框返回 NULL
        </script>
    </body>
</html>
```

### 2、测试确定/取消

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input type="button" value="测试" onclick="fun()" />
		<script>
			function fun(){
				var content;
				if(confirm("确定 & 取消")){
				     content_true ="您选择了确定";
				     document.write(content_true);
				}else{	
				    content_false ="您选择了取消";
				     document.write(content_false);
				}
			}
		</script>
	</body>
</html>
```

### 3、测试输入框的返回值

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
		<input type="button" value="测试" onclick="fun()" />
		<script>
			function fun() {
				var name = prompt("我最喜欢的球员是：", "姚明");
				if(name == null || name == "") {
					var content_null = "该用户取消了输⼊"
					document.write(content_null);
				} else {
					document.write(name + "⽜逼");
				}
			}
		</script>
	</body>
</html>
```

### 4、测试联系

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<!--<script src="123.js"></script>-->
		<script>
			//弹出框，提示框
			alert("我的第一个JavaScript")
		</script>
	</head>
	<body>
		<h1 id="h1">你好</h1>
		<p>段落</p>
		<p>段落1</p>
		<p>段落2</p>
		<p>段落3</p>
		<!--点击操作-->
		<button onclick="fun()">点击</button>
		<script>
			
			//输出语句（页面控制台查看）
			console.log("记录日志");
			
			//判断提示框，点击确定返回true
			window.confirm();
			
			window.prompt("请输入","123");

			//定义方法
			function fun(){
//				if(confirm（"确定&取消")){
//					console.log("确认");
//				}else{
//					console.log("取消");
//				}
				var name = prompt ("我最喜欢的球员是:");
				if(name==null Ilname== ""）{
					var content_null="该用户取消了输入";
					document.write(content_null);
				}else{
					document .write (name +"牛逼");
				}

			}



			var p = document.getElementsByTagName ("p");
			console.log(p. length)
			for (var i =0;i<p. length;i++){
				console. log("检查"+ p[i].outerHTML)
			}
			
			//获取标签
			var h1 =document.getElementById("h1")
			console.log (h1);
			var a=10.10;
			console.log (typeof a);
			var a="你好js";
			console.log (typeof a);
			a="11";
			console.log (Number (a)+1);
			a="abc";
			console.log (Number (a)+1);
			if(isNaN(a)){
				console. log (1)
			}else{
				console. log (2)
			}
			
			a = "350px"
			console.log (Number (a));
		</script>
		
		<a href="" id="a">百度一下</a>
		<input type="text" id="ipt"><br />

		<script>
			//获取对象
			var a =document.getElementById("a");
			var ipt = document.getElementById("ipt");
			function fun(){
				//修改内容
				a.innerHTML="京东";
				//a.innerText="京东"
				ipt.value = "hello world" ;
				//修改样式
				a.style.color = "green";
				a.style.backgroundColor = "red";
				
				//修改属性
				a . setAttribute ("class","abc");
				a. removeAttribute ( "name");
				var c = a.getAttribute("id");
				console.log(c)

			}
		</script>
	</body>
</html>
```



## 三、四、五、六、七、八、