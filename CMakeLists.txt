cmake_minimum_required(VERSION 3.5)
project(lipm_msgs)


find_package(catkin REQUIRED COMPONENTS
std_msgs
geometry_msgs
nav_msgs
message_generation
actionlib
actionlib_msgs
)

add_message_files(
DIRECTORY msg
FILES TrajectoryPoints.msg StepTarget.msg
)
add_action_files(
  DIRECTORY action
  FILES MotionPlan.action MotionControl.action
)

generate_messages(
DEPENDENCIES
std_msgs
geometry_msgs
actionlib_msgs
nav_msgs
)

catkin_package( CATKIN_DEPENDS std_msgs nav_msgs geometry_msgs message_runtime)
