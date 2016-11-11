DOL的配置过程
---------------------------
#####（一）配置过程
 首先因为上学期的课程用过Ubantu，所以这次还是继续沿用上学期的Ubantu，版本为14.04的。下面详细介绍安装配置DOL的整个过程。

1. 将压缩包systemc-2.3.1.tgz和dol-ethz.zip从主机拉入
   ubantu中。
2. 首先进入存放systemc-2.3.1.tgz和dol-ethz.zip压缩包的文件中。
3. 利用 $	mkdir dol命令新建一个dol文件夹，然后利用$	unzip dol_ethz.zip -d dol语句将压缩包dol-ethz.zip的内容提取到dol文件夹中。
4. 3的步骤或者直接解压dol-ethz.zip，然后将解压得到的文件名改为dol
5. 同理，用命令行$	tar -zxvf systemc-2.3.1.tgz或者直接解压压缩包systemc-2.3.1.tgz
6. 解压后，利用$	cd systemc-2.3.1命令进入systemc-2.3.1文件夹中，新建一个文件夹objdir
7. 利用$	cd objdir进入文件中objdir文件夹中，运行$	../configure CXX=g++ --disable-async-updates命令，根据系统的环境设置一下参数，用于编译。参数等设置成功能看待如下图片
 ![图片1](https://raw.githubusercontent.com/SYSULuxiaodan/SE2016_14353221/master/picture1.jpg)

8. 利用$	sudo make install进行编译，编译完后利用$ cd ..       $ ls命令可以看到objdir文件下的目录。编译成功可以看到objdir的目录文件如下

    ![图片2](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture2.jpg)

9. 利用 $	   pwd命令输出当前工作路径，并记录路径。如图，我的工作路径如下：

    ![图片3](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture3.jpg)

10. 进入dol文件夹，找到build_zip.xml文件，以gredit的方式打开文件，找到下面property name="systemc.inc" value="YYY/include"，property name="systemc.lib" value="YYY/lib-linux/libsystemc.a" 两句话，将YYY改成第9步骤记录的工作路径。
11. 利用$	ant -f build_zip.xml all进行编译，当看到build successful时表示编译成功。编译成功如图：

   ![图4](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture4.jpg)

12. 进入build/bin/mian路径，利用$	ant -f runexample.xml -Dnumber=1命令运行第一个例子，如果Build successful 则证明成功。

   ![图片5](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture5.jpg)


#####（二）遇到的问题及其解决方法

* 按照师兄给的ppt的步骤来，直到最后一步运行一个例子，其他的都挺顺利的，中间只有遇到一个就是利用$ ls看目录文件的，执行$ ls命令时，我退回都了主文件夹，所以输出的当前目录为如下

  ![图片6](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture6.jpg)

只是才知道自己弄错了，重新进入了objdir文件中。
*还有一个问题就是我是直接解压dol-ethz.zip，然后把解压文件放入了自己创建的dol文件中，这样导致后面编译dol的时候，一直找不到文件资源，然后后来才知道是我把整个文件放到了dol文件中，这样命令在执行$	ant -f build_zip.xml all 的时候，在dol文件目录在没有找到对应的build路径，所以才导致编译失败的。
* 一直到最后一步运行的时候，才出现了比较多的问题，忙着解决问题，忘记截图了。
>1. 首先是运行的时候提示找到ant命令，于是利用$	sudo apt-get install ant 命令安装了ant。
>2. 安装好ant工具后再次提示找不到src文件，后来找了师兄，师兄帮忙解决了，是因为没有jdk的原因，于是下载了jdk7。
>3. 安装好jdk后，再次运行，出现了中文配置的问题，于是按照师兄给的文件，在dol/build/bin/main 下 的 runexample.xml，对runexample.xml 215-217行进行了注释，最后成功运行成功。


#####（三）实验感想和体会#####
对ubantu系统还有好多好多不熟悉的地方，以后还要多了解，多问百度。
