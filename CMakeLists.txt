cmake_minimum_required(VERSION 3.12)
include(pico_sdk_import.cmake)

project(pico-template C CXX ASM)
pico_sdk_init()
set(CMAKE_BUILD_TYPE Debug)

add_executable(Pico src/main.c)
pico_enable_stdio_uart(Pico 0)
pico_enable_stdio_usb(Pico 1)

target_link_libraries(Pico pico_stdlib)
target_include_directories(Pico PRIVATE include src)
pico_add_extra_outputs(Pico)