cmake_minimum_required(VERSION 3.0.2)
project(robot_msgs)

find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  actionlib_msgs
  std_msgs
  geometry_msgs
  sensor_msgs
  message_generation
)

 add_service_files(
   FILES
   GeoGraspSrv.srv
   ldls.srv
 )

 add_action_files(
   FILES
   init.action
   global_scan.action
   zone_recognition.action
   ur_stow.action
   ur_canned.action
   ur_zimmer.action
   ur_goto_pose.action
   ur_go_down.action
  #  ur_canned.action
  #  generic.action
  perf_scan.action
  #  test1.action
  #  test2.action
  #  test3.action
   #Action2.action
 )
 
  add_message_files(
   FILES
   Result.msg
 )

 generate_messages(
   DEPENDENCIES
   actionlib_msgs
   geometry_msgs
   sensor_msgs
   std_msgs
 )

catkin_package(
  CATKIN_DEPENDS actionlib_msgs std_msgs message_runtime
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

