cmake_minimum_required(VERSION 3.10)
project(quicsample CXX)

set(CMAKE_CXX_STANDARD 11)

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

set_source_files_properties(sample.c PROPERTIES LANGUAGE CXX)

# Link the libmsquic library
target_link_libraries(quicsample 
    ${LIBMSQUIC_DIR}/libmsquic.so
    crypto
    dl
    numa
    pthread
)
