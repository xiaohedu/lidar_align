cmake_minimum_required(VERSION 2.8.3)
project(lidar_align)

add_definitions(-std=c++11 -ofast)


find_package(Curses REQUIRED)
find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)

include_directories(${CURSES_INCLUDE_DIRS})

############
# BINARIES #
############
add_executable(lidar_align 
  src/lidar_align_node.cpp
  src/sensors.cpp
  src/aligner.cpp  
  src/loader.cpp
)
target_link_libraries(lidar_align ${catkin_LIBRARIES} ${CURSES_LIBRARIES})

##########
# EXPORT #
##########
cs_install()
cs_export()
