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