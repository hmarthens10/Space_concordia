cmake_minimum_required(VERSION 3.0.2)
project(autonomy_training)

find_package(catkin REQUIRED COMPONENTS
  rosbridge_server roscpp std_msgs genmsg
)

## Generate added messages and services with any dependencies listed here
generate_messages(
   DEPENDENCIES std_msgs )

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES autonomy_training
#  CATKIN_DEPENDS rosbridge_server
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_executable(talker src/talker.cpp)
target_link_libraries(talker ${catkin_LIBRARIES})
add_dependencies(talker autonomy_training_generate_messages_cpp)
