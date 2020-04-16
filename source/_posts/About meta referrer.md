---
title: About　Meta referrer
date: 2018-08-30
tags: "<span style='color: #000; font-size: 20px;'>referrer</span>"
categories: 甫夸之谈———Http
---

> 关于

　　从一个文档发出的请求以及导航到其它页面，都会带有一个referrer头，即网页的来源。而referrer策略则允许手动控制相关信息。

> 用法

1. 设置请求头中的`Referrer-Policy`字段。
2. `meta`标签设置。
3. `a`标签、`link`标签设置`rel`属性

> 值

1. 空字符串。没有referrer策略，默认为`no-referrer-when-downgrade`
2. `no-referrer`。所有请求都不带。
3. `no-referrer-when-downgrade`。在https的页面中，对https的请求资源发送完整的referrer，http的资源则不带。
4. `same-origin`。同源带，否则不带。
5. `origin`。对任何资源只发送源的信息，不发送完整的url。
6. `strict-origin`。`origin`和`no-referrer-when-downgrade`的交集。
7. `origin-when-cross-origin`。同源发送完整的url，跨域的发送源信息。
8. `strict-origin-when-cross-origin`。`strict-origin`和`origin-when-cross-origin`的交集。
9. `unsafe-url`。https页面对http资源也发送完整的referrer。