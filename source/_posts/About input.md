---
title: About　input
categories: 甫夸之谈———input
date: 2017-04-29
tags: "html"
---

>  主要

　　input有多种类型，对应不同属性，具有不同功能。大多数类型value表示发送请求的值，具有disabled属性，禁用；required属性，必填；readonly，只读；操作事件为change、input；select()、focus多数可以选中；autocomplete属性，是否有自动完成功能，简单的值为on、off，有多种其它值；autofocus属性，是否自动聚焦；list属性，与datalist标签组合使用，实现列表选项；max、min、maxlegth、minlength属性，对不同类型适用不同，效果一致；name属性，请求的变量名；pattern属性，正则筛选；placeholder属性，默认提示；step属性，调整步长。

*	<b style="color:black;font-size:25px;">button</b>　　可绑定事件，value为显示名称
*	<b style="color:black;font-size:25px;">checkbox</b>　　checked属性为选中
<!---more--->
*	<b style="color:black;font-size:25px;">color</b>　　
*	<b style="color:black;font-size:25px;">date</b>
*	<b style="color:black;font-size:25px;">datetime-local</b>
*	<b style="color:black;font-size:25px;">email</b>
	multiple属性，是否允许多个值
*	<b style="color:black;font-size:25px;">file</b>　　
	accept属性，筛选特定类型文件，值可为(.jpg/.png.doc..)、MIME类型、audio/*、video/*、image/*
	captur属性，调用相机、摄像、录音等功能，值可为camera、camcorder、microphone
*	<b style="color:black;font-size:25px;">hidden</b>
*	<b style="color:black;font-size:25px;">image</b>
	src属性，资源路径
*	<b style="color:black;font-size:25px;">month</b>
*	<b style="color:black;font-size:25px;">number</b>
*	<b style="color:black;font-size:25px;">password</b>
*	<b style="color:black;font-size:25px;">radio</b>
*	<b style="color:black;font-size:25px;">range</b>
*	<b style="color:black;font-size:25px;">reset</b>
*	<b style="color:black;font-size:25px;">search</b>
*	<b style="color:black;font-size:25px;">submit</b>
	formenctype属性，对发送数据进行编码，值可为application/x-www-form-urlencoded，对所有字符进行编码（默认，空格转为'+'，特殊字符转为HEX）；multipart/form-data，不进行编码；text/plain，将空格转换为'+'，不对特殊字符编码（get方式）
	multiple属性，是否允许多个值
*	<b style="color:black;font-size:25px;">tel</b>
*	<b style="color:black;font-size:25px;">text</b>
*	<b style="color:black;font-size:25px;">time</b>
*	<b style="color:black;font-size:25px;">url</b>
*	<b style="color:black;font-size:25px;">week</b>