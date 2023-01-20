include(FetchContent)

FetchContent_Declare(
    googletest
    GIT_REPOSITORY https://github.com/google/googletest.git
    GIT_TAG v1.13.0
)

FetchContent_MakeAvailable(googletest)

enable_testing()

add_executable( simulator_test )

target_sources(simulator_test PRIVATE
    BodyTest.cpp
)

target_link_libraries(simulator_test PRIVATE simulator GTest::gtest_main)

include(GoogleTest)
gtest_discover_tests(simulator_test)