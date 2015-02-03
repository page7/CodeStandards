开发代码规范
===================

规范版本：1.0 
适用范围：适用于所有开发项目使用 
编写作者：[nolanchou@gmail.com](mailto:nolanchou@gmail.com) 


PHP部分
----------
###文件/文件夹###
文件根据项目差异允许使用__小驼峰__或__以下划线间隔的小写名称__，推荐使用后者，以较完整的词汇描述文件内容。新的词汇使用，请在部门内公开探讨。
所有php后缀应均为.php，且使用utf-8 (non-BOM)格式。

除此之外，对以下特殊类型的文件，要求特殊的文件后缀。
类：.class.php
配置：.conf.php
方法(集)：.func.php
流程性文件： .inc.php
钩子文件： .hook.php
模板文件： .tpl.php
语言文件： .lang.php
**使用框架开发，请使用此框架要求的文件命名规范定义。**

文件夹命名与文件要求统一。


###代码结构###
* 缩进：所有代码缩进约定为**4个空格**，不可使用TAB键替换。

* 大括号：左括号和右括号要求在编辑器内处于同一列，且在关键词下一行。该条件应用于所有if / else if / else / for / foreach / switch / do / while / try 等语句。
	<pre><code>if ($i > 1)
	{
	    // ..statement..
	}
	else
	{
	    // ..other statement..
	}
	</code></pre>

* 运算符、小括号、空格、关键词和函数：
	1. 不同优先级运算符运算，不论是否需加括号，都应该补全括号表明运算顺序。
	2. 左括号“(”应与关键词或其他非括号字符之间有一个空格。
	3. 右括号“)”后非括号，点符号其他字符之间应有一个空格。
	4. 任何情况下，都应**禁止出现仅有空格或TAB的空行**，同时，**任何程序行尾不能出现多余的TAB或空格**。 
	5. 关键词应全部使用小写。
	6. 函数命名应根据开发框架环境使用对应的命名方式，**函数名后无空格**。
	7. 代码区域应规划合理，**任何超过15行的段落都应对应的断行并添加注释内容**。

	<pre><code>$a = (($c / 10 * 12) + ($a * 11) + $b);
	$b = 0;
    for ($i = 0; $i &lt;= $a; $i ++)
    {
        $b += $i;
    }
    </code></pre>

* 引号：所有单纯的文本引用，必需使用单引号。对于文本中存在小于三个的变量拼接，可使用单引号与点符号，也可以使用双引号。大量字符拼接务必使用双引号，并使用花括号如下格式：
	**严禁**在双引号中不使用花括号直接引用数组或对象的内容。
	<pre><code>$str = "{$world}，这是{$project['name']}的文档。请阅读并在第{$line -> number}行填写…";
	</code></pre>


###变量###
* 变量命名：
	由**约定俗成的缩写**和**完整词义单词**以及**下划线“_”**组成，如：
	<pre><code>$pre_column_name, $username, $translation_lang</code></pre>
	如使用临时变量，请在“$”后增加“_”（较大的临时数据请务必在使用结束后使用 unset 注销）如：
	<pre><code>$_time, $_temp, $_user</code></pre>
	
* 所有自定义变量必需经过初始化后才可以使用。
	<pre><code>$b = array();             // 不可省略此句
	foreach ($array as $v)
	{
		$b[] = $v;
	}
    </code></pre>


* 在变量不可控的情况下，一定要使用 isset() 或 empty() 判断变量是否存在后再运算。特别是如 GET、COOKIE、数据库读取结果等变量时。
	**禁止出现因此而引起的遍历或赋值报错，此错误大多会影响最终的结果。**

* 数组和多个变量赋值，要求等号的对齐：
	<pre><code>$username = 'ABC';
	$password = md5('123456');
	$lang     = 'zh-CN';
	
	$array    = array(
		'username'    => $username,
		'password'    => $password,
		'lang'        => $lang,
	);
	</code></pre>


###数据库查询###

简单的查询语句请在一行内完成。如涉及表关联、子表、多条件查询等，一律按照SQL标准格式化语句。
需要达到的要求是可逐层分析语句结构，如：
<pre><code>
SELECT  o.`order`, o.`time`, o,`status`, o,`uid`, 
		u.`name`, p.`product` 
FROM `order` AS o
	LEFT JOIN `user` AS u ON o.`uid` = u.`id` 
	LEFT JOIN `product` AS p ON o.`product` = p.`id`
WHERE o.`uid` = 12 AND p.`name` LIKE "%衬衣%"
ORDER BY o.`id` DESC
LIMIT 0,10;

</code></pre>

要点：

