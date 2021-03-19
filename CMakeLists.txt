cmake_minimum_required(VERSION 3.0.2)
project(autonomous_description)
set(CMAKE_CXX_FLAGS "-std=c++11 ${CMAKE_CXX_FLAGS}")
find_package(gazebo REQUIRED)

find_package(catkin
  REQUIRED
    gazebo_ros
)

# add_service_files(
#   FILES
# )

# generate_messages(
#   DEPENDENCIES std_msgs geometry_msgs
# )

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
  ${GAZEBO_INCLUDE_DIRS}
  ${Boost_INCLUDE_DIRS}
  ${SDFormat_INCLUDE_DIRS}
)


catkin_package(
  CATKIN_DEPENDS
    gazebo_ros
  DEPENDS
    gazebo_ros
    gazebo
    SDF
  #LIBRARIES
)

find_package(gazebo REQUIRED)

link_directories(${GAZEBO_LIBRARY_DIRS})

include_directories(${Boost_INCLUDE_DIR} ${catkin_INCLUDE_DIRS} ${GAZEBO_INCLUDE_DIRS})
include_directories(${roscpp_INCLUDE_DIRS})
include_directories(${std_msgs_INCLUDE_DIRS} ${SDFormat_INCLUDE_DIRS})


# add_library(rosrider_controller src/rosrider_controller.cpp)
# add_dependencies(rosrider_controller rosrider_description_generate_messages_cpp)
# target_link_libraries(rosrider_controller gazebo_ros_utils ${GAZEBO_LIBRARIES} ${catkin_LIBRARIES} ${Boost_LIBRARIES})
