# Task-2-Use Turtlebot3 with SLAM approach to create and save a map

Quick Start Guide to PC Setup 

Installed ROS 1 on Remote PC with the following commands:

$ sudo apt-get update

$ sudo apt-get upgrade

$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh

$ chmod 755 ./install_ros_kinetic.sh 

$ bash ./install_ros_kinetic.sh

Installed Dependent ROS 1 Packages with the following commands:

$ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy \

  ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc \
  
  ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan \
  
  ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python \
  
  ros-kinetic-rosserial-server ros-kinetic-rosserial-client \
  
  ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server \
  
  ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro \
  
  ros-kinetic-compressed-image-transport ros-kinetic-rqt* \
  
  ros-kinetic-gmapping ros-kinetic-navigation ros-kinetic-interactive-markers
  
  Install TurtleBot3 Packages with the following commands:
  
$ sudo apt-get install ros-kinetic-dynamixel-sdk

$ sudo apt-get install ros-kinetic-turtlebot3-msgs

$ sudo apt-get install ros-kinetic-turtlebot3

simulation with Gazebo simulation

Install Simulation Package with the following commands:

$ cd ~/catkin_ws/src/

$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git

$ cd ~/catkin_ws && catkin_make

Launch Simulation World with the following commands:

1-Empty World

![embty world 1](https://user-images.githubusercontent.com/85695324/123649284-4efb7980-d832-11eb-9228-8d5f87a11cd1.png)

$ export TURTLEBOT3_MODEL=burger

$ roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch

2-TurtleBot3 World

![turtle world 1](https://user-images.githubusercontent.com/85695324/123649571-879b5300-d832-11eb-81af-767b81fef42d.png)

$ export TURTLEBOT3_MODEL=waffle

$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

3-TurtleBot3 House

![house world 1](https://user-images.githubusercontent.com/85695324/123649715-a568b800-d832-11eb-8ab5-fbb86c19ad28.png)

$ export TURTLEBOT3_MODEL=waffle_pi

$ roslaunch turtlebot3_gazebo turtlebot3_house.launch

Operate TurtleBot3 with the following command:

$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

SLAM Simulation

Launch Simulation World with the following commands:

$ export TURTLEBOT3_MODEL=burger

$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

Run SLAM Node with the following command:

$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

![gmapping 2](https://user-images.githubusercontent.com/85695324/123650318-245df080-d833-11eb-86f5-cd9e5446066d.png)

Run Teleoperation Node with the following command:

$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

Save Map with the following command:

![map turtlebot3](https://user-images.githubusercontent.com/85695324/123648694-d399c800-d831-11eb-8e95-d8f1a6dae9ce.png)

$ rosrun map_server map_saver -f ~/map
