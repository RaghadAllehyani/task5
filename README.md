# task5
Use Turtlebot3 with SLAM approach to create and save a map

In this task, we will explain how to launch Turtlebot3 on Ubuntu 20.04 and ROS Noetic:

1- Install Ros on Remote PC by pasting the following commands:
$ sudo apt update
$ sudo apt upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh 
$ chmod 755 ./install_ros_noetic.sh 
$ bash ./install_ros_noetic.sh

2- Install dependent ROS packages:
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers

3-Install TurtleBot3 via Debian Packages:
$ sudo apt install ros-noetic-dynamixel-sdk
$ sudo apt install ros-noetic-turtlebot3-msgs
$ sudo apt install ros-noetic-turtlebot3

4- install the simulation package in Gazebo:
$ cd ~/catkin_ws/src/
$ git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make

5- launch simulation world:
$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
![image2](https://user-images.githubusercontent.com/108802123/184684670-36db2eb8-c189-4d68-b8fc-dfd51eb74800.jpeg)

6- Launch Simulation by using SLAM:
$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
![image3](https://user-images.githubusercontent.com/108802123/184685382-6c31434b-589f-4336-8264-548c78cc9fb2.jpeg)

7- Run SLAM node to Gmapping SLAM methode:
$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
![image1](https://user-images.githubusercontent.com/108802123/184685927-010e8956-b845-494d-b80e-52663bd3ebb2.jpeg)


8-To run the teleoperation node from the Remote PC:
$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
![image0](https://user-images.githubusercontent.com/108802123/184686313-36450411-8e9b-4921-8429-dcca5f9b5ad8.jpeg)





