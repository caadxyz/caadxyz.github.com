---
layout: post
title: "Caad4Rhino:建筑绘图工具插件"
permalink: "blog/caad4rhino-zh"
categories:
  - tools
  - zh
comments_id: 2
---


* verion 0.0.1  
* 版权 (c) 2019-2020 马海东
* 由ikuku.cn & caad.xyz 提供支持
* [English](/blog/caad4rhino-en)

![caad4rhino](/assets/images/1-caad4rhino/caad4rhino-w.png)

### 简介

Caad4Rhino 是一个由python语言开发的在[rhino三维软件](https://www.rhino3d.com)中用于计算机辅助建筑设计的2D绘图工具包.

### 目前有哪些绘图功能?

* 墙线
    * 画墙线: 居中,左,右
    * 单线变墙
    * 修剪相交的墙线: 包括L,X,T三种情况
* 门窗
    * 开窗
    * 开各种方向的门
* 尺寸
    * 拆分尺寸线
    * 合并尺寸线

### 为什么要开发这个插件?

**问**: 在建筑绘图类工具里面,已经存在大量的插件工具尤其是在Autocad软件里面,为什么还要开发一个?  
**答**: 这些工具存在一个不足的地方就是他们大部分是闭源的, 这意味着你没法拿到源代码,你没法对某一个功进行改进与更新. 这些到最后都会限制你的设计与创作.

作为本身自己就是一个建筑师同时又是一个计算机开发人员,我一直以来都期望可以做一个这样都开源类代码库,在这个库所提供的最基本的工具础上,建筑开发社区可以一起共同发展这个库,使之成一个比较完整的建筑师绘图工具库.

关于从哪个软件平台入手的方面,基于现在的建筑师正在使用的软件中,即有建模部分又有2D绘图功能的是Rhino,所以就这么自然而然的开始了在rhino中开发这个工具类项目.

优势:任何人都可以在LGPL3.0的许可证下自由的下载源代码,并推进工具库的开发.


### 为什么选python脚本语言?

[Python](https://www.python.org)是一种易于读写的语言。   
Python跨平台,这意味着这个插件可以在Windows和Mac版本的Rhino中使用。   
由于Python也可以在Grasshopper组件中运行。 因此将来Caad4Rhino扩张到Grasshopper到时候,依然可以使用.

但更重要的是：Python在Rhino之外也非常流行！   
因此这个工具库的许多模块也可以应用于许多其他领域。  

另外一个考虑就是基于社区的考虑,期望工具库可以早发布, 常发布.  
通过简单的python可以把用户变成代码贡献者, 把代码贡献者变成项目维护者。   

同时也通过这个项目向建筑师展示python编程脚本的魅力.  
期望这个Caad4Rhino成为建筑们熟悉编程语言的一个入口。   

### 将来有什么目标?

* 参照autocad建筑工具类插件，继续增加与完善已有的2D绘图功能.

### 如何下载及安装?

* 下载地址: [ https://www.food4rhino.com/app/caad4rhino ](https://www.food4rhino.com/app/caad4rhino)  
* 创建以下文件夹   
**mac**:   
`~/Library/Application Support/McNeel/Rhinoceros/6.0/Plug-ins/PythonPlugIns/caad4rhino{417c9034-2152-48dc-b487-29b584c473a5}`  
**win**:   
`%APPDATA%\McNeel\Rhinoceros\6.0\Plug-ins\PythonPlugIns/caad4rhino{417c9034-2152-48dc-b487-29b584c473a5}`
* 拷贝 `dev` 文件夹到 `caad4rhino{417c9034-2152-48dc-b487-29b584c473a5}`
* 打开Rhino软件, 在命令行下输入`caad` 会打开帮助页.
* 在 `dev/alias.txt` 文件中你可以找到所有的命令,你也可以把这些快捷键导入到Rhino的快捷键环境中.  

>Note: Sometimes, Rhino requires that Python be loaded before it can see the new command for the first time in a session - running EditPythonScript, or any other python script should allow the command to work. 

### 如何使用?

![wall](/assets/images/1-caad4rhino/wall.gif)
![line2wall](/assets/images/1-caad4rhino/line2wall.gif)
![opening](/assets/images/1-caad4rhino/opening.gif)
![dim](/assets/images/1-caad4rhino/dim.gif)
![dimscale](/assets/images/1-caad4rhino/dimscale.gif)
![frame](/assets/images/1-caad4rhino/frame.gif)

### 许可证(LGPL-3.0)

You can redistribute it and/or modify it under the terms of the GNU Lesser General Public License version 3 as published by the Free Software Foundation.

### 评价摘选

>>Great Plug-in! Thank you so much! You've saved so so so so much time for me by creating such a GREATE TOOL!  
---AzimArch on Mon, 09/03/2020 - 19:37  

>>Very useful   
thanks  
Keep trying to develope it  
---persimoon on Fri, 06/03/2020 - 10:09

### 如何参与？

如果你有问题或想参与到caad4rhino的开发中， 你可以通过 [google mailing list](https://groups.google.com/d/forum/rhino4caad) 与作者联系. 你也可以通过[ http://www.ikuku.cn/user/1510 ]( http://www.ikuku.cn/user/1510 ) 联系到作者.


### 广告时间

![python tutorial](/assets/images/1-caad4rhino/pyClass.jpg)

[**ikuku精选课 Python4Rhino 建筑师编程课 2020.3.28开始线上直播！讲师:马海东**](http://www.ikuku.cn/activity/jianzhushibianchengke)
