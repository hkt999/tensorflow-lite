cmake_minimum_required(VERSION 3.12)

project(kernel_pooling_test C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "-fno-rtti -fno-threadsafe-statics")

add_executable(kernel_pooling_test "")

target_include_directories(kernel_pooling_test
  PRIVATE
  ${CMAKE_CURRENT_LIST_DIR}/../../tests/kernel_pooling_test
)

target_compile_options(
  kernel_pooling_test
  PUBLIC
  -fno-exceptions
)

target_sources(kernel_pooling_test
  PRIVATE
  ${CMAKE_CURRENT_LIST_DIR}/../../tests/kernel_pooling_test/pooling_test.cpp
)

target_link_libraries(
  kernel_pooling_test
  tensorflow-lite
  tensorflow-lite-test
)

#pico_add_extra_outputs(kernel_pooling_test)
