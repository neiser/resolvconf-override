cmake_minimum_required (VERSION 2.6)

# check for in-source build, forbid it!
if(CMAKE_BINARY_DIR STREQUAL CMAKE_SOURCE_DIR AND NOT MSVC_IDE)
  message(FATAL_ERROR "\nIn-source build attempt detected!\n"
    "Please create a new directory (e.g. build) and run `cmake ..`.\n"
    "Also don't forget to delete the created CMakeCache.txt and CMakeFiles dir"
    )
endif()

project(resolvconf-override)
add_library(resolvconf-override SHARED resolvconf-override.c)
target_link_libraries(resolvconf-override dl)
add_executable(mytest test.c)