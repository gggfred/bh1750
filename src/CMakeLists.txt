cmake_minimum_required(VERSION 3.18)

project(bh1750-library C)

set(CMAKE_C_STANDARD 99)

add_library(bh1750 STATIC bh1750.c)

target_link_libraries(bh1750 i2c)

target_include_directories(bh1750 PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>
    $<INSTALL_INTERFACE:include>
)

install(TARGETS bh1750
    EXPORT bh1750-targets
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
    RUNTIME DESTINATION bin
)

install(EXPORT bh1750-targets
    FILE bh1750-config.cmake
    DESTINATION lib/cmake/bh1750
)

install(FILES bh1750.h DESTINATION include)