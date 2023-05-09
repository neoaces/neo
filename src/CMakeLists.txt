cmake_minimum_required(VERSION 3.26)

add_executable(neo main.cc)
target_link_libraries(neo PRIVATE neoserver)