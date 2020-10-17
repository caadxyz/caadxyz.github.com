# 建筑师编程课(第五期)

![cover](./images/pycover7.png)

**导师简介**

* 马海东:[ikuku.cn](http://www.ikuku.cn)创始人, mahaidong@live.com [ https://github.com/caadxyz ]( https://github.com/caadxyz )
* 毕业于苏黎世联邦理工学院(ETHZ) CAAD MAS 2009-2010, 十多年的建筑设计与编程经验

**课程简介**  
* 课程为10周，主要内容是计算机辅助建筑设计(CAAD),**算法研究**与**自动生成**。
* 学生可以通过**脚本与编程语言(Python, Grasshopper)**的学习去探求新的设计方法及手段。
* 掌握与编程相关的辅助设计方法后,学生可以丰富其原有的设计能力,从而**开创新的建筑设计领域**。

**课程结构**   
1. CAAD & Scripting 简介
1. 基于Rhino的参数化插件 Grasshopper 
1. Rhino.python 脚本编程
1. 经典算法讲解

**资格要求**  
1. 学生已经掌握一些基本的rhino知识或者其他类似的3d建模软软件
1. grasshopper零基础，python零基础
1. 学习期间要求学生提交的主要课程作业有:
    * Grasshopper  参数化几何形体建模
    * Rhino.python 算法设计
    * Final Project(期终作业) 

**适合人群**: 建筑设计领域的学生与从业人员, 设计与制造相关领域的学生与从业人员

### 日程安排及学费

* 线上**腾讯课堂**
* **9月26日-11月28日**,每个周六的晚上20:00-23:00, 总学时30个课时
* 节假日可以与学生商量具体合适的时间
* 学费: 1500元
* 学员: 不超过30人

#### CAAD及脚本简介(共一周)

**第一周**

CAAD简介

1. 参数化设计与脚本编程基础
2. 通过面向对象编程范式来生成及扩展设计领域
3. 数字建造, CNC, Physical Computing: 真实世界与传感器

Scripting简介

1. Grasshopper(数据流可视化脚本编程): 建筑设计师可以将设计问题分解为一系列的深层次的关系，并将这些关系映射成相关图形和程序, 在这样的图解系统中, 这些图示与程式可以相互关联互动.
1. python: 是一种通用的易于读写的编程语言, 功能强大，可用于构建工具及生成自动化脚本.
1. Rhino.python
    * 算法及交互式脚本
    * 创建自定义的Rhino命令
    * 创建Rhino插件
    * 创建自定义的Grasshopper组件
    * 读写自定义的数据及文件
    * 与云应用交互
    * 创建与其他程序的实时关联
    * 在Rhino文件中存储用户自定义的数据信息
4. .net & RhinoCommon
    * Rhinocommon是Rhino平台的底层SDK, 面向中高级程序员. 
    * 在Python Scripts中可以使用RhinoCommon, 并访问到.NET框架及运行环境
5. Hello world & fun  
    * python help
    * 你第一个Rhino.Python脚本

#### Grasshopper101 & python 101 （共两周)

作业: 2D/3D 参数化编程

**第二周**

* Gh: 界面, Grasshopper组件
* Gh: 数据结构及流程控制
* Py: python help
* Py: 数据类型与变量,条件判断与循环
* Py: 函数定义及调用(1)
* Git & VsCode

**第三周**

* Gh: Range vs. Series vs. Interval
* Gh: 数据流匹配
* Gh: Datatree
* Py: Tuples,List,Dictionaries,Set: Points and Vectors
* Py: io & error
* Py: 面向对象简介　
* Py: 函数定义及调用(2)
* Py: 算法一:递归与分形,树


#### 点线面 （共三周)

几何形体: https://developer.rhino3d.com/guides/rhinopython/primer-101/8-geometry  
作业1：自由形体脚本建模  
作业2：2D/3D 算法编程  

**第四周**

* 矢量基础:vector,matrix,plane,xform
* 类与对象的使用及如何定义(1)

**第五周**

* 曲线类型:Spline, NURBS
* 类与对象的使用及如何定义(2)

**第六周**

* 曲面类型: Surface, Mesh
* 算法二:field & force
* 类与对象的使用及如何定义(3)

#### Rhino.python（共两周）

作业: 开发一个Rhino命令及Grasshopper组件

**第七周**

* rhinoscriptsyntax
* scriptcontext: object, selection, command
* data & json
* Eto & Event
* 算法三: 粒子系统

**第八周**

* Python脚本与Grasshopper组件交互
* 交互界面: Rhino命令行定制, Grasshopper组件定制
* Dotnet & RhinoCommon
* kangaroo2, ladybug

#### Final Project (期终作业)（共两周）

参考案例: 

* [caad4rhino](https://github.com/caadxyz/caad4rhino): 一个辅助建筑设计的工具类python库
* PolisFramework: 一个自动化生成建筑的框架

**第九周**  

* 常用第三方图片处理模块: OpenCV, PIL, System.Drawing
* 在revit API & dymamo环境中python编程
* 算法四: 元细胞自动机

**第十周** 

* FinalProject总答疑
* 项目策划/算法评估
* 文档组织/docFile
* 编程与调试/unitTest

### 教学案例

**grasshopper组件**: 数据流  
![gh_01](./images/gh_01.png)

**python基础**: patten
![pattern](./images/py_pattern.png)

**python基础**: 递归与分形  
![tree](./images/py_tree.png)
![recursion](./images/py_recursion.jpg)

**python, grasshopper**: 遍历数组,datatree
![py_01](./images/py_01.png)

**python基础**: 图片数据读取与分析
![readimage](./images/readimage.png)

**python面向对象编程**: 物理模拟    
![py_simulate0](./images/py_simulate.jpg)

**python面向对象编程**: 物理模拟    
![py_simulate1](./images/field02.png)

**python面向对象编程**: 元细胞自动机  
![py_simulate](./images/ac.jpg)

**工具库开发**: 画墙线,开门窗,标尺寸  
https://github.com/caadxyz/caad4rhino  
![wall](./images/wall.gif)
![line2wall](./images/line2wall.gif)
![opening](./images/opening.gif)
![dim](./images/dim.gif)

### 参考资料  

* [建筑师为什么要会python编程?](http://www.ikuku.cn/post/1870413)
* [漫谈算法设计(computational design)与脚本语言(grasshopper, python)](http://www.ikuku.cn/post/1876611)

### Q & A

**上课形式是怎么样的？**  
* 腾讯课堂，线上直播+录播视频。
* 报名后加入课程专属交流群，主讲老师会在群里做课后答疑。
* 课程涉及的grasshopper文件及python源码等都会提供。
* 并提供多个由导师亲自编写或相关的openscource源码库。 

**我的rhino水平零基础可以上课吗？**  
* 课程要求学员对rhino有粗略的了解,如果学员零基础可以通过自学一下资源达到对rhino的初步了解:
    * rhino level1 中文pdf教材 https://www.rhino3d.com/download/rhino/6/training-level-1
    * 官方英文教程(包括视频): https://www.rhino3d.com/tutorials  

**我是设计专业领域但不是建筑设计,可以上课吗?**

* 可以, 查看教学大纲, 你会发现课程中会有大量的点线面方面的编程知识, 以及经典算法的学习, 大纲中80%以上内容都是与设计专业息息相关,不仅仅局限于建筑设计领域.
* Final Project 鼓励大家自选题目, 老师会协助辅导. 如果没有自己的题目, 老师会建议选PolisFramework(一个自动化生成建筑的框架), 这是一个设计类通用框架,但是大部分已有构件代码是与建筑相关的.



