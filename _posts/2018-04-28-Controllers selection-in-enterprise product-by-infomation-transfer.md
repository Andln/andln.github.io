---
layout: post
title: 从信息传递谈B端交互设计的控件选择
subtitle: Controllers selection in enterprise product by information transfer
date: 2018-04-28
categories: blog
tags: [UX,controller,toB]
description: 设计B端产品一年半的产品小节
catalog: true
type: article
---


要理解交互设计，我们先理解什么是界面。界面顾名思义，两个物体的接触面。在计算机领域，就是两个系统互相协作的边界。
它的作用就是把信息从一个系统传递到另外一个系统。但是信息的传递本身就是存在障碍的，信息会衰减，会被干扰等等。所以对于设计师而言，要明白界面设计的目标，是通过控制界面上的各个通道，更高效率低传递信息。

那什么是信息的传递？ 信息是为了减少可能性空间[1]。这就涉及知道和不知道的事情，我不知道的时候，我是无头苍蝇，我会无所适从。但如果我知道了，那我就会根据信息的内容，来执行。

比如一个海报，就是一个界面，一个海报要介绍一个校园活动，时间地点，有效的海报传递了信息，就降低了可能性空间，观众就不会像无头苍蝇一样，在一天里面去每个教室找活动。

所以一张优秀的海报设计，就是正确地传递信息，减少可能性空间，通过一些视觉手段，把活动内容，时间，地点准确地传达给受众。

同理，界面设计也是为了信息传递，只不过是双向的，尤其在B端产品的设计过程中，需要大量的信息输入和输出。在以前，没有系统的时候，传递信息的界面是各类票据。我们耳熟能详的就是出库单，入库单，销售单。

![出库单](http://www.andln.com/post_img/Outbound_order.png)

票据承载的信息是什么？就是数据呀，所以翻翻数学书，从数据统计的角度来说，数据变量其实可以分为几种类型：
- 数值型变量（Numeric）
	- 连续数值（Continuous），变量在一定范围的实数之间取任何值，比如身高，价格，温度等。
	- 离散数值（Discrete），变量在一定范围内只能取固定的数值，比如球镜，柱镜等
- 分类型变量（Categorical）
	- 二元值（Binary），比如是否默认，是否离职，真假等
	- 顺序值（Ordinal），比如几星评分，奖项，等级，学历等
	- 无序值（Nominal），比如性别，商品分类，产业类型，婚姻状态等
![变量与控件关系](http://www.andln.com/post_img/controller_variable_and_controller.png)

在对数据有一定的理解下，这时候我们就会发现，界面的控件是为数据服务的。我们耳熟能详的界面控件中，Slider是为了输入连续数据，Stepper是为了输入离散数据，Switch是为了输入二元制，Radio Button，Picker，Checkbox 是为了输入类别分类。

所以基于这样的理解，那控件就像界面上的一个一个的小通道，每个通道都是一个筛子，数据可以通过通道传输，通道也会过滤数据，整理数据。那我们如何取选择控件呢？这里就需要一个概念。叫通道容量，一个通道，在单位时间内，可以传递最大的信息量成为这一通道的通道容量。
其中容量是由三个因素决定的
- 人对通道的控制力，可以理解为人如何操作控件，这能影响人的输入速度等
- 通道的可辨识状态，可以理解为这个通道可以传递多少种信息，这能帮助筛选数据，所谓garbage in, garbage out，可辨识状态越少，信息量越少，但信息越干净，数据完整性data integrity越强。
- 通道对人的控制力，可以理解为通道如何提醒，给予人反馈，减少错误（本文不细说）


![变量如何通过界面](http://www.andln.com/post_img/controller_relation_between_variable_controller.png)
开关（Switch），只能开和关，一次点击就是一次输入，所需要花费的时间固定不变，数据很干净；

单选框（Radio），一般离散和分类数据都可以通过它来输入，但要注意的是，分类项要少，否则占用界面的空间就会太多，浏览寻找的时间也会增加。在浏览所有选项后，点击选择项目。输入的数据也很干净；

多选框（CheckBox），与单选框的区别就是可以同时点击选择多个；

输入框（Text Area），人可以任意输入信息内容，但输入所花的时间和输入的内容基本成正比，可能的干扰数据也越多。几乎所有的信息都可以通过这个控件来输入；

选择器（Picker），选择器可以单选和多选，但比他们节约了界面控件。如果选项太多的话，可以通过搜索和拆分选择的方式来降低选择项。


![宝岛眼镜的选择器](http://www.andln.com/post_img/controller_picker.png)

滑动条（Slider），我个人不是很喜欢，不过在选择某个值或某个范围时，经常会用到滑动条。所以一般不需要太精确的数值，但又想很快设置好，就可以选用。

步进器（Stepper），一般步进器会跟输入框同时使用，步进的好处是可以微调数值，特别是当步长是一个不规则数值的时候，用起来会更方便。比如度数的步长是0.25.

总的来说，之所以需要界面，我觉得就是电脑需要人辅助数据输入，所以为了让数据的输入输出效率最大化，就需要正确的选择控件。

控件的输入能力 = 控件输入信息 / 控件所占控件 * 控件输入时间



[1] 观涛, 国凡, and 控制论. 控制论与科学方法论. 科学普及出版社, 1983.

[2] Ant Design 文档 https://ant.design/components/auto-complete-cn/

[3] Cooper, Alan, Robert Reimann, and David Cronin. About face 3: the essentials of interaction design. John Wiley & Sons, 2007.

[4] 变量类型的参考
- https://stats.stackexchange.com/questions/158214/explanation-of-the-different-variable-types-in-statistics
- http://dni-institute.in/blogs/variable-type-from-analysis-perspective/
- http://www.indiana.edu/~educy520/sec5982/week_2/variable_types.pdf

[5] [滑动条设计](http://blog.jobbole.com/95198/)

