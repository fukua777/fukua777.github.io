---
title: About　Gulp
tags: "<h1>gulp</h1>"
categories: 甫夸之谈———gulp
---

> <h1>关于</h1>

　gulp是前端开发过程中一种基于流的代码构建工具，是自动化项目的构建利器。它是基于nodejs的自动任务运行器，能够自动化地完成js、css、html/image、less等文件的测试、合并、压缩、格式化、浏览器自动刷新、部署文件生成，并可以监听文件在改动后重复指定的这些步骤。事实上，她借鉴了Unix操作系统的管道（pipe）思想，前一级的输出，直接变成后一级的输入，使得在操作上非常简单。

> <h1>安装</h1>

* 在安装nodejs环境后，以全局方式安装gulp
    `npm install -g gulp`
* 在全局安装gulp之后，还需要再每个要使用gulp的项目中单独安装一次。在项目文件夹中执行以下命令
    `npm install gulp --save`
<!---more--->

> <h1>使用</h1>

* 建立gulpfiles文件
	gulp需要一个叫做gulpfiles.js的文件作为主文件
* 运行gulp任务
	gulp中的功能的实现方式是通过运行相关任务的形式。在主文件中执行以下命令可以进行简单测试。如果没有指定任务名称，默认执行default任务。


	var gulp  = require('gulp');
	gulp.task('default',function(){
		console.log('hello world');
	});

> <h1>工作方式</h1>


　在gulp中，工作方式使用的是nodejs中的stream（流），然后通过stream的pipe()方法把流导入到想要的地方，比如gulp的插件中，经过插件处理后又可以继续导入到其他插件中，也可以把流写入到文件中。
　gulp的使用流程一般是，首先通过gulp.src()方法获得想要处理的文件流，然后把文件流通过pipe()方法导入到gulp的插件中，最后把经过处理的流再通过pipe()导入到gulp.dest()中，gulp.dest()方法则把流中的内容写入到文件中	

---

<H2>gulp.src(globs[, options])</H2>

　输出（Emits）符合所提供的匹配模式（glob）或者匹配模式的数组（array of globs）的文件。 将返回一个 Vinyl files 的 stream 它可以被 piped 到别的插件中。　
　<b>[glob](https://github.com/isaacs/node-glob) </b>请参考 node-glob 语法 或者，你也可以直接写文件的路径。


<b>globs</b>
　类型： String 或 Array.所要读取的 glob 或者包含 globs 的数组。
<b>options</b>
　类型： Object.通过 glob-stream 所传递给 node-glob 的参数。除了 node-glob 和 glob-stream 所支持的参数外，gulp 增加了一些额外的选项参数：
<b>options.buffer</b>
　类型： Boolean 默认值： true.如果该项被设置为 false，那么将会以 stream 方式返回 file.contents 而不是文件 buffer 的形式。这在处理一些大文件的时候将会很有用。**注意：**插件可能并不会实现对 stream 的支持。
<b>options.read</b>
　类型： Boolean 默认值： true.如果该项被设置为 false， 那么 file.contents 会返回空值（null），也就是并不会去读取文件。
<b>options.base</b>
　类型： String 默认值： 将会加在 glob 之前.

---

<h2>gulp.dest(path[, options])</h2>

　能被 pipe 进来，并且将会写文件。并且重新输出（emits）所有数据，因此你可以将它 pipe 到多个文件夹。如果某文件夹不存在，将会自动创建它。
<b>path</b>
　类型： String or Function.文件将被写入的路径（输　出目录）。也可以传入一个函数，在函数中返回相应路径，这个函数也可以由 vinyl 文件实例 来提供。
<b>options</b>
　类型： Object
<b>options.cwd</b>
　类型： String 默认值： process.cwd().输出目录的 cwd 参数，只在所给的输出目录是相对路径时候有效。
<b>options.mode</b>
　类型： String 默认值： 0777.八进制权限字符，用以定义所有在输出目录中所创建的目录的权限。

---

<h2>gulp.task(name[, deps], fn)</h2>

　定义一个任务
<b>name</b>
　任务的名字，如果你需要在命令行中运行你的某些任务，那么，请不要在名字中使用空格。
<b>deps</b>
　类型： Array.一个包含任务列表的数组，这些任务会在你当前任务运行之前完成。
<b>fn</b>
　该函数定义任务所要执行的一些操作。通常来说，它会是这种形式：
　gulp.src().pipe(someplugin())。

---

<h2>gulp.watch(glob[, opts], tasks)</h2>

<b>glob</b>
　类型： String or Array.一个 glob 字符串，或者一个包含多个 glob 字符串的数组，用来指定具体监控哪些文件的变动。
<b>opts</b>
　类型： Object.传给 gaze 的参数。
<b>tasks</b>
　类型： Array.需要在文件变动后执行的一个或者多个通过 gulp.task() 创建的 task 的名字，

> <h1>实例</h1>

　在编写gulp代码的时候，需要用到一些gulp插件，下面通过一个实现重命名的实例，来简单阐释一下插件的运用

	var gulp = require('gulp');
	var rename = require('gulp-rename');
	gulp.task('rename',function(){
		gulp.src('src/1.js')
		.pipe(rename('new.js'))
		.pipe(gulp.dest('js'));
	});
　上述代码实现了将src文件夹中的1.js文件重新命名为new.js，并将新的文件放到了js文件夹中。