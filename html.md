
HTML
========

缩进
--------
HTML所有代码均必须按照层级关系进行缩进，且只能使用**TAB**来作为缩进单位，每层级缩进一个单位。**不能使用任何空格用来作为缩进**。


元素
--------
+ 在非特殊情况下，仅使用HTML5包含的所有元素标签；  

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
	```
	可以使用w3c官方验证进行审核：http://validator.w3.org/

+ 尽可能的使用alt及title元素补全描述及不可见内容：
	```html
	<img src="demo.jpg" alt="样例" />
	
	<a href="/index.php" title="一个现实补全的新闻标题">一个显示不全的...</a>
	```
	
