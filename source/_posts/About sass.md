---
title: About　SASS
tags: "<h1>css</h1>"
categories: 甫夸之谈———CSS
---

> 关于

　　Sass是一种CSS辅助工具，在CSS语法基础上增加了变量、嵌套、混合、导入等功能，使得开发更加高效。
<!---more--->

　　<b style="color:black;font-size:25px;">嵌套</b>　在`{}`内写样式，内层样式以外层选择器为父选择器
　　<b style="color:black;font-size:25px;">$</b>　引用父选择器
　　<b style="color:black;font-size:25px;">属性嵌套</b>　允许使用属性命名空间
　　<b style="color:black;font-size:25px;">注释</b>　允许多行注释`/* */`、单行注释`//`，前者会输出到编译后的文件中，后者不会
　　<b style="color:black;font-size:25px;">SassScript</b>　允许常规JS操作，包括变量`$var`、常规运算等
　　<b style="color:black;font-size:25px;">插值语句</b>　`#{ }`，直接引用变量
　　<b style="color:black;font-size:25px;">变量定义</b>　`!default`，给变量添加保护赋值
　　<b style="color:black;font-size:25px;">引入</b>　`@import`，引入Sass或Scss文件为导入，其它为普通引用CSS语句
　　<b style="color:black;font-size:25px;">分音</b>　在Scss或Sass文件名前加下划线，引入语句不变，则引入文件不会编译
　　<b style="color:black;font-size:25px;">继承</b>　`@extend`，引用其它样式
　　<b style="color:black;font-size:25px;">占位符</b>　`@extend %var`，定义样式，只能用来继承，不会参与编译
　　<b style="color:black;font-size:25px;">声明</b>　`!optional`，为引用或继承的选择器添加保护
　　<b style="color:black;font-size:25px;">控制指令</b>　允许使用JS中基础的控制指令，包括`@if`、`@for $var from <start> through <end>`（包含始终）、`@for $var from <start> to <end>`、`@each $var in <list>`、`@while`等
　　<b style="color:black;font-size:25px;">混合指令</b>　在`@mixin`后添加名称和样式，使用`$incllude`引用混合样式，可运用参数，引用时参数写法可为`key: value`形式，`@mixin`可以用`=`表示，`@incllude`可以用`+`表示
　　<b style="color:black;font-size:25px;">函数</b>　允许使用JS中简单函数操作，包括`@function funcname`、`@return result`等
　　<b style="color:black;font-size:25px;">输出格式</b>　用`:style option`命令选项来设置输出格式，`:nested`，默认格式，缩进、嵌套与Sass一致；`:expanded`，与手写格式相似，无嵌套、缩进；`:compact`，每条规则只占一行；`:compressed`，在`:expanded`基础上删除无意义的空格、空白、注释，压缩为最小

