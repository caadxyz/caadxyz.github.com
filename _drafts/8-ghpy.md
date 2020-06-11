### grasshopper vs python




**我对grasshopper已经很熟悉,为什么我还要学python?**    

* 如果gh可以被称之为计算机语言的话:
*
* 从可视化的编程语言的角度来讲: gh是很好的可视化编程语言,简单易用,但是同时自由度受限制,有些功能需要第三方插件来实现.
* 从面向对象与函数式编程的角度来讲: py是可以同时是面向对象编程与函数式编程, 而gh只有函数式.


helo.... i am new to this thing.... can anyone tell me what is the difference between using visual programming and textual programming......

which is much better?



I am very far of to know much about it, but if you're considering learn to program, three questions, if you see it interesting, if you see it entertaining, and if you want to develop new tools or make innovative designs, do it. With grasshopper you work with molecules, from code you work with their atoms.


The advantages of grasshopper: simple to use, intuitive, quick to read (an algorithm), nice, robust components, many interoperability, the benefits of using graphics, the magic of making complex things quickly and easily...
The advantages of programming source code: access to other libraries, the benefits of object-oriented programming (creating your own classes, functions, libraries... with an organic hierarchy), maximum customization of functions or components, create your own tools in a deeper level, increase understanding of rhino, more creative possibilities...

Both have pros and cons, one better than another depending on what you need to do.


If you have no backroung in coding, better start with grasshopper and it will introduce you to logics; will give you faster understanding of how things are done. At a point of your life when you realize that GH is not enougn for you - go deeper to actual programming. In my opinion.


right now i am in a studio that is going to be using grasshopper... the professor says the use of the new scripting functions built into grasshopper is optional... but it is recommended that we do script

i need to know what grasshopper and scripting are so i can move on into the next phase of the project

since i know absolutely nothing about either grasshopper and and scripting. reading the online resources would have been just as helpful if they were all written in Greek.

i understand that grasshopper was made to be user friendly for people that have no knowledge of scripting...

so how does what grasshopper does without the scripting function differ from what rhinoscripting or monkey and grasshopper with scripting do?

and is there any difference between scripting with VB.NET and C# in grasshopper?



hi hans
you should have this:
http://www.grasshopper3d.com/

that's the best resource.

without scripting components in grasshopper, you cannot run recursive functions--info travels in one direction only.

monkey is just an alternative scripting editor. It is not unlike the built in editor that comes w/ rhino.

scripting isn't easy(vb/c#--these are full on programming languages). just learning grasshopper will keep you busy for a while. I myself am waiting for the implementation of python to give it a try (rhino 5 I believe will have it)--it's a more legible language

(if your instructor is able to help you--i.e. he/she actually knows how to write code-- then that may be a good opportunity to learn it)



Hans, in terms of what you can do within grasshopper, I think both languages will be able to do the same things. On the grasshopper discussion threads, it seems like I see more support for VB, mainly because the syntax of VB is pretty close to Rhinoscript. I think if you've never coded before and don't plan on going beyond grasshopper, than picking up the syntax of VB will be a bit easier. It also reads more like python to me.
If you have aspirations of moving beyond grasshopper, than c# might be better to learn. To begin with, the syntax looks pretty close to Processing (Java), Javascript, Perl, even php. I think once you've got a grasp of c# and the way it looks it will be easier to migrate to other programming languages.