+ 关键词大写
+ 库名、表名、字段名需要右 “`” 符号包裹（大键盘数字1前的符号）
+ 独立子句要求缩进


HTML / CSS部分
----------

StackEdit stores your documents in your browser, which means all your documents are automatically saved locally and are accessible **offline!**

> **Note:**

> - StackEdit is accessible offline after the application has been loaded for the first time.
> - Your local documents are not shared between different browsers or computers.
> - Clearing your browser's data may **delete all your local documents!** Make sure your documents are synchronized with **Google Drive** or **Dropbox** (check out the [<i class="icon-refresh"></i> Synchronization](#synchronization) section).

#### <i class="icon-file"></i> Create a document

The document panel is accessible using the <i class="icon-folder-open"></i> button in the navigation bar. You can create a new document by clicking <i class="icon-file"></i> **New document** in the document panel.

#### <i class="icon-folder-open"></i> Switch to another document

All your local documents are listed in the document panel. You can switch from one to another by clicking a document in the list or you can toggle documents using <kbd>Ctrl+[</kbd> and <kbd>Ctrl+]</kbd>.

#### <i class="icon-pencil"></i> Rename a document

You can rename the current document by clicking the document title in the navigation bar.

#### <i class="icon-trash"></i> Delete a document

You can delete the current document by clicking <i class="icon-trash"></i> **Delete document** in the document panel.

#### <i class="icon-hdd"></i> Export a document

You can save the current document to a file by clicking <i class="icon-hdd"></i> **Export to disk** from the <i class="icon-provider-stackedit"></i> menu panel.

> **Tip:** Check out the [<i class="icon-upload"></i> Publish a document](#publish-a-document) section for a description of the different output formats.


----------


Synchronization
-------------------

StackEdit can be combined with <i class="icon-provider-gdrive"></i> **Google Drive** and <i class="icon-provider-dropbox"></i> **Dropbox** to have your documents saved in the *Cloud*. The synchronization mechanism takes care of uploading your modifications or downloading the latest version of your documents.

> **Note:**

> - Full access to **Google Drive** or **Dropbox** is required to be able to import any document in StackEdit. Permission restrictions can be configured in the settings.
> - Imported documents are downloaded in your browser and are not transmitted to a server.
> - If you experience problems saving your documents on Google Drive, check and optionally disable browser extensions, such as Disconnect.

#### <i class="icon-refresh"></i> Open a document

You can open a document from <i class="icon-provider-gdrive"></i> **Google Drive** or the <i class="icon-provider-dropbox"></i> **Dropbox** by opening the <i class="icon-refresh"></i> **Synchronize** sub-menu and by clicking **Open from...**. Once opened, any modification in your document will be automatically synchronized with the file in your **Google Drive** / **Dropbox** account.

#### <i class="icon-refresh"></i> Save a document

You can save any document by opening the <i class="icon-refresh"></i> **Synchronize** sub-menu and by clicking **Save on...**. Even if your document is already synchronized with **Google Drive** or **Dropbox**, you can export it to a another location. StackEdit can synchronize one document with multiple locations and accounts.

#### <i class="icon-refresh"></i> Synchronize a document

Once your document is linked to a <i class="icon-provider-gdrive"></i> **Google Drive** or a <i class="icon-provider-dropbox"></i> **Dropbox** file, StackEdit will periodically (every 3 minutes) synchronize it by downloading/uploading any modification. A merge will be performed if necessary and conflicts will be detected.

If you just have modified your document and you want to force the synchronization, click the <i class="icon-refresh"></i> button in the navigation bar.

> **Note:** The <i class="icon-refresh"></i> button is disabled when you have no document to synchronize.

#### <i class="icon-refresh"></i> Manage document synchronization

Since one document can be synchronized with multiple locations, you can list and manage synchronized locations by clicking <i class="icon-refresh"></i> **Manage synchronization** in the <i class="icon-refresh"></i> **Synchronize** sub-menu. This will let you remove synchronization locations that are associated to your document.

> **Note:** If you delete the file from **Google Drive** or from **Dropbox**, the document will no longer be synchronized with that location.

----------


Publication
-------------

Once you are happy with your document, you can publish it on different websites directly from StackEdit. As for now, StackEdit can publish on **Blogger**, **Dropbox**, **Gist**, **GitHub**, **Google Drive**, **Tumblr**, **WordPress** and on any SSH server.

#### <i class="icon-upload"></i> Publish a document

You can publish your document by opening the <i class="icon-upload"></i> **Publish** sub-menu and by choosing a website. In the dialog box, you can choose the publication format:

- Markdown, to publish the Markdown text on a website that can interpret it (**GitHub** for instance),
- HTML, to publish the document converted into HTML (on a blog for example),
- Template, to have a full control of the output.

> **Note:** The default template is a simple webpage wrapping your document in HTML format. You can customize it in the **Advanced** tab of the <i class="icon-cog"></i> **Settings** dialog.

#### <i class="icon-upload"></i> Update a publication

After publishing, StackEdit will keep your document linked to that publication which makes it easy for you to update it. Once you have modified your document and you want to update your publication, click on the <i class="icon-upload"></i> button in the navigation bar.

> **Note:** The <i class="icon-upload"></i> button is disabled when your document has not been published yet.

#### <i class="icon-upload"></i> Manage document publication

Since one document can be published on multiple locations, you can list and manage publish locations by clicking <i class="icon-upload"></i> **Manage publication** in the <i class="icon-provider-stackedit"></i> menu panel. This will let you remove publication locations that are associated to your document.

> **Note:** If the file has been removed from the website or the blog, the document will no longer be published on that location.

----------


Markdown Extra
--------------------

StackEdit supports **Markdown Extra**, which extends **Markdown** syntax with some nice features.

> **Tip:** You can disable any **Markdown Extra** feature in the **Extensions** tab of the <i class="icon-cog"></i> **Settings** dialog.

> **Note:** You can find more information about **Markdown** syntax [here][2] and **Markdown Extra** extension [here][3].


### Tables

**Markdown Extra** has a special syntax for tables:

Item     | Value
-------- | ---
Computer | $1600
Phone    | $12
Pipe     | $1

You can specify column alignment with one or two colons:

| Item     | Value | Qty   |
| :------- | ----: | :---: |
| Computer | $1600 |  5    |
| Phone    | $12   |  12   |
| Pipe     | $1    |  234  |


### Definition Lists

**Markdown Extra** has a special syntax for definition lists too:

Term 1
Term 2
:   Definition A
:   Definition B

Term 3

:   Definition C

:   Definition D

	> part of definition D


### Fenced code blocks

GitHub's fenced code blocks are also supported with **Highlight.js** syntax highlighting:

```
// Foo
var bar = 0;
```

> **Tip:** To use **Prettify** instead of **Highlight.js**, just configure the **Markdown Extra** extension in the <i class="icon-cog"></i> **Settings** dialog.

> **Note:** You can find more information:

> - about **Prettify** syntax highlighting [here][5],
> - about **Highlight.js** syntax highlighting [here][6].


### Footnotes

You can create footnotes like this[^footnote].

  [^footnote]: Here is the *text* of the **footnote**.


### SmartyPants

SmartyPants converts ASCII punctuation characters into "smart" typographic punctuation HTML entities. For example:

|                  | ASCII                        | HTML              |
 ----------------- | ---------------------------- | ------------------
| Single backticks | `'Isn't this fun?'`            | 'Isn't this fun?' |
| Quotes           | `"Isn't this fun?"`            | "Isn't this fun?" |
| Dashes           | `-- is en-dash, --- is em-dash` | -- is en-dash, --- is em-dash |


