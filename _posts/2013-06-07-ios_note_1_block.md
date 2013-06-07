---
layout: post
title: "iOS_Note_1_Block"
categories:
- iOS笔记
tags:
- iOS


---
##废话

一直想写一些关于iOS开发的东西，却又不知道写什么。
刚好最近打算抽空看些东西。就把笔记记下来放在这里吧。

---
##正文

Block写法
    Block在iOS里引入很久了，估计人人都知道了，也就懒得介绍了。
    第一次接触block应该会觉得比较诡异
    
    *一个空block*
    {% highlight objc %} 
    ^{
        //Block
    }
    {% endhighlight %}
 
    *一个名字定义为aBlock的block*
 
    {% highlight objc %}
    void(^aBlocak)()=^(){
         //do something
     };
    {% endhighlight %}

    *block格式*
    {% highlight objc %}
    return_type (^ block_name)  (parameters) = ^(parameters) {
        //do something
    } 
    {% endhighlight %}



![image](/media/image/block_1.png)
