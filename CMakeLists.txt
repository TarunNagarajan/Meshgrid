cmake_minimum_required(VERSION 3.15)
project(Meshgrid LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(GNUInstallDirs)

add_subdirectory(src)
add_subdirectory(tests)
add_subdirectory(examples)
