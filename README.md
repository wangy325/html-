### [网页的基本结构](#网页的基本结构)
### [标签](#标签)
#### [标题](#标题)
#### [特殊符号](#特殊符号)
#### [格式标签](#格式标签)
##### [分组标签](#分组标签)
##### [粗体、斜体文本](#粗体、斜体文本)
#### [链接标签](#链接标签)

### 1 网页的基本结构
```html
    <html>
    	<head>
	    	<title> 网页标题 </title>
	    	<meta charset="utf-8"/> <!--设定字符编码-->
	    </head>
    	<body>
        网页主体
    	</body>
    </html>
```
### 2 标签（Lablels）

#### 2.1 标题

这分别表示网页的6级标题：
```html
    <h1>文字内容</h1>
      ...
    <h6>文字内容</h6>
```
#### 2.2 特殊符号

如**换行符**用`<br/>`表示，在网页中加入**水平线**用`<hr/>`, 插入**空格**一般用`&emsp;`或者`&nbsp;`，还有一些特殊符号如`&gt;`和`&lt;`分别表示“&gt;” 和“&lt;”号

引号`&quot;`；版权符号`&copy;`

#### 2.3 格式标签

##### 分组标签:

```html
    <span style=" "> text </span> /*分组内容可以设置特殊格式（字体，字号，颜色，加粗等等）*/
```

##### 粗体、斜体文本：    
```html

    <strong> 粗体文本</strong>
 
    <em> 斜体文本</em>
```

想玩点不一样的东西，可以试试`< ? style=" ">设置样式的（富）文本</>`，其中"?"代表标签内容，这里面有很多属性值得研究

#### 2.4 链接标签

##### 2.4.1 页面内部链接

先添加链接目的地的标签：
```html
    <a name = "mark"> destnation text </a>
```
再对链接文本建立引用
```html
    <a href = "mark"> link text </a>
```
##### 2.4.2 外部链接
```html
    <a> href = "path" target = "_self(_blank)"</a>
```    
##### 2.4.3 图片引用：
```html
    <img src="path" alt="replace text(img url is null)" title = "promote info" width = "x" height = "y"/>
```    
### 3 列表和表格

#### 3.1 列表（list）

##### 3.1.1 order-list
```html
	<ol type="A/a/I/i/1"> /*有序列表5大排序方式，数字默认*/
		<li > content </li>
		...
		<li> content </li>
	</ol>
```		
##### 3.1.2 disorder-list
```html
	<ul type="disc"> /*无序列表3种排序方式，默认实心圆圈*/
		<li type="disc(default)/circle/square"> content </li>
		...
		<li> content </li>
	</ul> 
```		
>*在css样式中，可以设置列表的样式*
```
	ul{
		list-style:none; /*取消列表前面的排序*/
		margin:0px;
		padding-left:0px auto; /*外间距和内边距设置，控制ul的强制缩进（不让其缩进）*/
	}
```		
##### 3.1.3 define-list
```html
	<dl> /*目前已知适用功能 可以控制悬挂缩进,如上所述*/
		<dt> content
			<dd>
				content
			</dd>
		</dt>
	</dl>
```		
#### 3.2 表格（table）

##### 3.2.1 basical format

基本格式：
```html
	<table>
		<tr >
			<td>
				单元格内容
			</td>
		</tr>
	
	</table>
```
基本属性：
```
	align="left(default)/center/right" /*水平对齐方式*/

	valign="top/middle(default)/bottom/baseline" /*垂直对齐方式*/

	rowspan="x" /*跨行*/

	colspan="y" /*跨列*/
```
##### 3.2.2 A typical table style code 典型的css样式列表 
```html
	<style type="text/css"> /* 表格全局设定，优先级低于表格正文的设定 , 对现网页内所有表格生效*/
			
	table {
		width: 800px; height: 300px; 
          
		margin:0px auto; /* 顶端边距0px， 左右居中*/
         
		border-spacing: 0px; /*单元格边距调为0px，将单元格边界重合（默认不重合）*/
         
		border-collapse:collapse; /*接上个设定，将重合的单元格边界只显示一个（去掉线条颜色加深）*/ 
          
		color: black;/*设定文本颜色，优先级低，table内可以重新定义颜色*/ 
	}
	
	 td {
		border: 1px dashed blue; /*显示单元格边界，1px黑色虚线（实线为solid），只能在td下设置*/
        
		text-align: center; /*设定文本对齐方式，优先级高于table 内设定*/
		
		**！！这是css样式属性，table内设定algin是表格属性，2者不存在优先级问题，下同 **
        
		border-style:dotted; /*设定单元格边界样式，同第一个设定相同，优先级高*/
        
		border-color: black; /*设定单元格边框颜色，同第一个设定相同，优先级高*/
				
	}
			
	.a{
		background-color:beige; /* 设定分组a的背景颜色*/
        
		/*text-align: left; 设定分组的对齐方式*/	
	}
			
	.b{
		background-color: honeydew; /* 设定分组b的背景颜色*/
	}
 	</style>
```

