set(CMAKE_CXX_FLAGS "-O2 -std=c++14 -Wall -Wextra")

add_library(PROJECT_NAME
    PROJECT_NAME.cpp
)

target_include_directories(PROJECT_NAME
    PUBLIC ${PROJECT_SOURCE_DIR}/include
    PRIVATE ${PROJECT_SOURCE_DIR}/src
)

target_add_mason_package(PROJECT_NAME PUBLIC variant)
