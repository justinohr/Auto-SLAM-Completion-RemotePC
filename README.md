How to setup your Remote PC
===========================
Preface
-------
* The guideline given here is based on official ROBOTIS website: http://emanual.robotis.com/docs/en/platform/turtlebot3/pc_setup/#install-ubuntu-on-remote-pc
* However, the guideline uploaded on official website can make beginners confusing and this README file was written hopefully to help them.
* Especially, number three and four item will greatly help them since it suggests quite different and detailed guideline compared to the one on the official website.
1. Required Operating System
----------------------------
Ubuntu 16.04 is recommended.

2. Installing ROS on Remote PC
------------------------------
* Following scripts will automatically install ROS Kinetic Kame on your PC.
* $ sudo apt-get update
* $ sudo apt-get upgrade
* $ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh && chmod 755 ./install_ros_kinetic.sh && bash ./install_ros_kinetic.sh
3. Installing dependent ROS packages
------------------------------------
* The following commands will install dependent ROS packages on your PC.
* $ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python ros-kinetic-rosserial-server ros-kinetic-rosserial-client ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro ros-kinetic-compressed-image-transport ros-kinetic-rqt-image-view ros-kinetic-gmapping ros-kinetic-navigation
* $ cd ~/catkin_ws/src
* git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
* git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
* git clone https://github.com/ROOBITS-GIT/turtlebot3_simulations.git
* cd ~/catkin_ws && catkin_make
4. Configuring network
----------------------
* First of all, you need to figure out your own IP.
* You may check your IP using ifconfig command on your terminal.
* ifconfig will print out various information.
* Your IP will be printed next to "inet addr".
* If you are on virtual machine, you should not share network with your host. Instead the virtual machine should have its own network. You can change this configuration on your virtual machine software.
* You can change your network configuration by editing ".bashrc" file on your home directory using any editor. (The example here will use vim editor)
* $ vim ~/.bashrc
* Set ROS_HOSTNAME to your own IP.
* e.g.) export ROS_HOSTNAME=192.168.1.15
* Set ROS_MASTER_URI to http://${your own IP}:11311
* e.g.) export ROS_MASTER_URI=http://192.168.1.15:11311
