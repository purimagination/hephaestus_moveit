# hephaestus_moveit
MoveIt Application for Hephaestus.

## 1. Prerequisites
* Ubuntu 20.04.
* ROS Noetic.
* [CANable](https://canable.io/) Devices.
* Install [hephaestus_msgs](https://github.com/purimagination/hephaestus_msgs).
* Install [hephaestus_hardware](https://github.com/purimagination/hephaestus_hardware).

## 2. Install this package.
```sh
cd <your_ws>/src
git clone https://github.com/0nhc/hephaestus_moveit.git
cd ..
rosdep install --from-path src --ignore-src -r -y
catkin_make
```

## 3. Manipulation
* Remember to set up your CANable devices.
```sh
sudo ip link set can0 type can bitrate 1000000
sudo ifconfig can0 up
```
Then try this MoveIt demo.</br>
```sh
# Make sure hardware is connected.
roslaunch hephaestus_moveit hephaestus.launch
```