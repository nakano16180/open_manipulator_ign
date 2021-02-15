## Open Manipulator for ignition

### setup with ROS2 (eloquent)

```
$ sudo apt install ros-eloquent-xacro 
```

```
$ mkdir -p ~/catkin_ws/src && cd ~/catkin_ws/src/
$ git clone git@github.com:nakano16180/open_manipulator_ign.git
$ git clone git@github.com:ignitionrobotics/ros_ign.git

$ cd ~/ign_ws/src/open_manipulator_ign/models/openManipulator/urdf/
$ ros2 run xacro xacro --inorder -o open_manipulator.urdf open_manipulator.urdf.xacro 

$ gz sdf -p open_manipulator.urdf > open_manipulator.sdf
$ ign gazebo -r -v 3 open_manipulator.sdf 
```

### setup with ROS1

```
$ sudo apt install ros-melodic-controller-* ros-melodic-gazebo-* ros-melodic-moveit* ros-melodic-industrial-core
$ sudo apt install ros-melodic-joint-state-publisher-gui 

$ sudo apt install python-catkin-tools python-rosdep
$ source /opt/ros/melodic/setup.bash 
$ mkdir -p ~/catkin_ws/src && cd ~/catkin_ws/src/

$ git clone https://github.com/nakano16180/open_manipulator_ign.git
$ git clone https://github.com/ignitionrobotics/ros_ign.git
$ rosdep install -r -y --from-paths ros_ign --ignore-src
$ cd ~/catkin_ws/ && catkin build
```


### run

```
$ source ~/catkin_ws/devel/setup.bash 
$ cd ~/catkin_ws/src/open_manipulator_ign/models/openManipulator/
$ roslaunch open_manipulator_ign display.launch model:=open_manipulator.urdf.xacro
```

or

```
$ cd ~/catkin_ws/src/open_manipulator_ign/models/openManipulator/urdf/
$ gz sdf -p open_manipulator.urdf > open_manipulator.sdf

$ cd ~/catkin_ws/ && catkin build && source ~/catkin_ws/install/setup.bash
$ roslaunch open_manipulator_ign open_manipulator_ign.launch
```