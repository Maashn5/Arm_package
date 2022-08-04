# Arm_package
## Make a work space 
By typing the following command in the terminal
<br/> ```$ mkdir -p ~/catkin_ws/src``` // this will make a directory called catkin_ws/src
<br/> ```$ cd ~/catkin_ws/``` // this to go to catkin_ws directory 
<br/> ```$ catkin_make ``` // this will make the work space
![alt text](picture1)
## Installing the arm package
Here is the guide for installing the arm package for ros noetic 
* first: install the arduino_robot_arm package by typing the next commands in the terminal 
<br/>```$ cd ~/catkin_ws/src``` // this to go to src directory in catkin_ws directory
<br/>```$ sudo apt install git``` //to install git
<br/>```$ git clone https://github.com/smart-methods/arduino_robot_arm``` // to install the arduino_robot_arm
![alt text](picture2)
* second: install the dependencies by typing the next commands in the terminal
<br/> ```$ cd ~/catkin_ws/``` // this to go to catkin_ws directory
<br/> ```$ rosdep install --from-paths src --ignore-src -r -y```  
<br/> ```$ sudo apt-get install ros-noetic-moveit``` // to install moveit 
<br/> ```$ sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui``` // to install joint state publisher gui 
<br/> ```$ sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher``` //to install joint state publisher gazebo
<br/> ```$ sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control``` //to install ros control
* third: compile the package
<br/> ```$ catkin_make```
* finaly : launch the package
<br/>```$ roslaunch robot_arm_pkg check_motors.launch```
<br/>```$ roslaunch robot_arm_pkg check_motors_gazebo.launch```
<br/>```$ rosrun robot_arm_pkg joint_states_to_gazebo.py```
<br/> ![alt text](picture3)
<br/> ![alt text](picture4)
* Tips
you amy face some problem & here is the solutions
<br/> When you launch the package you may face error: 
<br/> ```[check_motors.launch] is neither a launch file in package [robot_arm_pkg] nor is [robot_arm_pkg] a launch file name``` 
<br/> ![alt text](picture4)
<br/> the solution is by typing ```$ source devel/setup.bash``` //to set the environment variables
<br/> anthor error you may face when launch the command ```$ rosrun robot_arm_pkg joint_states_to_gazebo.py```
<br/> so you need to change the permission by typing the following commands 
<br/> ```$ cd catkin/src/arduino_robot_arm/robot_arm_pkg/scripts```//to go to script directory
<br/> ```$ sudo chmod +x joint_states_to_gazebo.py```

![alt text](picture5)
## Install arduino
<br/> The arduino intallation in ubuntu is different from windows, the next is the guide for arduino intallation
<br/> * first: make sure the ubuntu package are updated by typing the next command
<br/> ```$ sudo apt update```
<br/> ```$ sudo apt upgrade```
<br/> * Scond: download the arduino IDE extract 
<br/> download the arduino from the website [Arduino IDE](https://www.arduino.cc/en/software) & put it in folder called arduino
<br/> or by the typing the next commands 
<br/> ```$ mkdir arduino``` // to make folder called arduino
<br/> ```$ cd arduino/```// to go to arduino directory
<br/> ```$ wget https://downloads.arduino.cc/arduino-1.8.19-linux64.tar.xz``` // to download the arduino IDE 
<br/> * Third: extract the tar.xz file by the typing in the terminal 
<br/> ```$ tar -xvf ./arduino-1.8.19-linux64.tar.xz``` 
<br/> finaly: install the arduino IDE by typing the following commands
<br/>```$ cd arduino-1.8.19/``` //to go to arduino-1.8.19 directory
<br/>```$ sudo ./install.sh``` // installing the arduino
<br/> ![alt text](picture6)

## Install rosserial lib
Here is the guide for installing the rosserial library
<br/> which allow the arduino to communicate with ros by the serial communication
<br/> by typing the next commands 
<br/>```$ sudo apt-get install ros-noetic-rosserial-arduino```//
<br/>```$ sudo apt-get install ros-noetic-rosserial```//
<br/>```$ cd arduino/arduino-1.8.19/libraries```// to go to arduino libraries directory 
<br/>```$ rm -rf ros_lib```// remove ros_lib if it presented before
<br/>```$ rosrun rosserial_arduino make_libraries.py .```//install ros_lib
<br/> ![alt text](picture7)
