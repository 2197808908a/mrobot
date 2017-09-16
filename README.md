# mrobot ros package by ROSClub
## 环境
系统环境：<br>
ubuntu14.04 + ros-indigo-desktop<br>
ubuntu16.04 + ros-kinetic-desktop<br>
推荐组合：
NVIDIA Jetson TK1 （ubuntu14.04 + ros-indigo-desktop）
树莓派3 （ubuntu16.04 + ros-kinetic-desktop）
## 工作空间
mkdir -p mrobot_ws/src
cd ..
catkin_init_workspace
cd src
git clone https://github.com/ROSClub/mrobot.git
cd ~/mrobot_ws && catkin_make
## USB绑定
见使用手册3.4节，购买小车都会赠送详细的使用手册，及其大量资料。
## 主从机配置
⼿动配置略麻烦，新⼿不友好。
在远程主机使⽤我们提供的⼩⼯具⼀键配置即可
cd ~/mrobot_ws/src/mrobot/startup/Bin
./ToolBox
## 串口工具
主要⽤来测试⼩⻋数据是否正常，以及⼤家更改源码后验证使⽤。
cd ~/mrobot_ws/src/mrobot/startup/Bin
./ToolBox
## 基础操作
1、键盘控制实体机器人
roslaunch mrobot_bringup mrobot_core.launch
roslaunch mrobot_teleop mrobot_teleop_key.launch
2、键盘控制实体机器人并查看
roslaunch mrobot_bringup mrobot_robot.launch
roslaunch mrobot_bringup mrobot_model.launch
roslaunch mrobot_teleop mrobot_teleop_key.launch
3、SLAM
传感器为rplidar A2
roslaunch mrobot_bringup mrobot_robot.launch
roslaunch mrobot_slam mrobot_slam.launch
rosrun rviz rviz -d `rospack find mrobot_slam`/rviz/mrobot_slam.rviz
roslaunch mrobot_teleop mrobot_teleop_key.launch
4、Navigation
roslaunch mrobot_bringup mrobot_robot.launch
roslaunch mrobot_navigation mrobot_navigation.launch map_file:=/home/m1/map/
20170826.yaml
rosrun rviz rviz -d `rospack find mrobot_navigation`/rviz/mrobot_nav.rviz
5、其他
时间控制⼩⻋前进⼀⽶并返回
rosrun mrobot_bringup timed_out_and_back.py
时间控制⼩⻋前进⼀⽶并返回
rosrun mrobot_bringup odom_out_and_back.py
在地⾯⾏⾛⼀个边⻓为⼀⽶的正⽅格
rosrun mrobot_bringup nav_square.py
使⽤PS2遥控控制⼩⻋
roslaunch mrobot_teleop mrobot_teleop_joystick.launch

## 待续。。
