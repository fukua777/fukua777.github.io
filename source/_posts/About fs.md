---
title: About　fs
categories: 甫夸之谈———node
tags: "<span style='color: orange;'>fs</span>"
---

>fs　　文件系统

　　文件 I/O 是由简单封装的标准 POSIX 函数提供的。通过 require('fs') 使用该模块。所有的方法都有异步和同步的形式。异步形式始终以完成回调作为它最后一个参数。 传给完成回调的参数取决于具体方法，但第一个参数总是留给异常。 如果操作成功完成，则第一个参数会是 null 或 undefined。当使用同步形式时，任何异常都会被立即抛出。 可以使用 try/catch 来处理异常，或让它们往上冒泡。（以下fs均以已经引进fs模块为前提）
>常用函数

+	<b style="color:black;font-size:18px;">fs.readFile(filename,[options],callback);　　读取文件</b>
	filename,　必选参数，文件名 
	[options]　可选参数，可指定flag（文件操作选项，如r+ 读写；w+读写，文件不存在则创建）及encoding属性
	callback　读取文件后的回调函数，参数默认第一个err,第二个data数据
<!---more--->
+	<b style="color:black;font-size:18px;">fs.writeFile(filename,data,[options],callback);　　写文件</b>
	filename,　必选参数，文件名
	data, 写入的数据，可以字符或一个Buffer对象
	[options]　[options],flag,mode(权限),encoding
	callback　读取文件后的回调函数，参数默认第一个err,第二个data数据
+	<b style="color:black;font-size:18px;">fs.appendFile(filename,data,[options],callback);　　以追加方式写文件</b>
	filename,　必选参数，文件名
	data, 写入的数据，可以字符或一个Buffer对象
	[options]　[options],flag,mode(权限),encoding
	callback　读取文件后的回调函数，参数默认第一个err,第二个data数据
+	<b style="color:black;font-size:18px;">fs.open(filename, flags, [mode], callback);　　打开文件</b>
	filename,　必选参数，文件名
	flags, 操作标识，如"r",读方式打开
	[mode],权限，如777，表示任何用户读写可执行
	callback 打开文件后回调函数，参数默认第一个err,第二个fd为一个整数，表示打开文件返回的文件描述符，window中又称文件句柄
+	<b style="color:black;font-size:18px;">fs.read(fd, buffer, offset, length, position, callback);　　读文件，读取打开的文件内容到缓冲区中</b>
	fd, 使用fs.open打开成功后返回的文件描述符
	buffer, 一个Buffer对象，v8引擎分配的一段内存
	offset, 整数，向缓存区中写入时的初始位置，以字节为单位
	length, 整数，读取文件的长度
	position, 整数，读取文件初始位置；文件大小以字节为单位
	callback(err, bytesRead, buffer), 读取执行完成后回调函数，bytesRead实际读取字节数，被读取的缓存区对象
+	<b style="color:black;font-size:18px;">fs.write(fd, buffer, offset, length, position, callback);　　写文件，将缓冲区内数据写入使用fs.open打开的文件</b>
	fd, 使用fs.open打开成功后返回的文件描述符
	buffer, 一个Buffer对象，v8引擎分配的一段内存
	offset, 整数，从缓存区中读取时的初始位置，以字节为单位
	length, 整数，从缓存区中读取数据的字节数
	position, 整数，写入文件初始位置；
	callback(err, written, buffer), 写入操作执行完成后回调函数，written实际写入字节数，buffer被读取的缓存区对象
*****
+	<b style="color:black;font-size:18px;">fs.mkdir(path, [mode], callback);　　创建目录</b>
	path, 被创建目录的完整路径及目录名；
	[mode], 目录权限，默认0777
	[callback(err)], 创建完目录回调函数,err错误对象
+	<b style="color:black;font-size:18px;">fs.readdir(path, callback);　　读取目录</b>
	path, 要读取目录的完整路径及目录名；
	[callback(err, files)], 读完目录回调函数；err错误对象，files数组，存放读取到的目录中的所有文件名
+	<b style="color:black;font-size:18px;">fs.stat(path, callback);　　查看文件与目录的信息</b>
	path, 要查看目录/文件的完整路径及名；
	[callback(err, stats)], 操作完成回调函数；err错误对象，stat fs.Stat一个对象实例，提供如:isFile, isDirectory,isBlockDevice等方法及size,ctime,mtime等属性
