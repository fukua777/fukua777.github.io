---
title: About　sql
categories: 甫夸之谈———sql
tags: "sql"
---

>DML　　数据操纵语言(select,delete,uqdate,insert)

　　<b style="color:black;font-size:25px;">select</b>　选择　　
　　<b style="color:black;font-size:25px;">insert</b>　插入　insert into table1(key1,key2) values(val1,val2)
　　<b style="color:black;font-size:25px;">delete</b>　删除
　　<b style="color:black;font-size:25px;">update</b>　更新　update table1 set key1 = val1
<!---more--->
　　<b style="color:black;font-size:25px;">like</b>　select * from table1 where key1 like "%val%"
　　<b style="color:black;font-size:25px;">order by</b>　select * from order by key1
　　<b style="color:black;font-size:25px;">count</b>　select count as name_other from table1
　　<b style="color:black;font-size:25px;">sum</b>　select sum(key1) as name_other from table1
　　<b style="color:black;font-size:25px;">avg</b>　select avg(key1) as name_other from table1
　　<b style="color:black;font-size:25px;">max</b>　select max(key1) as name_other from table1
　　<b style="color:black;font-size:25px;">min</b>　select min(key1) as name_other from table1
*****
　　<b style="color:black;font-size:25px;">union</b>　返回两个结果集的并集 select * from table1 union select * from table2
　　<b style="color:black;font-size:25px;">except</b>　返回两个结果集的差，查询符合左表不符合右表的 select * from table1 union select * from table2
　　<b style="color:black;font-size:25px;">intersect</b>　返回两个结果集的并集 select * from table1 intersect select * from table2
*****
　　<b style="color:black;font-size:25px;">left join on</b>　返回连接表的匹配项，也返回左表的所有项 select * from table1 left join table2 on table1.key1 = table2.key2
　　<b style="color:black;font-size:25px;">right join on</b>　返回连接表的匹配项，也返回右表的所有项
　　<b style="color:black;font-size:25px;">full join on</b>　返回连接表所有项
　　<b style="color:black;font-size:25px;">inner join on</b>　返回连接表的共同项
*****
　　<b style="color:black;font-size:25px;">between</b>　限制查询范围，同时包括边界值 select * from table1 where time between time1 and time2 
　　<b style="color:black;font-size:25px;">not between</b>　反之
　　<b style="color:black;font-size:25px;">in</b>　匹配条件中的任意值 select * from table1 where key1 in (val1,val2)
　　<b style="color:black;font-size:25px;">not in</b>　反之
　　<b style="color:black;font-size:25px;">group by</b>　根据某一项或多项对结果进行分组统计 select key1,sum(key2) name_other from table1 group by key1
*****
　　纯属基础，稍作总结，全属语义，全靠用熟。