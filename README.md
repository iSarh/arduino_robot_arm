# Controlling a Robot Arm: Joint State Publisher, Moveit, and Kinematics

In this repository, I will detail the process of controlling a robot arm using ROS (Robot Operating System), specifically focusing on three key components: Joint State Publisher, Moveit, and kinematics. These tools are essential for simulating, planning, and executing movements for robotic arms in a virtual environment.

## Forking the Repository
I began by forking the original arduino_robot_arm repository from [smart-methods] to my own GitHub account. This repository provides a foundation for controlling a robotic arm, integrating hardware control and simulation capabilities using ROS.

## Setup Environment
**Operating System and ROS Version**
- Operating System: Ubuntu 20.04
- ROS Version: ROS Noetic

## Requirements
1. **Preparing ROS**
   Create a workspace by using ```catkin_make``` http://wiki.ros.org/catkin/Tutorials/create_a_workspace
2. **Add the “arduino_robot_arm” package to “src”**
   ~~~bash
   cd ~/catkin_ws/src
   sudo apt install git
   git clone githttps://github.com/smart-methods/arduino_robot_arm
   ~~~
3. **Install all the dependencies**
   ~~~bash
   cd ~/catkin_ws
   rosdep install --from-paths src --ignore-src -r -y
   sudo apt-get install ros-noetic-moveit
   sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
   sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
   sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
   ~~~
   Compile the package
   ~~~bash catkin_make ~~~












