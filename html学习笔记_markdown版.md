# 学习html标签语言
<hr/>

<a name="content"><h2>目录</h2></a>
                 
[学习html标签语言](#title)
  - [1. 有序列表的写法](#head)
  - [2. 无序列表的写法](#emphasize)
  - [3. 定义描述标签的写法](#list)
  - [4. 定义描述标签的写法](#block-quote)
  - [5. 分区标签语法的写法](#link-image)
  - [6. 常用的行级标签的用法](#table)
  - [7. 图片和链接的插入](#code)
  - [8. 表格标签的使用](#splitter)
  - [9. 其他标签的使用](#construct-content)

##主要内容
1.块级标签
2.有序列表
3.无序标签
4.定义描述标签——dl标签
5.分区标签语法
6.常用的行级标签
7.超链接、图片以及特殊符号的使用

###1 块级标签[<sup>目录</sup>](#content)
      ```<!doctype html>
      <html>
      <head>
      <title>第一次学习html标签语言</title>
    <meta http-equiv="Content-Type" content="text/html;charset=gb2312"/>
    <meta name="keywords" content="Fang的html笔记"/>
    <meta name="description" content="fang'notebook of html"/>  
     </head>
     <body>
    此次学习时间是2018年3月9号，星期五
    主要的学习内容有：
    1. html的基本结构
    2. head标签的主要元素
     </body>
    </html>```

+ 这个是html的大框架，包括html，head，body，还有最开始的引用（HTML5版本对此要求不严）

###2 有序列表的写法[<sup>目录</sup>](#content)
例如：

	  <ol>
      <li>使用有序列表符号ol和列表符号li编写</li>
	  <li>记得要写上“<>”的符号</li>
      </ol>
###3 无序列表的写法	[<sup>目录</sup>](#content)
例如：
	 
	 <ul>
	 <li>首先使用无序列表符号ul和列表符号li编写</li>
	 <li>然后也要记得写上“<>”的符号</li>
	 </ul>
###4 定义描述标签的写法[<sup>目录</sup>](#content)
例如：

      <dl>
          <dt>水</dt>
		  <dd>符号：H<sub>2</sub>O</dd>
		  <dd>生命之源</dd>
		  
		  <dt>氧气</dt>
		  <dd>符号：O<sup>2</sup></dd>
		  <dd>人呼吸之必须物质</dd>
      </dl>
###5 分区标签语法的写法[<sup>目录</sup>](#content)
+ 使用div标签开头和结尾
+ 在书写开头的div标签时候可以加入id=“what”来对该分区进行命名

例如： 

      <div id="各标签语言的写法">
      123456789.
      </div>

+ `<div>`标签的使用我没有精学，等到用的上的时候，再做详细介绍。

###6 常用的行级标签的用法[<sup>目录</sup>](#content)

定义粗体文本——`<b>`<br/>
定义斜体文本——`<i>`<br/>
定义强调文本，实际效果与斜体文本差不多，但是语义是不一样的。——`<em>`<br/>
定义粗体文本，与b的作用基本相同，但是语义不一样。——`<strong>`<br/>
定义小号文本，——`<small>`<br/>
定义下标文本——`<sub>`<br/>
定义上标文本——`<sup>`<br/>
定义文字的显示方向，内有dir属性，只能取值"ltr"或者"rtl"——`<bdo>`<br/>
+ 反方向的格式化元素举个栗子</li>
	  
	  <p>豪哥帅</p>
	  <p><bdo dir="rtl">豪哥帅</bdo></p>
反向效果：
   
  <a href="http://www.baidu.com.cn" target="_blank"><img src="./ppp/headsome.png"alt="帅哥豪"></a>

###7 图片和链接的插入[<sup>目录</sup>](#content)
####7.1 图片的插入   
例如：
     ```<img src="./ppp/happy.jpg"alt="baidu">```
效果如下：
     <img src="./ppp/happy.jpg"alt="baidu"/>

####7.2 链接的插入 
例如：
   `<a href="http://www.baidu.com.cn" target="_blank">baidu</a>`
链接效果：<a href="http://www.baidu.com.cn" target="_blank">baidu</a>

###8 表格标签的使用[<sup>目录</sup>](#content)
####8.1 表格的相关元素
`<table>`-用于定义表格
    `<tr>`-定义表格的“行”，该元素只能包括td或者th两种元素
    `<td>`-定义单元格，包括两个主要的属性：colspan-制定单元格跨多少列，rowspan-制定单元格可横跨的行数。
	`<caption>`-用于定义表格标题
	`<tbody>`-用于定义表格的主体
	`<thead>`-用于定义表格头
	`<tfoot>`-用于定义表格脚
####8.2 表格的书写
例子
     `<table width="40%" height="0px" boder="0" bgcolor="#ffffff" cellspacing="0px" cellpadding=""0px align="center">`
     ```<caption>我喜欢的歌曲</caption>
    <thead>
	    <tr><th>歌名</th><th>作者</th></tr>
     </thead>
	 <tbody>
	    <tr><td>光辉岁月</td><td>Beyond</td></tr>
	    <tr><td>红豆</td><td>王菲</td></tr>
	    <tr><td>我只在乎你</td><td>邓丽君</td></tr>
	    <tr><td>倩女幽魂</td><td rowspan="2">张国荣</td></tr>
	    <tr><td>有谁共鸣</td></tr>
	 </tbody>
     <tfoot>
	    <tr><td colspan="2">现在总计：5首歌曲</td></tr>
	 </tfoot>
     </table>```
+ 上面两段代码是放在一起的
+ html的表格制作略显繁琐，还是Markdown Pad好些。
效果图如下：
<img src="./ppp/table1.png"alt="我喜欢的音乐" >
+ Markdown里面没法对图片进行居中。


###9 其他标签的使用[<sup>目录</sup>](#content)
####9.1 botton标签的使用
botton标签是一个按钮标签，在标签内写文字只是按钮上的文字，没有什么作用，所以botton标签需要安装在其他的标签之内，<br/>比如链接标签。
	 
<a href="http://www.baidu.com.cn" target="_blank"> <button>baidu</button> </a>
 
####9.2 code and pre标签
   这两个标签中都可以加代码<br/>`<code>`标签是镶嵌式的加入代码，而`<pre>`是大段大段的加入代码。
这个跟Markdown里面的<code>`</code>是一样的，用一对反引号将代码括起来，是可以完成“嵌入型”代码插入。
如果用三对反引号，即<code>```</code>来高过代码，是可以完成“引用式”的代码插入。
####9.3 换行标签
`<br/>`标签在html中还是比较常见的，使用该标签可以使得在一个`<p>`标签里面完成多行文本的书写。
####9.4 上标下标标签
`<sup>,<sub>`分别是上标和下标
例子：`H<sub>2</sub>O   跟 O<sup>2-</sup>`
效果：H<sub>2</sub>O   跟 O<sup>2-</sup>

####9.5 html中的空格跟商标
`&nbsp;跟&copy;`分别表示空格，跟版权
例如&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&copy;版权所有
上述例子有10个空格和一个版权符号组成。







