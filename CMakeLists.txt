# %Tag(FULLTEXT)%
cmake_minimum_required(VERSION 2.8.3)
project(gimbal)
add_definitions(-std=c++11)

## Find catkin and any catkin packages
find_package(catkin REQUIRED COMPONENTS roscpp rospy std_msgs genmsg message_generation geometry_msgs)
# find_package( OpenCV 2 REQUIRED)
# find_package( VISP REQUIRED)

## Declare ROS messages and services
# add_message_files(FILES Num.msg)
# add_service_files(FILES AddTwoInts.srv)
add_message_files(
  FILES
  Gimbal_log.msg
)
## Generate added messages and services
generate_messages(DEPENDENCIES std_msgs geometry_msgs)

## Declare a catkin package
catkin_package(CATKIN_DEPENDS message_runtime)

## Build talker and listener
include_directories(include ${catkin_INCLUDE_DIRS} ${OpenCV_INCLUDE_DIRS} ${VISP_INCLUDE_DIRS})


# add_executable(talker src/talker.cpp)
# target_link_libraries(talker ${catkin_LIBRARIES} ${OpenCV_LIBS})
# add_dependencies(talker beginner_tutorials_generate_messages_cpp)
#
# add_executable(listener src/listener.cpp)
# target_link_libraries(listener ${catkin_LIBRARIES})
# add_dependencies(listener beginner_tutorials_generate_messages_cpp)
#
# add_executable(tracker src/tracker.cpp)
# target_link_libraries(tracker ${catkin_LIBRARIES} ${OpenCV_LIBS} ${visp_bridge_LIBRARIES} ${VISP_LIBRARIES})

#get_cmake_property(_variableNames VARIABLES)
#foreach (_variableName ${_variableNames})
#    message(STATUS "${_variableName}=${${_variableName}}")
#endforeach()

# generate_messages(
#   DEPENDENCIES
#   std_msgs
# )

# %EndTag(FULLTEXT)%
