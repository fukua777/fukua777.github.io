---
title: About　js
tags: "<h1>js</h1>"
categories: 甫夸之谈———JS
---

> 关于

　　参考相关文档，基于平常积累，总结原生js的一些点。
<!---more--->

　　<a href="#load">加载</a>　　<a href="#href&src">href、src</a>　　<a href="#closure">闭包</a>　　<a href="#es6">ES6</a>

> 主要

* <h1 id="load">加载</h1>
    1. js加载过程中会造成阻塞，即其它内容暂时停止，加载完成之后会有一定的解析时间。
    2. js按块顺序加载，即按`<script>`标签区分，但内容共享。
    3. js加载完解析时有两个阶段，预编译与执行。预编译时会对变量和函数进行提前定义，但不会赋值，赋值按顺序执行。
    ```
    <!-- js文件书写顺序 -->
    test();
    var test = function(){
        alert('first');
    }
    function test(){
        alert('second');
    }
    test();
    ```
    ```
    <!-- 实际执行顺序 -->
    var test;
    function test(){
        alert('second');
    }
    test();
    test = function(){
        alert('first');
    }
    test();
    ```
* <h1 id="href&src">href、src</h1>
    1. href用于建立链接关系，解析页面遇到时不会加载该内容，页面不会暂停加载。
    2. src用于引入内容，解析页面遇到要等待加载指向地址的内容，会暂停。
* <h1 id="closure">闭包</h1>
    * 条件
        1. 内部函数使用了外部函数的变量
        2. 外部函数已经退出
        3. 内部函数可以访问
    * 概念
        1. 允许函数访问局部作用域之外的数据；
    * 实现
        1. 返回函数，创建新的作用域，使函数中调用的变量不被回收；
        2. 传递参数，形成私有变量
* <h1 id="es6">ES6</h1>
    * 部分特性
        1. let　const
        2. default parameters　rest parameters
        3. template string　Multi-line string　　　　（``表示起始，${var}引用变量）
        4. destructuring
        5. arrow function　　　　（内部没有定义this，通过继承而来）
        6. Promise
        7. Class　　　　（class，extends，constructor，super）
        8. module　　　　（export import）