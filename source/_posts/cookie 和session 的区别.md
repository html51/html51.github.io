title: cookie 和session 的区别
date: 2016-03-16 22:20:45
categories:
- JavaScript
tags: [cookie,和session]

-------

cookie 和session 的区别：

-cookie数据存放在客户的浏览器上，session数据放在服务器上。
-cookie不是很安全，别人可以分析存放在本地的COOKIE并进行COOKIE欺骗，考虑到安全应当使用session。
-session会在一定时间内保存在服务器上。当访问增多，会比较占用你服务器的性能，考虑到减轻服务器性能方面，应当使用COOKIE。
-单个cookie保存的数据不能超过4K，很多浏览器都限制一个站点最多保存20个cookie。
-所以个人建议：(1)将登陆信息等重要信息存放为SESSION；(2)其他信息如果需要保留，可以放在COOKIE中