cmake_minimum_required(VERSION 3.18)
project(bh1750 C)

set(CMAKE_C_STANDARD 99)

add_subdirectory(src)
add_subdirectory(example)

target_link_libraries(bh1750 i2c)
