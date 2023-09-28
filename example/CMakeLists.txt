cmake_minimum_required(VERSION 3.18)

project(tests)

set(CMAKE_C_STANDARD 99)

add_executable(test_bh1750 main.c)

target_include_directories(test_bh1750 PUBLIC .)

target_link_libraries(test_bh1750 bh1750)
