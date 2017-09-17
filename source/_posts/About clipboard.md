---
title: About　Clipboard
categories: 甫夸之谈———JS
date: 2017-05-13
tags: clipboard
---

>	主要

　　JS中实现特定内容的复制，基本依赖于execCommand()、ClipboardEvent()两者的结合。

*	execCommand()，对选中、聚焦区域的进行操作，多用于文本编辑。通过运用`copy`命令可以实现复制到系统粘贴板，限于必须能选中、聚焦。
	```
	document.execCommand('Copy');
	```

*	ClipboardEvent()，监听系统中`copy`、`cut`、`paste`等操作。
<!-- more -->
	```
	document.body.addEventListener('copy',function(e){
		console.log(e);
		e.clipboardData.setData('text/plain','自定义内容');
		e.preventDefault();		//没有阻止，则内容为选中内容
	});
	```
	```
	e.clipboardData.getData('text/plain');
	e.clipboardData.clearData('text/plain');
	```
*	在非IE中clipboardData存在于事件中，而IE中则直接在window中即可得到。