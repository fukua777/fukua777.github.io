---
title: About　$.when()
categories: 甫夸之谈———JS
date: 2016-10-11
tags: "<div style='transform: rotate(10deg) scale(3); color: pink;'>$.when()</div>"
---

>关于deferred对象

　　简单来说，deferred对象就是jQuery的回调函数解决方案。本意是”延迟“，即程序延迟到某个点再向下执行。

>主要

+	类比于传统ajax操作，运用deferred对象后的链式写法使得代码的可读性更强。


	$.ajax(
		url: "fukua.html",
		success: function(){
			alert("messi is best!");
		},
		error: function(){
			alert("messi is no better than!");
		}
	)
+	如上，$.ajax()接受一个对象参数，成功、失败分别对应success、error方法。若用deferred延迟对象则可用done、fail方法解决。


	$.ajax("fukua.html")
	.done(function(){alert("messi is best!");})
	.fail(function(){alert("messi is no better than!");})

<!--- more --->	
+	deferred对象的优点更在于她可以给多个事件绑定多个回调函数。


	$.ajax("fukua.html")
	.done(function(){alert("messi is best!");})
	.fail(function(){alert("messi is no better than!");})
	.done(function(){alert("messi is very good!");})
	
+	如上，要为多个事件绑定回调需要用到$.when()。


	$.when($.ajax("fukua.html"),$.ajax("messi.html"))
	.done(function(){alert("messi is best!");})
	.fail(function(){alert("messi is no better than!");})	
	
*****

+	deferred对象的最大优点在于，她把整个一套回调函数接口从ajax操作扩展到了所有操作，即不仅是ajax还是本地操作，不管异步还是同步，都可以使用deferred对象的方法。


	$.when(anyFunc())
	.done(function(){alert("messi is best!");})
	.fail(function(){alert("messi is no better than!");})	

+	如上，当参数是普通函数时done()方法会立即执行，原因在于$.when()的参数只能是deferred对象。


	var testParam = $.Deferred();	//新建一个deferred对象
	var anyFunc = function(testParam){
		var testFunc = function(){
			alert("It is OK!");
			testParam.resolve();	//改变deferred对象的执行状态
		}	
		return testParam;	
	}	
	//现在anyFunc返回的是deferred对象了，即可运用链式操作
	$.when(anyFunc(testParam))
	.done(function(){alert("messi is best!");})
	.fail(function(){alert("messi is no better than!");})
	


























