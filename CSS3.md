# 字体样式属性
1. 字号大小：font-size: 14px;
2. 字体：font-family: "Microsoft YaHei",tahoma,arial;
	英文包含空格，中文必须加引号。
3. CSS Unicode字体:"\5B8B\4F53"
	尽量只写Unicode字体，宋体和微软雅黑:"\5FAE\8F6F\96C5\9ED1", "\5B8B\4F53"
4. 字体粗细：font-weight: 700;
	normal等价400，bold等价400
5. 字体风格：font-style: italic; 
	italic 斜体	，normal 正常
6. font：font-style font-weight font-size font-familiy;
	如：font: italic bold 14px "Microsoft YaHei"，不能更改顺序，字号字体不能省略
7. CSS注释：/* */
# CSS基本选择器
## 标签选择器（元素选择器）
p {
	color: red;
}
## 类选择器
.className {
	color: red;
}
<div class="className"></div>
## 多类名选择器
.c-orange {
	color: orange;
}
.font14 {
	font-size: 14px;
}
<div class="c-orange font-size"></div>

## id选择器
#big {
	color: pink;
}
<div id="big"></div>
## id选择器和类选择器的区别
-类选择器可以重复使用
-id是惟一的，只允许调用一次
## 通配符选择器（实际很少使用）
* { * 表示所有元素
	color: purple;
}
## 伪类选择器
### 链接伪类选择器
顺序不要变
:link 未访问
:visited 已访问
:hover 鼠标悬停
:active 选定链接
a:link {
	font-size: 16px;
	color: gray;
	font-weight: 700;
}
a:visited {
	font-size: 16px;
	color: orange;
	font-weight: 700;
}
a:hover {
	font-size: 16px;
	color: red;
	font-weight: 700;
}
a:active {
	font-size: 16px;
	color: green;
	font-weight: 700;
}
<div> 
	<a href="#">秒杀</a> 
	<a href="#">闪购</a> 
</div>

一般写法
a {
	font-weight: 700;
	font-size: 16px;
	color: gray;
}
a:hover {
	color: red;
}
### 结构伪类选择器(CSS3)
:first-child
:last-child
:nth-child() 如 :nth-child(4)  :nth-child(odd/even) 奇数/偶数  nth-child(n/2n/2n+1)
:nth-last-child() 逆序
### 目标伪类选择器
配合锚点定位使用
:target {
	color: red;
}
# CSS外观属性
1. color：文本颜色
	.red {
		color: red;
	常用：color: #FF0000;简写：f00
		color: rgb(255,0,0);
	}
2. line-height：行间距
	line-height: 14px;
3. text-align：水平对齐方式
	text-align: center; left/center/right;
4. text-indent：首行缩进
	text-indent: 2em; em：一个汉字的宽度
5. letter-spacing：字间距
	letter-spacing: 8px;
6. word-spacing：单词间距
	word-spacing: 10px; 对英文有效
7. word-break：自动换行
	word-break: normal; break-all/keep-all 允许在单词内换行/只能在半角空格或连字符处换行
8. 文字半透明(CSS3)
	color: rgba(r,g,b,a) a是alpha透明的意思，0~1
9. 文字阴影(CSS3)
	前两者必须有
	text-shadow:水平位置 垂直位置 模糊距离 阴影颜色
	text-shadow: 1px 2px 3px rgba(0,0,0,0.4);
# CSS样式表
## 行内式（内联样式）
直接在标签内部写：```<div style="color: #f00; font-size: 14px;">```
## 内部样式表（内嵌式）
<head>
	<style>
		div {
			color: pink;
		}
	</style>
</head>

## 外部样式表（外链式）
``` html
	<head>
		<link href="demo.css" type="text/css" rel="stylesheet" />
	</head>
```

## 三种样式表总结
|样式表		|优点					|缺点						|使用情况		|控制范围			|
|--			|--						|--							|--				|--					|
|行内样式表	|书写方便，权重高		|没有实现样式和结构的分离	|较少			|控制一个标签（少）	|
|内嵌样式表	|部分结构和样式相分离	|没有彻底分离				|较多			|控制一个页面（中）	|
|外部样式表	|完全实现结构和样式分离	|需要引入					|最多，强烈推荐	|控制整个站点（多）	|

# 标签显示模式
## 块级元素(block-level)
每个块元素通常都会独自占据一整行或多行，可以对其设置宽度、高度、对齐等属性，常用于网页布局和网页结构的搭建。
如h1~h6,p,div,ul,ol,li等

**特点**
1. 总是从新行开始
2. 高度，行高，外边距以及内边距都可以控制
3. 宽度默认是容器的100%
4. 可以容纳内联元素和其它块元素

## 行内元素(inline-level)
行内元素（内联元素）不占有独立的区域，仅仅靠自身的字体大小和图像尺寸来支撑结构，一般不可设置宽度、高度、对齐等属性，常用于控制页面中文本的样式。
如：a,strong,b,em,i,del,s,ins,u,span（最典型行内元素）

**特点**
1. 和相邻行内元素在一行上
2. 高、宽无效，但水平方向的padding和margin可以设置，垂直方向的无效
3. 默认宽度就是它本身内容的宽度
4. 行内元素只能容纳文本或其它行内元素，a特殊

**注意**
1. 只有文字才能组成段落，因此p里面不能放块级元素，同理h1~h6,dt也不能
2. 链接里面不能再放链接

## 块级元素和行内元素的区别
**块级元素特点**
1. 总是从新行开始
2. 高度，行高，外边距以及内边距都可以控制
3. 宽度默认是容器的100%
4. 可以容纳内联元素和其它块元素

**行内元素特点**
1. 和相邻行内元素在一行上
2. 高、宽无效，但水平方向的padding和margin可以设置，垂直方向的无效
3. 默认宽度就是它本身内容的宽度
4. 行内元素只能容纳文本或其它行内元素，a特殊

## 行内块元素(inline-block)
如img,input,td可以对它们设置宽高和对齐属性

**特点**
1. 和相邻行内元素（行内跨）在一行上，但是之间会有空白缝隙
2. 默认宽度就是它本身内容的宽度
3. 高度、行高、外边距以及内边距都可以控制

## 显示模式转换
块转行内：```display: inline;```
行内转块：```display: block;```
块、行内元素转换为行内块：```display: inline-block;```

