cmake_minimum_required(VERSION 3.12)

project(kernel_arg_min_max_test C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "-fno-rtti -fno-threadsafe-statics")

add_executable(kernel_arg_min_max_test)

target_include_directories(kernel_arg_min_max_test
  PRIVATE
  ${CMAKE_CURRENT_LIST_DIR}/../../tests/kernel_arg_min_max_test
)

target_compile_options(
  kernel_arg_min_max_test
  PUBLIC
  -fno-exceptions
)

target_sources(kernel_arg_min_max_test
  PRIVATE
  ${CMAKE_CURRENT_LIST_DIR}/../../tests/kernel_arg_min_max_test/arg_min_max_test.cpp
)

target_link_libraries(
  kernel_arg_min_max_test
  tensorflow-lite
  tensorflow-lite-test
)
