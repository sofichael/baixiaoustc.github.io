---
author: baixiaoustc
comments: true
date: 2016-10-07 10:34:32+00:00
layout: post
link: http://baixiaoustc.com/wordpress/2016/10/07/%e8%b7%af%e7%ba%bf%e8%bd%a8%e8%bf%b9%e8%81%9a%e9%9b%86%ef%bc%9a%e5%88%86%e5%89%b2%e5%92%8c%e6%b1%87%e9%9b%86%ef%bc%886%ef%bc%9a%e8%ae%a1%e7%ae%97%e4%bb%a3%e8%a1%a8%e8%bd%a8%e8%bf%b9%ef%bc%89/
slug: '%e8%b7%af%e7%ba%bf%e8%bd%a8%e8%bf%b9%e8%81%9a%e9%9b%86%ef%bc%9a%e5%88%86%e5%89%b2%e5%92%8c%e6%b1%87%e9%9b%86%ef%bc%886%ef%bc%9a%e8%ae%a1%e7%ae%97%e4%bb%a3%e8%a1%a8%e8%bd%a8%e8%bf%b9%ef%bc%89'
title: 路线轨迹聚集：分割和汇集（6：计算代表轨迹）
wordpress_id: 257
categories:
- 路线聚集
tags:
- trajectory
---

《Trajectory Clustering- A Partition-and-Group Framework》学习笔记

前文计算出聚类cluster的集合之后，需要计算出每个cluster的代表轨迹，即为该聚类中的“热点路径”。

原文提出，用一条垂直于cluster中线段的平均走向的直线扫描各条线段，每次经过一条线段的起点或终点时都要判断一下此时相交线段的个数是否不小于MinLns。若是，则计算一个所有交点的平均点并存储于列表中，否则不予理会。最终生成的列表即为平均轨迹的结点坐标信息。 为了计算方便，用到了坐标系旋转的操作，让“cluster中线段的平均走向”和x轴平行。

![%e6%9c%aa%e5%91%bd%e5%90%8d](http://baixiaoustc.com/wordpress/wp-content/uploads/2016/10/未命名-9.png)

算法如下：

![%e6%9c%aa%e5%91%bd%e5%90%8d](http://baixiaoustc.com/wordpress/wp-content/uploads/2016/10/未命名-10.png)

根据此算法，我模拟的结果如下：

黑色粗线就是代表性轨迹，也就是我们需要的“热点路径”

![%e6%9c%aa%e5%91%bd%e5%90%8d](http://baixiaoustc.com/wordpress/wp-content/uploads/2016/10/未命名-11.png)
