cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)
include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/andrewja/hunter/archive/v0.19.137.1.tar.gz"
    SHA1 "fd39a77be768f8b552da09337de9641bf3119508"
)
project(demo)

hunter_add_package(print)
find_package(print)

add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/sources/demo.cpp)
target_link_libraries(demo print)

install(TARGETS demo RUNTIME DESTINATION bin)
