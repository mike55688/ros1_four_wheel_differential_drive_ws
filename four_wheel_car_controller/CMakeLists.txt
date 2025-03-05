cmake_minimum_required(VERSION 3.0.2)
project(four_wheel_car_controller)

find_package(catkin REQUIRED COMPONENTS 
  roscpp 
  rospy 
  std_msgs 
  serial 
  tf 
  nav_msgs
)

## Declare a catkin package
catkin_package()

## Build talker and listener
include_directories(
  include 
  ${catkin_INCLUDE_DIRS}
)

# 修改目標名稱以確保唯一性
add_executable(four_wheel_car_controller_node src/car_controller.cpp)
target_link_libraries(four_wheel_car_controller_node ${catkin_LIBRARIES})

add_executable(four_wheel_car_listener_node src/car_listener.cpp)
target_link_libraries(four_wheel_car_listener_node ${catkin_LIBRARIES})

add_executable(tttt_node src/tttt.cpp)
target_link_libraries(tttt_node ${catkin_LIBRARIES})
