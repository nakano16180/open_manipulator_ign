## Open Manipulator for ignition

### setup

```
$ sudo apt install ros-melodic-controller-* ros-melodic-gazebo-* ros-melodic-moveit* ros-melodic-industrial-core
$ sudo apt install ros-melodic-joint-state-publisher-gui 

$ sudo apt install python-catkin-tools 
$ source /opt/ros/melodic/setup.bash 
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/ && catkin build 
```

```
$ cd ~/catkin_ws/src/
$ git clone https://github.com/nakano16180/open_manipulator_ign.git
$ cd ~/catkin_ws/ && catkin build
```


### run

```
$ source ~/catkin_ws/devel/setup.bash 
$ cd ~/catkin_ws/src/open_manipulator_ign/worlds/openManipulator/
$ roslaunch open_manipulator_ign display.launch model:=open_manipulator.urdf.xacro
```

### run with ignition

```
$ sudo apt install python-rosdep
$ cd ~/catkin_ws/src/
$ git clone https://github.com/ignitionrobotics/ros_ign.git
$ rosdep install -r -y --from-paths ros_ign --ignore-src
$ cd ~/catkin_ws/ && catkin build
```

```
$ cd ~/catkin_ws/src/open_manipulator_ign/worlds/openManipulator/
$ gz sdf -p open_manipulator.urdf > open_manipulator.sdf

$ cd ~/catkin_ws/ && catkin build && source ~/catkin_ws/install/setup.bash
$ roslaunch open_manipulator_ign open_manipulator_ign.launch
```