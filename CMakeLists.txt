cmake_minimum_required(VERSION 3.10)
project(_)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Clang tidy
include(cmake/StaticAnalyzers.cmake)

# Set build type if not set
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Debug)
endif()

if (MSVC)
    add_compile_options(/W4)
else()
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

include_directories(include)

## Use external libs
## CMake will search here for Find <pkg >.cmake files
# SET( CMAKE_MODULE_PATH
#    ${PROJECT_SOURCE_DIR}/ cmake_modules )

## Search for Findsome_pkg.cmake file and load it
# find_package(some_pkg )

## Add the include folders from some_pkg
# include_directories(${some_pkg_INCLUDE_DIRS})
##

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
# add_subdirectories(src)
# create libraries
add_library()
# add main executable
add_executable(main _.cpp)
# Linker binding
target_link_libraries(main )


# This is just a template. TAILOR PER USE!
