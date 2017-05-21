---
title: About　RegExp
categories: 甫夸之谈———正则
date: 2016-09-27
tags: "<b style='font-size:40px;'>RegExp</b>"
---

>关于RegExp

　　RegExp正则表达式以简要的格式对字符进行筛选。

>主要

　　<b style="color:red;font-size:25px;">\</b>　　将下一个字符标记为特殊字符，进行转义。如；"\n"匹配换行符，"\ \"匹配"\"
　　<b style="color:red;font-size:25px;">^</b>　　匹配输入字符串的开始位置。如果设置了RegExp对象的Multiline属性（多行），也匹配"\n"或"\r"之后的位置
　　<b style="color:red;font-size:25px;">$</b>　　匹配输入字符串的结束位置。如果设置了RegExp对象的Multiline属性，也匹配"\n"或"\r"之前的位置

<!---more---> 

　　<b style="color:red;font-size:25px;">*</b>　　匹配前面的子表达式零次或多次
　　<b style="color:red;font-size:25px;">+</b>　　匹配前面的子表达式一次或多次
　　<b style="color:red;font-size:25px;">?</b>　　匹配前面的子表达式零次或一次
　　<b style="color:red;font-size:25px;">{n}</b>　　n是一个非负整数，匹配确定的n次
　　<b style="color:red;font-size:25px;">{n,}</b>　　n是非负整数，至少匹配n次
　　<b style="color:red;font-size:25px;">{n,m}</b>　　n和m均为非负整数，其中n<=m，最少匹配n次，最多匹配m次
　　<b style="color:red;font-size:25px;">x|y</b>　　匹配x或y
　　<b style="color:red;font-size:25px;">[xyz]</b>　　匹配所包含的任意一个字符
　　<b style="color:red;font-size:25px;">[^xyz]</b>　　匹配未包含的任意字符
　　<b style="color:red;font-size:25px;">[a-z]</b>　　匹配指定范围内的任意字符
　　<b style="color:red;font-size:25px;">[^a-z]</b>　　匹配任何不在指定范围的任意字符
　　<b style="color:red;font-size:25px;">\b</b>　　匹配一个单词边界
　　<b style="color:red;font-size:25px;">\B</b>　　匹配非单词边界
　　<b style="color:red;font-size:25px;">\cx</b>　　匹配由x指明的控制字符。如：\cM匹配一个Control-M或回车符。x的值必须为A-Z或a-z之一，否则将c视为一个原义的"c"字符
　　<b style="color:red;font-size:25px;">\d</b>　　匹配一个数字字符。等价于[0-9]
　　<b style="color:red;font-size:25px;">\D</b>　　匹配一个非数字字符。等价于[^0-9]
　　<b style="color:red;font-size:25px;">\f</b>　　匹配一个换页符。等价于\x0c和\cL
　　<b style="color:red;font-size:25px;">\n</b>　　匹配一个换行符。等价于\x0a和\cJ
　　<b style="color:red;font-size:25px;">\r</b>　　匹配一个回车符。等价于\0d和\cM
　　<b style="color:red;font-size:25px;">\t</b>　　匹配一个制表符。等价于\x09和\cI
　　<b style="color:red;font-size:25px;">\v</b>　　匹配一个垂直制表符。等价于\x0b和\cK
　　<b style="color:red;font-size:25px;">\s</b>　　匹配任何非空白字符，包括空格、制表符、换页符等等。等价于[\f\n\r\t\v]
　　<b style="color:red;font-size:25px;">\w</b>　　匹配包括下划线的任何单词字符。等价于[a-zA-Z0-9_]
　　<b style="color:red;font-size:25px;">\W</b>　　匹配任何非单词字符。等价于[^a-zA-Z0-9_]
































