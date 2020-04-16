---
title: About　JS模块
date: 2018-09-09
tags: "JS模块"
categories: 甫夸之谈———JS
---

> 关于

　　随着前端业务复杂度的增加，模块化开发成为共识。ES6语法`import`、`export`也逐渐被广泛应用，在此之前常用的模块化解决方案有`commonjs`、`AMD`、`CMD`。

> commonjs

　　commonjs的目标是指定一个js模块化的标准，指定出可以同时在客户端和服务端运行的模块。这些模块有自己独立的作用域，可以向顶层曝露自己（`module.exports`），也可以引用其它模块（`require`）。nodejs和webpack都是采用了这样的规范。
<!-- more -->
> AMD

　　AMD，异步模块定义规范，弥补了commonjs规范模中块依赖只能同步加载的缺陷，对浏览器异步加载模块提供了解决方案。`requirejs`是典型的实践者。
```
    define(String: name?, Array: dependencies?, factory);
```

> CMD

　　CMD，通用模块定义规范，偏向于commonjs规范，以一个文件为一个模块，支持同步加载和异步加载模块。
```
    define(function(require, exports, module){
        require();
        require.async();
        module.exports = {};
    });
```

> AMD和CMD区别

* AMD异步加载模块，CMD同步、异步均可。
* AMD推崇依赖前置，需要将依赖前置在依赖数组中；CMD推崇依赖就近，在使用模块前将模块`require`进来。