### Table of contents

You can insert a table of contents using the marker `[TOC]`:

[TOC]


### MathJax

You can render *LaTeX* mathematical expressions using **MathJax**, as on [math.stackexchange.com][1]:

The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral

$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$

> **Tip:** To make sure mathematical expressions are rendered properly on your website, include **MathJax** into your template:

```
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>
```

> **Note:** You can find more information about **LaTeX** mathematical expressions [here][4].


### UML diagrams

You can also render sequence diagrams like this:

```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```

And flow charts like this:

```flow
st=>start: Start
e=>end
op=>operation: My Operation
cond=>condition: Yes or No?

st->op->cond
cond(yes)->e
cond(no)->op
```

> **Note:** You can find more information:

> - about **Sequence diagrams** syntax [here][7],
> - about **Flow charts** syntax [here][8].

### Support StackEdit

[![](https://cdn.monetizejs.com/resources/button-32.png)](https://monetizejs.com/authorize?client_id=ESTHdCYOi18iLhhO&summary=true)

  [^stackedit]: [StackEdit](https://stackedit.io/) is a full-featured, open-source Markdown editor based on PageDown, the Markdown library used by Stack Overflow and the other Stack Exchange sites.


  [1]: http://math.stackexchange.com/
  [2]: http://daringfireball.net/projects/markdown/syntax "Markdown"
  [3]: https://github.com/jmcmanus/pagedown-extra "Pagedown Extra"
  [4]: http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference
  [5]: https://code.google.com/p/google-code-prettify/
  [6]: http://highlightjs.org/
  [7]: http://bramp.github.io/js-sequence-diagrams/
  [8]: http://adrai.github.io/flowchart.js/