##### 3.2.3 2种使其生效的方法：

1）code it within `<head> </head>`
```html
			
	<head>
		<title> title </title>
				
		<style type="text/css"> 
					
			type setting
		</style>
	</head>
```
2) firstly, creat a new `.css `file, and then write the 
```
				
	<style type="text/css">
					
		type setting
	</style>

```
 into the file;
				
 secondly,  quote the css file by using code below

				
	<link rel="stylesheet" type="text/css" href="filename.css"/>
  

##### 3.2.4 table nesting 表格嵌套

```html	
	<table>
		<tr>
			<td>
				<table>
					<tr>
						<td> content1</td>
					</tr>
					<tr>
					<tr>
						<td>content2</td>
					</tr>
				</table>				
			</td>
		</tr>
		<tr>
			<td>
				no nesting here
			</td>
		</tr>
	</table>
```
### 4 表单
#### 4.1表单基本表现
```html
	<form method="post/get" action=""> /* "action"表示向何处发送数据*/
	
		<input type="" ...>
	
		<select name="">  /*下拉列表框至少有一个option*/
	
			<option value="" selected="selected">下拉选项（选中）</option>
	
			...
	
		</selected>
	</form>

```
#### 4.2 表单的type属性
>text，指定为普通文本框 默认属性
>
>password 指定为密码框（隐藏输入内容）
>
>checkbox 指定为多选框
>
>radio 指定为单选框 /*单选框属于一个类别，其name属性必须相同*/
>
>submit 提交按钮 /*文本框和按钮在同一个form里面，按钮功能生效*/
>
>reset 重置按钮
>
>image 图片按钮
>
>button 普通按钮 /*实现功能需要指定oneclick事件*/
>
>file 文件域，用于选择上传文件
>
>hidden 隐藏框 /*具体意义？*/
>
>...

#### 4.3 文本域
```html
	<textarea  name="showText"  cols="x"  rows="y">文本内容 </textarea >
	/*样式设置： style="resize:none;" 可固定文本域大小*/
```
#### 4.4 fieldset 和label 标签
```html
	<fieldset>
		<legend>表单名</legengd> /*用于制作带标题的边框*/
		<input type="text" >
		...
	</fieldset>

	<lable for="id">提示文本</label>
		<input type="text" name="gen" value="" id="id" > /*如果在 label 元素内点击文本，就会触发此控件。*/
 ```
>贴士：利用fieldset制作带标题的边框的时候，可以设置margin-style来设置表单名的缩进

#### 4.5 关于列表，表单，div css的综合应用几点总结

