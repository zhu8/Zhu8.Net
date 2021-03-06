---
categories:
- 黑犬 | Other
date: "2008-12-26T15:33:00+08:00"
tags:
- Blogger
- ScribeFire
title: ScribeFire添加Blogger出错及解决
url: /blog/2008/12/error-scribefire-to-blogger.html
---
ScribeFire添加Blogger出错，按照常规的步骤来，提示消息只是说出错，没有任何内容。
<!--more-->

<span class="center">![](/images/posts/blogger-error.jpg)</span>

解决方法：把Http://改成<span style='color: red;'>**Https://**</span>，如图：

<span class="center">![](/images/posts/Blogger-set.png)</span>

**Ok，搞定！**

> P.S：为了凑点字数，同时测试一下新买的键盘Dell SK-8115。发表感想若干：  
> *   很想把全站都弄成[Google](http://www.google.com/)集成的，用 [Google Apps](http://start.zhu8.net/) 中的Pages或者Sites发布首页和其他页面。用[Blogger](http://www.blogger.com/)发布[Blog](http://blog.zhu8.net/)。
>   
> *   目前[WhoPig.Com][1]不在我的控制之下（使用了[WHB](http://www.webhostingbuzz.com/)的空间），所以修改域名DNS比较麻烦，只好拿[Zhu8.Net][2]来试验。
>   
> *   WhoPig.Com目前又没有什么激情去弄了，我发觉我已经没有以前在学校为了某个CSS错误一个通宵做网站的耐性了。
>   
> *   Blog.Zhu8.Net很快就被Google全盘收录了（*数小时之内，并且连我开始发布错误的测试页都收了*），而WhoPig.Com到目前还没有收完……
>   
>

>   **测试Windows Live Writer，发现配置同样需要修改，先选择其他日志服务，使用原始地址http://zhu8.blogspot.com或者http://chenjun.com/都提示错误，必须将两个都改成HTTPS才可以，然后输入你的Google帐号和密码，另外类型需选择Atom Publishing Protocol，不要选择Blogger，然后在下面的地址输入：https://www.blogger.com/feeds/1265273302531055728/posts/default。记得将blogID换成你自己的。**_——其实我自己试下来，无法读取旧日志，提示：远程主机强迫关闭了一个现有的连接，而且开始连接老是断掉，ScribeFire却不会断，亦可以读取，具体原因不明。_

>   **_延伸阅读：什么是[HTTPS](http://zh.wikipedia.org/wiki/HTTPS)_**

> **HTTPS**以保密为目标研发，简单讲是[HTTP](http://zh.wikipedia.org/wiki/HTTP "HTTP")的安全版。其安全基础是SSL协议，因此加密的详细内容请看[SSL](http://zh.wikipedia.org/wiki/SSL "SSL")。全称**Hypertext Transfer Protocol over Secure Socket Layer**。  
> 它是一个[URI](http://zh.wikipedia.org/wiki/URI "URI") scheme，句法类同<tt>http:</tt>体系。它使用了HTTP，但HTTPS存在不同于HTTP的默认[端口](http://zh.wikipedia.org/wiki/%E7%AB%AF%E5%8F%A3 "端口")及一个加密/身份验证层（在[HTTP](http://zh.wikipedia.org/wiki/HTTP "HTTP")与[TCP](http://zh.wikipedia.org/wiki/TCP "TCP")之间）。这个协议的最初研发由[网景公司](http://zh.wikipedia.org/wiki/%E7%BD%91%E6%99%AF%E5%85%AC%E5%8F%B8 "网景公司")进行，提供了[身份验证][3]与[加密][4]通讯方法，现在它被广泛用于[互联网][5]上安全敏感的通讯，例如交易支付方面。

 [1]: http://www.whopig.com/
 [2]: http://chenjun.com/
 [3]: http://zh.wikipedia.org/wiki/%E8%BA%AB%E4%BB%BD%E9%AA%8C%E8%AF%81 "身份验证"
 [4]: http://zh.wikipedia.org/wiki/%E5%8A%A0%E5%AF%86 "加密"
 [5]: http://zh.wikipedia.org/wiki/%E4%BA%92%E8%81%94%E7%BD%91 "互联网"