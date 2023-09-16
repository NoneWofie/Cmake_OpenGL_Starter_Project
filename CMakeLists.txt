cmake_minimum_required(VERSION 3.27)
project(mike_shah_opengl VERSION 1.0.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Create an executable target
add_executable(${CMAKE_PROJECT_NAME} src/main.cpp)

# Include and link SDL2 library dynamically
add_subdirectory(lib/SDL EXCLUDE_FROM_ALL)
add_subdirectory(lib/glad)

target_include_directories(${CMAKE_PROJECT_NAME} PRIVATE ${PROJECT_SOURCE_DIR}/lib/SDL/include)
target_link_libraries(${CMAKE_PROJECT_NAME} PRIVATE SDL2::SDL2 glad)