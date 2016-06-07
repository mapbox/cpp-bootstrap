add_library(PROJECT_NAME
    ${PROJECT_SOURCE_DIR}/include/PROJECT_NAME/PROJECT_NAME.hpp
    PROJECT_NAME.cpp
)

target_include_directories(PROJECT_NAME
    PUBLIC ${PROJECT_SOURCE_DIR}/include
    PRIVATE ${PROJECT_SOURCE_DIR}/src
)

target_add_mason_package(PROJECT_NAME PUBLIC variant)

create_source_groups(PROJECT_NAME)
