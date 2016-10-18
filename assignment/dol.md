### Lab2: DOL 实例分析&编程

### 实验目的

1. 修改example2，让3个square模块变成2个
2. 修改example1，使其输出3次方数

### 实验步骤

分析实验代码：square.c

![](http://i1.piimg.com/567571/00165c1ae52887d9.png)

从这里可以看出，每次进行square操作的时候，都把i进行了平方处理

因此，得到的结果是：

![](http://i1.piimg.com/567571/c4c9a8abce6aed7e.png)

根据实验要求，要使得example1输出立方数，只需要更改下代码

![](http://i1.piimg.com/567571/5406fe8bfd4face5.png)

这里把i输出的值进行了立方，得到以下结果：

![](http://i1.piimg.com/567571/c574aa15ab494d94.png)

这样example1的要求就实现了。



接下来看example2

通过观察example2.xml文件的代码，我们可以分析得到，value的值就等同于要经过多少个square的值，而每一个square就是对他们进行平方处理，因此原代码是对i进行的八次方的处理

![](http://i1.piimg.com/567571/1e20b104dba60a1f.png)

得到结果：

![](http://i1.piimg.com/567571/fe80bf70e6d2df5f.png)

因此，我们只需要把value的值改成2，就能满足实验要求

![](http://i1.piimg.com/567571/9f3580d96a33b5ec.png)

实验结果为：

![](http://i1.piimg.com/567571/fb5c25c6e0c86625.png)

最后example2也完成了。



### 实验感想

这个实验，我个人认为是比较简单的。但是也遇到了一个问题，就是一开始我用的运行代码是从PDF中复制过来的，结果进行编译的时候，就报错，说build.xml不存在，后来手打了一遍才可以。然后基本就没什么问题了，看了一下代码，发现这个生产者，square，消费者模块还是挺容易理解了。