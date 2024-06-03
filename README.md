# hephaestus_moveit
MoveIt Application for Hephaestus.

## 1. Prerequisites
* Ubuntu 20.04.
* ROS Noetic.
* [CANable](https://canable.io/) Devices.
* Install [hephaestus_description](https://github.com/purimagination/hephaestus_description).
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
* If hardware is connected:
```sh
# Terminal 1
roslaunch hephaestus_moveit hephaestus_moveit.launch

# Terminal 2
roslaunch hephaestus_moveit hephaestus_hardware.launch
```
* else:
```sh
roslaunch hephaestus_moveit demo.launch
```