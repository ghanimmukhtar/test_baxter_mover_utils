cmake_minimum_required(VERSION 2.8.3)
project(test_baxter_mover_utils)

find_package(catkin REQUIRED COMPONENTS
  actionlib
  actionlib_msgs
  baxter_mover_utils
  cafer_core
  cv_bridge
  moveit_ros_planning_interface
  roscpp
  rospy
  std_msgs
  tf
)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -fPIC")

catkin_package(
)


include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_executable(baxter_moveit_utils src/baxter_moveit_utils.cpp )
target_link_libraries(baxter_moveit_utils  ${catkin_LIBRARIES})
