cmake_minimum_required(VERSION 3.0.2)
project(cut_pliers_controller)

## 找到需要的 ROS 包
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  serial
  tf
  nav_msgs
)

## 宣告 catkin 包
catkin_package()

## 包含目錄
include_directories(
  ${catkin_INCLUDE_DIRS}
)

## 添加可執行檔案
add_executable(cut_pliers_controller src/cut_pliers_controller.cpp)
add_executable(keyboard_publisher src/keyboard.cpp) # 添加 keyboard 節點

## 連結庫文件
target_link_libraries(cut_pliers_controller ${catkin_LIBRARIES})
target_link_libraries(keyboard_publisher ${catkin_LIBRARIES}) # 連結 keyboard 節點
