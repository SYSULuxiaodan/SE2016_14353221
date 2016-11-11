#lab5  安装配置ROS环境
###一）配置Ubuntu的软件源
安装配置ROS首先要求Ubautu允许接受restricted, universe 和multiverse的软件源，所以先要配置Ubuntu的软件源。
我根据下面的链接配置了Ubuntu软件源。
https://help.ubuntu.com/community/Repositories/Ubuntu。

####配置过程如下：

1）打开ubuntu下的系统，选择系统管理下的软件源，然后把5个选项都选择上.

2）然后选择“Ubuntu软件”标签下的“下载自：”下的其他选项，点击选择“选择最佳服务器”后等待。然后选择最后点击选择“选择服务器”

3）设置完成后，点击apply。

4）配置完成，显示列表如下
![picture1](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture51.png)

自此，Ubuntu软件源配置完成，下面进行添加软件源到sources.list
####添加软件源到sources.list

1) 使用下面的代码进行设置软件源，一旦添加了正确的软件源，操作系统就知道去哪里下载软件，并根据命令自动安装软件。
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

2)利用下面的代码设置key
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116

自此软件源添加到soruces.list完成，下面开始进行安装

####安装和环境设置
1）使用sudo apt-get update更新软件源为最新软件源。

2）选择desktop-full installation 进行安装


3）使用sudo rosdep init和rosdep update去初始化和下载rosdep

4）等待上面步骤完成，使用下面命令进行环境变量配置
echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
source ~/.bashrc
因为我只安装了一个版本的ROS，所以没有执行命令source /opt/ros/jade/setup.bash。如果安装的有多个版本的ROS，则需要使用source /opt/ros/jade/setup.bash让多个版本的ROS都可以生效。

5）最后安装rosinstall，使用这个命令可以让你轻松的给某个ROS下载码源等。

sudo apt‐get install python‐rosinstall

自此，ROS配置完成。下面进行一个测试，测试ROS是否配置成功

1）在命令行中输入roscore，运行结果如下
![picture2](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture52.png)

2)打开另外一个命令端，执行rosrun turtlesim turtlesim_node
执行结果如下
![picture3](https://github.com/SYSULuxiaodan/SE2016_14353221/blob/master/picture53.png)

3）打开另一终端，执行rosrun turtlesim turtle_teleop_key,执行结果，发现可以通过键盘的上下左右键来控制乌龟的移动。

哈哈，结果正常，说明ROS的配置是成功的





自此ROS的环境配置完成。

###实验感想
这次ROS环境的配置相对来说说遇到的问题没有配置DOL时候的问题遇到的多，按照链接的步骤一步一步进行，进行的比较顺利。这次实验之后才知道可以给ubuntu设置软件源。然后还有就是对于ROS的具体工作还不了解，只是通过这次的配置还有上面的测试初步了解。配置过程需要细心，不然某个环节出错了，又得重新来过，比如我这次一开始软件源没有配置好，然后导致后面连续出问题。










