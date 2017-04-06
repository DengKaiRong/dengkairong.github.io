---
layout: post
title:  "iOS-单独让某个控制器横屏"
date: 2017-04-06
desc: "iOS-单独让某个控制器横屏"
keywords: "iOS,屏幕横屏"
categories: [iOS]
tags: [iOS,Objective-C,横屏,开发]
icon: icon-html
---
### iOS程序开发中，若要单独让某个控制器横屏，可以用如下方法：

 在 AppDelegate.h 添加属性：

	 //屏幕方向  
	 @property (nonatomic, assign) NSInteger allowRotation; 

 在 AppDelegate.m 添加方法：

	 - (UIInterfaceOrientationMask)application:(UIApplication *)application supportedInterfaceOrientationsForWindow:(UIWindow *)window  
	 {  
	
	     if (_allowRotation == 1) {  
	
	         return UIInterfaceOrientationMaskLandscapeRight;  
	           
	     }else {  
	
	         return UIInterfaceOrientationMaskPortrait;  
	
	     }  
	 }  
	
 可以在跳转控制器中设置:

	 HWGoalVC *vc = [[HWGoalVC alloc] init];  
	 [self.navigationController presentViewController:vc animated:YES completion:nil]; 

 在目标控制器中设置：

	 AppDelegate *appDelegate = (AppDelegate *)[UIApplication sharedApplication].delegate;  
	 appDelegate.allowRotation = 1;

 在目标控制器返回时设置：

	 - (void)back  
	 {  
	
	     AppDelegate *appDelegate = (AppDelegate *)[UIApplication sharedApplication].delegate;  

	     appDelegate.allowRotation = 0;  
	
	     [self dismissViewControllerAnimated:YES completion:nil];  
	 } 

 若想隐藏StatusBar，可调用如下方法：

	 - (BOOL)prefersStatusBarHidden  
	 {  
		//iOS7前隐藏StatusBar  
		[[UIApplication sharedApplication] setStatusBarHidden:YES withAnimation:UIStatusBarAnimationFade];
		//iOS7以后隐藏StatusBar  	
		return YES;  
	 }


