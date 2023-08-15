set(CXXFLAGS -Wno-attributes -Wall -g -fpermissive -std=c++1y -fPIC)
include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_SOURCE_DIR}/../src)

file(GLOB_RECURSE SRCS "*.cpp" "*.c")

add_library(rdkperf SHARED ${SRCS})

target_link_libraries(rdkperf perftool rt pthread stdc++)
