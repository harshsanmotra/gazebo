cmake_minimum_required(VERSION 3.0 FATAL_ERROR)

# Set the path to the directory containing GazeboConfig.cmake
set(gazebo_DIR /path/to/gazebo/share/gazebo/cmake)

find_package(gazebo REQUIRED)
include_directories(${GAZEBO_INCLUDE_DIRS})
link_directories(${GAZEBO_LIBRARY_DIRS})
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")

add_library(hello SHARED script/hello.cpp)
target_link_libraries(hello ${GAZEBO_LIBRARIES})

