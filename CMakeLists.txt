cmake_minimum_required(VERSION 3.15)
project(meshgrid_main)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add source files
add_executable(meshgrid_main
    src/main.cpp
    src/meshgrid.cpp
)

# Include directories
target_include_directories(meshgrid_main
    PRIVATE
    ${CMAKE_SOURCE_DIR}/src/include
)
