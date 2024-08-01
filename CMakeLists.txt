cmake_minimum_required(VERSION 3.14)
project(MyProject VERSION 1.0 LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Include directories
include_directories(${PROJECT_SOURCE_DIR}/helpers/include
                    ${PROJECT_SOURCE_DIR}/project/include
                    ${PROJECT_SOURCE_DIR}/vendors/gtest-1.7.0/include
                    ${PROJECT_SOURCE_DIR}/vendors/imgui/include
                    ${PROJECT_SOURCE_DIR}/src)

# Add subdirectories
add_subdirectory(helpers)
add_subdirectory(project)
add_subdirectory(tests)
add_subdirectory(vendors/gtest-1.7.0)

# Add the main executable
add_executable(MyProject src/main.cpp)

# Link libraries
target_link_libraries(MyProject PRIVATE Helpers Project)
