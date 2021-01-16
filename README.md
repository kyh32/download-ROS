# download-ROS

1.备份原来的源（随意）
sudo cp /etc/apt/sources.list /etc/apt/sources.list_backup
2.编辑源列表
sudo gedit /etc/apt/sources.list
3.换源
百度搜索 Ubuntu清华源（链接：https://mirror.tuna.tsinghua.edu.cn/help/ubuntu/）选择下载的Ubuntu版本后，复制第2~8段内容
4.删除第二步打开的文件里的全部内容，并粘贴第三步复制的内容，点右上角的保存后可以关掉
5.在终端更新
sudo apt-get update
6.添加中科大ros软件源
sudo sh -c 'echo "deb http://mirrors.ustc.edu.cn/ros/ubuntu $(lsb_release -sc) main" >/etc/apt/sources.list.d/ros-latest.list'
7.设置密钥
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key F42ED6FBAB17C654
8.更新软件列表
sudo apt-get update
9.安装ros库（本人网速正常，只用了5分多钟）
sudo apt-get install ros-melodic-desktop-full
10.初始化rosdep
先   sudo rosdep init
后   rosdep update
11.将ros环境变量写入bashrc
先   echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
后   source ~/.bashrc
12.执行 roscore 测试ros安装是否正确 
13.构建软件包依赖关系
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

