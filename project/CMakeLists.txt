# Define the library
file(GLOB_RECURSE PROJECT_SOURCES "src/*.cpp")

add_library(Project STATIC ${PROJECT_SOURCES})

# Specify include directories for this library
target_include_directories(Project PUBLIC
    ${PROJECT_SOURCE_DIR}/project/include
)