# CSS复合选择器
## 交集选择器
标签选择器.class选择器 {}
如```div.className{}```
使用较少

## 并集选择器
用**逗号**隔开
```p,div,h1 {}```

## 后代选择器
用**空格**隔开
.nav ul li {}

## 子元素选择器
用**>**隔开
```.item > li {}```

## 练习题
``` html
	<div class="nav"> <!-- 主导航栏 -->
		<ul>
			<li><a href="#">公司首页</a></li>
			<li><a href="#">公司简介</a></li>
			<li><a href="#">公司产品</a></li>
			<li>
				<a href="#">联系我们</a>
				<ul>
					<li><a href="#">公司电话</a></li>
					<li><a href="#">公司邮箱</a></li>
				</ul>
			</li>
		</ul>
	</div>
	<div class="sitenav">  <!-- 测导航栏 -->
		<div class="site-l">左侧导航栏</div>
		<div class="site-r"><a href="#">登录</a></div>
	</div>
```
要求：在不修改以上代码的前提下，完成以下任务：
1. 链接 登录 的颜色为红色，同时主导航栏里面的所有链接改为蓝色
2. 主导航栏和测导航栏里面文字都是14像素并且是微软雅黑
3. 主导航栏里面的一级菜单链接文字颜色为绿色
答案：
``` css
		<style>
			.site-r a {
				color: red;
			}
			.nav ul li a {
				color: blue;
			}
			.nav,.sitenav {
				/* font-size: 14px;
				font-family: "microsoft yahei"; */
				font: 14px "microsoft yahei";
			}
			.nav > ul > li > a {
				color: #008000;
			}
		</style>
```

## 属性选择器
选取标签带有某些特殊属性的选择器
用**[]**表示
``` css
	a[title] {} /*titile属性*/
	input[type=text] {} /*等于text的type属性*/
	div[class^=font] /*表示以font开始的*/
	div[class$=footer] /*表示以footer结尾的*/
	div[class*=tao] /*表示含有tao*/
```

## 伪元素选择器(CSS3)
1. E::first-letter：文本第一个字，```p::first-letter {}```
2. E::first-line：文本第一行，```p::first-line {}```
3. E::selection：可改变选中文本的样式，```p::selection {}```
4. E::before：在E中的内容前面添加content中的内容，```div::before { content: "开始"}```
5. E::after：在E中的内容后面添加content中的内容，```div::after { content: "结束"}```

# CSS背景(background)
CSS可以添加背景颜色和背景图片，以及进行图片设置

|background-color									|背景颜色			|
|--													|--					|
|background-image									|背景图片地址		|
|background-repeat									|是否平铺			|
|background-position								|背景位置			|
|background-attachment								|背景固定还是滚动	|
|背景的合写（复合属性）								|					|
|background: 背景颜色 背景图片地址 背景平铺 背景位置|					|

## 背景附着
``` background-attachment: scroll | fixed;```
scroll：背景图随内容滚动
fixed：背景图固定

## 背景简写
background: 背景颜色 背景图片地址 背景平铺 背景滚动 背景位置
如：``` background: #000 url(bg.jpg) no-repeat fixed center 100px;```

## 背景透明(CSS3)
``` background: rgba(0,0,0,0.5)```

## 背景缩放(CSS3)
background-size: 宽度 高度; 尽量只改一个值，防止失真
``` background-size: 50%;```
background-size: cover | contain
cover：图片进行等比例缩放，超出盒子的部分看不到（相对用的多）
contain：图片进行等比例缩放，保证图片始终在盒子中，盒子部分未填满
## 多背景(CSS3)
background: url(1.jpg) no-repeat left top,
			url(2.jpg) no-repeat right bottom #aaa;
			多背景，背景颜色写在最后一个背景
			
## 凹凸文字
1. 背景色和文字颜色要相同
``` background-color: #ccc;
	color: #ccc
```
2. 凸起：左上白，右下黑
``` text-shadow: 1px 1px 1px #000, -1px -1px 1px #fff;```
3. 凹下：左上黑，右下白
``` text-shadow: -1px -1px 1px #000, 1px 1px 1px #fff;```
## 导航栏案列
1. 文本装饰：text-decoration: none|underline|overline|line-through;
none：默认
underlin：下划线
overline：上划线
line-through：横穿文本线
2. 技巧：在一行内的盒子内，设定行高等于盒子高度，可使文字垂直居中
``` html
	<head>
		<style>
			body {
				background-color: #000;
			}
			a {
				width: 200px;
				height: 50px;
				/* background-color: orange; */
				display: inline-block;
				text-align: center;
				line-height: 50px; /* 在同一个盒子，设定行高等于盒子高度，可使文字垂直居中 */
				color: #fff;
				font-size: 22px;
				text-decoration: none;
			}
			a:hover {
				background: url(images/logo.jpg) no-repeat;
			}
		</style>
	</head>
	<body>
		<a href="#">专区说明</a>
		<a href="#">申请资格</a>
		<a href="#">兑换奖励</a>
		<a href="#">下载游戏</a>
	</body>
```

# CSS三大特性
## CSS层叠性
若出现样式冲突，会按照CSS书写顺序，以最后的样式为准

## CSS继承性
子标签会继承父标签的某些样式，如字体，文本属性等网页中通用的样式可以使用继承
例如：字体、字号、颜色、行距等可在body中统一设置，影响所有文本
不可继承：边框、外边距、内边距、背景、定位、元素高等属性

## CSS优先级
### CSS特殊性（计算CSS权重的方式）
0,0,0,0 从左至右，权重减小
|继承或者*的贡献值			|0,0,0,0	|
|--							|--			|
|每个元素（标签）贡献值为	|0,0,0,1	|
|每个类，伪类贡献为			|0,0,1,0	|
|每个ID贡献为				|0,1,0,0	|
|每个行内样式贡献值为		|1,0,0,0	|
|每个!import贡献值为		|∞无穷大	|

如：
div ul li ---> 0,0,0,3
.nav ul li ---> 0,0,1,2
a:hover ---> 0,0,1,1
.nav a ---> 0,0,1,1

注：继承的权重为0

