cmake_minimum_required(VERSION 3.26)
project(neo)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_subdirectory(neoserver)
add_subdirectory(src)