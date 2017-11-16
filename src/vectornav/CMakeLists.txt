cmake_minimum_required(VERSION 2.8.3)
project(vectornav)

find_package(catkin REQUIRED COMPONENTS)

catkin_package(
        INCLUDE_DIRS include
)

## Start Global Marker

## End Global Marker

## Check C++11 / C++0x
include(CheckCXXCompilerFlag)
CHECK_CXX_COMPILER_FLAG("-std=c++11" COMPILER_SUPPORTS_CXX11)
CHECK_CXX_COMPILER_FLAG("-std=c++0x" COMPILER_SUPPORTS_CXX0X)
if(COMPILER_SUPPORTS_CXX11)
  set(CMAKE_CXX_FLAGS "-std=c++11")
elseif(COMPILER_SUPPORTS_CXX0X)
  set(CMAKE_CXX_FLAGS "-std=c++0x")
else()
  message(FATAL_ERROR "The compiler ${CMAKE_CXX_COMPILER} has no C++11 support. Please use a different C++ compiler.")
endif()

include_directories(include/vectornav)
add_library(vectornav
  src/vectornav/vn100.c
  src/vectornav/vncp_services.c
  src/vectornav/vndevice.c)
