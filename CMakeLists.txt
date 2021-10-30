cmake_minimum_required(VERSION 3.20)
project(template_cpp_executable)

# Set global parameters
set(CMAKE_CXX_STANDARD 20)
list(PREPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake/")

# Set project parameters / options
option(ENABLE_TESTING "Configure CMake to add tests targets" OFF)
add_subdirectory(scripts/)

# Include third-party projects
add_subdirectory(vendor/)

# Create executable, link sources
add_executable(${PROJECT_NAME})
add_subdirectory(src/)

# Link libraries

# Enable testing if requested
if (ENABLE_TESTING)
    add_subdirectory(tests/)
endif()