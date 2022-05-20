cmake_minimum_required(VERSION 3.10)
project(_)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Clang tidy
include(cmake/StaticAnalyzers.cmake)

if (MSVC)
    add_compile_options(/W4)
else()
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

include_directories(include)

## To install a lib
# set(CMAKE_INSTALL_PREFIX install) # Prevents systemwide install
# install(TARGETS _)

## Testing
# enable_testing()
# add_subdirectory (/usr/src/gtest tests)
# include(CTest)
# set(TEST_BINARY ${PROJECT_NAME }_test)
# add_executable(${TEST_BINARY} test_tools.cpp) #executable that runs tests
# target_link_libraries (${TEST_BINARY }
# tools # Library we are testing
# gtest gtest_main # GTest libraries
# )
# add_test(
# NAME ${TEST_BINARY}
# COMMAND ${EXECUTABLE_OUTPUT_PATH}/${TEST_BINARY})

## Build
# When this is a top level cmake
# add_subdirectories(src)
# create libraries
add_library()
# add main executable
add_executable(main _.cpp)
# Linker binding
target_link_libraries(main )


# This is just a template. TAILOR PER USE!
