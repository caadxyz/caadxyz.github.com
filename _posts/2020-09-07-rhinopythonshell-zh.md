---

layout: post
title: "Rhino插件:RhinoPythonShell"
permalink: "blog/rhino-python-shell-zh"
categories:
  - zh
comments_id: 14

---
* Verion alpha 0.0.2
* 版权  (c) 2019-2020 mahaidong
* 由ikuku.cn & caad.xyz 提供支持
* [English](/blog/rhino-python-shell-en)

![sample](/assets/images/14-rhinoPythonShell/sample.png)    


在rhino软件中没有python的REPL交互环境,RhinoPythonShell为Rhino提供了这种编程环境.

本插件为Rhino增加一個IronPython解釋器,可以让你通过交互的方式用Python编写Rhino3d的脚本。让您在输入代码时可以同时看到代码的执行结果。

这对于在编写Rhino.python脚本时探索 [rhinscriptsyntax](https://developer.rhino3d.com/api/RhinoScriptSyntax/), scriptcontext, [RhinoCommon](https://developer.rhino3d.com/api/RhinoCommon/html/R_Project_RhinoCommon.htm) API 是非常棒的。

注: 本插件受到RevitPythonShell启发。

## 简介

* 交互式IronPython解释器。
  * 语法高亮
  * 自动完成(句号后按CTRL+SPACE)
  * 基于[IronLab](http://code.google.com/p/ironlab/) 项目
* 包括所有Rhino内置的api (Rhinoscriptsyntax, scriptcontext)
* 完全接入.NET框架和RhinoCommon API。

## 安装

1. 适用于rhino6 和 rhino7 wip
1. 减压 `RhinoPythonShell.zip` 到rhino的pluginin文件夹
1. 在 rhino 命令中输入 `RhinoPythonShell`
1. enjoy it!

## 贡献

- Issue Tracker:  https://github.com/caadxyz/RhinoPythonShell/issues
- 源码: [https://github.com/caadxyz/RhinoPythonShell](https://github.com/caadxyz/RhinoPythonShell)

- food4rhino: [https://www.food4rhino.com/app/rhinopythonshell](https://www.food4rhino.com/app/rhinopythonshell)

## Todo

* 缓存输入的命令列表


### 相关文章

* [建筑师为什么要会python编程?](http://www.ikuku.cn/article/jianzhushiweishenmyhpythonbc)
* [Caad4Rhino:建筑绘图工具插件](http://www.ikuku.cn/article/caad4rhinojzhtgjcj)
* [Rhino及Bob McNeel的故事(转载)](http://www.ikuku.cn/article/rhinoandbobmcneeldegushi)
* [计算机曲线spline简史(转载)](http://www.ikuku.cn/article/jisuanjiquxianjianshi)
* [漫谈算法设计(computational design)与脚本语言(grasshopper, python)](http://www.ikuku.cn/post/1878164)
* [算法: 平面图自动生成(转载)](http://www.ikuku.cn/post/1878615)

### 建筑师编程课推广

**[ikuku精选课 Python4Rhino 建筑师编程课 2020.9.26开始线上直播！讲师:马海东](https://item.taobao.com/item.htm?id=612510660299)**

![python tutorial](/assets/images/13-evolvingFloorplans/pyClass.jpg)




