cmake_minimum_required(VERSION 3.16)

project(sdl2_tutorial VERSION 1.0.0)

set(CMAKE_CXX_STANDARD 17)

find_package(SDL2 REQUIRED CONFIG)
find_package(SDL2_image REQUIRED CONFIG)
find_package(SDL2_ttf REQUIRED CONFIG)

get_property(allTargets DIRECTORY PROPERTY IMPORTED_TARGETS)
message(STATUS "Imported targets: ${allTargets}")

add_executable(sdl2_tutorial main.cpp)

target_link_libraries(
    sdl2_tutorial
    PRIVATE
    SDL2::SDL2 
    SDL2_image::SDL2_image
    SDL2_ttf::SDL2_ttf
)

if(TARGET SDL2::SDL2main)
    target_link_libraries(sdl2_tutorial PRIVATE SDL2::SDL2main)
endif()