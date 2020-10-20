cmake_minimum_required(VERSION 2.8.3)
project(turtlesim_mark_LXIX_pkg)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS
  roscpp
  turtlesim
)

###################################
## catkin specific configuration ##
###################################
catkin_package(
)
include_directories(
  ${catkin_INCLUDE_DIRS}
)
###########
## Build ##
###########


# Declare Kill Turtles C++ executable and rename to short name (in case catkin_make is used).
add_executable(turtlesim_games_kill_turtles src/kill_turtles.cpp)
set_target_properties(turtlesim_games_kill_turtles PROPERTIES OUTPUT_NAME kill_turtles PREFIX "")
# Link to Catkin libraries
target_link_libraries(turtlesim_games_kill_turtles
  ${catkin_LIBRARIES}
)



#############
## Install ##
#############

# Mark executables for installation
install(TARGETS
turtlesim_games_kill_turtles
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
