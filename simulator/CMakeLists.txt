#
#include(ExternalProject)
#
#ExternalProject_Add(
#        mp-units
#        GIT_REPOSITORY https://github.com/mpusz/units
#        GIT_TAG v0.7.0
#        GIT_SHALLOW TRUE
#
#        CMAKE_GENERATOR "Ninja Multi-Config"
#        CMAKE_ARGS -DCMAKE_TOOLCHAIN_FILE=conan_toolchain.cmake
#)

find_package(mp-units CONFIG REQUIRED)

add_library(simulator)

target_sources(simulator PRIVATE
    Body.cpp
)

target_include_directories(simulator PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(simulator PUBLIC mp-units::mp-units)
target_compile_features(simulator PUBLIC cxx_std_20)

add_subdirectory(test)
