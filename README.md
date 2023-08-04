# Ros-installation-in-windows-
## step1 : Donwload and Install VirtualBox
Begin by downloading VirtualBox from the official website: https://www.virtualbox.org/wiki/Downloads. 

Follow the installation instructions based on your operating system.


## step2 : Donwlaod Unbntu Image 
Next, download the Ubuntu Desktop image from the official website: https://ubuntu.com/download/desktop. 

Choose the appropriate version, such as Ubuntu 20.04 LTS.

## step3 : Create a New virual machine in VirualBox
- Open VirtualBox and click on "New" to create a new virtual machine.
- Provide a name for the virtual machine (e.g., "ROS_Noetic") and select "Linux" as the Type and "Ubuntu (64-bit)" as the Version.
- Assign memory (RAM) to the virtual machine (at least 2 GB is recommended).
- Choose "Create a virtual hard disk now" and select "VDI" as the hard disk file type.
- Choose "Dynamically allocated" for the storage on physical hard disk and set the desired size (at least 20 GB).


## step4 : Configure Virtual Macine Settings 
Before starting the virtual machine, right-click on it in VirtualBox and select "Settings." In the settings, navigate to the "Storage" tab and add the Ubuntu ISO image to the virtual CD/DVD drive as the installation medium.



## step5 : Install Ubuntu in Virtal machine 
- Start the virtual machine, and it will boot from the Ubuntu ISO image.
- Follow the on-screen instructions to install Ubuntu as you would on a regular system.
- Once the installation is complete, the virtual machine will restart, and you will have a fresh Ubuntu installation.

### 5.1 Open Terminal on Ubuntu:
After Ubuntu is installed in the virtual machine, open the Terminal by clicking on the "Activities" button in the top-left corner, searching for "Terminal," and launching it.

### 5.2 Install ROS Noetic:
In the Terminal, execute the following commands to install ROS Noetic:

```
bash
sudo apt update
sudo apt install -y curl gnupg2 lsb-release
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt update
sudo apt install -y ros-noetic-desktop-full
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

### 5.3 Create a Catkin Workspace:
In the Terminal, create a catkin workspace to organize your ROS packages:

```
bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin_make
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```


## step6 : install the Robot arm package 
Finally, use the Terminal to install the Robot Arm package (replace "robot_arm_package" with the actual package name):

```
bash
sudo apt install ros-noetic-robot-arm-package
```


With these steps completed, you now have a virtual machine with Ubuntu, ROS Noetic installed, and the Robot Arm package ready to be used for your robotics projects. Ensure to refer to official ROS documentation for further information on working with ROS and the Robot Arm package.
