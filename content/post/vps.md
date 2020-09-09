---
title: 'VPS笔记'
date: Thu, 16 Oct 2014 18:31:50 +0000
draft: false
tags: ['Linux Settings', 'VPS']
---

LNMP
----

当我还徘徊在 `yum install` 和 `make` 之间的时候，[一键安装](http://lnmp.org/) 已在大家的终端里风驰电掣。

SSL证书
-----

当你选择了HTTPS，你需要一个免费的StartSSL证书来避免浏览器警告对小白们的困扰。[这里](http://blog.weiliang.org/linux/632.html) 有详细教程。

Node.js
-------

为了搞个在线电子表格，我需要EtherCalc； 为了安装EtherCalc，我需要Node.js； 为了管理Node.js应用，我需要forever； 为了forever能更接近它的名字，我需要一个init.d的脚本。 简单直接的如同霍金说过的那样:

> In order to get married, I had to get a job. And in order to get a job, I needed to finish my thesis.

vsftpd
------

许多Google来的教程里都少了点目录访问控制： (1)`vsftpd.conf`:```
chroot_list_enable=YES
chroot_list_file=/path/to/chroot_list 
```(2)`chroot_list`: 添加受限用户 绑定ftp目录和下载目录也是很有用的： `/etc/fstab`:```
/path/to/download /path/to/ftp none bind 0 0 
```至于启动的话就交给`chkconfig`了。

Transmission 和 Mldonkey
-----------------------

看上去都很简单的样子，唯一的困扰是Transmission用了init.d[脚本](http://www.live-in.org/wp-content/uploads/2011/07/transmission.txt)，而Mldonkey用了`rc.local`:
```
/path/to/mlent > /dev/null 2>&1 & 
```

vnstat
------

明知道流量够用却还是忍不住要看看的朋友们请从源码安装 `vnstat`，不然小心在“not enough data available yet”中等待一生。

代理
--

`ssh` 做 `socks`代理苦的是Windows。`3proxy`支持HTTP和socks看上去很美，只是加密还是交给VPN吧。

openVPN
-------

选好一个与时俱进的[教程](http://nmshuishui.blog.51cto.com/1850554/1544212)是成功的关键。

wordpress
---------

一个好的[官网教程](http://codex.wordpress.org/Installing_WordPress)需要一个好的排版才让人有跟从的欲望。至于插件么，`Crayon`、`Jetpack`的`Markdown`和`UpdraftPlus`。偶尔改改模板的`css`和`php`也是个不错的体验。