+	<b style="color:black;font-size:18px;">fs.exists(path, callback);　　查看文件与目录的是否存在</b>
	path, 要读取目录的完整路径及目录名；
	[callback(exists)], 操作完成回调函数；exists true存在，false表示不存在
+	<b style="color:black;font-size:18px;">fs.rename(oldPath, newPath, callback);　　移动/重命名文件或目录</b>
	oldPath, 原目录/文件的完整路径及名；
	newPath, 新目录/文件的完整路径及名；如果新路径与原路径相同，而只文件名不同，则是重命名
	[callback(err)], 操作完成回调函数；err操作失败对象
+	<b style="color:black;font-size:18px;">fs.rmdir(path, callback);　　删除空目录</b>
	path, 目录的完整路径及目录名；
	[callback(err)], 操作完成回调函数；err操作失败对象
*****
+	<b style="color:black;font-size:18px;">fs.utimes(path, atime, mtime, callback);　　修改文件访问时间与修改时间</b>
	path, 要查看目录/文件的完整路径及名；
	atime, 新的访问时间
	ctime, 新的修改时间
	[callback(err)], 操作完成回调函数；err操作失败对象
+	<b style="color:black;font-size:18px;">fs.utimes(path, mode, callback);　　修改文件或目录的操作权限</b>
	path, 要查看目录/文件的完整路径及名；
	mode, 指定权限，如：0666 8进制，权限：所有用户可读、写，
	[callback(err)], 操作完成回调函数；err操作失败对象
*****
+	<b style="color:black;font-size:18px;">fs.watchFile(filename, [options], listener);　　对文件进行监视，并且在监视到文件被修改时执行处理</b>
	filename, 完整路径及文件名；
	[options], persistent true表示持续监视，不退出程序；interval 单位毫秒，表示每隔多少毫秒监视一次文件
	listener, 文件发生变化时回调，有两个参数：curr为一个fs.Stat对象，被修改后文件，prev,一个fs.Stat对象，表示修改前对象
