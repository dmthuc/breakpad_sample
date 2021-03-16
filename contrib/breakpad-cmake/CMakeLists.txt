cmake_minimum_required(VERSION 3.1.0)
project(libbreakpad)

# external breakpad repo
set(BREAKPAD_SOURCE_DIR "${CMAKE_SOURCE_DIR}/contrib/breakpad")
include_directories ("${BREAKPAD_SOURCE_DIR}/src")
set(ENV{BREAKPAD_SOURCE_DIR} "${BREAKPAD_SOURCE_DIR}")

if (USE_BREAKPAD)
    execute_process(COMMAND bash -c "cd ${BREAKPAD_SOURCE_DIR} && ./configure && make -j 4")
endif (USE_BREAKPAD)

