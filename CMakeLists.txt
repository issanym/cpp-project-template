cmake_minimum_required(VERSION 3.10)
project(cars CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Set compiler to Clang
set(CMAKE_CXX_COMPILER clang++)

# Set compiler flags
if(MSVC)
    add_compile_options(/W4 /O2)
else()
    add_compile_options(-Wall -Wextra -O3)
endif()

# Set directories
set(SOURCE_DIR ${CMAKE_SOURCE_DIR}/src)
set(INCLUDE_DIR ${CMAKE_SOURCE_DIR}/headers)
set(OUTPUT_DIR ${CMAKE_BINARY_DIR}/bin)

# Set output directories
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${OUTPUT_DIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${OUTPUT_DIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${OUTPUT_DIR})

# Find all source files
file(GLOB SOURCES "${SOURCE_DIR}/*.cpp")

# Create executable
add_executable(cars ${SOURCES})

# Add include directories
target_include_directories(cars PRIVATE ${INCLUDE_DIR})
