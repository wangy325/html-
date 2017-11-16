目录
======
* [1 网页的基本结构](#1)
* [2 标签](#2)
	* [2.1 标题](#2.1)
	* [2.2 特殊符号](#2.2)
	* [2.3 格式标签](#2.3)
		* [2.3.1 分组标签](#2.3.1)
		* [2.3.2 粗体、斜体文本](#2.3.1)
	* [2.4 链接标签](#2.4)
		* [2.4.1 页面内部链接](#2.4.1)
		* [2.4.2 外部链接](#2.4.2)
		* [2.4.3 图片引用](#2.4.3)
* [3 列表和表格](#3)
	* [3.1 列表](#3.1)
		* [3.1.1 有序列表](#3.1.1)
		* [3.1.2 无序列表](#3.1.2)
		* [3.1.3 定义列表](#3.1.3)
	* [3.2 表格](#3.2)
		* [3.2.1 基本格式](#3.2.1)
		* [3.2.2 典型的css样式列表](#3.2.2)
		* [3.2.3 2种使其生效的方法](#3.2.3)
		* [3.2.4 表格嵌套](#3.2.4)
* [4 表单](#4)
	* [4.1 表单基本表现](#4.1)
	* [4.2 表单的type属性](#4.2)
	* [4.3 文本域](#4.3)
	* [4.4 fieldset和label标签](#4.4)
	* [4.5 关于列表，表单，div css的综合应用几点总结](#4.5)
* [5 CSS(cascading style sheet 层叠样式表)](#5)
	* [5.1 选择器](#5.1)
		* [5.1.1 标签选择器](#5.1.1)
		* [5.1.2 类(class)选择器](#5.1.2)
		* [5.1.3 ID选择器](#5.1.3)
	* [5.2 样式优先级](#5.2)
	* [5.3 高级选择器](#5.3)
	* [5.4 常用样式属性](#5.4)
		* [5.4.1 字体样式](#5.4.1)
		* [5.4.2 文本样式](#5.4.2)
		* [5.4.3 背景样式](#5.4.3)
		* [5.4.4 列表样式](#5.4.4)
		* [5.4.5 鼠标样式](#5.4.5)
	* [5.5 伪类](#5.5)
		* [5.5.1 超链接伪类（锚伪类）](#5.5.1)
		* [5.5.2 元素伪类](#5.5.2)
* [6 文档流，浮动和定位](#6)
	* [6.1 文档流](#6.1)
	* [6.2 浮动](#6.2)
	* [6.3 定位](#6.3)
	

===============

<h2 id="1"> 1 网页的基本结构</h2>

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
<h2 id="2"> 2 标签（Lablels）</h2>

<h3 id="2.1">2.1 标题</h3>

这分别表示网页的6级标题：
```html
<h1>文字内容</h1>
   ...
<h6>文字内容</h6>
```
<h3 id="2.2">2.2 特殊符号</h3>

如**换行符**用`<br/>`表示，在网页中加入**水平线**用`<hr/>`, 插入**空格**一般用`&emsp;`或者`&nbsp;`，还有一些特殊符号如`&gt;`和`&lt;`分别表示“&gt;” 和“&lt;”号

引号`&quot;`；版权符号`&copy;`

<h3 id="2.3">2.3 格式标签</h3>

<h4 id="2.3.1">分组标签</h4>

```html
<span style=" "> text </span> /*分组内容可以设置特殊格式（字体，字号，颜色，加粗等等）*/
```

<h4 id="2.3.2">粗体、斜体文本</h4>

```html

<strong> 粗体文本</strong>
 
<em> 斜体文本</em>
```

*想玩玩不一样的东西？可以试试`< ? style=" ">设置样式的（富）文本</>`，其中"?"代表标签内容，这里面有很多属性值得研究*

<h3 id="2.4">2.4 链接标签</h3>

<h4 id="2.4.1">2.4.1 页面内部链接</h4>

先添加链接目的地的标签：

```html
<a name = "mark"> destnation text </a>
```
再对链接文本建立引用

```html
<a href = "mark"> link text </a>
```
<h4 id="2.4.2">2.4.2 外部链接</h4>

```html
<a href = "path" target = "_self(_blank)">链接文字</a>
``` 

<h4 id="2.4.3">2.4.3 图片引用</h4>

```html
<img src="path" alt="replace text(img url is null)" title = "promote info" width = "x" height = "y"/>
```

<h2 id="3">3 列表和表格</h2>

<h3 id="3.1"> 3.1 列表（list）</h3>

<h4 id="3.1.1">3.1.1 order-list</h4>

```html
<ol type="A/a/I/i/1"> /*有序列表5大排序方式，数字默认*/
	<li > content </li>
	...
	<li> content </li>
</ol>
```		
<h4 id="3.1.2">3.1.2 disorder-list</h4>

```html
<ul type="disc"> /*无序列表3种排序方式，默认实心圆圈*/
	<li type="disc(default)/circle/square"> content </li>
	...
	<li> content </li>
</ul> 
```		
>*在css样式中，可以设置列表的样式*

```css
ul{
	list-style:none; /*取消列表前面的排序*/
	margin:0px;
	padding-left:0px auto; /*外间距和内边距设置，控制ul的强制缩进（不让其缩进）*/
}
```		
<h4 id="3.1.3">3.1.3 define-list</h4>

```html
<dl> /*目前已知适用功能 可以控制悬挂缩进,如上所述*/
	<dt> content
		<dd>
			content
		</dd>
	</dt>
</dl>
```		
<h3 id="3.2">3.2 表格（table）</h3>

<h4 id="3.2.1">3.2.1 basical format</h4>

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

<h4 id="3.2.2">3.2.2 A typical table style code 典型的css样式列表 </h4>

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
        
	text-align: left; /*设定分组的对齐方式*/	
}
			
.b{
	background-color: honeydew; /* 设定分组b的背景颜色*/
}
</style>
```

<h4 id="3.2.3">3.2.3 2种使其生效的方法</h4>

1. code it within `<head> </head>`
```html
<head>
	<title> title </title>				
	<style type="text/css"> 			
		type setting
	</style>
</head>
```
2. firstly, creat a new `.css `file, and then write the 
```css		
<style type="text/css">					
	type setting
</style>

```
into the file;
				
secondly,  quote the css file by using code below
			
	<link rel="stylesheet" type="text/css" href="filename.css"/>
  
<h4 id="3.2.4">3.2.4 table nesting 表格嵌套</h4>

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

<h2 id="4">4 表单</h2>

<h3 id="4.1">4.1表单基本表现</h3>

```html
<form method="post/get" action=""> /* "action"表示向何处发送数据*/
	
	<input type="" ...>
	
	<select name="">  /*下拉列表框至少有一个option*/
	
		<option value="" selected="selected">下拉选项（选中）</option>
	
		...
	
	</selected>
</form>

```
<h3 id="4.2">4.2 表单的type属性</h3>

>text，指定为普通文本框 默认属性
>
>password 指定为密码框（隐藏输入内容）
>
>checkbox 指定为多选框
>
>radio 指定为单选框 	/*单选框属于一个类别，其name属性必须相同*/
>
>submit 提交按钮 	/*文本框和按钮在同一个form里面，按钮功能生效*/
>
>reset 重置按钮
>
>image 图片按钮
>
>button 普通按钮 	/*实现功能需要指定oneclick事件*/
>
>file 文件域，用于选择上传文件
>
>hidden 隐藏框 	/*具体意义？*/
>
>...

<h3 id="4.3">4.3 文本域</h3>

```html
<textarea  name="showText"  cols="x"  rows="y">文本内容 </textarea >
/*样式设置： style="resize:none;" 可固定文本域大小*/
```
<h3 id="4.4">4.4 fieldset和label 标签</h3>

```html
<fieldset>
	<legend>表单名</legengd> /*用于制作带标题的边框*/
	<input type="text" >
	...
</fieldset>

<lable for="id">提示文本</label>
<input type="text" name="gen" value="" id="id" > /*如果在 label 元素内点击文本，就会触发此控件。*/

/*</lable>标记也可以在`input`标签后面*/

/*也可把`label`标签写在`input`标签后面，这样，文字就在控件后面（前者是文字在前，控件(选框)在后。）*/
 ```
 
>贴士：利用fieldset制作带标题的边框的时候，可以设置`margin-style`来设置表单名(文字)的缩进

<h3 id="4.5">4.5 关于列表，表单，div css的综合应用几点总结</h3>

1.[网易邮箱登录页面](/3-表单/netease.html)
是对div设计网页的一次大胆探索。网页设计的过程中对css样式的引用**杂乱不堪**，既有行内引用，也有基于`.css`样式的外部引用。刚开始，对css还不是很熟练。
		
2.[阿里巴巴注册页面](/3-表单/alibaba.html)
是利用div和table设计网页的代表，这里利用table较为合理地规避了提示信息和表单的对齐问题。这里特别要补充的一点是：`网页的页头部分，可以用一个div实现的`，需要做好的就是理解好[盒子模型](https://www.w3.org/TR/CSS22/box.html)的内涵，本次设计中，利用了嵌套的div和表格的方式实现，略显繁琐。

3.[人人注册页面](/3-表单/renren.html)已经是一个利用`div`实现网页设计很完美的例子了，前面说的网页head部分，也用一个`div`搞定了。唯一不足之处在于，右边**热门主页**和**游戏**这两个板块，中间还是用了`table`实现。这里用`table`实现确实很容易理解，其实用`div`也是完全可以实现的，把照片和名字用一个`div`套起来，就可以了。此外还有一种用无序列表(ul)实现的方式，具体的代码可参见[图文排版](/3-表单/头像+文字.html)

4.[新浪资料修改](/3-表单/sina.html)这个网页虽然没用到`table` 但是`div`用的很乱。但是将文本和表单分开为两个`div`某种意义上提升了编辑效率。	

5.[qq注册页面](/3-表单/acount-apply.html)是利用`div`和`css`设计网页最好的例子，虽然运用的东西并不多，但网页结构明朗。	

<h2 id="5">5 CSS(cascading style sheet)样式总结</h2>

关于css的详细文档，参阅[Cascading Style Sheets Level 2](https://www.w3.org/TR/CSS22/)，这不是最新的发布版本（2016年发布）。

<h3 id="5.1">5.1 选择器</h3>

<h4 id="5.1.1">5.1.1 标签选择器</h4>

```css
p{
	font: 16px bold Italic;
	color：red；
	text-decoration：underline(none)
}
```

<h4 id="5.1.2">5.1.2 类(class)选择器</h4>

```css
.class{
	padding:0px auto;
}
```

<h4 id="5.1.3">5.1.3 ID选择器</h4>

```css
#id{
	background-color:#800000;
	}
```

**ID选择器在同一个页面中只能用一次**,这句话要加深理解

<h3 id="5.2">5.2 样式优先级</h3>

* 行内样式>内部样式>外部样式

* ID选择器>类选择器>标签选择器

**并不是所有的属性都可以写在css样式里面，或者说（表格/列表）的某些属性就是html
属性，并不是css样式属性，切不要混淆了**

**`!important` 可以提升样式的优先级**

<h3 id="5.3">5.3 高级选择器</h3>

* 通用选择器

* 子选择器（ul>li）`第一代子元素套用样式`

* 后代选择器（.class p）`某个特定的类里面的p段落套用样式` 

* 交集选择器（div.class）`most used`

* 并集选择器（div,p,li） `已用于设置全局文本格式`

* 相邻选择器 `选择紧接在另一个元素后的元素，而且两者有相同的父元素，可以使用相邻兄弟选择器`

<h3 id="5.4">5.4 常用样式属性</h3>

<h4 id="5.4.1">5.4.1 字体样式</h4>

```html
font-family:times new roman "楷体"；

font-size:16px(in cm mm pt);

font-style:italic(oblique, normal);

font-weight:bold(er) light(er) normal;

[all in one] font:style weight size family;

```
<h4 id="5.4.2">5.4.2 文本样式</h4>

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

<h4 id="5.4.3">5.4.3 背景样式</h4>

```html
background-color:red/transparent;

background-image: url(...);

background-repeat:repeat/no-repeat/repeat-x(y)；

background-position:x% y% / left/center/right top/middle/right;

[all in one] background:color image position repeat;

```
<h4 id="5.4.4">5.4.4 列表样式</h4>

```html
list-style-type:none/disc/circle/square/decimal;

list-style-image:url();

list-style-position:inside/outside;

[all in one] list-style:type position image;

```

<h4 id="5.4.5">设置鼠标形状 （cursor：pointer）</h4>

* default
	
* pointer
	
* wait
	
* help
	
* text
	
* crosshair

<h3 id="5.5">5.5 伪类(Pseudo-classes)</h3>

[PSEUDO-CLASSES](https://www.w3.org/TR/CSS22/selector.html#pseudo-elements) is used to add special effect to some selecters.

>Syntax:selecter(Elemment):pseudo-class{property:value;}

<h4 id="5.5.1">超链接伪类（锚伪类）</h4>

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
>关于hover制作画框的用法，参见[css-gallary.html](/5-伪类（pseudo-classes）/css-gallary.html)
>
>说明的是要注意`position`属性值`relative`和`absolute`之间的差异

<h4 id="5.5.2">伪元素（pseudo-elements）</h4>

* [:first-child](https://www.w3.org/TR/CSS22/selector.html#first-child)
	
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
>上述代码块，若样式改为`p:last-of-type{fontsize:0.75em}`，且即使`<span>`行存在，也能找到`<p>`段落
	
* [:only-child](https://developer.mozilla.org/en-US/docs/Web/CSS/:only-child)
	
>represents an element without any siblings. This is the same as :first-child:last-child or :nth-child(1):nth-last-child(1), but with a lower specificity.	
	
* [:nth-child(2n-1)](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child)
	
>matches one or more elements based on their position among a group of siblings.
>
>更多多信息参考伪类文件夹中[nth-child.html](/5-伪类（pseudo-classes）/nth-child.html)

* [:first-letter(css2)/::first-letter(css3)](https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter)

    >applies styles to the first letter of the first line of a block-level element, but only when not preceded by other content (such as images or inline tables).
    >
    >[百度音乐标签](/4-盒子和CSS/musictags.html)用到了此伪类。
	
* :first-line
	
* [:after](https://www.w3.org/TR/CSS22/selector.html#before-and-after)

:after 用于设置在某元素之后出现某元素，具体的应用可以参见[CSS下拉菜单](/7-CSS3过渡和动画/vertical-accordion-menu.html)以及[下拉菜单](/v+project/dropdown-menu.html)
	
* :before

和`:after`类似	

<h2 id="6">6 文档流，浮动和定位</h2>

<h3 id="6.1">6.1 文档流(document flow)</h3>

>- 所有的元素默认情况下都是在文档流中存在的
>
>- 文档流是网页的最底层
>
元素在文档流中的特点：

*  - **块元素**

	1.默认宽度是父元素的全部
	
	2.默认高度被内容（子元素）撑开
			
	3.在页面中自上而下垂直排列
	
* - **内联元素**

	1.默认高度和宽度都被内容撑开
	
	2.在页面中自左向右水平排列，如果一行不足以容下所有的元素则换到下一行继续从左向右



<h3 id="6.2">6.2 浮动(float)</h3>

* 使用float来设置元素的浮动

	* 可选值：
	
		none 默认值，元素不浮动，就在文档流中
		
		left 元素向页面的左侧浮动
		
		right 元素向页面的右侧浮动
		
	* 浮动特点：
	
		1.元素设置浮动以后，会完全脱离文档流，并向页面的左上或右上浮动m，直到遇到父元素的边框或其他的父元素时则停止浮动
		
		2.如果浮动元素上边是一个没有浮动的块元素，元素不会超过该块元素
		
		3.浮动元素的浮动位置不能超过他上边浮动的兄弟元素，最多一边齐
		
		4.浮动元素不会覆盖文字，文字会围绕在浮动元素的周围，所以可以通过浮动来实现文字环绕图片的效果
		
	* 浮动以后元素会完全脱离文档流，脱离文档流以后元素会具有如下特点：
	
		1.块元素不独占一行
		
		2.块元素的宽度和高度都被内容撑开
		
		3.元素不在文档流占用位置
		
		4.内联元素会变成块元素
		
	* 高度塌陷
		-在文档流中元素的高度默认被子元素撑开，当子元素浮动时，子元素会脱离文档流，此时将不能撑起父元素的高度，会导致父元素的高度塌陷。父元素高度塌陷会导致其他元素的位置上移，导致页面的布局混乱
		
		- 可以通过开启元素的BFC(Block Formatting Context)来处理高度塌陷的问题
			
			* 它是一个隐含属性，默认情况是关闭，当开启以后元素会具有如下的特性：
			
				1.父元素的垂直外边距不会和子元素重叠
				
				2.开启BFC的元素不会被浮动元素覆盖
				
				3.父元素可以包含浮动的子元素 ******
			
			* 开启BFC的方式很多：
			
				1.设置元素浮动
				
				2.设置元素绝对定位
				
				3.设置元素为`inline-block`
				
				4.将元素的`overflow`设置为一个非默认值
				
			* 一般我们采取副作用比较小的方式
			```
				overflow:hidden;
            ```
<h3 id="6.3">6.3 定位(position)</h3>

>- 通过定位可以将元素摆放到页面的任意位置
>
>- 使用position来设置元素的定位
	
		* 可选值：
		
			1. static 默认值 元素不开启定位
			
			2. relative 开启元素的相对定位
			
			3. absolute 开启元素的绝对定位
			
			4. fixed 开启元素的固定定位
			
		* 相对定位
		
			1.相对于元素自身在文档流中的位置进行定位
			
			2.相对定位的元素不会脱离文档流，定位元素的性质不会改变，块还是块，内联还是内联
			
			3.如果不设置偏移量，元素不会发生任何的变化
			
			4.会提升元素的层级
			
		* 绝对定位
		
			1.相对于离它最近的开启了定位的祖先元素进行定位，如果祖先元素都没有开启定位则相对于浏览器窗口进行定位
			
			2.绝对定位会使元素完全脱离文档流，会改变元素的性质，内联变成块元素，块元素的宽度被内容撑开
			
			3.绝对定位的元素如果不设置偏移量，元素的位置不会发生变化
			
			4.会提升元素的层级
			
		* 固定定位
		
			1. 固定定位也是一种绝对定位，它的大部分特点都和绝对定位是相同的
			
			2. 不同的是：
			
				- 固定定位永远相对于浏览器窗口进行定位
				
				- 固定定位会固定在浏览器的指定的位置，不会随页面一起滚动
				
		* 偏移量
		
			* 当元素开启了定位以后，可以通过四个偏移量来设置元素的位置
			
				top：相对于定位位置的顶部的偏移量
				
				bottom：相对于定位位置的底部的偏移量
				
				left：相对于定位位置的左侧的偏移量
				
				right：相对于定位位置的右侧的偏移量
				
			* 一般只需要使用两个值即可给元素进行定位
			
				top left
				
				top right
				
				bottom left
				
				bottom right
				
			* 偏移量也可以指定一个负值，如果是负值则元素会向相反的方向移动
			
		* 层级
			- 当元素开启定位以后，可以通过`z-index`来设置层级,它需要一个正整数作为参数，值越大层级越高，层级越高越优先显示,如果层级一样，则后边的会盖住前边的，父元素永远都不会盖住子元素。
				
			- 文档流 < 浮动 < 定位	
			
		* 元素的透明
		
			1.使用opacity来设置元素的透明度
			
				- 需要一个0-1之间的值
				- 0 表示完全透明
				- 1 表示完全不透明
				
			2.IE8及以下的浏览器不支持该样式，需要使用如下方式来设置
			
				filter:alpha(opacity=透明度);
				
				- 需要一个0-100之间的值
				
				- 0 表示完全透明
				
				- 100 表示完全不透明



	
		
