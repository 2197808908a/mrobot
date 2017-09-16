# mrobot ros package by ROSClub
## 环境
系统环境：
<p>
    ubuntu14.04 + ros-indigo-desktop<br/>
    ubuntu16.04 + ros-kinetic-desktop
</p>
<p>
    推荐组合：
</p>
<p>
    NVIDIA Jetson TK1 （ubuntu14.04 + ros-indigo-desktop）
    树莓派3 （ubuntu16.04 + ros-kinetic-desktop）
</p>
<p>
    ## 工作空间
</p>
<p>
    mkdir -p mrobot_ws/src
</p>
<p>
    cd ..
</p>
<p>
    catkin_init_workspace
</p>
<p>
    cd src
</p>
<p>
    git clone https://github.com/ROSClub/mrobot.git
</p>
<p>
    cd ~/mrobot_ws &amp;&amp; catkin_make
</p>
<p>
    ## USB绑定
</p>
<p>
    见使用手册3.4节，购买小车都会赠送详细的使用手册，及其大量资料。
</p>
<p>
    ## 主从机配置
</p>
<p>
    ⼿动配置略麻烦，新⼿不友好。
</p>
<p>
    在远程主机使⽤我们提供的⼩⼯具⼀键配置即可
</p>
<p>
    cd ~/mrobot_ws/src/mrobot/startup/Bin
</p>
<p>
    ./ToolBox
</p>
<p>
    ## 串口工具
</p>
<p>
    主要⽤来测试⼩⻋数据是否正常，以及⼤家更改源码后验证使⽤。
</p>
<p>
    cd ~/mrobot_ws/src/mrobot/startup/Bin
</p>
<p>
    ./ToolBox
</p>
<p>
    ## 基础操作
</p>
<p>
    1、键盘控制实体机器人
</p>
<p>
    roslaunch mrobot_bringup mrobot_core.launch
</p>
<p>
    roslaunch mrobot_teleop mrobot_teleop_key.launch
</p>
<p>
    2、键盘控制实体机器人并查看
</p>
<p>
    roslaunch mrobot_bringup mrobot_robot.launch
</p>
<p>
    roslaunch mrobot_bringup mrobot_model.launch
</p>
<p>
    roslaunch mrobot_teleop mrobot_teleop_key.launch
</p>
<p>
    3、SLAM
</p>
<p>
    传感器为rplidar A2
</p>
<p>
    roslaunch mrobot_bringup mrobot_robot.launch
</p>
<p>
    roslaunch mrobot_slam mrobot_slam.launch
</p>
<p>
    rosrun rviz rviz -d `rospack find mrobot_slam`/rviz/mrobot_slam.rviz
</p>
<p>
    roslaunch mrobot_teleop mrobot_teleop_key.launch
</p>
<p>
    4、Navigation
</p>
<p>
    roslaunch mrobot_bringup mrobot_robot.launch
</p>
<p>
    roslaunch mrobot_navigation mrobot_navigation.launch map_file:=/home/m1/map/
</p>
<p>
    20170826.yaml
</p>
<p>
    rosrun rviz rviz -d `rospack find mrobot_navigation`/rviz/mrobot_nav.rviz
</p>
<p>
    5、其他
</p>
<p>
    时间控制⼩⻋前进⼀⽶并返回
</p>
<p>
    rosrun mrobot_bringup timed_out_and_back.py
</p>
<p>
    时间控制⼩⻋前进⼀⽶并返回
</p>
<p>
    rosrun mrobot_bringup odom_out_and_back.py
</p>
<p>
    在地⾯⾏⾛⼀个边⻓为⼀⽶的正⽅格
</p>
<p>
    rosrun mrobot_bringup nav_square.py
</p>
<p>
    使⽤PS2遥控控制⼩⻋
</p>
<p>
    roslaunch mrobot_teleop mrobot_teleop_joystick.launch
</p>
<p>
    <br/>
</p>
<p>
    ## 待续。。
</p>
<p>
    <br/>
</p>
