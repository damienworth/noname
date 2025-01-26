cmake_minimum_required(VERSION 3.30 FATAL_ERROR)

set(CMAKE_CXX_STANDARD 20)

project(
    noname
    VERSION 0.0.1
    LANGUAGES CXX)

if (BUILD_TESTS)
    include(CTest)
    enable_testing()
endif ()

add_subdirectory(3rdparty)

add_executable(noname src/noname.cpp)

target_compile_options(noname PRIVATE -Wall -Wextra -Werror -Wpedantic)

target_link_libraries(noname PRIVATE fmt::fmt)
