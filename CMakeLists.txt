# Specify minimum required CMake version
cmake_minimum_required(VERSION 3.10)

# Project name
project(PerfProject)

# Exported Build directory variable
set(BUILD_DIR ${CMAKE_BINARY_DIR}/build)

# Include features from Makefile.Features
option(ENABLE_PERF_REMOTE "Enable Perf Remote" OFF)
option(ENABLE_SHOW_CPU "Enable Show CPU" OFF)
option(ENABLE_NO_PERF "Enable No Perf" OFF)

if(ENABLE_PERF_REMOTE)
    add_definitions(-DPERF_REMOTE)
endif()

if(ENABLE_SHOW_CPU)
    add_definitions(-DPERF_SHOW_CPU)
endif()

if(ENABLE_NO_PERF)
    add_definitions(-DNO_PERF)
endif()

# Add subdirectories
add_subdirectory(src)
add_subdirectory(rdkperf)
add_subdirectory(test)
add_subdirectory(service)
