---
categories:
- 石马 | Code
date: "2006-08-13T12:30:25+08:00"
tags:
- Usebb
- 汉化
- 论坛
title: UseBB汉化暨论坛搭建完成
url: /blog/2006/08/usebb-chinese-simplified.html
---
好啦，昨晚折腾了一个晚上，总算完成了。***〔Update:2007/03/08：把链接修改到我的永硕硬盘上去。〕***<span class="right">![ScreenShot of UseBB Chinese](/images/posts/usebb-chinese.jpg "ScreenShot of UseBB Chinese")</span>最近想搭建一个论坛玩玩，结果，找到的个个功能惊人，体积同样**惊人**。用UseBB的介绍文件来说就是<acronym title="Unnecessary features">**bloat**</acronym>。后来找到了[UseBB](http://www.usebb.net/)，汉化了一下，本来不想汉化后台的，就和WP一样，后来发现到现在为止还没有人弄简体中文的汉化包，后来发现了和WP一样存在中文字符截断的问题，今天就[修改](http://groups.google.com/group/Zhu8/browse_thread/thread/7cf0947ec61ac13a/4cf29f9e175b04fe "UseBB中文字符截断函数（UTF-8）修改")了一下源代码，唉，发现玩程序真的有时候挺头大的，特别是这些英文软件压根就不可能考虑到咱中文的编码问题。可是要想程序如自己的意，只好自己动手，丰衣足食<sub>By Chairman Mao</sub>了。

废话少说，简单介绍一下UseBB吧！
<!--more-->

*   UseBB使用*PHP+Mysql*编写，支持mod_rewrite*（可惜我的空间并不支持）*整个程序简洁小巧。
*   **独立**的模版和语言包，可定制程度高。
*   支持<acronym title="Bulletin Board Code, replacing HTML">BBCode</acronym>和表情图标，同样可定制。
*   每个用户可以设置自己的个人资料、头像（只支持外部链接）、浏览论坛的模式以及语言。
*   支持帖子置顶、移动、删除、编辑（仅管理员和版主，用户可以在一定时间间隔内修改自己的帖子），支持完整HTML的帖子（仅管理员）。
*   支持群发邮件、关键字过滤，用户名、邮件地址、IP过滤、搜索、在线用户、论坛详细状态。
*   支持可开发的<acronym title="Admin Control Panel">ACP</acronym>插件
*   支持**RSS** 2.0订阅
*   **搜索引擎友好 .html 格式的URL**（需mod_rewrite支持）

当前不具备的功能也有一些，简单列举一下，包括：附件上传、投票、站内信件、子论坛、用户组等等。不过UseBB团队已经在开发[UseBB2](http://usebb.sourceforge.net/UseBB2/ "UseBB2")了，相信不久会有全新的出来的。

好了，如果你感兴趣，可以到 [这里](http://zhu8.ys168.com/ "我的永硕硬盘") 下载。