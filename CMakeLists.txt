cmake_minimum_required(VERSION 3.5)

project(open_manipulator_ign)

find_package(catkin REQUIRED)
find_package(ignition-gazebo3 3.1 QUIET REQUIRED)

catkin_package()

catkin_add_env_hooks(ign SHELLS bash
  DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/env-hooks)

install(
  DIRECTORY
    launch/
  DESTINATION
    ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)

install(
  DIRECTORY
    rviz/
  DESTINATION
    ${CATKIN_PACKAGE_SHARE_DESTINATION}/rviz
)

install(
  DIRECTORY
    models/openManipulator/
  DESTINATION
    ${CATKIN_PACKAGE_SHARE_DESTINATION}/models/openManipulator/
)