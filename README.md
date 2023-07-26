# robot_arm
## explane of commands
This command is used to prepares the device to install ROS:
```
$sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list' 
```
then use this command to open the recv key in the device:
```
$sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```
This command used to Updated list:
```
$sudo apt-get update 
```
This command used to install the version of the ROS for the Kinetic: 
```
$sudo apt-get install ros-kinetic-desktop-full  
```
This to looking for for ROS packages available:
```
$apt-cache search ros-kinetic 
$echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
$source ~/.bashrc
```
Then i use this commands to install some packages to run ROS: 
```
$sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential 
$sudo apt install python-rosdep
$sudo rosdep init
$rosdep update
```
This commands used to install ROS virsion:
```
$sudo apt-get install ros-noetic-catkin
$mkdir -p ~/catkin_ws/src
$cd ~/catkin_ws/
```
Using this command to build my workspace in Catkin:
```
$catkin_make
```
This it takes me to the src folder:
```
$cd ~/catkin_ws/src
```
This will leads to the package of the robot arm:
```
$git clone https://github.com/smart-methods/arduino_robot_arm.git 
$cd ~/catkin_ws
```
Then run all packages that are required commends:
```
$rosdep install --from-paths src --ignore-src -r -y
$sudo apt-get install ros-kinetic-moveit
$sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui
$sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher
$sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control
```
Then open the bashrc file:
```
$sudo nano ~/.bashrc
```
This command is used to create the environment needed to run the ROS package:
```
$(source /home/wafaa/catkin_ws/devel/setup.bash)
```
To reload the bashrc file:
```
$source ~/.bashrc
```
Then finally write this command to run the ROS:
```
$roslaunch robot_arm_pkg check_motors.launch
```
## run the simulator arm
![picture](robot_arm.png)
