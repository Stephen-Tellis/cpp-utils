cmake_minimum_required(VERSION 3.10)
project()
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Clang tidy
include(cmake/StaticAnalyzers.cmake)

if (MSVC)
    add_compile_options(/W4)
else()
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

include_directories(include/)

# create libraries
add_library()

# add main executable
add_executable(main )

# Linker binding
target_link_libraries(main )
