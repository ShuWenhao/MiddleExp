# NotePad 两大基本功能的实现

* 姓名: 舒文豪</br>

* 学号: 116052017131</br>

* 班级: 软工3班 (大数据方向)</br>

## 实验环境

* Windows10、Android Studio3.5

* AS采用安卓10

## 实验内容

### 下面先来看看它原来的样子

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/原版界面.jpg" width="500" />

### 一、实现在title底部的时间显示

* 这是新版界面，每个笔记的最近修改时间显示在了它标题的下方

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/新版界面1.jpg" width="500" />

* 我们要做的工作其实就一点————修改NoteList部分的投影（Projection）

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/修改时间投影1.jpg" width="500" />

* 再为Projection进行两层的装配就行了：

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/修改时间投影2.jpg" width="500" />

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/修改时间投影3.jpg" width="500" />

### 二、实现在title列表顶部显示搜索框

* 首先是searchView（搜索框）的核心代码：

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/搜索框函数.jpg" width="500" />

* 上述代码的思想其实很简单，目的就是实时监听搜索输入框，由输入框中的内容去做一个判断来决定输出哪些符合条件的title
  也就相当于为我们的标题列表的显示增加了一个触发器（原来的触发器是基于增删改操作的，并且显示时按时间排列，修改时间越新的
  标题就显示在越上方）
  
* 这里介绍下该方法的逻辑：首先是传入搜索框中的内容's',然后定义了一个筛选变量selection，内容采用了模糊匹配的方式（GLOB*s*）
  s分两种情况，1、s为空：则按我们上面修改投影部分展示的代码中的cursor一样，不做筛选显示所有标题。2、s非空：这里我们注意到
  cursor形参中的selection项不为了null了，这里我们传入了前面定义的实参selection，说明不再默认显示所有，而是加入了一个筛选条件。
  最后把判断结果中产生的newCursor装配到adapter.swapCursor()中进行动态显示。

* 最后我们来看看它的效果如何：

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/新版界面2.jpg" width="500" />
