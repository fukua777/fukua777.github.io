---
title: About　$.Deferred()
categories: 甫夸之谈———JS
tags: "$.Deferred()"
---

>关于deferred对象

　　deferred对象有三种执行状态---未完成，已完成和已失败。如果执行状态是“已完成”，deferred对象会立刻调用done()方法指定的回调函数；如果执行状态是“已失败”，调用fail方法指定的回调函数；如果执行状态是“未完成”，则继续等待，或者调用progress()方法指定的回调函数。
　　对于ajax操作，deferred对象会根据返回结果自动改变执行状态，但在普通方法中必须手动指定。在前面关于$.when()的文章中，deferred对象.resolve()即将该对象的执行状态从“未完成”改为“已完成”，从而触发done()方法。类似，还有deferred.reject()方法，作用是将deferred对象的执行状态从“未完成”改为“已失败”，从而触发fail()方法。

>关于deferred.promise方法

　　在前面$.when()文章中对普通方法运用deferred对象的例子中，由于deferred对象是全局对象，所以在执行的方法外部也能改变执行状态。为了避免这种情况的发生，产生了deferred.promise()方法。它的作用是在原来deferred对象上返回另一个deferred对象，后者只开放与改变执行状态无关的方法，即done()和fail()，屏蔽了改变执行状态的方法，即resolve()和reject()。
