---
categories:
- 石马 | Code
date: "2006-11-19T04:17:00+08:00"
tags:
- Hack
- UTW
- 汉化
- 链接
title: 解决WP汉化和UTW链接问题
url: /blog/2006/11/wordpress-language-pack-and-utw-permalink-structure-fix.html
---
其实严格说来是因为我在[我要安家][1]的服务器的关系，所以导致无法使用中文语言包。看下我要安家的配置：

> 操作系统 Linux Fedora core 1.0(2.4内核)或Linux Fedora core 2.0(2.6内核);  
> web服务器 Apache 1.3.31  
> PHP版本 PHP 4.3.11  
> Mysql版本 Mysql 4.0.20  
> Zend支持 支持
<!--more-->

原来都是**PHP版本**搞的鬼，Wordpress默认的是PHP 5的，但是我现在的服务器是4.3.11，因为在****wp-includes/gettext.php****中**第105行**有这样一段代码：

```php
// $MAGIC1 = (int)0x950412de; //bug in PHP 5.0.2, see https://savannah.nongnu.org/bugs/?func=detailitem&item_id=10565  
$MAGIC1 = (int)&1794895138;  
// $MAGIC2 = (int)0xde120495; //bug  
$MAGIC2 = (int)&569244523;
```

其中注释掉的目的是为了修复PHP 5的错误的，因为我的服务器不是PHP 5，所以不需要**注释**掉。相反需要注释掉正在使用的，所以将上面那段代码替换成：

```php
 $MAGIC1 = (int)0x950412de; //bug in PHP 5.0.2, see https://savannah.nongnu.org/bugs/?func=detailitem&item_id=10565  
 // $MAGIC1 = (int)&1794895138;  
 $MAGIC2 = (int)0xde120495; //bug  
 // $MAGIC2 = (int)&569244523;
```

上面的解决方案是在[WordPress Support][2]找到的。好了，照上面做完一切OK了，现在可以正常使用中文包（zh\_CN.mo以及zh\_CN.po）了。这里放下本人正在使用的中文包：[下载][3]，使用方法如下：

> 下载编译好的zh\_CN.mo文件(当然你也可以下载zh\_CN.po文件然后自行编译)  
> 在Blog的wp-includes目录下建立languages文件夹  
> 将zh\_CN.mo文件上传到wp-includes/languages文件夹  
> 修改Blog根目录下的wp-config.php文件，将  
> define (&#8216;WPLANG&#8217;, &#8220;);  
> 修改为  
> define (&#8216;WPLANG&#8217;, &#8216;zh\_CN&#8217;);  
> 注意：zh和CN之间是下划线，引号和括号都是英文半角字符。

*Updated On 2006/11/20：*

昨天把WP升级到了2.0.5，结果问题出来了，在先将所有的插件停用再启用的时候，其他的都可以，就是UTW（Ultimate Tag Warrior）的链接结构（Permalink Structure）不工作了，搞得我到处搜，去修改.htaccess文件，都不能解决，后来实在没辙了，把WP的链接结果先改成别的，再改回来，就OK了，虽然昨天我也试过，但是是在UTW还没有重新激活的情况下，将WP的链接结构重新升级了一遍之后才激活的UTW，所以没有起到作用。我的天啊，原来是这么简单的事情，偏偏我又是不见棺材不掉泪的类型，折腾到最后还是没弄好才回去睡觉的，记下来，以防自己（以及遇到此类问题的朋友）以后再干这种蠢事。Sigh……

 [1]: http://www.512j.com/ "我要安家"
 [2]: http://wordpress.org/support/topic/66818 "Language set up problem (portuguese) « WordPress Support"
 [3]: /uploads/zh_CN.rar "中文汉化包：zh_CN.mo和zh_CN.po"