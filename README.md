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

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/新版界面.jpg" width="500" />

* 我们要做的工作其实就一点——修改NoteList部分的投影（Projection）

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/修改时间投影1.jpg" width="500" />

* 再为Projection进行两层的装配就行了：

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/修改时间投影2.jpg" width="500" />

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/修改时间投影3.jpg" width="500" />

### 二、实现在title列表顶部显示搜索框

* 首先是searchView（搜索框）的核心代码：

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/搜索框函数.jpg" width="500" />

* 然后我们来看看它的效果如何：

<img src="https://github.com/ShuWenhao/MiddleExp/blob/master/android期中截图/新版界面2.jpg" width="500" />
