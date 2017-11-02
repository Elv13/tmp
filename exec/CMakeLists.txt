project(exe)

cmake_minimum_required(VERSION 3.4)

find_package(foo REQUIRED)

add_executable(exe main.cpp)

TARGET_INCLUDE_DIRECTORIES(exe PRIVATE foo)

target_link_libraries(exe PUBLIC foo)
