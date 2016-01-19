add_executable(first_test test.cc)
add_test(NAME first_test COMMAND first_test WORKING_DIRECTORY ${CMAKE_RUNTIME_OUTPUT_DIRECTORY})
