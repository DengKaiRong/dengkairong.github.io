---
layout: post
title:  "iOS-把文字转换成语音播报"
date: 2017-04-05
desc: "iOS-把文字转换成语音播报"
keywords: "iOS,语音播报"
categories: [iOS]
tags: [iOS,语音播报,Objective-C]
icon: icon-html
---
    AVSpeechUtterance *utterance = [[AVSpeechUtterance alloc] initWithString:@"八百标兵奔北坡，北坡炮兵并排跑，炮兵怕把标兵碰，标兵怕碰炮兵炮。"];

    //设置发音
    AVSpeechSynthesisVoice *voice = [AVSpeechSynthesisVoice voiceWithLanguage:@"zh-TW"];

    utterance.voice = voice;

    utterance.rate = 0.1;

    //显示所有支持的发音
    NSLog(@"%@",[AVSpeechSynthesisVoice speechVoices]);

    AVSpeechSynthesizer *synth = [[AVSpeechSynthesizer alloc]init];

    [synth speakUtterance:utterance];