cmake_minimum_required(VERSION 3.9)
project(zstd_cmake_lto_bug CXX)

set(CMAKE_CXX_STANDARD 20)

message(STATUS "CMAKE_VERSION = ${CMAKE_VERSION}")

include(CheckIPOSupported)

get_property(LANGUAGES GLOBAL PROPERTY ENABLED_LANGUAGES)
message(STATUS "LANGUAGES = ${LANGUAGES}")

check_ipo_supported()

add_subdirectory(zstd/build/cmake EXCLUDE_FROM_ALL)

get_property(LANGUAGES GLOBAL PROPERTY ENABLED_LANGUAGES)
message(STATUS "LANGUAGES = ${LANGUAGES}")

check_ipo_supported()
