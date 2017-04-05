---
layout: post
title:  "iOS-解决警告“ld: warning: directory not found for option”"
date: 2017-04-05
desc: "iOS-解决警告“ld: warning: directory not found for option”"
keywords: "iOS"
categories: [iOS]
tags: [iOS,Objective-C]
icon: icon-html
---
从项目中删除了某个目录、文件以后，编译出现警告信息：

	ld: warning: directory not found for option“XXXXXX”

很奇怪，为什么已经从项目中删除了文件和文件夹还是报这个警告呢？

去掉警告的办法如下：

	1.选择工程, 编译的 (targets)

	2.选择 Build Settings 菜单

	3.查找 Library Search Paths 和 Framework Search Paths， 删掉编译报warning的路径即OK
