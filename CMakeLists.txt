cmake_minimum_required(VERSION 3.0.2)
project(rucas_msgs)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  message_generation
  roscpp
  rospy
  std_msgs
)
add_message_files(
  DIRECTORY msg
  FILES
  robot_purpose.msg
  TaskInfo.msg
  order.msg
)
add_service_files(
  DIRECTORY srv
  FILES
  robot_current.srv
  isempty.srv
  linear_on.srv
  door_open.srv
  marker_msgs.srv
) 
generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS
  roscpp std_msgs geometry_msgs message_runtime
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)
