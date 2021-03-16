cmake_minimum_required(VERSION 3.1.0)
project(testbreakpad)

set(USE_BREAKPAD ON)

set(ENV{BREAKPAD_SOURCE_DIR})
add_subdirectory(contrib/breakpad-cmake)

set(BREAKPAD_SOURCE_DIR "$ENV{BREAKPAD_SOURCE_DIR}")

include_directories ("${BREAKPAD_SOURCE_DIR}/src")
message("Hello ${BREAKPAD_SOURCE_DIR}")

add_executable(main src/main.cpp)

target_link_libraries(main PUBLIC breakpad_client)