### 权重精华题目
``` html
<head>
	<style>
		#father #son {
			color: blue;
		}
		#father p.c2 {
			color: black;
		}
		div.c1 p.c2 {
			color: red;
		}
		#father {
			color: green!important;
		}
	</style>
</head>
<body>
	<div id="father" class="c1">
		<p id="son" class="c2">
			试问这行字体是什么颜色？
		</p>
	</div>	
</body>
```
答案：blue
权重分别为：
	0,2,0,0
	0,1,1,1
	0,0,2,2
	∞  （继承的权重为0）

``` html
<head>
	<style>
		.c1 .c2 div {
			color: blue;
		}
		div #box3 {
			color: green;
		}
		#box1 div {
			color: yellow;
		}
	</style>
</head>
<body>
	<div id="box1" class="c1">
		<div id="box2" class="c2">
			<div id="box3" class="c3">
				文字
			</div>
		</div>
	</div>
</body>
```
答案：yellow
权重相同，就近原则。
### 优先级总结
1. 使用!important声明的规则
2. 内嵌在HTML元素的style属性里的声明
3. 使用了ID选择器的规则
4. 使用了类选择器、属性选择器、伪元素和伪类选择器的规则
5. 使用了元素选择器的规则
6. 只包含通用选择器的规则（*）
7. 同一类选择器规则遵循就近原则

# 盒子模型(CSS重点)
## 盒子边框(border)
border:border-width || border-style || border-color
border-style常用属性值：
	none：没有边框（默认）
	solid：边框为实线（最常用）
	dashed：边框为虚线
	dotted：边框为点线
	double：边框为双实线
	
## 盒子边框写法总结表
|设置内容		|样式属性							|常用属性值										|
|--				|--									|--												|
|上边框			|border-top:宽度 样式 颜色			|												|
|下边框			|border-bottom:宽度 样式 颜色		|												|
|左边框			|border-left:宽度 样式 颜色			|												|
|有边框			|border-right:宽度 样式 颜色		|												|
|样式综合设置	|border-style:上边[右边 下边 左边]	|none、solid、dashed、dotted、double			|
|宽度综合设置	|border-width:上边[右边 下边 左边]	|像素值											|
|颜色综合设置	|border-color:上边[右边 下边 左边]	|颜色值、#十六进制、rgb(r,g,b)、rgb(r%,g%,b%)	|
|边框综合设置	|border:四边宽度 四边样式 四边颜色	|												|

## 合并细线表格
```border-collapse: collapse;``` 表示边框合并在一起

## 圆角矩形(CSS3)
```border-radius: 左上角 右上角 右下角 左下角;``` 一个数值表示4个相同的值
```border-radius: 50%;```结果是一个圆
```border-radius: 左上角，右下角  右上角，左下角;``` 两个值
```border-radius: 左上角 右上角，左下角 右下角；```三个值

## 盒子内边距(padding)
指边框与内容之间的距离
padding-top
padding-right
padding-bottom
padding-left

|值的个数	|表达意思				|
|--			|--						|
|1个值		|padding: 上下左右;		|
|2个值		|padding: 上下 左右;	|
|3个值		|padding: 上 左右 下;	|
|4个值		|padding: 上 右 下 左;	|

## 外边距以及盒子居中对齐
### 外边距
margin，设置外边距会在元素之间创建“空白”，这段空白通常不能放置其他内容。
margin-top
margin-right
margin-bottom
margin-left
margin: 上外边距 右外边距 下外边距 左外边距;

### 外边距实现盒子居中
1. 必须是块级元素
2. 盒子必须制定宽度(width)
``` 
.header{
	width: 960px;
	margin: 0 auto;
}
```

### 文字水平居中和盒子水平居中
文字：text-align: center;
盒子：margin: 0px auto;

### 插入图片和背景图片区别
插入图片更改大小和位置：width,height; margin,padding（插入图片类似盒子）
背景图片更改大小和位置：background-size: 200px 200px; background-position: 30px 50px;
一般情况：
	背景图片适合做小图标使用（如logo）
	产品展示类用插入图片（一般选用此类）

## 清除内外边距
div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,form,fieldset,input,textarea,blockquote,p {
	padding: 0;
	margin: 0;
}

## 行内元素上下内外边距问题
行内元素只有左右外边距，尽量不给行内元素指定上下内外边距

## 外边距合并
### 相邻块元素垂直外边距的合并
垂直的盒子以最大外边距为准，平常避免就行

### 嵌套块元素垂直外边距合并（塌陷问题）
1. 可以为父元素定义1像素的上边框或上内边距
2. 可以为父元素添加overflow: hidden;

## content宽度和高度
使用width和height可控制盒子大小，常用像素值
盒子模型总宽度和总高度计算原则：
- 外盒尺寸计算（元素空间尺寸）
Element空间高度 = content height + padding + border + margin
Element空间宽度 = content width + padding + border + margin
- 内盒尺寸计算（元素实际大小）---较多用
Element Height = content height + padding + border(Height为内容高度)
Element Width = content widht + padding + border(Width为内容宽度)
注意：
- width和height仅适用于块级元素，对行内元素无效（img和input标签除外）
- 计算盒子模型总高度时，还应考虑上下两个盒子垂直外边距合并的情况
- **如果一个盒子没有给定宽度/高度或者继承父亲的宽度/高度，则padding不会影响本盒子大小**

```
	ul {
		list-style: none; 取消列表自带的小点
	}
```

### 盒子模型布局稳定性
使用顺序：width > padding > margin
原因：
	margin会有外边距合并，ie6下margin加倍的bug
	padding会影响盒子的大小，需要进行加减计算
	width，经常使用宽度剩余法，高度剩余法做
	
### CSS3盒子模型
CSS3中可通过box-sizing指定盒模型：content-box、border-box
1. box-sizing: content-box 盒子大小为：width+padding+border
2. box-sizing: border-box 盒子大小为：width（padding和border包含在width中）
### 盒子阴影
``` box-shadow: 水平阴影 垂直阴影 模糊距离 阴影尺寸 阴影颜色 内/外阴影;```

|值			|描述							|
|--			|--								|
|h-shadow	|必须，水平阴影位置，允许负值	|
|v-shadow	|必须，垂直阴影位置，允许负值	|
|blur		|可选，模糊距离					|
|spread		|可选，阴影尺寸					|
|color		|可选，阴影颜色					|
|inset		|可选，将外部阴影改为内部阴影	|