+	<b style="color:black;font-size:18px;">fs.watch(filename, [options], [listener]);　　对文件进行监视，并且在监视到文件被修改时执行处理</b>
	filename, 完整路径及文件名或目录名；
	[listener(event, filename], 监听器事件，有两个参数：event 为rename表示指定的文件或目录中有重命名、删除或移动操作或change表示有修改，filename表示发生变化的文件路径
	fs.watch返回一个fs.FSWatcher对象，拥有一个close方法，用于停止watch操作；
	当fs.watch有文件变化时，会触发fs.FSWatcher对象的change(err, filename)事件，err错误对象，filename发生变化的文件名
*****
*****
>文件流

　　流，在应用程序中表示一组有序的、有起点有终点的字节数据的传输手段；Node.js中实现了stream.Readable/stream.Writeable接口的对象进行流数据读写；以上接口都继承自EventEmitter类，因此在读/写流不同状态时，触发不同事件；关于流读取：Node.js不断将文件一小块内容读入缓冲区，再从缓冲区中读取内容；关于流写入：Node.js不断将流数据写入内在缓冲区，待缓冲区满后再将缓冲区写入到文件中；重复上面操作直到要写入内容写写完；readFile、read、writeFile、write都是将整个文件放入内存而再操作，而则是文件一部分数据一部分数据操作；
+	流读取
	+	读取数据对象：
	<b style="color:black;font-size:18px;">fs.ReadStream　　读取文件</b>
	<b style="color:black;font-size:18px;">http.IncomingMessage　　客户端请求或服务器端响应</b>
	<b style="color:black;font-size:18px;">net.Socket　　Socket端口对象</b>
	<b style="color:black;font-size:18px;">child.stdout　　子进程标准输出</b>
	<b style="color:black;font-size:18px;">child.stdin　　子进程标准入</b>
	<b style="color:black;font-size:18px;">process.stdin　　用于创建进程标准输入流</b>
	<b style="color:black;font-size:18px;">Gzip、Deflate、DeflateRaw　　数据压缩</b>
	+	触发事件：
	<b style="color:black;font-size:18px;">fs.ReadStream　　读取文件</b>
	<b style="color:black;font-size:18px;">data　　数据读取后</b>
	<b style="color:black;font-size:18px;">end　　数据读取完成时</b>
	<b style="color:black;font-size:18px;">error　　数据读取错误时</b>
	<b style="color:black;font-size:18px;">close　　关闭流对象时</b>
	+	读取数据的对象操作方法：
	<b style="color:black;font-size:18px;">read　　读取数据方法</b>
	<b style="color:black;font-size:18px;">setEncoding　　设置读取数据的编</b>
	<b style="color:black;font-size:18px;">pause　　通知对象众目停止触发data事件</b>
	<b style="color:black;font-size:18px;">resume　　通知对象恢复触发data事件</b>
	<b style="color:black;font-size:18px;">unpipe　　取消通道</b>
	<b style="color:black;font-size:18px;">unshift   当流数据绑定一个解析器时，此方法取消解析器</b>
+	流写入
	+	写数据对象：
	<b style="color:black;font-size:18px;">fs.WriteStream　　写入文件对象</b>
	<b style="color:black;font-size:18px;">http.clientRequest　　写入HTTP客户端请求数据</b>
	<b style="color:black;font-size:18px;">http.ServerResponse　　写入HTTP服务器端响应数据</b>
	<b style="color:black;font-size:18px;">net.Socket　　读写TCP流或UNIX流，需要connection事件传递给用户</b>
	<b style="color:black;font-size:18px;">child.stdout　　子进程标准输出</b>
	<b style="color:black;font-size:18px;">child.stdin　　子进程标准入</b>
	<b style="color:black;font-size:18px;">Gzip、Deflate、DeflateRaw　　数据压缩</b>
	+	写入数据触发事件：
	<b style="color:black;font-size:18px;">drain　　当write方法返回false时，表示缓存区中已经输出到目标对象中，可以继续写入数据到缓存区</b>
	<b style="color:black;font-size:18px;">finish　　当end方法调用，全部数据写入完成</b>
	<b style="color:black;font-size:18px;">pipe             当用于读取数据的对象的pipe方法被调用时</b>
	<b style="color:black;font-size:18px;">error　　数据读取错误时</b>
	<b style="color:black;font-size:18px;">error　　当发生错误</b>
	+	写入数据方法：
	<b style="color:black;font-size:18px;">write　　用于写入数据</b>
	<b style="color:black;font-size:18px;">end　　结束写入，之后再写入会报错；</b>
+	创建读取流
	<b style="color:black;font-size:18px;">fs.createReadStream(path, [options]);</b>
	path 文件路径
	[options] flags:指定文件操作，默认'r',读操作；encoding,指定读取流编码；autoClose, 是否读取完成后自动关闭，默认true；start指定文件开始读取位置；end指定文件开始读结束位置
	```
	var rs = fs.createReadStream(__dirname + '/test.txt', {start: 0, end: 2});
	rs.on('open', function (fd) {
	  console.log('messi is the best one');
	});
	```
+	创建写入流
	<b style="color:black;font-size:18px;">fs.createWriteStream(path, [options]);</b>
	path 文件路径
	[options] flags:指定文件操作，默认'w',；encoding,指定读取流编码；start指定写入文件的位置
	```
	var ws = fs.createWriteStream(__dirname + '/test.txt', {start: 0});
	var buffer = new Buffer('messi is the best one');
	ws.write(buffer, 'utf8', function (err, buffer) {
		console.log(arguments);
	});
	```
+	管道pipe实现流读写
	<b style="color:black;font-size:18px;">rs.pipe(destination, [options]);</b>
	destination 必须一个可写入流数据对象
	[opations] end 默认为true，表示读取完成立即关闭文件；
	```
	var rs = fs.createReadStream(__dirname + '/test/Until You.mp3');
	var ws = fs.createWriteStream(__dirname + '/test/untiyou.mp3');
	rs.pipe(ws);
	rs.on('data', function (data) {
	  console.log('success')
	});
	```
*****
*****
　渺小的搬运工　<span>&hearts;</span>　<a href="http://www.jianshu.com/u/a7bbc65dd117">明明三省</a>
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	
	