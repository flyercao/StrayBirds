---
layout: post
title: 深入理解Java内存模型
category: Java内存模型
comments: true
---
### 博客模板

深入理解Java内存模型（四）——volatile
volatile的特性

当我们声明共享变量为volatile后，对这个变量的读/写将会很特别。理解volatile特性的一个好方法是：把对volatile变量的单个读/写，看成是使用同一个监视器锁对这些单个读/写操作做了同步。下面我们通过具体的示例来说明，请看下面的示例代码：
```
class VolatileFeaturesExample {
    volatile long vl = 0L;  //使用volatile声明64位的long型变量

    public void set(long l) {
        vl = l;   //单个volatile变量的写
    }

    public void getAndIncrement () {
        vl++;    //复合（多个）volatile变量的读/写
    }


    public long get() {
        return vl;   //单个volatile变量的读
    }
```

--------
**参考文档：**


> [Java并发编程：volatile关键字解析](http://www.cnblogs.com/dolphin0520/p/3920373.html)

>[Java 中的双重检查(Double-Check)](http://blog.csdn.net/dl88250/article/details/5439024)

>[主题：单例模式与双重检测](http://www.iteye.com/topic/652440)

>[volatile的适用场景](http://www.blogjava.net/syniii/archive/2010/11/18/338382.html)

>[《Java编程思想》](http://baike.baidu.com/link?url=bdZcSPk1qEwscbiBiTxNzNp3o7r_GsLnr3PxkMbjwXJ7-EIccwr5TTcbN_dp4eY0H3P1qglggJhqqNHizvTSSq)

>[《深入理解Java虚拟机》](http://baike.baidu.com/view/6164161.htm)