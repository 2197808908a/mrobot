# mrobot ros package by ROSClub
## 环境
系统环境：<br>
ubuntu14.04 + ros-indigo-desktop<br>
ubuntu16.04 + ros-kinetic-desktop<br>
推荐组合：<br>
NVIDIA Jetson TK1 （ubuntu14.04 + ros-indigo-desktop）<br>
树莓派3 （ubuntu16.04 + ros-kinetic-desktop）<br>
## 工作空间
mkdir -p mrobot_ws/src<br>
cd ..<br>
catkin_init_workspace<br>
cd src<br>
git clone https://github.com/ROSClub/mrobot.git<br>
cd ~/mrobot_ws && catkin_make<br>
## USB绑定
见使用手册3.4节，购买小车都会赠送详细的使用手册，及其大量资料。<br>
## 主从机配置
⼿动配置略麻烦，新⼿不友好。<br>
在远程主机使⽤我们提供的⼩⼯具⼀键配置即可<br>
cd ~/mrobot_ws/src/mrobot/startup/Bin<br>
./ToolBox<br>
## 串口工具
主要⽤来测试⼩⻋数据是否正常，以及⼤家更改源码后验证使⽤。<br>
cd ~/mrobot_ws/src/mrobot/startup/Bin<br>
./ToolBox<br>
## 基础操作
1、键盘控制实体机器人<br>
roslaunch mrobot_bringup mrobot_core.launch<br>
roslaunch mrobot_teleop mrobot_teleop_key.launch<br>
2、键盘控制实体机器人并查看<br>
roslaunch mrobot_bringup mrobot_robot.launch<br>
roslaunch mrobot_bringup mrobot_model.launch<br>
roslaunch mrobot_teleop mrobot_teleop_key.launch<br>
3、SLAM<br>
传感器为rplidar A2<br>
roslaunch mrobot_bringup mrobot_robot.launch<br>
roslaunch mrobot_slam mrobot_slam.launch<br>
rosrun rviz rviz -d `rospack find mrobot_slam`/rviz/mrobot_slam.rviz<br>
roslaunch mrobot_teleop mrobot_teleop_key.launch<br>
4、Navigation<br>
roslaunch mrobot_bringup mrobot_robot.launch<br>
roslaunch mrobot_navigation mrobot_navigation.launch map_file:=/home/m1/map/
20170826.yaml<br>
rosrun rviz rviz -d `rospack find mrobot_navigation`/rviz/mrobot_nav.rviz<br>
5、其他<br>
时间控制⼩⻋前进⼀⽶并返回<br>
rosrun mrobot_bringup timed_out_and_back.py<br>
时间控制⼩⻋前进⼀⽶并返回<br>
rosrun mrobot_bringup odom_out_and_back.py<br>
在地⾯⾏⾛⼀个边⻓为⼀⽶的正⽅格<br><br>
rosrun mrobot_bringup nav_square.py<br>
使⽤PS2遥控控制⼩⻋<br>
roslaunch mrobot_teleop mrobot_teleop_joystick.launch<br>

## 待续。。
