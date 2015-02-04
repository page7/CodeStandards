
HTML
========

基本
--------

+ 文件编码：使用 utf-8（非 BOM） 国际编码。

+ 文本编码：使用 `<meta charset="utf-8" />` 声明。

+ 代码缩进：使用**TAB**作为缩进单位，按照HTML层级关系进行缩进，**禁用空格**。

+ 资源加载：《CSS样式表》于页面顶部head内加载，《JS脚本》于页面底部body标签结束前加载。


标签
--------

+ 基本标签使用，请参详：http://www.w3school.com.cn/tags/index.asp，非特殊情况禁止使用自定义标签。

+ 标签及其属性需使用小写字母编写：
	```html
	<a href="/index.html" target="_blank">超链接</a>
	```

+ 编码规范**错误**示例：
	```html
	<p><span> 标签闭合顺序错误 </p></span>

	<a><div> 标签嵌套不规范 </div></a>

	<ul><a><li> 不被允许的结构 </li></a></ul>

	<img src="demo.jpg"> 标签未闭合

	<form method=get> 属性值缺少引号 </form>

	<img src='demo.jpg' /> 勿使用但因好编写属性值
	```

+ 基本编码规范说明：
	* **内联标签** 内部禁止嵌套 **块级标签**
	* 勿过度使用语义标签，如：**section、aside、article**
	* 勿打破标签默认关系，如：**ol/ul > li、dl > dt + dd**

+ 标签描述（不可见内容补全）：
	```html
	<img src="demo.jpg" alt="样例" />

	<a href="/index.php" title="一个不可见的新闻标题">样例</a>
	```

+ 项目协作请确保**标签结构、样式表、脚本文件**独立。

+ 请勿省略 table 标签下的 thead、tbody 标签。


属性
--------

+ 使用标签默认属性，请务必到相关网站查询属性是否继续被支持，如：td 标签的 bgcolor 属性等；

+ 用来执行脚本的空链接，必须使用 `href="javascript:void(0);"` 属性；

+ input 元素的 type 属性不可省略；

+ 省略 CSS 及 JS 引用时的 type 属性。



特殊符号/图标
--------
特殊符号请使用标准的文本转义字符，特别是例如 “<”，“>”，“=” 等会影响HTML结构的字符。  
参考：http://www.nolanchou.com/?p=897

常用图标集可免除大量的图片引入，降低服务器请求性能。常用的图标库包括：  
Font Awesome： http://fontawesome.io/icons/  
Glyphicons：http://glyphicons.com/  


SEO
--------
针对需要所搜索引擎优化的页面，具有以下要求：

+ TITLE 长度不宜过长，Google 可显示33个汉字，百度可显示30个汉字。

+ KEYWORDS 5个左右，不超过10个。长度不超过100汉字，且用英文“,”分隔。  
	关键词请参考百度搜索指数等工具。

+ DESCRIPTION 不超过255个字符  


验证
--------
使用w3c官方验证进行代码检查：http://validator.w3.org/
