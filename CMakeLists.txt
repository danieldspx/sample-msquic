cmake_minimum_required(VERSION 3.10)
project(quicsample)

# Set the paths to the library and include directories
set(LIBMSQUIC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/bin)
set(INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Add the include directory
include_directories(${INCLUDE_DIR})
# link_directories(${INCLUDE_DIR})

# Add the executable
add_executable(quicsample 
    sample.c
)

# Link the libmsquic library
target_link_libraries(quicsample 
    ${LIBMSQUIC_DIR}/libmsquic.so.2.3.5
    crypto
    dl
    numa
    pthread
)
