cmake_minimum_required(VERSION 3.23) # mp-units req's CMake 3.23
project(Kerbaroo)

add_subdirectory(simulator)

add_executable(Kerbaroo main.cpp)

