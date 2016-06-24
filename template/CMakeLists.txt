cmake_minimum_required(VERSION 3.0.0 FATAL_ERROR)
project(PROJECT_NAME LANGUAGES CXX C)

include(cmake/build.cmake)
include(cmake/mason.cmake)

set(CMAKE_OSX_DEPLOYMENT_TARGET 10.10)
set(CMAKE_CONFIGURATION_TYPES Debug Release)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra -Wpedantic")

set(MASON_variant_VERSION 1.1.0)

add_subdirectory(src)
