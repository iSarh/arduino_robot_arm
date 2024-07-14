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
   ~~~bash
   catkin_make
   ~~~
# Controlling the robot arm by joint_state_publisher

```joint_state_publisher``` provides a straightforward way to manually control and visualize the movements of each joint of a robot arm, facilitating tasks such as calibration, basic movement testing, and initial setup in robotic applications developed with ROS.

> [!IMPORTANT]
> Make sure you install ```robot-state-publisher ``` the Robot State Publisher in ROS dynamically publishes the state of a robot defined by its URDF, including joint positions and TF transforms, crucial for simulation and control within the ROS ecosystem.
> ~~~bash
> sudo apt-get install ros-noetic-robot-state-publisher
> ~~~

**Now, let's control the motors in simulation by executing the following:**

~~~bash
roslaunch robot_arm_pkg check_motors.launch
~~~
This command initiates nodes that monitor and manage the operational status of motors within the robotic arm using ROS.

![rviz](https://github.com/user-attachments/assets/6d913273-3587-4f8b-87ba-430c4b9f9557)

~~~bash
roslaunch robot_arm_pkg check_motors_gazebo.launch
~~~

This command launches nodes to simulate and monitor the behavior of motors within the robotic arm using Gazebo in ROS.

![Screenshot 2024-07-14 040610](https://github.com/user-attachments/assets/e3155b9a-3317-4687-9341-c72988961443)

~~~bash
rosrun robot_arm_pkg joint_states_to_gazebo.py
~~~

This command runs a Python script that publishes joint states to Gazebo, enabling visualization and simulation of a robotic arm's movements within the ROS ecosystem.

![Screenshot 2024-07-14 042153](https://github.com/user-attachments/assets/f3c3ec80-1b39-49b5-a772-ebc791937783)

# Controlling the robot arm by Moveit and kinematics

~~~bash
roslaunch moveit_pkg demo.launch
~~~
This command sets up a demo environment in ROS with MoveIt, enabling visualization, motion planning, and execution capabilities for a robotic system.

![image](https://github.com/user-attachments/assets/6b45d41b-4260-443e-9d75-a53cc5b51550)


~~~bash
roslaunch moveit_pkg demo.launch
~~~

This ommand initializes a MoveIt demo environment in ROS with Gazebo integration, facilitating simulated motion planning, visualization, and execution for a robotic system.

