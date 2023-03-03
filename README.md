# map
hector地图

1,启动:

先启动雷达,在rviz添加了map话题后

2,建图:

开始启动hector建图程序:

cd 功能包(hector)下 

source ./devel/setup.bash 

roslaunch nav_demo1 map.launch

3,移动建图:

可以另开终端执行

rosrun teleop_twist_keyboard teleop_twist_keyboard.py

进行机器控制(也可以进行手持),在机器人移动过程中就会开始建图

3,保存地图:

在nav_demo包内,使用

source devel/setup.bash

roslaunch nav_demo de02_map_save.launch

进行保存地图,地图文件所在位置由launch文件决定.

也可以自己指定存储文件夹，会产生pgm和yaml文件
rosrun map_server map_saver –f ~/rplidar_ws/src/data/map_0729/mymap

读取地图数据

rosrun map_server map_server  ~/rplidar_ws/src/data/map_0729/mymap.yaml

4,全局定位:

可使用AMCL需要先加载全局地图，然后启动 rviz 显示全局定位结果

source ./devel/setup.bash roslaunch nav_demo test_amcl.launch

5,路径规划(代价地图):

source ./devel/setup.bash

roslaunch nav_demo nav05_path.launch

6,导航与SLAM建图

source ./devel/setup.bash 

roslaunch nav_demo nav07_slam_auto.launch

