---
title: About　ng-if、ng-show
categories: 甫夸之谈———Angular
tags: "ng-if、ng-show"
---

>关于ng-if、ng-show

　　Angular中ng-if、ng-show都可以用来控制dom元素进行显示和隐藏，所给表达式为真时即为显示元素，反之则隐藏。
	
>主要

　　Angular中ng-if的本质是添加或删除节点，而ng-show是通过css对元素进行显示或隐藏。通过用ng-if添加的节点会处于一种最原始的状态，包括相关作用域也是新的。