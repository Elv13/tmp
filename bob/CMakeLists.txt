cmake_minimum_required(VERSION 3.4)

file(WRITE bob.cpp)

add_library(bob bob.cpp)

SET_TARGET_PROPERTIES(bob PROPERTIES PUBLIC_HEADER "bob.h")

install(TARGETS bob EXPORT bobexport DESTINATION lib)
install(EXPORT bobexport DESTINATION cmake)
