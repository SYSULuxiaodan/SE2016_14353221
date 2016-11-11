#lab3 DOL实例分析&编程#
_______________________
####任务一
      ————修改example2的代码，使其3个square模块变成两个模块
1）未修改代码，直接运行example2的运行结果如下：[picture1](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture31.png)
可以看到输出值是以三次方的形式出现的。
根据代码如下:[picture2](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture32.png)
在上面的代码中，代码通过定义了3个square模块，通过迭代生成了连接connection。通过<variable value="3" name="N"/>定义了3个square模块，其中N值表示square的模块数量，整个过程generatort通过N个square模块与consumer进行连接。而square的模块通过N值来进行迭代，当还未到N数量的时候，它的输入端口还是设定为C2,即它连接的端口还是下一个square模块，当square模块达到N值时，它连接的端口是consumer的端口。所以我改变定义中的N的values值，改为2，这样就使3个square模块变为2个square模块。一个模块是平方化，两个模块是2的四次方。运行完，结果如下：[picture3](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture33.png)
example2.dot图如下：[picture4](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture34.png)



####任务二
    ————修改example1的代码，使其输出3次方数
1）未修改代码，直接运行example1的运行结果如下：[picture5](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture35.png)
可以看到其输出结果是以2次方的形式出现的。
根据代码如下：[picture6](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture36.png)
代码通过square.c的代码将读入输入端信号i，将其平方后写到输出端，这样结果以平方的结果出现。修改代码i=ixi为i=ixixi的形式。将其三次方后再写到输出端，这样就运行结果以三次方的形式出现，运行结果如下：[picture7](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture37.png)
example1.dot图如下：[picture8](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture38.png)

####实验感想
这次的实验主要是了解各个进程之间的功能定义，以及模块之间的架构连接方式。通过PPT上的代码讲解以及TA上课的讲解，对这个过程有了个大致的了解。看了几遍的代码，逐渐了解了对进程的定义和通道的定义，以及各个模块是如何通过通道连接起来的，通道又是怎样将模块间的端口连接起来的有了个大致的了解。不过对于DOL具体是干嘛的，感觉还是晕晕的。看来有时间还是有必要琢磨一下。

