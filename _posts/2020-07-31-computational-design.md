---

layout: post
title: "漫谈算法设计(computational design)与脚本语言(grasshopper, python)"
permalink: "blog/computational-design-grasshopper-python"
categories:
  - zh
comments_id: 11

---

作者: 马海东  
时间: 2020.7.31  

自从2020.3.28日以来已经开了3期的建筑师编程课(python4rhio), 在课上被问过几次关于grasshopper与python的区别,因此这次尝试着从算法设计的方向以及方法论的角度聊聊这方面的事情.

### 什么是算法设计?

在回答这个问题之前,先聊聊什么是设计? 简单的一句话设计就是处理内容与形式之间的关系.

![data-flow](/assets/images/11-computationalDesign/py-gh-cd03.png)  

工业化生产之前,形式美学上的工艺性，如形状、颜色、材料和纹理等是设计师需要掌握的核心技能。随着第一次工业化时代的到来,设计师面临工业化标准化生产模式产生的新内容. 包豪斯(1919-1933),现代主义是对这一情况在形式上应对. 现代主义在今天依然发挥着重要的作用.   

但是随着时代的发展,第二次工业化时代数字化时代到来了, 在全球商业化,数字化时代背景下,设计师要面对的不仅仅是实体的产品,而是用户需求的解决, 这包括了: 复杂问题的提出,服务流程的设计,目标的达成等等,其工作领域甚至扩展到了与设计无关的领域. 系统控制论和计算机化的方法成为这一时期的一种新的设计形式。这不仅要求设计师有关于外形上的创新，而且在某种意义上也要求设计过程的内部的重组。[1][2][3]

![data-flow](/assets/images/11-computationalDesign/computational-design.jpg)  

在这一语境下,什么是**算法设计**?

算法设计是设计与计算机科技的融合。计算机与其他人类科技不同的地方是它会思考,中文称之为电脑.

正因为计算机会思考, 这种思考能力从根本上改变了人们构建交互界面、生产产品、提供服务、或建造建筑的方式。

传统设计师习惯于使用Sketchup、Rhino和3ds Max, Maya等绘图工具来实现他们的想法。从一个概念开始，绘图软件帮助他们从抽象的概念到具体的表现。这个过程在许多领域都被采用，从工业设计到建筑设计，其最终成果是由设计师的思维驱动而完成的。

而算法设计的设计师对如何设置生成的过程更加感兴趣. 在对这个生成过程中, 设计师通过脚本语言与计算机沟通, 用算法来驱动计算机，通过这种方式由计算机输出最终的设计成果,

犹如一个小孩可以慢慢成长成大人一样, 计算机的智力也在慢慢的成长中. 随着计算机变的越来越聪明, 算法设计将会在未来的日子里极大地改变商业、文化和社区生活。

### 编程范式(programming paradigms)

> 任何傻瓜都能写出计算机能理解的代码。优秀的程序员写的代码，人类可以理解。  
  ——马丁-福勒


当你开始编程的时候, 你期望通过计算机解决你的问题, 在这里存在三个角色: 你, 你的问题, 计算机. 
所谓编程程范式就是你与计算机一起来解决你的问题或任务的方法。  

你与计算机对话的媒介是编程语言,编程范式[5]作为方法, 它会使用一些编程语言来解决你的问题. 到目前为止世界上已经有几千种的编程语言,与自然界的语言相比,这么多的编程语言一般都大同小异,它们都需要遵守一些方法论或策略, 这些方法论被称之为范式.最主要的两大类范式为: 命令式范式与声明式范式.

那在实施层面上具体是如何做到呢?

目前主流的计算机系统的软件及应用的架构是分层的，也就是下层做一些支持的工作，暴露接口给上层调用, 这种分层的方式是相对的抽象的分层, 在构架的设计上每一层自己也可以分为很多层. 

![paradigms](/assets/images/11-computationalDesign/layer-of-software.png)

在这一架构中, 内核(kernel)是计算机操作系统最核心的部分, 软件部分的最底层, 其本质就是用“变量定义+顺序执行+分支判断+循环”所表达的逻辑过程对计算机硬件进行管理与调用。计算机应用的最上层是实现人类社会的某种功能, 或某项任务. 

