cmake_minimum_required(VERSION 3.12)

project(vision)

# Setting the C++ standard directly
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS ON)

# Add OpenCV package
set(OpenCV_DIR ${CMAKE_CURRENT_SOURCE_DIR}/ext/opencv/build)
find_package(OpenCV REQUIRED)
if(OpenCV_FOUND)
	include_directories(${OpenCV_INCLUDE_DIRS})
endif(OpenCV_FOUND)

# Add include path
#include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

# Add the executable
add_executable(vision src/main.cpp)

# Add link libraries
target_link_libraries(vision ${OpenCV_LIBS})
