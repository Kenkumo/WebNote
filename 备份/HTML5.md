# HTML

## Web标准

- 结构标准：HTML
- 样式标准：CSS
- 行为标准：js

## HTML基本结构

``` html
<html>
    <head>
      <title></title>
	</head>
	<body>
	</body>
</html>
```

# HTML标签
## 标签分类
双标签:`<body> </body>`
单标签:`<br />`
## 标签关系
嵌套关系
并列关系
## doctype文档类型
`<!DOCTYPE html>`:表示HTML5的版本
## 字符集
`<meta charset="UTF-8">`
## 标签语义化（含义）
1.方便阅读和维护
2.浏览器，爬虫更好解析
3.更好的搜索引擎优化
## HTML常用标签
### 排版标签
1. 标题标签:`<h1~6></h1~6>`
2. 段落标签:`<p></p>`,根据浏览器窗口大小自动换行
3. 水平线标签:`<hr />`
4. 换行标签:`<br />`
5. div和span标签:`<div></div>,<span></span>`
### 文本格式化标签
1. 加粗:`<b></b>,<strong></strong>`,推荐strong
2. 倾斜:`<i></i>,<em></em>`,推荐em
3. 删除线:`<s></s>,<del></del>`,推荐del
4. 下划线:`<u></u>,<ins></ins>`,推荐ins
### 标签属性(尽量不使用)
比如:`<hr width="500" color="red" />`
### 图像标签
`<img src="图形URL" />
#### 属性
1.	alt:图片显示不出时替换成文字
2.	title:鼠标悬停显示文字
3.	width:宽度(一般选一个就行)
4.	height:高度(一般选一个就行)
5.	border:设置边框(一般不使用)
### 链接标签
`<a herf="跳转路径" target="目标窗口的弹出方式"></a>`
链接地址：
	外部链接:http://
	内部链接:index.html
弹出方式：
	-self
	-blank
### 锚点定位
适合较长页面，通过点击关键词，从而迅速到达这个位置
<a href="#id名"></a>
<h3 id="id名"></h3>
### base标签
<head>
	<base target="_blank" />新窗口打开
</head>
### 特殊字符标签
1.	空格:&nbsp;
2.	<:&lt;
3.	>:&gt;
4.	©:&copy;
### 注释标签
<!-- -->
快捷键：
	单行注释：ctrl + /
	多行注释：ctrl + shift + /
# 路径
## 相对路径
1.	同一级路径:<img src="logo.jpg" />
2.	下一级路径:<img src="image/logo.jpg" />
3.	上一级路径:<img src="../../logo.jpg" />
## 绝对路径（很少使用）
#列表标签
## 无序列表ul
注：ul中只能放li
<ul>
	<li>1</li>
	<li>2</li>
	<li>3</li>
</ul>
## 有序列表ol
<ol>
	<li>1</li>
	<li>2</li>
	<li>3</li>
</ol>
## 自定义列表
经常用于对术语或名词进行解释和描述
<dl>
	<dt>定义标题</dt>
	<dd>定义描述、解释</dd>
</dl>
# 表格table
## 结构
注：table中只能放tr，tr中只能放td
<table>
	<tr><!-- 行标签 -->
		<td></td><!-- 单元格标签 -->
	</tr>
</table>
## 属性
1. border：表格边框，默认为0
2. cellspacing：单元格与单元格边框之间的空白间距
3. cellpadding：单元格内容与单元格边框之间的空白间距
4. width：表格宽度
5. height：表格高度
6. align：表格在网页中的水平对齐方式，left,center,right
## 表头标签
<table>
	<tr>
		<th></th><!-- 加粗居中显示 -->
	</tr>
</table>
## 可用结构
<table>
	<caption>表格标题</caption>
	<thead>
		<tr>
			<th></th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td></td>
		</tr>
	</tbody>
</table>
## 浏览器查看HTML标签元素
ctrl + shift + I
## 表格标题标签
<caption></caption>
## 合并单元格
跨行合并：rowspan <td rowspan="2"></td>
跨列合并：colspan <td colspan="2"></td>
# 表单标签
## input标签
<input type="" />
type:
文本框：text
密码框：password
单选按钮：radio,<input type="radio" name="sex" /> 女 <input type="radio" name="sex" /> 男`
复选框：checkout
普通按钮：button,`<input type="button" value="搜索" />`
提交按钮：submit,`<input type="submit" value="提交" />`
重置按钮：reset,<input type="reset" value="重置" />
图像形式的提交按钮：image,<input type="image" src="im.jpg" />
文件域：file,<input type="file" /><!-- 上传文件 -->
name：控件名称,`性别: 
value：默认值,`搜索: <input type="button" value="搜索" />
size：显示宽度
checked：选择控件默认被选中`性别: <input type="radio" name="sex" checked="checked" /> 女 <input type="radio" name="sex" /> 男`
maxlength：允许输入最多字符数
## label标签
用label直接包裹input：<label><input type="text" /></label>
用for id的格式来定位某个表单：<label for="two"> <input type="text" /> <input type="text" id="two" /> </label>
## textarea文本域标签
用作留言框
<textarea></textarea><!-- 可变文本框 -->
## 下拉菜单
<select>
	<option></option>
	<option></option>
	<option></option>
</select>
默认：selected="selected"
## 表单域
收集表单控件信息并且提交
<form action="url" method="get/post" name="表单名称(区别不同表单)">
	<label>用户名: <input type="text" name="username"/></label>
	<label>密&nbsp;码 <input type="password" name="pwd"</label>
	<input type="submit" value="提交" />
	<input type="reset" value="重置" />
</form>
# HTML5X新增标签
1.	header：定义页面头部
2.	nav：定义导航栏
3.	footer：定义页面底部
4.	article：定义文章
5.	section：定义区域
6.	aside：定义侧边
7.	datalist：
<input type="text" value="输入明星" list="star" />
<datalist id="star">
	<option></option>
	<option></option>
	<option></option>
</datalist>
8.	fieldset：
<fieldset>
	<legend>用户登录</legend>
	用户名：<input type="text" />
	密 码:<input type="password" />
</fieldset>
9.	新增input type属性值
email：输入邮箱格式
tel：手机号码格式
url：url格式
number：格式
search：搜索框（体现语义化）
range：自由拖动滑块
time：小时分钟
date：年月日
datetime：时间
month：月 年
week：星期 年
color：颜色
10. 常用新属性
placeholder：提示信息占位符
autofocus：页面加载时input元素自动获取焦点
multiple：多文件上传
autocomplete：表单是否启动自动完成功能，on（记录上次提交值）、of
required：必填项
accesskey：规定激活（使元素获得焦点）元素的快捷键，采用alt+字母形式
## 多媒体标签
1.	视频：<embed></embed>
2.	音频：<audio src="" autoplay controls loop="-1"></audio>
autoplay：自动播放
controls：显示默认播放控件
loop：循环次数
浏览器兼容做法：
<audio controls autoplay>
	<source src="music.mp3" />
	<source src="music.ogg" />
	您的浏览器不支持播放声音
</audio>
3.	小视频：<video src="mp4.mp4" autoplay controls width="500"></video>
4.	兼容做法：
5.	<video controls autoplay>
6.		<source src="mp4.mp4" />
7.		<source src="mp4.ogg" />
8.		您的浏览器不支持视频播放
7.	</video>