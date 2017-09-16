cmake_minimum_required(VERSION 2.8.3)
project(mrobot_bringup)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  nav_msgs
  roscpp
  rospy
  sensor_msgs
  std_msgs
  tf
)

catkin_package()
add_executable(${PROJECT_NAME}_node src/serial_node.cpp)

target_link_libraries(${PROJECT_NAME}_node
  ${catkin_LIBRARIES}
)

