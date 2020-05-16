# Where-Am-I

## Project Description  
Directory Structure  
```
.Where-Am-I                                    # Where Am I Project
├── catkin_ws                                  # Catkin workspace
│   ├── src
│   │   ├── my_robot                           # my_robot package        
│   │   │   ├── config                         # config folder for configuration files   
│   │   │   │   ├── base_local_planner_params.yaml
│   │   │   │   ├── costmap_common_params.yaml
│   │   │   │   ├── global_costmap_params.yaml
│   │   │   │   ├── local_costmap_params.yaml
│   │   │   ├── launch                         # launch folder for launch files   
│   │   │   │   ├── amcl.launch
│   │   │   │   ├── robot_description.launch
│   │   │   │   ├── world.launch
│   │   │   ├── maps                           # maps folder for maps
│   │   │   │   ├── map.pgm
│   │   │   │   ├── map.yaml
│   │   │   │   ├── map_rotate_90.pgm
│   │   │   ├── meshes                         # meshes folder for sensors
│   │   │   │   ├── hokuyo.dae
│   │   │   ├── config                           # rviz folder for rviz configuration 
│   │   │   │   ├── config.rviz
│   │   │   ├── urdf                           # urdf folder for xarco files
│   │   │   │   ├── my_robot.gazebo
│   │   │   │   ├── my_robot.xacro
│   │   │   ├── worlds                         # world folder for world files
│   │   │   │   ├── life.world
│   │   │   ├── CMakeLists.txt                 # compiler instructions
│   │   │   ├── package.xml                    # package info
│   │   ├── teleop_twist_keyboard              # teleop_twist_keyboard
│   │   │   ├── CHANGELOG.rst                  # change log
│   │   │   ├── CMakeLists.txt                 # compiler instructions
│   │   │   ├── README.md                      # README for documentation
│   │   │   ├── package.xml                    # package info
│   │   │   ├── teleop_twist_keyboard.py       # keyboard controller
│   │   ├── config.rviz
|   |   |   
```

# Getting Started
1. Install ROS kinetic in Ubuntu 16.04 environment:
``` bash
$ sudo apt-get update
$ sudo apt-get install ros-kinetic-desktop-full
```
2. Install ROS packages used in this project.
``` bash
$ sudo apt-get install ros-kinetic-navigation
$ sudo apt-get install ros-kinetic-map-server
$ sudo apt-get install ros-kinetic-move-base
$ sudo apt-get install ros-kinetic-amcl
```
3. Clone this github repository:
``` bash
$ git clone https://github.com/YoussefAli99/Where-Am-I.git
```
4. Build:
``` bash
$ cd Where-Am-I/catkin_ws/
$ catkin_make
```
5. Launch environment. It launches gazebo and RViz:
``` bash
$ source devel/setup.bash
$ roslaunch my_robot world.launch
```
6. Open another terminal, and launch AMCL algorithm:
``` bash
$ cd Where-Am-I/catkin_ws/
$ source devel/setup.bash
$ roslaunch my_robot amcl.launch
```
7. In RViz window, select `File` -> `Open Config File`, and open
`catkin_ws/src/config.rviz`. Map is shown around the robot in RViz window.
8. Push `2D Nav Goal` button in the toolbar of RViz, and, then click and
drag on the map to send the goal to the robot.
It will start moving and localize itself in the process.

# Visualization

![](https://github.com/YoussefAli99/Where-Am-I/blob/master/supplies/desc.gif)
