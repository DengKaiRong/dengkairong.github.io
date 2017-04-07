---
layout: post
title:  "iOS-UIWebView获取内容高度和禁用长按手势"
date: 2017-04-07
desc: "iOS-UIWebView获取内容高度和禁用长按手势"
keywords: "iOS,UIWebView"
categories: [iOS]
tags: [iOS,UIWebView]
icon: icon-html
---
	- (void)webViewDidFinishLoad:(UIWebView *)webView{
	    
	    //获取内容高度
	    float contentHeight = [[_webView stringByEvaluatingJavaScriptFromString:@"document.body.clientHeight"]floatValue];
	    
	    //webview自适应大小
	    CGRect rect = _webView.frame;
	    rect.size.height = contentHeight;
	    _webView.frame = rect;
	    
	    //回调代理通知高度改变
	    if ([self.delegate respondsToSelector:@selector(qianKunWebCellHeightChange:)]) {
	        [self.delegate qianKunWebCellHeightChange:contentHeight];
	    }
	    
	    //禁用长按手势
	    [_webView stringByEvaluatingJavaScriptFromString:@"document.documentElement.style.webkitUserSelect='none';"];
	    [_webView stringByEvaluatingJavaScriptFromString:@"document.documentElement.style.webkitTouchCallout='none';"];
	    
	}