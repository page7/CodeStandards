
HTML
========

基本
--------

+ 文件：一律使用 utf-8 非 BOM 编码。

+  缩进：HTML所有代码均必须按照层级关系进行缩进，且只能使用**TAB**来作为缩进单位，每层级缩进一个单位。**不能使用任何空格用来作为缩进**。

+ 样式要在页面顶部加载，JS 文件在页面底部加载。


元素
--------

+ 在非特殊情况下，仅使用HTML5包含的所有元素标签； 
	虽然HTML5支持自定义标签，但在此不建议开发人员自定义，减少他人不便于理解的标签，
	所有标签描述：http://www.w3school.com.cn/tags/index.asp

+ 所有元素及其属性，必需使用小写字母；
	```html
	<a href="/index.html" target="_blank">超链接</a>
	```

+ 规范化的代码结构，**禁止**出现以下情况：
	```html
	<p><span>错误的标签结束顺序</p></span>
	
	<a><div>错误的内容元素类型</div></a>
	
	<ul><a><li>错误的内容元素类型，且打乱默认关系</li></a></ul>
	
	<img src="demo.jpg"> 不闭合的标签
	
	<form method=get>属性的值缺少引号</form>
	
	<img src='demo.jpg' /> 使用单引号包裹属性的值
	```
	关于各种元素所能包含的其他元素类型，主要在于区分**内联元素**及**块元素**。   
	其次需要特别注意：**section, article, aside** 元素的使用，这几个元素不是样式容器，而是内容中用来帮助构建文档概要的语义部分。  
	li 标签内必须被 ul / ol 包裹，dt / dd 必须被 dl 包裹。  

+ 尽量使用alt及title元素补全描述及不可见内容：
	```html
	<img src="demo.jpg" alt="样例" />
	
	<a href="/index.php" title="一个现实补全的新闻标题">一个显示不全的...</a>
	```
	
+ 非独立完成项目，确保结构、样式、行为文件的分离；

+ 不可省略 table 下的 tbody 元素。



属性
--------

+ 使用不常用属性，请务必到相关网站查询属性是否继续被支持，如：td 元素的 bgcolor 等；

+ 用来执行脚本的空链接，必须使用 `href="javascript:;"` 属性；

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

+ KEYWORDS 不超过5个，长度不超过100汉字，且用英文“,”分隔。  
	关键词请参考百度搜索指数等工具。

+ DESCRIPTION 不超过255个字符  


验证
--------
使用w3c官方验证进行代码检查：http://validator.w3.org/