cmake_minimum_required(VERSION 3.12)

project(kernel_resize_nearest_neighbor_test C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "-fno-rtti -fno-threadsafe-statics")

add_executable(kernel_resize_nearest_neighbor_test "")

target_include_directories(kernel_resize_nearest_neighbor_test
  PRIVATE
  ${CMAKE_CURRENT_LIST_DIR}/../../tests/kernel_resize_nearest_neighbor_test
)

target_compile_options(
  kernel_resize_nearest_neighbor_test
  PUBLIC
  -fno-exceptions
)

target_sources(kernel_resize_nearest_neighbor_test
  PRIVATE
  ${CMAKE_CURRENT_LIST_DIR}/../../tests/kernel_resize_nearest_neighbor_test/resize_nearest_neighbor_test.cpp
)

target_link_libraries(
  kernel_resize_nearest_neighbor_test
  tensorflow-lite
  tensorflow-lite-test
)
