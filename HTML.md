# HTML


http://www.w3school.com.cn/html/html_intro.asp

- HTML 指的是超文本标记语言 (Hyper Text Markup Language)
- HTML 不是一种编程语言，而是一种标记语言 (markup language)
- 标记语言是一套标记标签 (markup tag)
- HTML 使用标记标签来描述网页

所以学 HTML 最最基本的就是学习各种标签。

HTML文档 = 网页

HTML 标签对大小写不敏感 但推荐小写 所以还是用小写吧。


##　标签

基本格式

```
<html>

<head>
	<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>

<body>

<h1>My First Heading</h1>

<p>My first paragraph.</p>

</body>
</html>
```


html 定义了整个 HTML 文档。

body 定义了 HTML 文档的主体，可见内容。


h1 - h6  标题(heading)

```
<h1>这是个一级标题</h1>
```

p 段落

```
<p>This is a paragraph.</p>

```

`<hr />` 水平线

a 链接 href 属性指定链接

```
<a href="http://www.yifeiyuan.me">This is a link</a>
```

img 图片

```
<img src="imgs/ace.jpg" width="104" height="142" />
```

div 定义文档中的节或区域(块级)

span 定义文档中的行内的小块或区域

`<br/>` 换行

`<!-->` 注释

b  加粗

```
<b>This text is bold </b>
```

strong 加粗？
```
<strong>This text is strong</strong>
```

big 

em  emphasized 强调 斜体
```
<em>This text is emphasized</em>
```


i 斜体

sub 下标  sup 上标

```
<sub>subscript</sub>
```


pre 预格式文本的标签

code kbd tt samp var 显示计算机/编程代码  怎么这么多- -


address 地址


blockquote 长引用

q   短引用

del 删除线

ins 下划线


块级元素 p h1-h6



[HTML 文本格式化](http://www.w3school.com.cn/html/html_formatting.asp)


更多标签参考：
[HTML 参考手册](http://www.w3school.com.cn/tags/index.asp)


## HTML 属性

HTML 标签可以拥有属性。属性提供了有关 HTML 元素的更多的信息。
属性总是以名称/值对的形式出现，比如：name="value"。

属性总是在 HTML 元素的开始标签中规定。
始终为属性值加引号。

align="center" 		对齐方式
bgcolor="yellow" 	背景颜色
border="1"			表格边框

style 属性 css；多个属性用`;`分隔 
```
<p style="background-color:green">This is a paragraph.</p>

```

font-family 字体
font-size 尺寸
background-color 背景色

text-align 文本对齐  center

target="_blank" 在新窗口打开文档

name 属性规定 锚(anchor)的名称



## NOTE

HTML 会自动地在块级元素前后添加一个额外的空行

所有连续的空格或空行都会被算作一个空格



