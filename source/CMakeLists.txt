# Define source files alias
set (SOURCES 
    foo/foo.cpp)

# Create a target for a library
add_library (${PROJECT_NAME}Core ${SOURCES})
target_include_directories(${PROJECT_NAME}Core PUBLIC .)

