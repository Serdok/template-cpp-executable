# Testing configurations
enable_testing()
include(GoogleTest)

# Executables
add_executable(template_cpp_test hello_test.cpp)
target_link_libraries(template_cpp_test PRIVATE gmock gmock_main)

# Discover tests in above executables
gtest_discover_tests(template_cpp_test)