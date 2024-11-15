cmake_minimum_required(VERSION 3.10)
project(project-name)

set(CMAKE_CXX_STANDARD 11)

enable_testing()

add_subdirectory(tests)

include(GoogleTest)

find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})

add_executable(hello_world_test tests/hello_world_test.cpp)
target_link_libraries(hello_world_test GTest::GTest GTest::Main)

gtest_discover_tests(hello_world_test)