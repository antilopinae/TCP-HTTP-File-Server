cmake_minimum_required(VERSION 3.20.0)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

include(CCache)

project(TcpHTTPFileServer VERSION 1.0.0 LANGUAGES C)

set(SRC_SOURCES_DIR ${CMAKE_CURRENT_SOURCE_DIR})
file(GLOB SRC_SOURCES ${SRC_SOURCES_DIR}/*.c)

add_executable(${PROJECT_NAME} ${SRC_SOURCES})

target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -Wpedantic)
target_compile_definitions(${PROJECT_NAME} PRIVATE $<$<CONFIG:Debug>:DEBUG>)
