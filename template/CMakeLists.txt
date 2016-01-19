cmake_minimum_required(VERSION 3.0.2 FATAL_ERROR)
project(PROJECT_NAME VERSION 0.0.1 LANGUAGES CXX)

include_directories(${PROJECT_SOURCE_DIR}/include)

if(${CMAKE_SYSTEM_NAME} MATCHES "Linux")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra -pedantic -Wold-style-cast -Wuninitialized -Wunreachable-code -Wstrict-overflow=3 -D_FORTIFY_SOURCE=2 -ffunction-sections -fdata-sections")

  set(LINKER_FLAGS "-Wl,-O1 -Wl,--hash-style=gnu -Wl,--sort-common -Wl,--gc-sections")
  set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} ${LINKER_FLAGS}")
  set(CMAKE_SHARED_LINKER_FLAGS "${CMAKE_SHARED_LINKER_FLAGS} ${LINKER_FLAGS}")

  if(${CMAKE_CXX_COMPILER_ID} MATCHES "GNU")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fmax-errors=1")
    if (${CMAKE_BUILD_TYPE} MATCHES "Debug")
      set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Og -ggdb3 -fno-omit-frame-pointer")
    endif()
  elseif(${CMAKE_CXX_COMPILER_ID} MATCHES "Clang")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -ferror-limit=1")
    if (${CMAKE_BUILD_TYPE} MATCHES "Debug")
      set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-omit-frame-pointer")
    endif()
  endif()
else()
  message(FATAL_ERROR "Unsupported system")
endif()

add_subdirectory(src)

# enable_testing()
# add_subdirectory(test)
