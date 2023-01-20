cmake_minimum_required(VERSION 3.15)
project(Kerbaroo)

set(CMAKE_CXX_STANDARD 17)

add_subdirectory(simulator)

add_executable(Kerbaroo main.cpp)

