---
layout: post
title:  日记 04-21-case study
categories: [日记]
tags: 日记
tags: project
---

> case study for linear classifier and 2 layer nn.

1. 把整个流程重新解释了一遍，好像有点理解了

   2-d的 二次函数和参数，最好理解优化过程 ---以及notes里计算得到的，0< p <1, df = p -1{y = pk}

所有分类正确的class, 会有那一项 df <0, 这里的理解就是，gradient <0: 正确class 的scores 增加，使得loss减少，反之增加。

3. 然后就是进行参数更新，仔细想想二维的过程， 在某个点，计算出了当前点的gradient（复杂情况下，这里有chain rule, 传递的 gradient flow. ）

而learning rate，就是衡量，在确定了起始点，和进行的方向后，迈多大的步伐。这里，才是真正进行逼近的过程。。。

因此，一步步的重复，迭代，理论上，convec func是可以不断逼近optimal 的。。。

##===== linear and nn

在这个case study 里面，一开始，是用最简单的linear classify, 可以看到，对于稍微复杂一点的non-linear 就做不到区分了

而后面提出了add one hidden layer,就可以轻松解决这个问题，而为什么，也是deep nn一直在 尝试解释的问题

why bigger? deeper?

这一块就是一直尝试在说明的，特征，提取的问题

可以认为，人在对物体进行分类的时候，所依据的点，就是物体的特征。之前ml的时候，手工调，设置的提取方法比较多。而，in dl，将这些人工的东西，丢给nn, 让它们取自动提取区分，识别的特征。

几个说法是

1. 越前面的层，提取的特征越简单。轮廓，颜色，。。越往后，越有形象的object.

2. 二一个，就是越deeper,提取能力就越强，嗯。。

3. encoding的想法。230里面，用一个128-d vector来代替 a peron face. 可以认为，到最后一层的output 分类器之前的，forward前向这一部分，都是一个encoding的东西。

trained well 的nn,能使得，image,在通过forward之后得到的一个data, 能使得分类器将它正确分类。

而对于不使用fc layer的那些，最后用conv 层直接得到的数据，就是通过nn计算的encoding得到的 数据。。。这个想法不是特别清楚。