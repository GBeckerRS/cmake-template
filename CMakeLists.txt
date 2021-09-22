# Versão mínima necessária
cmake_minimum_required (VERSION 3.14)

project (cmake-template)

# Alias para os targets de teste e lib
set (TESTAPP ${PROJECT_NAME}Test)
set (LIBS ${PROJECT_NAME}Core)

# Habilita a versao C++11
set (CMAKE_CXX_STANDARD 11)

# Diretório de saída para criação do executável
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARIES_DIR ${CMAKE_SOURCE_DIR}/libraries)

include(FetchContent)
#---------------------------------------------------
# Inclui a biblioteca Catch2
FetchContent_Declare(
    catch2
    GIT_REPOSITORY https://github.com/catchorg/Catch2.git
    GIT_TAG        v2.9.1
    )
FetchContent_MakeAvailable(catch2)
#---------------------------------------------------

# Add main file subdirectory
add_subdirectory (app)

# Add souce files subdirectory
add_subdirectory (source)

# Add test files subdirectory
add_subdirectory (tests)

