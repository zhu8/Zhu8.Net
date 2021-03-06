---
categories:
- 言吾 | Talk
date: "2006-11-05T21:10:10+08:00"
tags:
- 404
- Hack
- UTF-8
- 乱码
- 微软
title: 二三事
url: /blog/2006/11/small-cases.html
toc: true
---
瞎忙乎了老半天，觉得还是记下来好，要不老是犯迷糊。

### 壹、解决了Live Search的编码问题

微软的Live Search其实很不错的，原来的MSN虽然默默无闻，但是索引起来也蛮勤快的，今天忽然想到在[首页][1]里面加上自定义的**404/500页面**，所以就用了**.htaccess**加了几句就OK，代码为：
<!--more-->

```html
ErrorDocument 404 /error.html  
ErrorDocument 500 /error.html  
RewriteEngine on  
RewriteCond %{HTTP_REFERER} !^$  
RewriteCond %{HTTP_REFERER} !^http://(www.)?zhu8.net/.*$ [NC]  
RewriteRule .(js¦mp3¦wma)$&[F]
```


我是把404和500放在一个页面的，省得麻烦，所以就想弄一个单纯的搜索页面，一直发现Live!对我的站索引还蛮全的，所以除了加上Google之外，还想加上Live Search的（[见此][2]），但是在编码上遇到了问题：

> 在下面的代码中，必须用您网站所用语言所对应的三位或四位数代码页编号来替换"您的网页所用代码页"。  
> 例如，如果您的网站是用源于拉丁文的语言（英语、法语或德语）编写的，则用 1252 编号来取代此指令：value="1252"  
> 有关各语言所对应的代码页值，请参阅 [Windows 支持的代码页][3]网页。

很显然，里面有GBK码（代码：936），但是没有UTF-8码（应该不是我没有找到），只好到网上去找，不经意发现了**UTF-8的代码：65001**，于是将代码一修改，就成了。详细可以到[这个页面][4]去看下源代码就好了。

### 贰、解决了WinXP下chm电子书无法显示页面的问题

本来想把原来的*偏航*里无声听雨的小波文集弄起来的，因为我这一直存着opig做的chm电子书档，结果在网吧翻出来弄，书的导航栏倒是没有问题，页面却老是*无法显示网页*，弄的我郁闷，网上去搜，先是到了微软的[官方说明页面][5]，以为要折腾注册表，在网吧要弄注册表是很烦的事情，再去搜搜，在这发现了最简单的方法：Loveyuki一语惊醒梦中人，原来[如此简单][6]（内有截图），还去按微软那样复杂何必呢？

### 叁、以前的旧Blog[重新贴出][7]

由于空间是PHP的，所以也没打算重新弄个Z-Blog重出江湖，把文档重新归了一下档，做成了HTML的静态页面，但是音乐文件就没去修改，因为很多都失效了。倒是网吧没有装Ofice，而我又需要打开ACCESS的数据库，先是下了微软的Excel Viewer，后来发现只能看，不能修改，而我恰恰需要把Mdb文件解下来提取日志的相关内容，后来终于找到了：[Microsoft Office 2003 Sp2〖精简免安装绿色版〗][8]。把该数据库导出成XLS，打开，选了文章、评论等等复制出来，一切OK。

### 肆、修改了原颜色代码

把原来的中英文颜色代码弄掉了，换了个国外的，胡乱翻译了一下，[放出来][9]了。页面自我感觉还蛮好看的，就是都是TABLE，想改成DIV+CSS可是东西太多，没什么必要。

 [1]: http://chenjun.com/
 [2]: http://help.live.com/help.aspx?project=wl_webmasters&#038;mkt=zh-cn "Live Search 站点所有者帮助"
 [3]: http://g.msn.com/0HEWL_WEBMASTERSZHCN9/91008 "Code Pages Supported by Windows"
 [4]: http://chenjun.com/404.html "404/500 错误页面"
 [5]: http://support.microsoft.com/kb/892675 "安装安全更新 896358 或 890175 后，某些网站和 HTML 帮助功能可能无法运作"
 [6]: http://www.i170.com/article/5298#comment "一起来&如何解决chm格式文件无法显示问题"
 [7]: http://chenjun.com/old/ "短长书"
 [8]: http://www.greendown.cn/soft/156.html "Microsoft Office 2003 Sp2 精简免安装绿色版"
 [9]: http://chenjun.com/other/color.html "Html color codes"