笼统的讲,编写程序就是通过计算机语言及层与层之间定义的接口进行调用并解决你的问题(对算法设计来说就是生成设计成果)。调用的策略称之为范式,越接近现实问题描述与表达就越接近“声明式”（declarative）范式，越接近计算机如何执行过程就越叫做“命令式”(imperative)范式。


抽象的讲: 当接口越是在表达“要什么”，就是越声明式；越是在表达“要怎样”，就是越命令式。

大家如果去线上数据库查过数据, 就会发现这是典型的在表达要什么（数据），而不是表达怎么弄出我要的数据，所以它就很“声明式”。至于如何弄出数据就由下一层的应用或程序来完成.

简单的说，越是声明式，越简单可读,越意味着下层要做更多的东西来协助你的实现. 这也意味着越受到下一层的限制。越是命令式，意味着上层对下层有更多的操作空间,更大的自由度，可以按照自己特定的需求要求下层按照某种方式来处理。

当你运用范式的思想去编程的时候, 在构建自己的代码的时候，为了结构的清晰可读，你也一样在架构上可以把代码分层，层与层之间的接口尽量声明式。这样你的代码自然在上一层主要描述从人的角度需要什么, 下一层用计算机逻辑实现人的需要。

![paradigms](/assets/images/11-computationalDesign/types-of-paradigms.png)


在这两大范式里面又可以细分为更详细的具体场景下的范式. 

其中在后面的论述中要提到grasshopper的这种图表式编程范式叫做 **数据流编程(data-flow paradigm)**

绝大部分的编程语言是文本的形式, 通常一种语言可以实现多种范式.

就python来讲可以实现: **面向对象编程**, **过程式编程**, **函数式编程**.[4]

### 脚本语言: 设计师与计算机的对话的接口

自世界上第一台通用计算机“ENIAC”于1946年诞生以来, 软件工程师们已经为设计人员开发出大量的软件, 单单从adobe,autodesk, dassault等巨头软件公司旗下就有大量的软件. 正如上面提到的那样, 这些软件大同小异的都是为绘图而存在的. 与此同时在工业化的生产流线的各个领域同样也有其他各类专业软件. 而脚本语言可以在这些软件应用层之上再建一层用户脚本层, 通过编写脚本把软件为你开放的接口关联起来为你的设计服务.

通过脚本语言, 设计师可以生成设计, 开发出设计原型,并快速迭代. 

**这类算法设计需求脚本语言具有以下计算机语言的特性**:

* 能够在宿主软件(即脚本语言的下一层)中快速组装各种设计组件. 搭建生成设计的框架.
* 在组装过程中能够随时更改设计条件或设计流程, 快速迭代.
* 可以充分利用计算机已有的海量算法,快速判断这些算法是否可以用于设计原型中.
* 基于特定的需求, 能够自己编写算法解决问题 

以下对grasshopper与python这两种语言哪个能够更好的达到以上四点快速设计原型方面的要求进行介绍并简单比较优劣.

### Grasshoppper: 数据流范式

![data-flow](/assets/images/11-computationalDesign/dataflow.png)

grasshopper是属于数据流范式[6], 也就是声明式范式中的一种类型. 通过上图右边的图表方式进行脚本的搭建来实现上图左边的功能, 该范式关注数据的流动， 把脚本分解为一系列的数据连接。明确定义输入和输出，而它们的功能组件(如上图中的 + / *)就像黑盒子一样(使用者不需要关注脚本是如何实现这些盒子的功能, 使用者需要告诉脚本你要什么样的盒子就可以), 当一个组件的所有输入条件都成为有效的时候, 脚本就会自动运行并返回结果给你. 

**优势**:

这种脚本语言本质上是并行的(即可以多个组件同时运行,没有关联的各组构件之间不会相互影响干扰), 用户可以同时启动多组程序,进行多方案的比较与分析, 能够快速组装, 更改方便,快速迭代. 这种高效率的人机交互方式为快速的进行设计原型开发提供极大的方便.

grasshopper另外一个优势就是,声明式的范式的思维更接近人类语言的思维,上手容易,表述清晰,与python的学习曲线相比grasshopper的学习曲线更短,几个小时之后可能就可以上手了. 

**劣势(与python比较)**

