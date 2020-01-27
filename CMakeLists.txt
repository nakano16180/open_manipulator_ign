cmake_minimum_required(VERSION 3.5)

project(open_manipulator_ign)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  gazebo_ros
  gazebo_ros_control
  controller_manager
  xacro
  urdf
)

find_package(catkin REQUIRED)

catkin_package(
  CATKIN_DEPENDS roscpp std_msgs gazebo_ros gazebo_ros_control controller_manager xacro urdf
)

link_directories(${GAZEBO_LIBRARY_DIRS})

include_directories(
  ${catkin_INCLUDE_DIRS}
  ${GAZEBO_INCLUDE_DIRS}
)

install(
  DIRECTORY
    launch/
  DESTINATION
    ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)

install(
  DIRECTORY
    models/
  DESTINATION
    ${CATKIN_PACKAGE_SHARE_DESTINATION}/models
)
