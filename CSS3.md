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
## 并集选择器
## 后代选择器
## 子元素选择器