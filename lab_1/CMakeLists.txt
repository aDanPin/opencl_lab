# Minimal version of CMake
cmake_minimum_required (VERSION 3.1)

# Define project name
project (OpenCL_Lab1)

find_package( OpenCL REQUIRED )

# Set include headers and OCL libs
set ( TO_INCLUDE
      include
      ${OpenCL_INCLUDE_DIR})

include_directories( ${TO_INCLUDE} )
link_directories(${OpenCL_LIBRARY})

#However, the file(GLOB...) allows for wildcard additions:
file(GLOB SOURCES "src/*.cpp" "*.cpp")

# Set up executable
add_executable (lab1 ${SOURCES})
target_include_directories (lab1 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(lab1 ${OpenCL_LIBRARIES})
