cmake_minimum_required(VERSION 3.12)

set(CMAKE_CONFIGURATION_TYPES Debug Release)

set(PROJECT_NAME "d3d-9211")

project(${PROJECT_NAME})

set_property(GLOBAL PROPERTY OS_FOLDERS ON)

if(MSVC)
    add_definitions(-DUNICODE -D_UNICODE)
endif()

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(TARGET_OUTPUT_DIRECTORY ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/$<CONFIGURATION>)

add_subdirectory(src)

# Assuming a simple executable target named 'my_executable'
add_executable(my_executable src/main.cpp)

# Optionally link any libraries
# target_link_libraries(my_executable SomeLibrary)

# Specify include directories if needed
# target_include_directories(my_executable PUBLIC ${SomeIncludeDirectory})
