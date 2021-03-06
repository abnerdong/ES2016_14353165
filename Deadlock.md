### Deadlock

### 实验目的

了解多进程中产生死锁的原因，实现死锁

### 实验步骤

进入文件Deadlock.java，进行对count的修改，这里利用了while函数，对count进行减法操作，当count减为0时，进行a线程的运行。而同时t线程的start进行了对b线程run的调度，这里就涉及到了关于线程等待序列位置的问题。

![](http://7xrn7f.com1.z0.glb.clouddn.com/16-11-1/14965052.jpg)

经过修改后，我们进行java的编译。

![](http://7xrn7f.com1.z0.glb.clouddn.com/16-11-1/80553408.jpg)

进入到java文件夹，我们可以看到生成了3个文件。

![](http://7xrn7f.com1.z0.glb.clouddn.com/16-11-1/91083183.jpg)

然后通过copy，在Windows进行Deadlock.bat的编译。

![](http://7xrn7f.com1.z0.glb.clouddn.com/16-11-1/60188792.jpg)

得到结果：

![](http://7xrn7f.com1.z0.glb.clouddn.com/16-11-1/27500771.jpg)

由于每次运行的结果停止的地方都不同，因此只放入标志性的。



### 实验感想及问题解答

 产生死锁的四个必要条件：

1.互斥条件：一个资源每次只能被一个进程使用

2.请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放

3.不剥夺条件:进程已获得的资源，在末使用完之前，不能强行剥夺

4.循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系



上述实验产生死锁的原因

在本次实验中，主要涉及到的是synchronized函数。根据定义，当一个线程访问object的一个synchronized(this)同步代码块时，其他线程对object中所有其它synchronized(this)同步代码块的访问将被阻塞。因此，在实验中，调用synchronized void methodB(A a)函数时，其实是对A线程进行了一个锁的操作，同理A也是如此。因此当我们等待序列中，A和B线程都同时对对方产生锁时，就会出现死锁的情况。



本次实验虽然只需要修改count的值，不过通过多次测试，我才终于得到了相对应的结果，一开始不知道究竟要把count改小还是改大，因此测试了很多遍，而且由于每次结果都不一样，曾经出现过全是先运行B线程才运行A线程的情况，还有就是，有时A线程先运行，有时B线程先运行，搞得很麻烦。通过慢慢修改，终于得到了，真的感动的泪流满面。这次实验主要知识就是synchronized产生死锁的原因。看了下博客，也懂了。