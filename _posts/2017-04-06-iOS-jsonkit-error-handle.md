---
layout: post
title:  "iOS-JSONKit编译报错解决方法"
date: 2017-04-06
desc: "iOS-JSONKit编译报错解决方法"
keywords: "iOS,语音播报"
categories: [iOS]
tags: [iOS,Objective-C]
icon: icon-html
---
如果从github上下来的JSONKit在使用的时候报编译错误，可以按如下的方式尝试解决

	1：Build Phases->Compile Sources,双击JSONKit.m,输入：-fno-objc-arc

	2：修改JSONKit.m文件第680行，修改为object_setClass(array, _JKArrayClass);

	3：修改JSONKit.m文件第932行，修改为object_setClass(dictionary, _JKDictionaryClass);

这个使用再去使用JSONKit库，就没问题了。