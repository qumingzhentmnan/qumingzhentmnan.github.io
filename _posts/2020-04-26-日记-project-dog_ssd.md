---
layout: post
title:  日记 2020- 04-26-project-dog_ssd
categories: [日记]
tags: 日记
tags: project
---

> ssd做dog检测，主要就是把model 和对应的weight配置好

##==========ssd for dog

？？？可以做，对人和人骑车的数据.append

然后再做iou如果dog and 这两个区域的Iou过大

----可以把那个visualize 包含多个类别再实现一次，看看。。。框的大小设置什么的。。。

##====这样容易导致漏检： 比如a doge, 同时被识别成人 and doge, 而且iou很近，这个就容易被漏掉： 打算从threshold来下手。。。分层次？？

----检出来的，重新试一下thresh 的层次： 并不是很好，有不少在0.1附近的。。。确实

###====== gan paper