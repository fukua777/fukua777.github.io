---
title: About　Git SSH
tags: Git
date: 2016-08-11
categories: 甫夸之谈————Git 
---
>设置SSH公钥的方法

* git Bash
* ssh-keygen -t rsa -C "邮箱"
* 一路Enter，直到生成一个图形，此时电脑里会生成一个文件夹
* C盘-->用户-->Administrator-->.ssh-->复制id_rsa.pub里面的内容（这个是公钥可以告诉任何人，id_rsa是私钥，千万不要泄露）,粘贴到添加公钥的地方，标题会自动生成
* 在git中运行ssh -T git@github.com，后面yes，如果提示welcome和用户名，就表示成功了

>用VSCode对项目进行提交和推送

* 项目列表中切换到SSH，复制路径，在git Bash中进行克隆
* 在克隆的项目文件中进行改动后，提交，然后在VSCode中Git有上角点出复选项，选择【推送】，则可以与远程代码库进行同步