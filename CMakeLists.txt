cmake_minimum_required(VERSION 2.8)
set(VERSION_MAJOR 0)
set(VERSION_MINOR 1)
set(VERSION_PATCH 0)

project(libhello C)

if (NOT CMAKE_BUILD_TYPE)
    message(STATUS "No build type selected, default to Release")
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Choose the type of build, options are: Debug, Release" FORCE)
endif()

add_definitions(-std=gnu99 -Wall -Wextra -Wconversion
    -Wno-missing-field-initializers)
set(CMAKE_C_FLAGS_RELEASE "-O0 -DNDEBUG")

include_directories(${PROJECT_SOURCE_DIR}/src)

add_subdirectory(src)
