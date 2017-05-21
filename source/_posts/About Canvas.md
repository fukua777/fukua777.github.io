---
title: About　Canvas
categories: 甫夸之谈———canvas
date: 2016-08-09
tags: Canvas
---

>关于canvas

　canvas是H5出现的新标签，自带某些属性、方法、事件，也可以通过运用js来进行绘图。

>基础

+   运用canvas绘图的主要流程
	1. 在js文件中找到canvas标签
	2. 用一个变量获取context对象，这个对象封装了很多绘图功能（因为某些原因目前不提供3d服务。。。）
	3. 运用属性和方法进行实际绘图


	var canvas = document.getElementById('canvas');
	var context = canvas.getContext('2d');

<!---more--->	

+	基本知识
	1. canvas有两种方法
		1. context.fill()  		填充
		2. context.stroke()  	绘制边框
	2. 绘制图形的样式可以通过两种方式来进行设置
		1. context.fillStyle  	填充的样式
		2. context.strokeStyle  边框的样式
	3. canvas中坐标原点为浏览器坐上角，x、y坐标分别随着向右、向下而增大，颜色样式可以使用'#xxx'、'red'、'rgb()'、'rgba()'，默认颜色均为黑色。


>主要
	
+	绘制线条
	* moveTo(x,y) 定义线条的开始坐标
	* lineTo(x,y) 定义线条的结束坐标


	context.moveTo(0,0);
	context.lineTo(200,100);
	context.stroke();
*****
+	绘制矩形
	* rect(x,y,width,height) 定义矩形的x、y坐标和宽度、高度
	* 如果同时绘制多个图形，要在绘制之前调用beginPath()方法


	context.rect(20,20,150,100);
	context.stroke();
*****
+	绘制圆形
	* arc(x,y,r,start,stop,flage) 定义圆形的原点坐标x、y，半径r，起始角度start，终点角度stop，flage值true、false分别表示角度顺时针旋转和逆时针旋转，默认值为false


	context.beginPath();
	context.arc(100,75,50,0,2*Math.PI);
	context.stroke();
*****
+	有关文本
	* font 定义字体
	* fillText(text,x,y) 绘制实心文本
	* strokeText(text,x,y) 绘制空心文本


	context.font="30px Arial";
	context.strokeText("Hello World",10,50);
*****
+	有关渐变
	* 线条渐变
		1. context.createLinearGradient(x0,y0,x1,y1) 渐变开始的坐标x0、y0；渐变结束的坐标x1、y1
		2. addColorStop(0,'color')、addColorStop(1,'color') 渐变起点、终点的颜色
	* 径向渐变
		1. context.createRadialGradient(x0,y0,r0,x1,y1,r1); 渐变开始圆的坐标x0、y0，半径r0；渐变结束圆的坐标x1、y1，半径r1
		2. addColorStop(0,'color')、addColorStop(1,'color') 渐变起点、终点的颜色


	var change=context.createLinearGradient(0,0,200,0);
	change.addColorStop(0,"red");
	change.addColorStop(1,"white");

	var change=context.createRadialGradient(75,50,5,90,60,100);
	change.addColorStop(0,"red");
	change.addColorStop(1,"white");
*****	
+	有关图像
	* 将图像放置到画布上 drawImage()
		* 必选属性img、x、y————img规定用的图像，图像放置位置的坐标x、y
		* 可选属性sx/sy————开始剪切的坐标x、y
		* 可选属性swidth/wheight————被剪切图像的宽度、高度
		* 可选属性width/height————要使用的图像的宽度、高度
		* 属性位置默认方式按上述顺序排列

	
	context.drawImage(img,90,130,50,60,10,10,50,60);
	




	