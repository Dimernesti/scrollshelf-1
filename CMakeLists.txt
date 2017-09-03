cmake_minimum_required(VERSION 3.8)
project(scrollshelf)

set(CMAKE_CXX_STANDARD 17)

find_package(Qt5 COMPONENTS Core REQUIRED)

add_subdirectory(scrollshelf-core)
add_subdirectory(scrollshelf-gui)