可扩展性弱, 所有声明式的语言都受制于下层接口能提供的可声明的功能的多少, 当你要的东西下层接口没法提供的时候, 在这里就是你的黑盒子里面没有你要的功能的时候,你就没法继续搭建下去了. 

为了解决这个劣势, grasshopper提供了用python,c#,vbscript的扩展,通过这些语言可以编写组件(黑盒子), 用户可以自己亲手编写, 也可以通过社区下载他人已经编写好的组件.


### python:多种范式编程

Python是一种通用的脚本语言，由Guido van Rossum 于1991创建, Python的设计理念强调代码的可读性。旨在帮助程序员为**小型**和**大型**项目写出清晰的逻辑代码。

**优势**:

* Python拥有海量的第三方算法库，为各种任务的提供大量的解决工具,因此可以在设计过程中快速组装,快速修改,快速迭代.
* Python支持多种编程范式。面向对象编程和结构化编程得到了充分的支持，它局部支持了函数式编程. 能够自己为特定的任务编写特定的算法, 这是纯grasshopper数据流范式所没法做到的.
* 强大的开源社区, 几乎与python相关的任何问题你都可以快速的在社区找到答案.

从以上可以看出python在编程对下层接口的调用能力是非常强大的, 这种多范式的编程语言, 几乎只有你想不到, 没有它python做不到的能力. 


**劣势(与grasshopper比较)**

一图胜千言, 在易读性方面虽然python在语法上已经做到极简与易读,但是与grasshopper这种图表的方式比较起来还是可读性要差一点.

但是这也是相对的,当你要解决的问题稍微复杂点的时候, 用grasshopper这种声明式的编程方式去模拟命令式的编程,其组件之间的的连线会变的非常混乱.  由于问题的复杂而使得grasshopper越来越不易读  
![data-flow](/assets/images/11-computationalDesign/py-gh-cd02.png)  

反而python这种可以通过分层把复杂的问题分解为可以声明的组件与组件内部的命令执行, 这种编程思维会简化问题的复杂度,加快开发.

![data-flow](/assets/images/11-computationalDesign/py-gh-cd01.png)  



### grasshopper与python在人机交互方面的比较  


grasshopper数据流的编程范式,天生拥有并行并发优势,同时图像化的用户界面更是在交互上拥有优势,在快速更改设置,快速迭代方面显得非常明显. 

这方面基于rhino环境的python是无法与grasshopper相提并论的. 但是python本身在其他的设计软件中一般会提供交互编程环境(**REPL**), 如revit, blender等软件,通过REPL可以快速的实时的查看设计成果, 并快速修改迭代.  

对于rhino来说, 只能通过安装REPL扩展来改善交互环境.

![data-flow](/assets/images/11-computationalDesign/human-computer-interaction.jpg)  

**reference**:  

1. https://uxdesign.cc/embracing-the-power-of-computational-design-3bb18ce98ffc  
1. https://qz.com/1585165/john-maeda-on-the-importance-of-computational-design  
1. https://www.interaction-design.org/literature/topics/design-thinking  
1. https://www.geeksforgeeks.org/programming-paradigms-in-python  
1. https://en.wikipedia.org/wiki/Programming_paradigm  
1. http://www.cs.ucf.edu/~dcm/Teaching/COT4810-Spring2011/Literature/DataFlowProgrammingLanguages.pdf  
1. http://www.globalnerdy.com/2019/12/10/worth-watching-videos-on-programming-paradigms-and-object-oriented-vs-functional-programming/



### 相关文章

* [建筑师为什么要会python编程?](http://www.ikuku.cn/article/jianzhushiweishenmyhpythonbc)
* [Caad4Rhino:建筑绘图工具插件](http://www.ikuku.cn/article/caad4rhinojzhtgjcj)
* [Rhino及Bob McNeel的故事(转载)](http://www.ikuku.cn/article/rhinoandbobmcneeldegushi)
* [计算机曲线spline简史(转载)](http://www.ikuku.cn/article/jisuanjiquxianjianshi)

### 建筑师编程课推广

**[ikuku精选课 Python4Rhino 建筑师编程课 2020.8.16开始线上直播！讲师:马海东](https://item.taobao.com/item.htm?id=612510660299)**

![python tutorial](/assets/images/11-computationalDesign/pyClass.jpg)


