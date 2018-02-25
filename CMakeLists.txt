cmake_minimum_required(VERSION 2.8.3)
project(test_baxter_mover_utils)

find_package(catkin REQUIRED COMPONENTS
  baxter_mover_utils
  cv_bridge
  moveit_ros_planning_interface
  roscpp
  rospy
  std_msgs
  tf
)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall -fPIC")

add_message_files(
        FILES
        object_position.msg
)

generate_messages(
        DEPENDENCIES
        std_msgs
        geometry_msgs
)

catkin_package(
)


include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_executable(baxter_moveit_utils src/baxter_moveit_utils.cpp )
target_link_libraries(baxter_moveit_utils  ${catkin_LIBRARIES})
