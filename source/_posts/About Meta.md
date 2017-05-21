---
title: About　Meta
categories: 甫夸之谈———移动端
tags: "<b style='color:red;'>meta</b>"
---

>关于meta标签

  　　meta标签是HTML语言head区的一个辅助标签，它位于HTML文档头部的标记和标题之间，提供用户不可见的信息。Meta标签通常用来为搜索引擎定义页面主题，或者是定义用户浏览器上的cookie；也可以用于鉴别作者，设定页面格式，标注内容提要和关键字；还可以设置页面使其可以根据你定义的时间间隔刷新自己，以及设置RASC内容等级等等。
>简要

  　　meta标签分为两大部分：HTTP标题信息（HTTP-EQUIV）和页面描述信息（NAME）。 http-equiv类似于HTTP的头部协议，回应给浏览器一些有用的信息，更精确的显示网页内容。name的content指定实际内容，如：如果指定level为value，则Content可能是beginner、intermediate、advanced。
   
<!---more---> 

>主要

+	Content-Type和Content-Language 对字符集进行设定
	
	
	<meta http-equiv="Content-Type" Content="text/html;Charset=utf-8">
	<meta http-equiv="Content-Language" Content="zh-CN">	
*****
+	Refresh 一定时间后刷新自己或者自动链接到其它网页


	<meta http-equiv="Refresh" Content="30">
	<meta http-equiv="Refresh" Content="5;Url=http://www.fukuamess.cn">	
*****
+	Expires 指定网页在缓存中的过期时间，一旦网页过期，必须到服务器上重新调阅，时间必须为GMT格式


	<meta http-equiv="Expires" Content="0">
	<meta http-equiv="Expires"	Content="fri,20,May 1314 00:00:01 GMT">
*****
+ Pragma即cache模式，禁止浏览器从本地机的缓存中调阅页面，这样设定，访问者将无法脱机浏览


	<meta http-equiv="pragma" content="no-cache">
*****
+	Set-Cookie浏览器访问某个页面时会将它存在缓存中，下次访问时可以从缓存中读取，以提高速度。


	<meta http-equiv="Set-Cookie" Content="cookievalue=fukua;expires=fri,20,May 1314 00:00:01 GMT">	
*****
+	Window-target强制页面在当前窗口以独立页面显示，用来防止别人在框架里调用你的页面，Content值可以是：_blank、_top、_self、_parent


	<meta http-equiv="Window-target" Content="_top">
*****
+	Page-Entet、Page-Exit页面被载入和调出时的一些特效


	<meta http-equiv="Page-Enter" Content="blendTrans(Duration=0.5)">
	<meta http-equiv="Page-Exit" Content="blendTrans(Duration=0.5)">
*****
+	X-UA-Compatible以IE的哪个版本去渲染页面，IE=Edge：以所在系统最新版本IE渲染


	<meta http-equiv="X-UA-Compatible" content="IE=Edge">	
<hr style="border:none;border-top:solid 2px red;">	
+	Keywords为搜索引擎提供关键字列表，各关键词以英文逗号隔开。当有多个meta元素提供文档语言从属信息时，搜索引擎会使用lang特性来过滤并通过用户的语言优先参照来显示搜索结果


	<meta name="Keywords" Lang="EN" Content="甫夸,messi">
	<meta name="Keywords" Lang="FR" Content="甫夸,messi">	
*****
+	Description简介网站的主要内容


	<meta name="Description" Content="messi超帅">
*****
+	Robots告诉搜索机器人哪些页面需要索引，哪些不需要。Content值可选：all文件被检索，页面上的链接可以被查询、none文件不被检索，页面上的链接不能被查询、index页面被检索、noindex页面不被检索，但页面上的链接可被查询、follow页面上的链接可被查询、nofollow文件不被检索，但页面上的链接可以被查询，默认是all
	
	
	
	<meta name="Robots" Content="All">
*****
+	Author标注网页的作者或制作组，可以是名字或Email


	<meta name="Author" Content="fukua">	
*****
+	Copyright版权


	<meta name="Copyright" Content="版权所有，翻版可不究">
*****
+	Generator编辑器说明


	<meta name="Generator" Content="VSCode">
<hr style="border:none;border-top:solid 2px red;">	
+	full-screen全屏显示网页，偏向于移动端适用


	<meta name="full-screen" content="yes">
*****
+	browsermode浏览器模式，可以强制竖屏显示


	<meta name="browsermode" content="application">
*****
+	format-detection对于telephone，iphone会自动给文字添加链接样式，点击还可以自动拨号，默认开启；对于email，浏览器会识别邮箱并添加样式，点击可以调用系统默认邮件应用给该地址发邮件，默认开启；对于address，开启点击地址直接跳转至地图，默认开启



	<meta name="format-detection" content="telephone=no">
	<meta name="format-detection" content="telephone=no,email=no,address=no">
*****
+	x5-orientation对于QQ浏览器可强制竖屏，类比可知x5-fullscreen为QQ浏览器强制全屏，x5-page-mode为QQ浏览器应用模式


	<meta name="x5-orientation" content="portrait">
	<meta name="x5-page-mode" content="app">
*****
+	renderer貌似360专用


	<meta name="renderer" content="webkit"> //默认webkit内核
	<meta name="renderer" content="ie-comp"> //默认IE兼容模式
	<meta name="renderer" content="ie-stand"> //默认IE标准模式
<hr style="border:none;border-top:solid 2px red">
+	viewport即可视区域，对桌面浏览器而言，就是除去所有工具栏、状态栏、滚动条等等之后用于看网页的区域。可设置的选项有：width宽度；height高度；intial-scale初始缩放比例；minimum-scale允许用户缩放到的最小比例；maximum-scale允许用户缩放到的最大比例；user-scalable用户是否可以手动缩放。对于这些属性，我们可以设置其中的一个或者多个，并不需要同时设置，iphone会根据设置的属性自动推算其它属性值，而非直接采用默认值


	<meta name="viewport" content="width=device-width;initial-scale=1.0;maximum-scale=1.0;user-scalable=0">
*****
+	apple-touch-fullscreen添加到主屏幕后，全屏显示；apple-mobile-web-app-capable删除默认的苹果工具栏和菜单栏，默认显示；app-mobile-web-app-status-bar-style苹果手机状态栏


	<meta name="apple-touch-fullscreen" content="yes">
	<meta name="apple-mobile-web-app-capable" content="yes">
	<meta name="apple-mobile-web-app-status-bar-style" content="black">	
	

		
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	