注：可用","隔开，添加多个效果

# 浮动(float)
## 普通流(normal flow)
网页布局核心：用CSS摆放盒子位置
CSS定位机制：普通流（标准流）、浮动和定位
普通流（标准流/文档流）：一个网页内标签元素正常从上到下，从左到右排列顺序的意思

## 什么是浮动
元素浮动：指设置浮动属性的元素会脱离标准普通流的控制，移动到其父元素中指定位置的过程

|属性值	|描述				|
|--		|--					|
|left	|元素向左浮动		|
|right	|元素向右浮动		|
|none	|元素不浮动（默认）	|

## 浮动详细内幕特性
**浮动脱离标准流，不占位置，会影响标准流，浮动只有左右浮动**
1. 浮动首先需要添加标准流父级
浮动不会超过父级的padding和border
2. 两个盒子都浮动，顶部对齐--->一个浮动，其它都要浮动，才能一行对齐显示
3. 第一个盒子不浮动，第二个盒子浮动，底部对齐
4. 元素添加浮动后，会具有行内块元素的特性。元素大小完全取决于定义的大小或者默认的内容多少，一行可放多个

## 浮动总结
float  浮漏特
浮：加了浮动的元素盒子是浮起来的，漂浮在其他的标准流盒子上面
漏：加了浮动的盒子，不占位置，它浮起来，原来的位置漏给标准流盒子
特：特别注意，首先浮动的盒子需要和标准流的父级搭配使用，其次，特别的注意浮动可以使元素显示模式体现为行内块特性

# 版心和布局流程
版心：指网页中主题内容所在的区域，一般在浏览器窗口中水平居中显示，常见的宽度为值为：960px、980px、1000px、1200px等

## 布局流程
1. 确定页面的版心（可视区）
2. 分析页面中的模块，以及每个行模块中的列模块
3. 制作HTML页面，CSS文件
4. CSS初始化，然后开始运用盒子模型的原理，通过DIV+CSS布局来控制网页的各个模块

### 一列固定宽度且居中
.top+.banner+.main+.footer：生成四个div盒子
CSS初始化
```
	* {
		margin: 0;
		padding: 0;
	}
	/*并集选择器写重复的属性*/
	.top,
	.banner,
	.main,
	.footer {
		width: 960px;
		text-align: center; /*文字居中*/
		margin: 0 auto; /*盒子居中*/
		margin-bottom: 10px;
	}
	.top {
		height: 80px;
		background-color: pink;
	}
	.banner {
		height: 120px;
		background-color: purple;
	}
	.main {
		height: 500px;
		background-color: hotpink;
	}
	.footer {
		height: 150px;
		background-color: yellow
	}
```

## 两列左窄右宽型(如小米官网)
.top+.banner+(.main>.left+.right)+.footer
```
	* {
		margin: 0;
		padding: 0;
	}
	.top,
	.banner,
	.main,
	footer {
		width: 960px;
		margin: 0 auto;
		text-align: center;
		border: 1px dashed #ccc
		background-color: #eee;
		margin-bottom: 8px;
	}
	.top{
		height: 80px;
	}
	.banner {
		height: 150px;
	}
	.main {
		500px;
	}
	.left {
		width: 360px;
		height: 500px;
		background-color: pink;
		float: left;
		
	}
	.right {
		width: 592px; /*中间留8px*/
		height: 500px;
		background-color: purple;
		float: right;
	}
	.footer {
		height:120px;
	}
```

## 通栏平均分布型(如锤子官网)

```
<head>
	<style>
		* {
			margin: 0;
			padding: 0;
		}
		ul {
			list-style: none;
		}

		.top {
			/* 通栏盒子不用写宽度 */
			height: 80px;
			border: 1px dashed #aaa;
			text-align: center;
			margin: 0 auto;
			background-color: #ccc;
		}

		.banner {
			width: 960px;
			height: 120px;
			border: 1px dashed #aaa;
			text-align: center;
			margin: 10px auto;
			background-color: #CCCCCC;
		}

		.small {
			width: 960px;
			height: 100px;
			/* background-color: pink; */
			margin: 0 auto;
			margin-bottom: 10px;
		}
		.small ul li {
			width: 230.5px; /*父盒子宽度-border-小盒子间距*/
			border: 1px dashed #aaa;
			background-color: #eee;
			height: 100px;
			float: left;
			margin-left: 10px;
		}
		.small .nomargin {
			margin-left: 0;
		}
		.footer {
			height: 150px;
			border: 1px dashed #AAAAAA;
			background-color: #EEEEEE;
			margin-top: 10px;
			text-align: center;
		}
	</style>
</head>
<body>
	<div class="top">top</div>
	<div class="banner">banner</div>
	<div class="small">
		<ul>
			<li class="nomargin">1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
		</ul>
	</div>
	<div class="small">
		<ul>
			<li class="nomargin">1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
		</ul>
	</div>
	<div class="small">
		<ul>
			<li class="nomargin">1</li>
			<li>2</li>
			<li>3</li>
			<li>4</li>
		</ul>
	</div>
	<div class="footer">footer</div>
</body>
```

# 清除浮动
## 清除浮动本质
主要为了坚决父级元素因为子级浮动引起内部高度为0的问题
不给父级元素给定高度：
	标准流：父级元素被子级元素撑开
	浮动：父级元素不能被子级元素撑开
	
**很多情况下，不方便给父级元素给定高度，如新闻模块**

## 清除浮动的方法(闭合浮动)
把浮动的盒子圈到里面，让父盒子闭合出口和入口不让它们出来影响其它元素
- 选择器{ clear: 属性值;}
|属性值	|描述									|
|--		|--										|
|left	|不允许左侧有浮动（清除左侧浮动的影响）	|
|right	|不允许右侧有浮动（清除右侧浮动的影响）	|
|both	|同时清除左右两侧浮动的影响				|

### 额外标签法
W3C推荐做法：在浮动元素末尾添加一个空标签如:```<div style="clear:both"></div>```或者其它标签br等亦可
优点：通俗易懂，书写方便
缺点：添加许多无意义标签，结构化较差，不推荐使用。

