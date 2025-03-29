cmake_minimum_required(VERSION 3.10)

# Project name
project(libusearch)

set(BUILD_SHARED_LIBS ON)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_BUILD_TYPE Debug)

# Source directories
set(SRC_DIR usearch)

# Gather all source files
file(GLOB_RECURSE SRC_FILES
    ${SRC_DIR}/*.cpp
)

# Include directories
include_directories(
    /usr/lib/jvm/temurin-23-jdk-amd64/include/
    /usr/lib/jvm/temurin-23-jdk-amd64/include/linux
    /home/agoncharuk/projects/usearch/include
    /home/agoncharuk/projects/usearch/fp16/include
)

add_library(usearch ${SRC_FILES})
target_link_libraries(usearch PRIVATE "/usr/lib/jvm/temurin-23-jdk-amd64/lib/server/libjvm.so")
