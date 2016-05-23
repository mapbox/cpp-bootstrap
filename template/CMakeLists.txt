cmake_minimum_required(VERSION 3.0.0 FATAL_ERROR)
project(PROJECT_NAME)

include_directories(${PROJECT_SOURCE_DIR}/include)

add_subdirectory(src)


option(ENABLE_TESTING "Enable testing" OFF)

if (${ENABLE_TESTING})
  enable_testing()
  add_subdirectory(test)
endif()