### 父级添加overflow属性方法
可以通过触发BFC的方式，可以实现清除浮动效果
给父级添加：```overflow: hidden | auto | scroll;```都可实现
优点：代码简洁
缺点：内容增多时容易造成不会自动换行导致内容被隐藏，无法显示需要溢出的元素

### 使用after伪元素清除浮动
:after方式为空元素升级版
```
	.clearfix:after {
		content: "."; /*尽量不要空，防止旧版本浏览器有空隙*/
		display: block;
		height: 0;
		clear: both;
		visibility: hidden;
	}
	.clearfix {
		*zoom: 1; /*IE6、7专有，带有*的属性，只有IE6、7能识别*/
	}
```
优点：复合闭合浮动思想，结构语义化正确
缺点：由于IE6、7不支持:after，使用zoom: 1;触发hasLayout
代表网站：百度、淘宝、网易等

### 使用before和after双伪元素清除浮动（推荐使用）
```
	.clearfix:before, .clearfix:after {
		content: "";
		display: table;
	}
	.clearfix:after {
		clear: both;
	}
	.clearfix {
		*zoom: 1;
	}
```
代表网站：小米，腾讯

# Photoshop基本使用
## 基本快捷键
- 移动工具：v
- 自由变形：ctrl+T，按住shift可等比缩放
- 图层操作：F7，图层就是一张张透明的纸，可实现叠加问题
- 复制图层：
	- 按住ALT拖曳图像
	- 重合：ctrl+J  
- 分组：
	- 选中目标图层：ctrl+G
	- 取消编组：ctrl+shift+G
