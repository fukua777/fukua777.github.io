---
title: About　Http options method
date: 2018-08-30
tags: "<span style='color: #000; font-size: 20px;'>options</span>"
categories: 甫夸之谈———Http
---

> 关于

　　Http中的options方法被称为预请求，是用于在通信过程中获得具有Request-uri标识资源的方法。
> 用途

1. 获取服务器支持的Http请求方法。
2. 检查服务器性能。（CORS）

> 触发条件

1. 请求方法不是Get/head/post。
2. Post方法手动设置Content-Type的值不是`application/x-www-form-urlencoded`、`multipart/form-data`、`text/plain`。
3. 设置了自定义的请求头。（不包括`Accept`、`Accept-Language`、`Content-Type`、`Viewport-width`等常用字段）