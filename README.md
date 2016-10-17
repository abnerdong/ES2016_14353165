## DOL

### Description

The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allowsto specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.And in this course we will use ant  to build java project.

### How  to install

1.配置实验环境，在这里我们首先安装一个vmware tool，实现电脑跟虚拟机更好的联动。

$	sudo apt-get upd

![](http://i1.piimg.com/567571/0ade17a0265a691c.png)

$  sudo apt-get install ant

![QQ截图20161010085417](QQ截图20161010085417.png)

$   sudo apt-get install openjdk-7-jdk

![](http://i1.piimg.com/567571/b695492022554cdb.png)

$  sudo apt-get install unzip

![](http://i1.piimg.com/567571/d3e561e9c88479bb.png)

2.根据实验步骤，开始接下来的操作

$  mkdir dol

新建了一个名叫dol的文件夹

![](http://i1.piimg.com/567571/e177617a641c5073.png)

$  unzip dol_ethz.zip -d dol

$	tar -zxvf systemc-2.3.1.tgz

然后将dolethz.zip和systemc解压到 dol文件夹中

![](http://i1.piimg.com/567571/e20134776a063382.png)

$  cd systemc-2.3.1

进入systemc文件夹

$  mkdir objdir

新建一个名叫objdir的文件夹

$  cd objdir

进入objdir文件夹

![](http://p1.bpimg.com/567571/e2bd1ae82e41cfd0.png)

$	../configure CXX=g++ --disable-async-updates

运行configure，进行环境参数配置

![](http://i1.piimg.com/567571/74ddcc407348b02a.png)

$	sudo make install

进行make的安装

![](http://p1.bpimg.com/567571/13f859c98b66ec36.png)

$ cd  ..

$ ls

返回上一级文件

$  pwd

获得当前文件路径

![](http://p1.bpimg.com/567571/3c5334aa7288be1f.png)

$  cd ../dol

进入上一级的dol文件夹

根据实验要求，更改build_zip.xml文件中value的本地路径

![](http://p1.bpimg.com/567571/210dfd8d5ba9c5d3.png)

$	ant -f build_zip.xml all

编译代码，看是否创建成功

![](http://p1.bpimg.com/567571/4913c12f7154d77d.png)

$	cd build/bin/main

进入该路径，测试样例是否成功

$	ant -f runexample.xml -Dnumber=1

![](http://p1.bqimg.com/567571/f760f754fe1e88fd.png)

到这一步，实验就算成功完成了。



### Experimental experience

当前实验基本还是比较简单的，基本按照ppt上的操作步骤来完成，其中出现过一些低级错误，例如忘记前面四条环境配置的代码之类的。然后就是我用64位的镜像来完成的时候，不知道为什么，ant -f build_zip.xml all已经编译成功了，不过在最后编译样例1的时候出现了错误。搞得我重装了几次ubuntu，后来还是一样的问题，我确认了步骤是没有问题的。后来实在不行就用了32位的系统，一次就完成了。如果不是64位系统把我坑了，这个实验还是很简单的。最后针对一下这个markdown的编译，第一次使用，排版什么的弄得不是很好，以后会多点了解这个语法，争取弄个更完美的报告。
