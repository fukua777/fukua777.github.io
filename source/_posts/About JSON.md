---
title: About　JSON
date: 2017-12-21
tags: "<h1>JSON</h1>"
categories: 甫夸之谈———JS
---

> 关于

　　JSON是一种数据格式，以`key: value`的形式来展现，常用处理方法有JSON.stringify、JSON.parse。

> 主要

- ``JSON.stringify(value[,replacer[,space]])``
     `value`
 　　值为基本数据类型或空对象时，返回值为原值或null，标准对象时为JSON数据。

 <!--- more --->
     `replacer`
　　1. 值为数组时，用来筛选返回值，只返回数组中有的项。
　　2. 值为函数时，用来对传入的对象进行遍历处理。
`space`
　　1.省略，显示为空；
　　2.数字代表缩进字符的数量，最大为10；
　　3.可以是转义字符；
　　4.字符串，则在每行输出前附加该字符，最大长度为10。
- ``JSON.parse(value[,reviver])``
    `value`
　　值为JSON数据，格式较为严格，标准格式
    `reviver`
　　函数，对传入的值进行遍历处理

　　　　