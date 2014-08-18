---
layout: post
published: true
title: Test Markdown
comments: true
categories: misc
---

#Test
![Mou icon](http://mouapp.cmo/Mou_128.png)
##Overview
**Mou**,the missing Markdown editor for *web developer*
###Syntax
####String and Emphasiza
**Stronger** or __strong__
*emphasizer* or _emphasizer_
**Sometimes I want a lot of text to be bold.
Like,seriously,a _LOT_OF text**
####Blockquotes
>Right andle brackets &gt;are used for block quotes.

####Links and Email
And email <example@example.com>link.
Simple inline link <http://cheluois.com>,another inline link[Smaller](http://smallerapp.com),one more inline link with title [Resize](http://z.cn)
A ![Resize icon][2]reference style image.
[2]:http://resizesafari.com/favicon.ico "Title"
####Codes
``` sh
git reset HEAD^
```

``` sh
rake install[classic]
```

Some [Zsh][] users know what would happen when we type that commands:

[Zsh]: http://www.zsh.org

``` sh
zsh: no matches found: HEAD^
```

``` sh
zsh: no matches found: install[classic]
```

This is caused by Zsh:

> zsh allows Filename Generation and Pattern Matching (Globbing) using square brackets and other characters (explained in the [zsh guide](http://zsh.sourceforge.net/Guide/zshguide05.html), section 5.9).

The solution is simple:

> The solution, found in the [zsh FAQ](http://zsh.sourceforge.net/FAQ/zshfaq03.html) (section 3.4), is simply adding a line in ~/.zshrc that disables globbing for a single command:

``` sh
alias rake="noglob rake"
```

Aliasing `git` is also useful:

``` sh
alias git="noglob git"
```