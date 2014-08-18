---
layout: post
published: true
title: Test Markdown
comments: true
categories: misc
---

#分享代码片段
原文链接[Sharing Code Snippets](http://octopress.org/docs/blogging/code/)  
分享代码非常重要,用代码写博客应该是容易而且优美的。这就是为什么Octopress包含一些特性来使你编码快步如飞。尽管Jekyll支持[Pygments语法高亮](http://pygments.org/)，Octopress能够使得它更好，如下所示。

* 专门为Octopress创造了[Solarized语法高亮](http://ethanschoonover.com/solarized)的Sass接口。
* 嵌入式Gist代码 - by [Brandon Tilly](https://gist.github.com/1027674)
* 简单地用`<figure>`和`<figcaption>`构造代码块和可选的下载链接。
* Pygments缓存 - 一个[Jekyll社区插件](https://github.com/rsim/blog.rayapps.com/blob/master/_plugins/pygments_cache_patch.rb).

点击[测试页面](http://octopress.org/docs/blogging/code/test)查看结果。

---
##反斜杠代码块
有了`backtick_codeblock`过滤器，你可以使用Github可爱的反斜杠语法高亮代码块。你只需要用三个反斜杠开始一行并开始编写代码。

---
##语法

	```[language] [title] [url] [link text] [linenos:false] 	[start:#] [mark:#,#-#]
	code snippet
	```

---
##基本选项
* `[language]`-用来进行语法高亮。传递'plain'参数禁用高亮.([支持的语言](http://pygments.org/docs/lexers/))
* `[title]`-向你的代码块添加figcaption
* `[url]`下载或指示你的代码引用链接
* `[Link Test]`链接的显示文本，默认为'link'

---
##附加选项
下列选项不依赖于之前的选项并且选项的先后顺序无关。
* `start:#`-行号以#开始(用代码片段引用长的代码段时有用)。
* `mark:#,#-#`-用"mared"这个类名来标记一行或多行代码。接受一个数字，用逗号分隔的数字和数字范围。例如`mark:1,5-8`标记第1,5,6,7,8行。注意：如果你已经改变了起始的行号，请确认这些能够匹配赋予的行号。
* `linenos:false`-不要向高亮代码添加行号。

---
##示例
1.没有设定语言
```
$ git clone git@github.com:imathis/octopress.git # fork octopress
```  
源码：

	```
	$ git clone git@github.com:imathis/octopress.git # fork octopress
    ```  
    
2.使用代码高亮和代码链接
``` ruby Discover if a number is prime http://www.noulakaz.net/weblog/2007/03/18/a-regular-expression-to-check-for-prime-numbers/ Source Article
class Fixnum
  def prime?
    ('1' * self) !~ /^1?$|^(11+?)\1+$/
  end
end
```  
源码：

	``` ruby Discover if a number is prime http://www.noulakaz.net/weblog/2007/03/18/a-regular-expression-to-check-for-prime-numbers/ Source Article
	class Fixnum
  	def prime?
    	('1' * self) !~ /^1?$|^(11+?)\1+$/
  	end
	end
	```  
    
3.使用自定义起始行号，标记第52行和54-55行。
``` coffeescript Coffeescript Tricks start:51 mark:52,54-55
# Given an alphabet:
alphabet = 'abcdefghijklmnopqrstuvwxyz'

# Iterate over part of the alphabet:
console.log letter for letter in alphabet[4..8]
```  
源码：
	``` coffeescript Coffeescript Tricks start:51 mark:52,54-55
	# Given an alphabet:
	alphabet = 'abcdefghijklmnopqrstuvwxyz'
	
	# Iterate over part of the alphabet:
	console.log letter for letter in alphabet[4..8]
	```

---
##其他嵌入代码的方式
你或许喜欢[从文件嵌入代码](http://octopress.org/docs/plugins/include-code)或[嵌入Github gists](http://octopress.org/docs/plugins/gist-tag).

---
##嵌入Gist
你需要的仅仅是一个gist id然后你就能够在你的页面中嵌入代码。这其实是下载gist的缓存并为了RSS阅读器和搜索引擎将它嵌入到`<noscript>`标签，与此同时仍然使用Github的javascript gist嵌入代码为浏览器。  
###语法
	{% gist gist_id [filename]%}
###示例
	{%gist 4321346%}
{%gist 4321346%}

如果你想要语法高亮(对[特定语言](http://pygments.org/docs/lexers/))，指定文件名(有后缀名)即可：
	{% gist 4321346 gistfile1.diff %}
{% gist 4321346 gistfile1.diff %}









