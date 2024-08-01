# Define the library
file(GLOB_RECURSE HELPER_SOURCES "src/*.cpp")

add_library(Helpers STATIC ${HELPER_SOURCES})

# Specify include directories for this library
target_include_directories(Helpers PUBLIC
    ${PROJECT_SOURCE_DIR}/helpers/include
)
