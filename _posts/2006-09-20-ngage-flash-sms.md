---
id: 119
title: N-Gage/QD也能发闪信(Flash SMS)?
date: 2006-09-20T00:15:36+00:00
author: oasisfeng
layout: post
guid: http://blog.oasisfeng.com/2006/09/20/ngage-flash-sms/
permalink: /2006/09/20/ngage-flash-sms/
dsq_thread_id:
  - "250426322"
  - "250426322"
categories:
  - Mobile
  - Symbian
tags:
  - Flash-SMS
  - N-Gage
  - NetMon
  - Symbian
  - zg
---
　　今天在zg的blog上看到他又更新了NetMon，加入了以下新特性：

　　(1) Send Flash SMS &#8211; 发送闪信（Flash SMS）
  
　　(2) Set Own Number &#8211; 设置本机号码
  
　　(3) Set SC Address &#8211; 设置短信中心号码

<!--more-->　　由于zg只是一语带过，而且也没有放出可运行的版本，所以我自己编译出来尝试了一下。

　　“发送闪信”功能从Tx信号的变化来看应该是通过网络发送出去了（后来通过移动网站确认有添加了前缀“00”的短信发送记录），但是对方手机却没有任何反应。因为我不知道具体哪些手机型号支持“闪信”，所以尚不能下结论，期待更多朋友的尝试。

　　“设置本机号码”这个功能我实在没搞懂有什么作用。虽然，凭俺搞信令这么多年的经验来说，手机终端根本无法越权修改对方“主叫号码”的显示（可以请求网络隐藏“主叫号码”）。但终归抱着那么一点幻想，尝试了用NetMon修改为非实际本机的号码。结果出现了无法接收短信的严重情况，但电话一切正常，发出的短信和拨出的电话同样显示的还是自己真实的手机号码……

　　至于最后那个“设置短信中心号码”的功能，不是NG本身就有的设置选项么？不解……

　　尽管beta测试不太顺利，但仍然期待zg尽快发布正式版本！（至少到那时会解释一下这些功能的作用了吧）