# Tests need to be added as executables first
add_executable(${TESTAPP} mainTest.cpp)

# Link the Catch2 testing library
target_link_libraries(${TESTAPP} PRIVATE ${LIBS} Catch2::Catch2)

