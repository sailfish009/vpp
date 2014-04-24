cmake_minimum_required (VERSION 2.6)

find_package(OpenCV REQUIRED)

add_definitions(-std=c++11)
add_definitions(-O3 -march=native -DNDEBUG -fopenmp)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/..)
include_directories(/usr/include/eigen3)

add_executable(parallel_gaussian_blur parallel_gaussian_blur.cc)
add_test(parallel_gaussian_blur parallel_gaussian_blur)

target_link_libraries(parallel_gaussian_blur ${OpenCV_LIBS} gomp)