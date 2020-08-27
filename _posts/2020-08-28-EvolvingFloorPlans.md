---

layout: post
title: "算法: 平面图生成(转载)"
permalink: "blog/evolving-floorplans"
categories:
  - zh
comments_id: 13

---

作者: Joel Simon  
翻译: 马海东

**编者按**: 一个关于平面生成的算法,期望可以启发对CAAD感兴趣的同学 :) 

平面图生成(EFP)是一个实验性的项目，研究平面的生成及优化的可能性。初始条件为各个房间关系及人流分布, 通过一个遗传算法来优化生成平面图，其优化的限制因素为步行时间和走廊的长度等。EFP项目只是从设定的优化条件来进行平面布局，而不去考虑传统的布局要求及可建性等因素。EFP的目标是如何通过算法将显性、隐性的限制条件结合起来,生成高复杂度的平面图。 EFP的平面图是从它的遗传编码中 "生长 "出来，使用的算法是图像收缩方法生成布局及蚁群算法生长走廊。

其最终的结果在外观上有生物学的特性，其特色看起来耐人寻味的, 从实践的角度来看是疯狂的非理性的。 本项目是一次有趣的学习经历，我期望在其他项目中可以继续使用本项目中的方法。

**原始的平面布局**    
![top](/assets/images/13-evolvingFloorplans/results_top.png)    
缅因州某个地方的小学平面图.

**'平面优化'**  
![bottom](/assets/images/13-evolvingFloorplans/results_bottom.jpeg)    
左：优化了班级之间的人流量和建材的使用量。右边：加入了消防通道长度因素。

**采光**  
![windows](/assets/images/13-evolvingFloorplans/windows.jpg)  
采光功能要求,其中教室的优先级高于储藏室。这导致了许多内部庭院

### 项目背景

空间设计的一个核心挑战是空间形式的优化, 其中包括位置关系、形状和大小。在建筑设计中，房间的布局处于设计过程的概念阶段，它受到多种相互关联及竞争的客观和主观因素的影响 。

随着计算机技术的发展, 计算工具可以用来模拟交通、声学和热保护等，使得对形式的评估更加客观量化。与这些计算能力相融合的是制造方面的进步，包括数控铣削、现场3D打印、自组装等等，这使得新的、更复杂的形式成为可能，这些新的形式可以赋予设计师探索和优化越来越复杂的空间处理能力。

### 相关算法

图形收缩和蚁群路径这两种模拟方法被用作平面的"成长"过程。图形收缩是一系列算法，旨在创建视觉上吸引人的图形布局。蚁群算法是一种概率论方法，其灵感来源于蚂蚁在寻找食物过程中发现路径的行为。这种算法具有分布计算、信息正反馈和启发式搜索的特征，本质上是进化算法中的一种启发式全局优化算法。

大致的原理如下: 平面图基因组是一个有加权因子、相互连接又不定向的图。每一个想要的房间都用一个节点基因来表示，这个节点基因包含了房间的大小等信息。t同时还有连接基因, 连接基因指定了两个要跨越的节点基因以及一个随机初始化的权重；这两种基因以随机的方式添加，直到图被连接。相邻性要求创建一个具有最大边缘权重的子图。例如，食堂必须与厨房相邻。

### 从基因信息映射成平面信息的绘制

从基因信息映射成平面信息的绘制过程分四个部分完成。首先，图中的每个节点都设置到一个中间位置（图1a）。第二，物理模拟将中间位置映射到最终坐标，该坐标是平面图中该房间的中心（图1b）。第三，将房间中心转换为代表墙壁的多边形网格（图1c，1d）。第四，沿着网格的边缘创建走廊，然后使用受蚂蚁群行为启发的算法进行修剪和最终确定，并转换为最终的几何体（图1e，1f）。

**Mapping Overview**  
![overview](/assets/images/13-evolvingFloorplans/overview_figure.jpg)      
**图1**：完整的映射过程。a)初始物理模拟。b)物理模拟的最终结果。c)轮廓图(红色)扩张，以产生边界Voronoi种子(紫色圆圈)。d)Voronoi镶嵌创建几何网格。e)添加了内部边缘的平面图，走廊算法的结果用黄色绘制。f)走廊被合并成最终的几何体，内部边缘用于门的放置。

