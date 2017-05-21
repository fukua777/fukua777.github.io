---
title: About　mode&flage of fs
categories: 甫夸之谈———node
tags: "<span style='color: orange;'>fs</span>"
---

>mode of fs

　　mode在fs操作中表示具有的权限。文件的基本权限有9个，分别是owner、group、others三种身份各有自己的read、write、execute权限。用不同的数字代表不同的权限。
+	r: 4
+	w: 2
+	x: 1

>flage of fs

　　flage在fs操作中用来设置文件的读写属性。
<!---more--->
　　<b style="color:black;font-size:25px;">r</b>　读取文件。如果文件不存在时抛出异常
　　<b style="color:black;font-size:25px;">r+</b>　读取并写入。如果文件不存在时抛出异常
　　<b style="color:black;font-size:25px;">rs</b>　以同步方式读取文件并通知操作系统忽略本地文件系统缓存。如果文件不存在时抛出异常
　　<b style="color:black;font-size:25px;">w</b>　写入文件。如果文件不存在时则创建该文件。如果文件已存在则清空文件内容
　　<b style="color:black;font-size:25px;">w+</b>　读取并写入文件。如果文件不存在时则创建该文件。如果文件已存在则清空文件内容
　　<b style="color:black;font-size:25px;">wx</b>　作用与”w”类似。但是以排他方式打开文件
　　<b style="color:black;font-size:25px;">wx+</b>　作用与”w+”类似。但是以排他方式打开文件
　　<b style="color:black;font-size:25px;">a</b>　以追加方式写入文件。如果文件不存在时则创建该文件
　　<b style="color:black;font-size:25px;">a+</b>　读取并以追加方式写入文件。如果文件不存在时则创建该文件
　　<b style="color:black;font-size:25px;">ax</b>　作用与”a”类似。但是以排他方式打开文件
　　<b style="color:black;font-size:25px;">ax+</b>　作用与”a+”类似。但是以排他方式打开文件	