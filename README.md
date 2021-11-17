# Reinforcement Learning Experiments on Champ quadrupeds

This meta package currently contains ROS packages used to bring up a modified version of the champ quadruped simulation.

The main difference from the champ repositories is the focus on using effort commands instead of position commands. Additionally this repo focuses on the anymal_c robot as the target.

![effort_command](images/effort_command.gif)

## Prerequisites

 - ROS Noetic recommended


## Setup
```shell
$ mkdir ~/<your_ws>
$ cd ~/<your_ws>
$ git clone https://github.com/dean4ta/champ_rl_experiments src
$ cd ~/<your_ws>/src
$ wstool update
$ cd ~/<your_ws>
$ cd ~/<your_ws>/src/robots
$ ./install_descriptions
$ cd ~/<your_ws>
$ rosdep install --from-paths src --ignore-src -r -y
$ catkin_make
```

## Quick Start

Terminal 1 - Launch the simulation
```shell
$ source devel/setup.bash
$ roslaunch anymal_c_config gazebo.launch
```

Terminal 2 - Give an effort command to the robot
```shell
$ source devel/setup.bash
$ rostopic pub /joint_LF_KFE_effort_controller/command std_msgs/Float64 "data: 50.0"
```

## ROS Packages
see [`.rosinstall`](.rosinstall) for packages included in this meta package.
