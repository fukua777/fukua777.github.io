---
title: About　Webpack
tags: "<h1>webpack</h1>"
categories: 甫夸之谈———JS
date: 2018-05-03
---

> 关于

　　参考相关文档，基于平常积累，总结webpack的一些基础。
<!---more--->

> 主要

* <h1 id="entry">入口</h1>
```
    entry: anyPath
    entry: {
        anyName: anyPath
    }
    entry: {
        anyNameOne: anyPathOne,
        anyNameTwo: anyPathTwo
    }
```
  1. 入口告诉webpack应该使用哪个模块来作为构建内部依赖图的开始，可指定单个、多个入口。
  2. 多入口配置可以用来实现分离应用和第三方库、多页面应用。多入口告诉webpack建立多个依赖图，依赖不同，加载资源不同。
* <h1 id="output">输出</h1>
```
    output: {
        filename: anyName,
        path: anyPath
    }
    output: {
        filename: [name].ext,
        path: anyPath/[hash]
    }
```
  1. 输出告诉webpack在哪里导出编译后的文件及文件相关信息，多个入口文件时可以用占位符指定名称、可以用【hash】、【chunkhash】等特殊标识来实现更新。
* <h1 id="loader">loader</h1>
```
    module: {
        rules: [
            {
                test: anyReg,
                use: anyLoader
            }
        ]
    }
```
  1. loader用来将不同类型的文件转化为webpack可以处理的模块，即实现加载模块的预处理。
* <h1 id="plugins">插件</h1>
```
    plugins: [
        new anyPlugin(options)
    ]
```
  1. plugins告诉webpack执行一系列模块处理。
* <h1 id="mainfest">mainfest</h1>
    1. webpack打包后的应用会产生三种类型代码，包括主动添加的应用业务代码、引用的第三方库代码、webpack的runtime和mainfest代码。
    2. runtime和mainfest用来处理应用中的模块交互，包括模块的懒加载，相互之间的连接等等。
    3. 当编译器执行、解析和映射应用程序时，会保留所有模块的要点，成为mainfest。当打包完在浏览器中运行时，会通过mainfest来加载和解析模块，通过使用mainfest的数据，runtime能够查询模块标识符，检索出特定模块。
* <h1 id="hmr">模块热替换</h1>
    1. 模块热替换会在应用运行中替换、添加或删除模块，无需重新加载整个页面。
    2. runtime和mainfest在与应用模块交互过程中，通过检查更新、实现更新来达到热替换。

