---
layout: post
category: CustomView
title: 安卓自定义View基础-坐标系
tags: 自定义View, 坐标系
keywords: 坐标系, 自定义View, 自定义控件, 安卓, Android, CustomView, GcsSloop
excerpt: 自定义View基础内容，主要讲述屏幕坐标系与数学坐标系等差别，以及MotionEvent中 get 和 getRaw 的区别。
redirect_from:
  - /2015/01/coordinate-system/
---

## 一.屏幕坐标系和数学坐标系的区别

由于移动设备一般定义屏幕左上角为坐标原点，向右为x轴增大方向，向下为y轴增大方向，
所以在手机屏幕上的坐标系与数学中常见的坐标系是稍微有点差别的，详情如下：

（**PS：其中的∠a 是对应的，注意y轴方向！**）

![数学坐标系](http://ww2.sinaimg.cn/large/005Xtdi2jw1f1qygzfvhoj308c0dwglr.jpg)
![安卓屏幕坐标系](http://ww1.sinaimg.cn/large/005Xtdi2jw1f1qyhbqvihj308c0dwjrh.jpg)

**实际屏幕上的默认坐标系如下：**

> PS: 假设其中棕色部分为手机屏幕

![屏幕默认坐标系示例](http://ww3.sinaimg.cn/large/005Xtdi2jw1f1qyhjy7h8j308c0dwq32.jpg)

## 二.View的坐标系

**注意：View的坐标系统是相对于父控件而言的.**

``` java
getTop();       //获取子View左上角距父View顶部的距离
getLeft();      //获取子View左上角距父View左侧的距离
getBottom();    //获取子View右下角距父View顶部的距离
getRight();     //获取子View右下角距父View左侧的距离
```

**如下图所示：**

![View坐标系](http://ww2.sinaimg.cn/large/005Xtdi2gw1f1qzqwvkkbj308c0dwgm9.jpg)

## 三.MotionEvent中 get 和 getRaw 的区别

``` java
event.getX();       //触摸点相对于其所在组件坐标系的坐标
event.getY();

event.getRawX();    //触摸点相对于屏幕默认坐标系的坐标
event.getRawY();
```

**如下图所示：**

> PS:其中相同颜色的内容是对应的，其中为了显示方便，蓝色箭头向左稍微偏移了一点.

![get雨getRaw区别](http://ww1.sinaimg.cn/large/005Xtdi2jw1f1r2bdlqhbj308c0dwwew.jpg)

## 四.核心要点

|  序号  | 要点                        |
| :--: | ------------------------- |
|  1   | 在数学中常见的坐标系与屏幕默认坐标系的差别     |
|  2   | View的坐标系是相对于父控件而言的        |
|  3   | MotionEvent中get和getRaw的区别 |

## 五.参考文章：

* [◎本系列相关文章](http://www.gcssloop.com/customview/CustomViewIndex/)
* [Android 屏幕（View）坐标系统](http://blog.csdn.net/wangjinyu501/article/details/21827341)


