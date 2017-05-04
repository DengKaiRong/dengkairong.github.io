---
layout: post
title:  "iOS-设置导航栏透明的方法"
date: 2017-04-05
desc: "iOS-设置导航栏透明的方法"
keywords: "iOS"
categories: [iOS]
tags: [iOS,Objective-C]
icon: icon-html
---
	- (void)viewWillAppear:(BOOL)animated{

	    //设置导航栏背景图片为一个空的image，这样就透明了
	    [self.navigationController.navigationBar setBackgroundImage:[[UIImage alloc] init] forBarMetrics:UIBarMetricsDefault];

	    //去掉透明后导航栏下边的黑边
	    [self.navigationController.navigationBar setShadowImage:[[UIImage alloc] init]];
	}

	- (void)viewWillDisappear:(BOOL)animated{

	    //    如果不想让其他页面的导航栏变为透明 需要重置
	    [self.navigationController.navigationBar setBackgroundImage:nil forBarMetrics:UIBarMetricsDefault];
	    [self.navigationController.navigationBar setShadowImage:nil];
	}