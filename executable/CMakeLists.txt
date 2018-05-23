cmake_minimum_required(VERSION 3.0.0)

project(executable VERSION 1.0.0 LANGUAGES CXX)


find_package(Example 1.0.0 REQUIRED)


add_executable(executable main.cpp)

target_link_libraries(executable PRIVATE Example::example)
