set(CXXFLAGS -Wno-attributes -Wall -g -fpermissive -std=c++1y -fPIC)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

file(GLOB_RECURSE SRCS "*.cpp" "*.c")

add_library(perftool SHARED ${SRCS})

target_link_libraries(perftool rt pthread stdc++)
