cmake_minimum_required(VERSION 2.8.3)
project(mobility)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  roscpp
  sensor_msgs
  std_msgs
  random_numbers
  message_generation
  shared_messages
)

catkin_package(
  CATKIN_DEPENDS geometry_msgs roscpp sensor_msgs std_msgs random_numbers message_runtime shared_messages
)



include_directories(
  include
)


add_executable(
  mobility
  src/mobility.cpp 
  src/Rover.cpp 
  src/TagObject.cpp
  src/MobilityHelper.cpp 
  src/Uniform.cpp
  src/SearchTile.cpp
  src/tag_store.cpp
  src/initialization.cpp
  src/rover_info.cpp
  src/Stoke.cpp
)

add_dependencies(mobility ${catkin_EXPORTED_TARGETS})

target_link_libraries(
  mobility
  ${catkin_LIBRARIES}
)

