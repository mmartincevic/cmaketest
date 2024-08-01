# Add test executable
file(GLOB TEST_SOURCES
    "*.cpp"
    "tests/*.cpp"
    "tests/tests/*.cpp"
)

add_executable(tests ${TEST_SOURCES})

# Link GoogleTest to the tests executable
target_link_libraries(tests
    PRIVATE
        gtest
        gtest_main
        Project
        Helpers
)

# Include directories for tests
target_include_directories(tests PRIVATE
    ${PROJECT_SOURCE_DIR}/project/include
    ${PROJECT_SOURCE_DIR}/helpers/include
)

# Add custom target to run tests
add_test(NAME MyTests COMMAND tests)
