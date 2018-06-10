---
title: About　RxJS
categories: 甫夸之谈———JS
tags: "RxJS"
date: 2018-03-13
---

> 关于

　　RxJS是一个js库，通过使用observable序列来编写异步和基于事件的程序。核心类型是Observable，附属类型有Observer、Subjects、Schedulers，还有一系列操作符。
* Observable(可观察对象)：表示一个概念，是一个可调用的未来值或事件的集合。
* Observer(观察者)：一个回调函数的集合，监听由Observable提供的值。
* Subscription(订阅)：表示Obervable的执行，用于取消Observable的订阅。
* Operators(操作符)：采用函数式编程风格的纯函数，用于处理集合。
* Subject(主体)：相当于EventEmitter，是将值或事件推送给多个Observer的唯一方式。
* Schedulers(调度器)：用来控制并发并且是中央集权的调度员，允许在发生计算时进行协调。
<!-- more -->

> Observable    是多个值的惰性推送集合。

||单个值 |多个值 |
|------|------|------|
|拉取|Function|Iterator|
|推送|Promise|Observable|

**拉取**：有消费者来决定何时从生产者那接受数据，生产者不知道何时交付。
**推送**：有生产者决定何时把数据发送给消费者，消费者不知道何时回接收数据。

　　Observables是使用Rx.Observable.create或通过操作符来**创建**的，并使用观察者**订阅**，然后**执行**并发送next / error / complate通知观察者，执行可能被**清理**。
> Subject
  
　　Subject是一种特殊类型的Observable，允许将值播给多个观察者，普通的Observables是单播的，类型有Subject（普通类型）、BehaviorSubject（记录当前值）、ReplaySubject（记录旧值）、AsyncSubject（只有当Observable执行完成时，才会将执行的最后一个值发送给观察者）。
