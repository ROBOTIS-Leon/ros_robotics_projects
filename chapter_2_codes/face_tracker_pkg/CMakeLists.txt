cmake_minimum_required(VERSION 2.8.3)
project(face_tracker_pkg)

find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport
  roscpp
  rospy
  sensor_msgs
  std_msgs
  message_generation
)

find_package(Boost REQUIRED COMPONENTS system)

## Since OpenCV error occurred, I added this here (changed in 11.27.2017)
find_package(OpenCV REQUIRED)

## Message releated stuffs should be placed before catkin_package comes in (changed in 11.27.2017)
add_message_files(
   FILES
   centroid.msg
)

generate_messages(
   DEPENDENCIES
   std_msgs
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

catkin_package(
  CATKIN_DEPENDS roscpp rospy std_msgs message_runtime 
)

add_executable(face_tracker_node src/face_tracker_node.cpp)

target_link_libraries(face_tracker_node
   ${catkin_LIBRARIES}
   ${OpenCV_LIBRARIES}
)

