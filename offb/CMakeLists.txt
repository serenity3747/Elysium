cmake_minimum_required(VERSION 2.8.3)
project(offb)





find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  mavros
)

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES offb
  CATKIN_DEPENDS roscpp
)

include_directories(
    include
    ${catkin_INCLUDE_DIRS}
)


add_executable(offb_node src/offb_node.cpp)
#add_dependencies(offb_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
target_link_libraries(offb_node ${catkin_LIBRARIES})

add_executable(pose_node src/pose_node.cpp)
#add_dependencies(pose_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
target_link_libraries(pose_node ${catkin_LIBRARIES})
