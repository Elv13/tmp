cmake_minimum_required(VERSION 3.4)

find_package(bob REQUIRED) 


add_library(foo foo.cpp)
 
add_library(bar bar.cpp)

TARGET_INCLUDE_DIRECTORIES( foo PRIVATE bob)

SET_TARGET_PROPERTIES(foo PROPERTIES PUBLIC_HEADER "foo.h")

target_link_libraries(foo PUBLIC bar PRIVATE bob)
 
install(TARGETS foo bar EXPORT myexport DESTINATION lib)
install(EXPORT myexport DESTINATION cmake)