**Hallways**  
![hallway](/assets/images/13-evolvingFloorplans/hallway_process.jpg)      
图2：走廊生成过程。a）具有三个房间的平面图。 b）内部节点和边缘的创建，显示为空心圆和虚线。c) OHP的初步结果。选定的边缘用红色画出。d)通过将走廊顶点移动到其投影到邻居形成的线段上来平滑走廊。 e)通过使用半径与旅行负荷成正比的圆的外切线来创建走廊几何体。 f)最终的走廊几何体，门从内部边缘放置，并带有旅行负荷。

### 后续发展

学校的一个特点就是学生的课表和平面布局的相互关联与演变。这样可以对整个学校一天的体验进行统一的优化处理。目前遗传算法已经可以应用于优化排课问题。

此外EFP的衡量标准可以扩展到包括地形图、太阳路径、现有树木和其他环境输入，使建筑物能够高度适应其环境。物理模拟也可以强制进行一定的边界形状约束。

EFP方法也可以用于其他功能的布置，如办公室布局或医院。医院可以尽量减少关键路线，如手术室和病理实验室之间或护士室和病人之间。办公室的规划可以旨在最大限度地减少声学问题，这是开放式办公室的一个常见问题，或者最大限度地减少步行路径，同时也最大限度地增加与其他部门员工共享的步行路径的比例。

### 结论

这是我的第一个大型生成式设计项目，我认为其底层想法有很大的潜力。目前各个步骤所需的工作可能过于复杂。由于不遵守任何建筑或设计的规律，也使得结果很难评估。

我希望它能引起读者对未来生成性和设计的一些想法。


### References

1. Michalek, J.J., Choudhary, R., Papalambros, P.Y.: Architectural layout design optimization. Eng. Optimization (2002)
1. Merrell, Paul, Eric Schkufza, and Vladlen Koltun. "Computer generated residential building layouts." ACM Transactions on Graphics (TOG). Vol. 29. No. 6. ACM, 2010.
 1. Liu, Han, et al. "Constraint aware interior layout exploration for pre-cast concrete based buildings." The Visual Computer (2013)
 1. Nassar, Khaled. "New advances in the automated architectural space plan layout problem." Proceedings Computing in Civil and Building Engineering (2010).
 1. O'Reilly, UnaMay, and Martin Hemberg. "Integrating generative growth and evolutionary computation for form exploration." Genetic Programming and Evolvable Machines (2007)
 1. Bentley, P. J. & Kumar, S. (1999). Three Ways to Grow Designs: A Comparison of Embryogenies for an Evolutionary Design Problem. Genetic & Evolutionary Computation Conference.
 1. Hornby, Gregory S., and Jordan B. Pollack. "The advantages of generative grammatical encodings for physical design." Evolutionary Computation, 2001. Proceedings of the 2001 Congress on. Vol. 1. IEEE, 2001.
 1. Feng, Tian, et al. "Crowddriven midscale layout design." ACM Transactions on Graphics 35.4 (2016).
 1. Stanley, Kenneth O., and Risto Miikkulainen. "Evolving Neural Networks through Augmenting Topologies." Evolutionary Computation (2002).
 1. Weisstein, Eric W. "Graph Embedding." From MathWorld Wolfram Web Resource. http://mathworld.wolfram.com/GraphEmbedding.html
 1. Luo, Bin, Richard C. Wilson, and Edwin R. Hancock. "Spectral Embedding of Graphs." Pattern Recognition 36.10 (2003): 2213230. Print.
 1. Fruchterman, Thomas M. J., and Edward M. Reingold. "Graph Drawing by Forcedirected Placement." Software: Practice and Experience 21.11 (1991): 1129164. Print.


* 项目代码: https://github.com/joel-simon/evo_floorplans    
* 原文连接: https://www.joelsimon.net/evo_floorplans.html