- 移动图层：
	- 向上移动：ctrl+]
	- 向下移动：ctrl+[
	- 图层置顶：ctrl+shift+]
	- 图层置底：ctrl+shift+[
	- 用鼠标拖动，按住shift可沿同一水平线、同一垂线，45°移动
- 撤销：
	- 撤销一步：ctrl+z
	- 撤销多步：ctrl+alt+z
- 合并图层：ctrl+e
- 取消选区：ctrl+d
- 颜色填充：
	- 前景色：alt+delete
	- 背景色：ctrl+delete
- 选区反选：ctrl+shift+I
- 选区布尔运算
	- 添加到选区：相加运算 按住shift再绘制选区
	- 从选区减去：相减 按住alt
	- 与选区交叉：保留重合部分 alt+shift
- 钢笔工具 P
	- 绘制路径后：ctrl+回车 生成选区
	- 按住alt点一下，回复直线

## 切图方法
1. 手动划片
2. 图层菜单-新建基于图层的切片
3. 利用标尺-基于参考线的切片
3. 视图-清除切片
4. 文件-存储为Web所用格式-存储-切片（选中的切片）

切图插件(Photoshop完整版才行)：Cutterman，能够自动将你需要的图层进行输出
点击快速选中图层：工具栏-选择-自动选择-图层
按住shift加选

# 学成网案例（上）

# 定位
## 元素的定位属性
### 边偏移
|边偏移属性	|描述											|
|--			|--												|
|top		|顶端偏移量，定义元素相对于其父元素上边线的距离	|
|bottom		|底部偏移量，定义元素相对于其父元素下边线的距离	|
|left		|左侧偏移量，定义元素相对于其父元素左边线的距离	|
|right		|右侧偏移量，定义元素相对于其父元素右边线的距离	|

### 定位模式
选择器 {position: 属性值;}
|值			|描述												|
|--			|--													|
|static		|自动定位（默认）									|
|relative	|相对定位，相对于其原文档流的位置进行定位			|
|absolute	|绝对定位，相对于其上一个已经定位的父元素进行定位	|
|fixed		|固定定位，相对于浏览器窗口进行定位					|

## 静态定位(static)
边偏移无效，一般用来清除定位。

## 相对定位(relative)
相对于自己移动位置，原来所在位置继续占有，相对定位的盒子仍在标准流中

## 绝对定位(absolute)
完全脱离标准流，不占有位置
### 父级没有定位
孩子以浏览器为基准点对齐

### 父级有定位(relative/absolute)
孩子以最近的父级为准

### 子绝父相
1. 相对定位：占有位置，不脱标
2. 绝对定位：不占有位置，完全脱标

孩子绝对定位，父亲相对定位

### 绝对定位水平/垂直居中
普通合子是左右margin改为auto就可，但绝对定位就无效了
绝对定位居中方法：
	1. 先left50%（父盒子的一半大小）
	2. 然后走自己外边距负的一半值（往左走自己宽度的一半）
如：
	left: 50%;
	margin-left: -50px;
	top: 50%;
	margin-top: -40px;
	
## 固定定位(fixed)
1. 固定定位元素跟父亲没有任何关系，只认浏览器
2. 完全脱标，以浏览器窗口为参照，不占有位置，不随着滚动条滚动

**固定定位的盒子一定要写宽和高，除非由内容撑开**
``` height: 44px;
	width: 100%;
	position: fixed;
```

## 叠放次序(z-index)
取值可为正整数、负整数和0
注意：
	z-index的默认属性值是0，取值越大，定位元素在层叠元素中越居上
	如果取值相同，则根据书写顺序，后来居上
	后面数字不能加单位
	只有相对定位、绝对定位、固定定位有此属性，其余标准流、浮动、静态定位都无此属性

## 定位总结
|定位模式			|是否脱标占有位置		|是否可以使用偏移	|移动位置基准				|
|--					|--						|--					|--							|
|静态定位static		|不脱标，正常模式		|不可以				|正常模式					|
|相对定位relative	|不脱标，占有位置		|可以				|相对自身位置移动			|
|绝对定位absolute	|完全脱标，不占有位置	|可以				|相对于定位父级移动位置		|
|固定定位fixed		|完全脱标，不占有位置	|可以				|相对于浏览器移动位置		|

## 定位模式的转换
与**浮动**一样，元素添加**绝对定位和固定定位**后，元素模式也会转换为行内块元素
**因此，行内元素如果添加了绝对定位和固定定位后，可以不用再转换模式，直接给高度和宽度就可以了**

# 元素的显示与隐藏
在页面中消失，但不在源码中删除。最常见的是广告

## display显示
display: none;隐藏对象
display: block;显示对象
特点：隐藏后不再保留位置

## visibility可见性
设置或检索是否显示对象
visible: 对象可视
hidden: 对象隐藏
特点：隐藏后，继续保留原有位置

## overflow溢出
检索或设置当前对象的内容超过其指定高度及宽度时如何管理内容
visible：不剪切内容也不添加滚动条（默认）
auto：超出自动显示滚动条，不超出不显示滚动条
hidden：隐藏超出部分的内容（用的最多）
scroll：不管是否超出，总是显示滚动条

# CSS高级技巧
## CSS用户界面样式
### 鼠标样式cursor
cursor: default | pointer | move | text

### 轮廓outline
outline: outline-color || outline-style || outline-width
通常只写：outline: 0/none;

### 防止拖拽文本域resize
resize: none; 防止火狐，谷歌等浏览器随意拖动文本域
右下角可拖拽：<textarea></textarea>
右下角不可拖拽：<textarea style="resize: none;"></textarea>

## vertical-align垂直对齐
### 图片、表单和文字对齐
vertical-align: baseline（默认） | top | middle | bottom
vertical-align不影响块级元素中的内容对齐，只针对行内元素或者行内块元素，**通常用来控制图片和表单与文字的对齐**

图片文字居中对齐:
img {
	vertical-align: middle;
}
表单与文字居中对齐：
textarea {
	vertical-align: middle;
}

### 去除图片底侧空白缝隙
重要特性：图片或表单等行内块元素，它的底线会和父级盒子的基线对齐，就会造成图片底侧有一个空白缝隙
解决办法：
	1. 给img添加vertical-align: middle | top（用的最多）等，让图片不要和基线对齐
	2. 给img添加display: block;转换为块级元素

# 溢出文字的隐藏
## word-break自动换行
normal：浏览器默认规则
break-all：允许在单词内换行（单词可拆开）
keep-all：只能在半角空格或连字符处“-”换行（没有连字符的单词不可拆）
主要处理英文单词

## white-space
通常用于强制一行显示内容
normal：默认
nowrap：强制在同一行显示所有文本，直到文本结束或者遭遇br标签对象才换行 （如新闻标题）

## text-overflow文字溢出
设置或检索是否使用一个省略标记（...）表示对象内文本的溢出
clip：不显示(...)而是简单的裁切
ellipsis：当对象内文本溢出时显示省略标记(...)
注：一定要首先强制一行内显示，再和overflow属性搭配使用
```
white-space: nowrap;
overflow: hidden;
text-overflow: ellipsis;
```

# CSS精灵技术（sprite）(小妖精/雪碧)
## 产生背景
有效减少服务器接受和发送请求的次数，提高页面的加载速度

## 精灵技术本质
用于处理网页背景图像的方式。将一个页面涉及到的所有背景图集中到一张大图中，然后将大图应用于网页，这样只需向服务器
发送一次请求就可全部展示网页中的背景图。一般称这个大图为<u>精灵图</u>

## 精灵图的使用
主要是盒子的width和height，以及所需图片在精灵图中的position（一般都是负值）

## 制作精灵图
一般由网页美工做
- 精灵图上放的都是小的装饰性质的背景图片。不能放插入图片
- 精灵图的宽度取决于最宽的背景
- 可以横向摆放，也可以纵向摆放，但每个图片之间间隔至少隔开偶数像素
- 在最低端留一片空隙，方便以后添加其它精灵图
背景图片较多时，建议使用精灵技术

PS:
- 新建文件
- 名称：sprite
- 设置合适的宽高（最宽背景图的宽）
- 背景内容：透明
- 找到psd文件中的背景图所包含的图层-复制到sprite-合并图层
- 保存1：文件-存储为psd格式
- 保存2：文件-存储为web所用格式-PNG-24/PNG-8-选中透明度

## 字体图标
### 字体图片使用流程
1. UI人员设计字体图标效果图(svg)
用illustrator或Sketch等矢量图形软件创建icon图标，保存为svg格式

2. 前端人员上传生成兼容性字体文件包
推荐网站：http://icomoon.io/http://www.iconfont.cn

3. 前端人员下载兼容字体文件包到本地
fonts文件夹

4. 把字体文件包引入到HTML页面中
将fonts文件夹复制到项目文件夹中
```
<style>
第一步：在样式中声明字体
	@font-face { /*声明电脑中没有的字体*/
		font-family: 'icomoon';
		src: url('fonts/icomoon.');
		src: url('fonts.icomoon.') format('后缀格式'),
		src: url('fonts.icomoon.') format('后缀格式'),
		src: url('fonts.icomoon.') format('后缀格式');
		font-weight: normal;
		font-style: normal;
	}
第二步：给盒子使用字体
	/*引用字体*/
	span {
		font-family: "icomoon"; /*保证和上面的font-family名字相同*/
	}
第三步：盒子里面添加结构(字体包中的index.html文件中)
	span::before {
		content: "\e900";
	}
	或者复制小方块
	<span>小方块</span>
</style>
```

### 追加新图标到原来库里面
把压缩包里面的selection.json从新上传，然后选中自己想要的新图标，从新下载压缩包替换原来的文件

# 滑动门
## 滑动门出现的背景
为了使各种特殊形状的背景能够自适应元素中文本内容的多少。它从新的角度构建页面，使各种特殊形状的背景能够自耦拉伸
滑动，以适应元素内部的文本内容，可用性更强。常见于各种导航栏的滑动门(如微信官网)

## 核心技术
利用CSS精灵（主要是背景位置）和盒子padding撑开宽度，以适应不同字数的导航栏
一般布局如下
```
	<li>
		<a href="#">
			<span>导航栏内容</span>
		</a>
	</li>
```
总结：
- a设置背景左侧，padding撑开合适宽度
- span设置背景右侧，padding撑开合适宽度，剩下由文字继续撑开宽度
- 之所以a包含span就是因为整个导航都是可以点击的
示例：
```
<style>
	* {
		margin: 0;
		padding: 0;
	}
	a {
		display: inline-block;
		height: ..px;
		/*不能给宽度,用padding挤开*/
		background: url(images/xx.png) no-repeat;
		padding-left: ..px; /*撑开盒子*/
		text-decoration: none;
		line-height: ..px;
	}
	a span {
		display: inline-block;
		height: ..px;
		background: url(images/xx.png) no-repeat right;/*背景右对齐right*/
		padding-right: ..px; /*撑开盒子*/
	}
</style>
<body>
	<a href="#">
		<span>首页</span>
	</a>
</body>
```

# before和after伪元素（详解）
.one：类选择器
:hover：伪类选择器
::after：伪元素选择器

伪元素选择器：本质上是插入一个元素（标签、盒子），只不过是行内元素（不能设置宽高）

## 鼠标经过显示边框
```
	div {
		width: 296px;
		height: 180px;
		margin: 20px auto;
		position: relative;
	}
	div:hover::before {
		content: "";
		width: 100%;
		height: 100%;
		border: 10px solid rgba(255,255,255, .4);
		display: block;
		position: absolute;
		top: 0;
		left: 0;
		box-sizing: border-box;
	}
```

# 过渡(CSS3)
transition:要过渡的属性 花费时间 运动曲线 何时开始;
如果有多组属性变化，用","隔开

|属性						|描述										|CSS|
|--							|--											|--	|
|transition					|简写属性，用于在一个属性中设置四个过渡属性	| 3	|
|transition-property		|规定应用过渡的CSS属性的名称				| 3	|
|transition-duration		|定义过渡效果花费的时间，默认是0s			| 3	|
|transition-timing-function	|规定过渡效果的时间曲线，默认是"ease"		| 3	|
|transition-delay			|规定过渡效果何时开始，默认是0s				| 3	|

属性名称：all（所有属性都变化）
花费时间：s | ms
过渡效果：匀速(linear) | 逐渐慢下来(ease) | 加速(ease-in) | 减速(ease-out) | 先加速后减速(ease-in-out)
例：
```
<style>
	div {
		width: 200px;
		height: 100px;
		background-color: pink;
		transition: width 0.6s ease 0s, height 0.3s ease-in 1s;
		/*transition写在div中而不是hover里，若写到hover里当鼠标移开时会一下恢复原样，没有过渡效果*/
	}
	div:hover {
		width: 600px;
		height: 300px;
	}
</style>
```

# 2D变形(CSS3) transform
可实现元素的位移、旋转、变形、缩放，甚至支持矩阵方式，配合过渡和即将学习的动画知识，可取代大量之前只能靠Flash才能实现的效果。
变形转换transform

- 移动translate(x,y)
移动translate(x,y)：水平方向和垂直方向同时移动
translateX(x)：仅水平方向移动
translateY(y)：仅垂直方向移动
transform: translate(50%); %表示走自己宽度的一半
transform: translate(-50%, -50%);

**定位的盒子居中对齐的完美写法：**
```
div {
	position: absolute;
	left: 50%;
	top: 50%;
	/*margin-left: -100px;*/
	transform: translate(-50%, -50%);
}
```

- 缩放scale(x,y)
scale(x,y)
scaleX(x)
scaleY(y)

transform: scale(0.8,1); /*缩小：0.01~0.99，放大：1.01~*/

- 旋转roate(deg)
transform: rotate(45deg);
transform-origin可以调整元素转换的原点,4个角可用left top等，精确位置用px像素
deg是单位，正值顺时针，负值逆时针

注：
元素旋转后，坐标轴也跟着发生转变
调整顺序后可以解决，把旋转放到最后
注意单位是deg度数

- 倾斜skew(deg, deg)
transform: skew(30deg, 0deg); /*水平倾斜30度，第二个参数不写默认为0*/

transform-origin可以调整元素转换的原点
```
div {
	 transform-origin: left top;
	 transform: rotate(45deg); 
}  /* 改变元素原点到左上角，然后进行顺时旋转45度 */    
```

# 3D变形(CSS3) transform
## 旋转 rotate
rotateX()：沿着x立体旋转
```
	img {
		transition: all 0.5s ease 0s;
	}
	img:hover {
		transform: rotateX(180deg);
	}
	
```
rotateY()：沿着y立体旋转
rotateZ()：沿着Z立体旋转
backface-visibility: hidden; 不是正面就隐藏

## 透视 perspective
透视原理：近大远小
浏览器透视：把近大远小的所有图像，透视在屏幕上
perspective：视距，表示视点距离屏幕的长短。视点，用于模拟透视效果时人眼的位置

perspective一般作为一个属性，设置给父元素，作用于所有3D转换的子元素

## 移动 translate
translateX(100px);
translateY(100px);
translateZ(100px); 物体到屏幕的距离

transform: translate3d(x, y, z);x和y可以是px或%，z只能是px

# 动画(CSS3) animation
animation: 动画名称 动画时间 运动曲线 何时开始 播放次数 是否反向;

|属性						|描述											|CSS|
|--							|--												|--	|
|@keyframes					|规定动画										|3	|
|animation					|除了animation-play-state属性外的属性的简写属性	|3	|
|animation-name				|规定@keyframes动画的名称						|3	|
|animation-duration			|规定动画完成一个周期所花费的秒或毫秒。默认是0	|3	|
|animation-timing-function	|规定动画的速度曲线。默认是ease					|3	|
|animation-delay			|规定动画何时开始。默认是0						|3	|
|animation-iteration-count	|规定动画被播放的次数。默认是1					|3	|
|animation-direction		|规定动画是否在下一周期逆向播放。默认是normal	|3	|
|animation-play-state		|规定动画是否正在运行或暂停。默认是running		|3	|
|animation-fill-mode		|规定对象动画时间之外的状态						|3	|
```
@keyframes 动画名称 {
	from {
		transform: translateX(0);
	}
	to {
		transform: translateX(500px);
	}
}
```
animation-iteration-count: infinite;无限循环
animation-direction: normal | reverse | alternate(交替正反) | alternate-reverse(交替反正);
一般情况只用：
	animation: animation-name animation-duration;

**多组动画**
```
@keyframes goback {
	0% {/*起始位置 等价于from*/
		
	}
	50% {
		transform: translateX(1000px);
	}
	51% { /*反转图片*/
		transform: translateX(1000px) rotateY(180deg);
	}
	100% {/*结束为止 相当于to*/
		transform: translateX(0) rotate(180deg);
	}
}
```

# 伸缩布局(CSS3)
父级添加：display: flex;

属性：

1. flex子项目在主轴缩放比例，不指定flex则不参与伸缩分配。flex: 1;
通过给某个盒子固定宽度：width: 100px; 则剩下的盒子在减去100px的宽度中分
min-width: 280px; 最小宽度不能小于280px;
max-width: 1200px; 最大宽度不能大于1200px;

2. flex-direction: row | column; 设置主轴方向水平|垂直 (父级添加)

3. justify-content调整主轴对齐(水平对齐)

|值				|描述											|												|
|--				|--												|--												|
|flex-start		|默认值。项目位于容器开头。						|让子元素从父容器开头排列						|
|flex-end		|项目位于容器结尾								|让子元素从父容器后面排列						|
|center			|项目位于容器中心								|让子元素从父容器中间显示						|
|space-between	|项目位于各行之间留有空白的容器内				|左右的盒子贴近父盒子，中间的平均分布空白间距	|
|space-around	|项目位于各行之前、之间、之后都留有空白的容器内	|相当于给每个盒子添加了左右margin外边距			|

4. align-items调整侧轴对齐(垂直对齐) *单行用的较多*

|值			|描述							|白话文												|
|--			|--								|--													|
|stretch	|默认值，项目被拉伸以适应容器	|让子元素的高度拉伸适用父容器（若子元素不给高度）	|
|center		|项目位于容器中心				|垂直居中											|
|flex-start	|项目位于容器的开头				|垂直对齐开始位置									|
|flex-end	|项目位于容器的结尾				|垂直对齐结束位置									|

5. flex-wrap控制是否换行
当我们盒子内容的宽度多于父盒子的时候如何处理

|值				|描述																|
|--				|--																	|
|nowarp			|默认值，规定灵活的项目不拆行或不拆列。不换行，则收缩（压缩）显示	|
|wrap			|规定灵活的项目在必要的时候拆行或拆列								|
|wrap-reverse	|规定灵活的项目在必要的时候拆行或拆列，但以相反的顺序				|

6. align-content堆栈（由flex-wrap产生的独立行）对齐
align-content是针对felx容器里面多轴（多行）的情况，align-items是针对一行的情况进行排列
必须对父元素设置自由盒属性display: flex;并且设置排列方式为横向排列flex-direction: row;并设置换行，flex-wrap: wrap;
如：
```
	display: flex;
	flex-flow: row wrap;
```
这样align-content属性才会起作用

|值				|描述											|
|--				|--												|
|stretch		|默认值，项目被拉伸以适应容器					|
|center			|项目位于容器中心								|
|flex-start		|项目位于容器的开头								|
|flex-end		|项目位于容器的结尾								|
|space-between	|项目位于各行之间留有空白的容器内				|
|space-around	|项目位于各行之前、之间、之后都有空白的容器内	|

7. order控制子项目的排列顺序，正序方式排序，从小到大
order: -1; 数字越小越靠前，可为负，默认为0；

# BFC(块级格式化上下文)
BFC是一个独立的渲染区域，只有Block-level Box参与，它规定了内部的Block-level Box如何布局，并且与这个区域外部毫不相干

## 能产生BFC的元素
display: block | list-item(ul>li) | table

给以上元素添加如下属性可触发BFC：
- float不为none
- display为inline-block,table-cell,table-caption,flex,inline-flex
- overflow不为visible

## BFC元素所具有的特性
BFC布局规则特性：
1. 在BFC中，盒子从顶端开始垂直地一个接一个排列
2. 盒子垂直方向的距离由margin决定。属于同一个BFC的两个相邻盒子的margin会发生重叠
3. 在BFC中，每一个盒子的左外边缘(margin-left)会触碰到容器的左边缘(border-left)（对于从右到左的格式来说，则触碰到右边缘）
4. BFC的区域不会与浮动的盒子产生交集，而是紧贴浮动边缘
5. 计算BFC的高度时，自然也会检测浮动的盒子的高度

它是一个独立的渲染区域，只有Block-level Box参与，它规定了内部的Block-level Box如何布局，并且与这个区域外部毫不相干

## BFC的用途
1. 清除元素内部浮动(父元素未设置高度时)
只要把父元素设为BFC就可以清理子元素的浮动了，最常见的用法是在父元素上设置overflow: hidden;对于IE6加上zoom: 1;
主要用到：
**计算BFC的高度时，自然也会检测浮动的盒子高度**

2. 解决外边距合并问题
主要用到
**盒子垂直方向的距离由margin决定。属于同一个BFC的两个相邻盒子的margin会发生重叠**
属于同一个BFC的两个相邻盒子的margin会发生重叠，那么我们创建不属于同一个BFC，就不会发生margin重叠了

3. 制作右侧自适应的盒子问题
主要用到
**BFC的区域不会与浮动盒子产生交集，而是紧贴浮动边缘**

# CSS补充知识
## 焦点部分所用知识点
## 背景半透明
## 优雅降级和渐进增强
渐进增强(progressive enhancement)：针对低版本浏览器进行构建页面，保证最低的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。
优雅降级(graceful degradation)：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容
*区别*：渐进增强是向上兼容，优雅降级是向下兼容

## 浏览器前缀
|浏览器前缀	|浏览器									|
|--			|--										|
|-webkit-	|Google Chrome, Safari, Android Browser	|
|-moz-		|Firefox								|
|-o-		|Opera									|
|-ms-		|Internet Explorer, Edge				|
|-khtml-	|Konqueror								|

## 背景渐变
兼容性问题很严重，必须在前面添加浏览器的私有前缀
线性渐变：
```
background: -webkit-linear-gradient(渐变的起始位置, 起始颜色, 结束颜色);
如:background: -webkit-linear-gradient(top, red, green);
background: -webkit-linear-gradient(渐变的起始位置, 颜色 位置, 颜色 位置...);
如:backgrouond: -webkit--linear-gradient(top, red 0%, green 50%, skyblue 80%, hotpink 100%);
```

## CSS3 W3C统一验证工具
CssStats是一个在线的CSS代码分析工具
http://www.cssstats.com

**[W3C统一验证工具](http://validator.w3.org/unicorn/)**

## CSS压缩
站长之家：http://tool.chinaz.com/Tools/CssFormat.aspx

## 旋转轮播图
需要用到**透视**，**过渡**，**子元素**，**preserve-3d**

**transform-style**
指定嵌套元素如何在3D空间中呈现
flat：默认值，表示所有子元素在2D平面呈现
preserve-3d：表示所有子元素在3D平面呈现