---
title: About　get　ip
categories: 甫夸之谈———php
date: 2017-04-17
tags: "<span style='color: cyan; font-size: 20px;'>php</span>"
---

>主要
　

　php获取ip地址有多种方法，判断空值、相辅相成比较容易得到对应的值。

```
$_SERVER['REMOTE_ADDR']		//获取最后一个代理服务器的IP，若无代理则是客户端IP

```
```
getenv('REMOTE_ADDR')		//同上

```
```
getenv('HTTP_X_FORWARDED_FOR')		//不同类型的代理显示的可能不同，真实IP或空

```
```
getenv('HTTP_CLIENT_IP')		//获取客户端IP

```
```
gethostbyname(fukua777.cn)		//获取服务器端IP

```

>另

　通过file_get_contents(xxx.xxx.xx)，通过调用不同的接口地址（BAT等），能获取相应的经纬、城市、运营商等信息
