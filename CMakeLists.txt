cmake_minimum_required(VERSION 3.16)
project(sdl2_tutorial VERSION 1.0.0)
set(CMAKE_CXX_STANDARD 17)

# Find the package
find_package(SDL2 REQUIRED)

add_executable(sdl2_tutorial main.cpp)

# Link against the target (this handles includes and library paths)
target_link_libraries(sdl2_tutorial PRIVATE SDL2::SDL2)