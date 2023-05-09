cmake_minimum_required(VERSION 3.26)
project(neoserver)
add_library(${PROJECT_NAME} STATIC)
set_target_properties(${PROJECT_NAME} PROPERTIES LINKER_LANGUAGE CXX)

target_sources(${PROJECT_NAME}
    PRIVATE
        neos.cc
    PUBLIC
        include/neos.h
)
target_include_directories(${PROJECT_NAME} 
    # where top-level project will look for the library's public headers
    PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    
        # where external projects will look for the library's public headers
    # $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
)

if(CMAKE_COMPILER_IS_GNUCXX)
    # compile options for this target only
    # treat warnings as errors
    target_compile_options(${PROJECT_NAME} PRIVATE -Werror)
endif()