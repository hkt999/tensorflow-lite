cmake_minimum_required(VERSION 3.12)

project(kernel_quantize_test C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "-fno-rtti -fno-threadsafe-statics")

add_executable(kernel_quantize_test "")

target_include_directories(kernel_quantize_test
  PRIVATE
  ${CMAKE_CURRENT_LIST_DIR}/../../tests/kernel_quantize_test
)

target_compile_options(
  kernel_quantize_test
  PUBLIC
  -fno-exceptions
)

target_sources(kernel_quantize_test
  PRIVATE
  ${CMAKE_CURRENT_LIST_DIR}/../../tests/kernel_quantize_test/quantize_test.cpp
)

target_link_libraries(
  kernel_quantize_test
  tensorflow-lite
  tensorflow-lite-test
)

