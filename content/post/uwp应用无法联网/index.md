---
title: uwp应用无法联网
description: 开启系统代理后，uwp应用无法联网
date: 2022-04-24
slug: 
image: 1.jpg
categories:
    - 折腾电脑
---



# 问题描述

clash开着系统代理的情况下，微软自带的应用基本都无法联网，比如下方的TODO应用。



![  ](https://s2.loli.net/2022/04/25/2Rn8lzWSufJ1Tj6.png)

但是关闭系统代理后，它联网同步是没有问题的。 

一方面，我的代理我习惯性的一直开着， 如果为了同步一下应用数据，开一下关一下会让我感觉很麻烦。 因此这个需求其实挺硬性的。 



# 问题原因

原因搜了一下，不是做android开发的，不太理解。 



>Win10 所有 UWP 应用均运行在被称为 App Container 的虚拟沙箱环境中，App Container 可以保证应用安全性，但同时也阻止了网络流量发送到本机（即 loopback）， 使大部分网络抓包调试工具无法对 UWP 应用进行流量分析。同样的，该机制也阻止了 UWP 应用访问 localhost，即使你在系统设置中启用了代理，也无法令 UWP 应用访问本地代理服务器。
>

# 问题解决

[Fiddler](https://www.telerik.com/fiddler) 一个抓包工具。

进入到官网之后，点击try for free 然后随便填写邮箱，下载启动。

进入到应用后，点击winConfig，然后弹出的窗口，把所有的全勾选上，即可。

![image-20220425235440723](https://s2.loli.net/2022/04/25/wIVsYZOxfQPBrpT.png)

