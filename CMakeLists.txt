cmake_minimum_required(VERSION 3.10)
project(quicsample CXX)

set(CMAKE_CXX_STANDARD 11)

# Set the paths to the library and include directories
set(LIBMSQUIC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/bin)
set(INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Add the include directory
include_directories(${INCLUDE_DIR})

# Add the executable
add_executable(quicsample sample.c)
set_source_files_properties(sample.c PROPERTIES LANGUAGE CXX)
target_link_libraries(quicsample ${LIBMSQUIC_DIR}/libmsquic.so.2.3.5)

# add_executable(client client.cpp)
# set_source_files_properties(client.cpp PROPERTIES LANGUAGE CXX)
# target_link_libraries(client ${LIBMSQUIC_DIR}/libmsquic.so.2.3.5)


# CLI Command: g++ -L./bin -I./include ./sample.c -o ./sample -lpthread -lnuma -ldl -lcrypto -lmsquic
# LD_PRELOAD=../bin/libmsquic.so.2.3.5 ./sample
# OR create link with ln -s /usr/lib/foo.so.1.1.1 /usr/lib/foo.so
