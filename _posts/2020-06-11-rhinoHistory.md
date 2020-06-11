---
layout: post
title: "Rhino及Bob McNeel的故事(转载)"
permalink: "blog/rhino&mcneel-zh"
categories:
  - tutorial
  - zh
comments_id: 5
---

2009年4月20日  
作者 deelip   
编辑整理 马海东  

![rhino](/assets/images/5-rhinoHistory/rhino.jpg)

原文链接: [ http://deelip.com/the-bob-mcneel-story ](http://deelip.com/the-bob-mcneel-story)  

我一直认为Bob McNeel是CAD软件行业中为数不多的脱颖而出的人之一。  
他决定不走大多数CAD厂商使用专有文件格式锁定客户的道路，这只是我敬佩他的原因之一。

2009年COFES展会的第二天，在亚利桑那州的餐后甜点的交流中，我有机会和他坐在一起喝着啤酒谈生意。  
我了解到很多关于他、他的公司和他对CAD软件行业的看法。  
Bob是一名专业的会计师。所以我问他，他是如何从一个会计到现在这个样子的。接下来的事情是我有史以来最有趣的一次谈话。这里有一个小小的免责声明。这不是一次采访，我没有做笔记。所以我说的一些内容完全有可能与事实不符。此外，请记住，我们当时正在喝啤酒，而我的大脑在酒精的作用下，记忆力不是很好。

不管怎样，事实证明，从前，Bob McNeel是一名执业会计师。  
一路走来，他开始为自己和别人写会计软件。软件方面的事情开始有了起色，他最终获得了不少客户。几年下来，他的一个客户向他寻求帮助，这涉及到购买和安装AutoCAD的许可证。于是Bob拿起电话，给Autodesk公司打了电话。他们告诉他，如果他注册成为经销商并订购一个经销商套件（2个AutoCAD许可证），他将获得50%的经销商折扣。因此，Bob认为他可以收支平衡，因为他可以把其中一个许可证卖给他的客户，然后还可以把另一个许可证卖给别人。所以Bob注册了一个经销商，并购买了一个经销商工具包。

Autodesk的事情是，他们不直接向最终用户销售。如果他们收到直接的询问，Autodesk会通过该地区的经销商进行销售。因此，通过自己的努力，Bob开始收到AutoCAD的询问，并开始销售AutoCAD。很快，转售AutoCAD开始成为一项相当有利可图的业务，Bob将业务范围扩大到惠普绘图仪和各种CAD用户需要的东西。

转售业务开始占用了他大量的时间和资源，以至于他慢慢地让会计软件业务消失了。Bob开始为他的AutoCAD客户增加增值服务，包括为AutoCAD编写插件和脚本。一件事情导致了另一件事情，他最终开发了一些插件，并将其进行商业销售。McNeel一度成为整个北美地区最大的AutoCAD经销商之一。

在这期间，Bob McNeel聘请了Michael Gibson，这个天才的人现在开发和销售Moment Of Inspiration (MoI)。Michael的第一个项目是为AutoCAD设计了一个工具栏插件，也就是Rhino至今为止的工具栏--当你左击鼠标和右击鼠标时，会发生一些不同的事情。

在客户提出了一些关于更多自由形式的建模工具的要求后，Bob决定为AutoCAD开发一个NURBS建模插件。这时，AutoCAD的架构提供的Windows NURBS建模器的集成支持很差，他的程序员们最终意识到，他们要遇到麻烦了。于是，Michael被委以开发一个独立的NURBS建模器的任务。他的想法是让NURBS建模发生在一个外部应用程序中，然后将模型来回传输到AutoCAD中。

Bob从Applied Geometry授权了AGLib NURBS建模内核来进行实际的NURBS建模。Bob很快就意识到AutoCAD插件的发展前景不容乐观，于是决定不再走这条路。Michael正在研究的独立建模器的代号是 "Rhinoceros"。当产品准备好后，Bob为产品选择的名字遇到了一些商标的发行的问题，他决定坚持使用Rhinoceros。Bob McNeel发布了Rhinoceros 1.0作为一个开放的测试版，直到今天，他仍在继续做。响应是惊人的。他收到了来自世界各地的错误报告和增强的请求。McNeel的程序员发现很难跟上用户的脚步。最终，在大约三年后，Rhinoceros正式发布，并瞬间成为了热门产品。

此时的McNeel还在使用AGLib建模库。当时Alias收购了Applied Geometry，于是出现了利益冲突。于是Bob开始开发自己的NURBS建模内核。

在这段时间里，Bob一直都是AutoCAD的转售商。他承认，他们的AutoCAD插件产品的利润支付了Rhinoceros的开发费用。在Autodesk收购了Alias公司后不久，AutoCAD的转售商关系就结束了，因为Alias公司的产品与Rhinoceros直接竞争。  

McNeel仍然在为AutoCAD和Revit开发插件，包括AccuRender和DOSLib。

时至今日，Bob觉得Alias Studio是Rhino的主要竞争对手之一，如果考虑到这两款产品的成本，似乎并不明显。他告诉我，"其实他们是在和我的产品竞争，而不是反过来竞争，如果你明白我的意思的话"。

于是，这就是一个执业会计师如何成为CAD软件行业中最值得尊敬和敬佩的人的故事。


### Rhino1.0的历史

[ https://wiki.mcneel.com/rhino/rhinohistory ]( https://wiki.mcneel.com/rhino/rhinohistory )  

* 1992年5月 - 与AG公司的第一次会面。Applied Geometry (AG)公司向我们寻求帮助，在AutoCAD中集成他们的AGLib，NURBs几何图形库。AG的客户包括Alias Research, Spatial, Honda和Tecnomatix。
* 1992年7月 - 经过大约三天的工作后，在AutoCAD中制作出第一个原型。
* 1992年11月 - McNeel与AG公司达成协议，为AutoCAD开发AccuModel、NURBs建模。McNeel将负责市场营销，AG将负责所有的开发工作。McNeel将根据需要提供AutoCAD的开发支持。
* 1992年11月 - Michael Gibson被聘为实习生。他带来了Sculptura，一个他在课堂上做的网格建模工具。
* 1993年3月 - Sculptura发布
* 1993年3月 - McNeel接任AccuModel开发的领导职务
* 1993年7月 - Sculptura 2的第一个原型机已准备就绪，可供NURB使用
* 1993年11月 - Sculptura 2绰号犀牛
* 1994年1月 - 新的McNeel/AG协议。McNeel向AG授权AGLib，AG提供所需的AGLib增强和维护。
* 1994年4月 - Rhino测试版在Graphic Alternative BBS上发布。这是我们第一个版本的公共测试版程序。
* 1994年5月 - Dale Lear博士受聘于AG公司。我们发现我们需要内部的几何学专家来开发客户需要的功能和可用性。
* 1994年5月 - Alias Research同意收购AG公司。Alias是AG的最大客户，他们认为他们的优势之一就是几何技术。
* 1994年5月 - 使用AccuModel完成了第一批商业产品。Ed Monk & Son Naval Architect发布了82英尺的运动渔船。
* 1994年7月 -几何学的开发工作正式开始。Alias似乎对几何图形库业务不感兴趣。
* 1994年8月 - 在确定我们无法解决AccuModel的商标问题后，Sculptura更名为Rhinoceros。
* 1994年8月 - 犀牛在SIGGRAPH展会上的私人展示
* 1994年11月 -将AG公司出售给Alias公司的交易最终完成
* 1995年3月 - McNeel为Alias提供了几何技术软件的第一部分
* 1995年6月 - Silicon Graphics公司收购了Alias
* 1995年6月 - McNeel收到AGLib的最后一次更新。
* 1997年5月 - AccuModel for AutoCAD的最后一个版本。随着Rhino产品的发展，我们决定最好是专注于Windows版本。
* 1997年9月 - 在没有任何推广工作的情况下，我们的测试版网站达到了50,000个，并且增长迅速。
* 1998年7月 - 10万个,测试版网站
* 1998年7月 - 在SIGGRAPH展会上宣布10月发布
* 1998年10月 - Rhino 1.0版发布

### 相关文章

* [建筑师为什么要会python编程?](http://www.ikuku.cn/article/jianzhushiweishenmyhpythonbc)
* [Caad4Rhino:建筑绘图工具插件](http://www.ikuku.cn/article/caad4rhinojzhtgjcj)

### 广告时间

**[ikuku精选课 Python4Rhino 建筑师编程课 2020.5.16开始线上直播！讲师:马海东](https://zhuanlan.zhihu.com/p/112421161)**

![python tutorial](/assets/images/1-caad4rhino/pyClass2.jpg)

