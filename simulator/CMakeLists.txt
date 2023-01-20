add_library(simulator)

target_sources(simulator PRIVATE
    Body.cpp
)

target_include_directories(simulator PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

add_subdirectory(test)
