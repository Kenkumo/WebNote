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

