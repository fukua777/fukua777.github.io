---
title: About　Socket.io
tags: "<h1>Websocket</h1>"
date: 2016-09-25
categories: 甫夸之谈———websocket
---

> 关于


　Socket.io是WebSocket的一个库，包括了客户端的js和服务端的nodejs,它的目标是构建可以在不同浏览器和移动设备上使用的实时应用。Socket.io支持跨平台，在不同的平台下，使用方法大同小异。下面主要阐释在node.js中的简单使用。
> 服务端

* 安装nodejs之后，npm安装socket.io模块
	`npm install socket.io`
* 搭建socket服务器。为了便捷，在这里使用了nodejs中常用的express框架来实现web服务。同时使用了connection事件来测试。
<!---more--->


	var express = require('express');
	var app = express();
	app.get('/',function(req,res){
		res.status(200).send('前后端连接成功');
		res.sendFile('index.html',{root.__dirname});
	});
	var server = require('http').createServer(app);
	var io = require('socket.io')(server);
	io.on('connection',function(socket){
		socket.send('后端发到前端的消息');
		socket.on('message',function(data){
			console.log(data);
		});
	});
	server.listen(3000,function(){
		console.log('服务器启动成功');
	});
> 前端

* 在index文件中引入客户端js文件
	`<script src='https://cdn.socket.io/socket.io-1.2.1.js'></script>`
* 在index文件中添加与后端交互的信息


	var socket = io.connect('/');
	socket.on('connect',function(){
		socket.send('前端发到后端的消息');
	});
	socket.on('message',function(data){
		alert(data);
	});






	
	

    