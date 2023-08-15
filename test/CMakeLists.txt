set(CXXFLAGS -Wno-attributes -Wall -g -fpermissive -std=c++1y -fPIC)
include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/../src ${CMAKE_CURRENT_SOURCE_DIR}/../rdkperf)

file(GLOB_RECURSE SRCS "*.cpp" "*.c")

add_executable(perftest ${SRCS})

target_link_libraries(perftest rdkperf perftool pthread stdc++)