1.[网易邮箱登录页面](https://github.com/wangy325/html-note/blob/master/3-%E8%A1%A8%E5%8D%95/netease.html)
是对div设计网页的一次大胆探索。网页设计的过程中对css样式的引用**杂乱不堪**，既有行内引用，也有基于`.css`样式的外部引用。刚开始，对css还不是很熟练。
		
2.[阿里巴巴注册页面](https://github.com/wangy325/html-note/blob/master/3-%E8%A1%A8%E5%8D%95/alibaba.html)
是利用div和table设计网页的代表，这里利用table较为合理地规避了提示信息和表单的对齐问题。这里特别要补充的一点是：`网页的页头部分，可以用一个div实现的`，需要做好的就是理解好[盒子模型](https://www.w3.org/TR/CSS22/box.html)的内涵，本次设计中，利用了嵌套的div和表格的方式实现，略显繁琐。

3.[人人注册页面](https://github.com/wangy325/html-note/blob/master/3-%E8%A1%A8%E5%8D%95/renren.html)已经是一个利用div实现网页设计很完美的例子了，前面说的网页head部分，也用一个div搞定了。唯一不足之处在于，右边**热门主页**和**游戏**这两个板块，中间还是用了table实现。这里用table实现确实很容易理解，其实用div也是完全可以实现的，把照片和名字用一个div套起来，就可以了。此外还有一种用无序列表(ul)实现的方式，具体的代码可参见[图片+文本](https://github.com/wangy325/html-note/blob/master/3-%E8%A1%A8%E5%8D%95/%E5%A4%B4%E5%83%8F%2B%E6%96%87%E5%AD%97.html)

4.[新浪资料修改](https://github.com/wangy325/html-note/blob/master/3-%E8%A1%A8%E5%8D%95/sina.html)这个网页虽然没用到table 但是div用的很乱。但是将文本和表单分开为两个div某种意义上提升了编辑效率。	

5.[qq注册页面](https://github.com/wangy325/html-note/blob/master/3-%E8%A1%A8%E5%8D%95/acount-apply.html)是利用div和css设计网页最好的例子，虽然运用的东西并不多，但网页结构明朗。	

### 5 [CSS](https://www.w3.org/TR/CSS22/)(cascading style sheet 层叠样式表)样式总结

#### 5.1 选择器

##### 标签选择器

```css
p{
	font: 16px bold Italic;
	color：red；
	text-decoration：underline(none)
}
```

##### 类(class)选择器

```css
.class{
	padding:0px auto;
}
```

##### ID选择器

```css
#id{
	background-color:#800000;
	}
```

**ID选择器在同一个页面中只能用一次**

#### 5.2 样式优先级

* 行内样式>内部样式>外部样式

* ID选择器>类选择器>标签选择器

**并不是所有的属性都可以写在css样式里面，或者说（表格/列表）的某些属性就是html
属性，并不是css样式属性，切不要混淆了**

**`!important` 可以提升样式的优先级**

#### 5.3 高级选择器

* 通用选择器

* 子选择器（ul>li）`第一代子元素套用样式`

* 后代选择器（.class p）`某个特定的类里面的p段落套用样式` 

* 交集选择器（div.class）`most used`

* 并集选择器（div,p,li） `已用于设置全局文本格式`

* 相邻选择器 `选择紧接在另一个元素后的元素，而且两者有相同的父元素，可以使用相邻兄弟选择器`

#### 5.4 常用样式属性

##### 5.4.1 字体样式
```html
font-family:times new roman "楷体"；

font-size:16px(in cm mm pt);

font-style:italic(oblique, normal);

font-weight:bold(er) light(er) normal;

all in one: font:style weight size family;

```
##### 5.4.2 文本样式
```html
color:red(#00c);

text-align:left/center/right/justify;

text-indent:20px/2em;

line-height:20px;

text-decoration：underline/overline/line-through/blink/none;

vertical-align:middle/top/bottom; `设置图片和文本居中对齐`

letter-sapcing：字符间距

word-spacing：单词间距
```

##### 5.4.3 背景样式
```html
background-color:red/transparent;

background-image: url(...);

background-repeat:repeat/no-repeat/repeat-x(y)；

background-position:x% y% / left/center/right top/middle/right;

all in one:background:color image position repeat;

```
##### 5.4.4 列表样式
```html
list-style-type:none/disc/circle/square/decimal;

list-style-image:url();

list-style-position:inside/outside;

all in one:list-style:type position image;

```

##### 5.4.5 [伪类(Pseudo-classes)](https://www.w3.org/TR/CSS22/selector.html#pseudo-elements)

Add special effect to some selecters.

Syntax:selecter(Elemment):pseudo-class{property:value;}

* 超链接伪类（锚伪类）

	* a:link {color:#ff0000;} /*未单击访问时超链接样式*/

	* a:visited {text-decoration: line-through} /*访问后的样式*/

	* a:hover {background-color:yello;} /*鼠标悬停时的样式*/

	* a:active {color：purple;} /*鼠标单击未释放的样式*/
	
> 伪类可以和CSS类配合使用
>
>	`a.red : visited {color: #FF0000}`
>
>	`<a class="red" href="css_syntax.asp">CSS Syntax</a>`
>
>关于hover制作画框的用法，参见[css-gallary.html](https://github.com/wangy325/html-note/blob/master/%E4%BC%AA%E7%B1%BB%EF%BC%88pseudo-classes%EF%BC%89/css-gallery.html)
>
>说明的是要注意`position`属性值`relative`和`absolute`之间的差异，以及，`relative`属性值生效的前提是，block区块的的``height`值不能设置。

* :first-child
	
>The `:first-child` pseudo-class matches an `element` that is the `first child element` of `some other element`.

```html
			<!DOCTYPE html>
			<html>
				<head>
					<meta charset="utf-8" />
					<title>:first-child</title>
					<style type="text/css">
						   p:first-child { text-transform: uppercase ;}  /*设置所有元素的第一个<p>子元素为大写*/
						  
			/*equals to*/  * > p:first-child{text-transform: uppercase;}

						   div > p:first-child {font-weight: bold;} /*设置所有div元素的第一个<p>子元素字体加粗*/
						  
						   p:first-child em { font-weight : bold } /*设置所有<p>元素的第一个<em>子元素为粗体*/
						   /*等价于  p > em:first-child { font-weight : bold }*/
					</style>
				</head>
				<body>
					<P> The <em>last</em> P before the note.</p> <!--此行会变成大写-->
					<DIV class="note">
						<!--<H2>Note</H2>--> <!--此行存在时，下面<p>元素非为此div的第一子元素-->
					   <P> The first P inside the note.</P>
					</DIV>
					<div class="quote">
						<p> A light heart lives long. </p>
						<p> You are <em>apple</em> in my eyes.</p>
					</div>
				</body>
			</html>
```

* [:last-child](https://css-tricks.com/almanac/selectors/l/last-child/) 
	
>Allows you to target the last element directly inside its containling element.指定父元素的最后一个子元素的格式，如果指定的子元素错误（不存在），则属于无效设置
		
```html			
	p:last-child{fontsize:0.75em;} /*指定最后一个p段落子元素的字号为0.75em*/
				
	<article>
	  <p>Lorem ipsum...</p>
				  
	  <p>Dolor sit amet...</p>
				  
	  <p>Consectetur adipisicing...</p>
				  
	  <!--<span>Last paragraph...</span>--> <!--若此行存在，则上述伪类设置无效-->
				  
	</article>
```				
			
>关于`:lsat-child`和`:last-of-type`的区别，参见[*it targets a particular type of element in a particular arrangement*](https://css-tricks.com/almanac/selectors/l/last-of-type/)
>
>上述代码块，若样式改为`p:last-of-type{fontsize:0.75em}`，且<span>行存在，也能找到<p>段落
	
*[:only-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child)
	
>represents an element without any siblings. This is the same as :first-child:last-child or :nth-child(1):nth-last-child(1), but with a lower specificity.	
	
*[:nth-child(2n-1)](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)
	
>matches one or more elements based on their position among a group of siblings.
>
>更多多信息参考伪类文件夹中[nth-child.html](https://github.com/wangy325/html-note/blob/master/%E4%BC%AA%E7%B1%BB%EF%BC%88pseudo-classes%EF%BC%89/nth-child.html)
	
	
* 伪元素（pseudo-elements）

* [:first-letter(css2)/::first-letter(css3)](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter)

    >applies styles to the first letter of the first line of a block-level element, but only when not preceded by other content (such as images or inline tables).
    >
    >[百度音乐标签](https://github.com/wangy325/html-note/blob/master/4-%E7%9B%92%E5%AD%90%E5%92%8CCSS/musictags.html#L22)用到了此伪类。
	
* :first-line
	
* :after
	
* :before
	
* 设置鼠标形状 （cursor：pointer）
	* default
	
	* pointer
	
	* wait
	
	* help
	
	* text
	
	* crosshair
	
		
