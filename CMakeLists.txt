cmake_minimum_required(VERSION 3.28.3)
project(dywoqc)

include("cmake/modules/os/${CMAKE_SYSTEM_NAME}.cmake")
include("cmake/modules/arch/${CMAKE_SYSTEM_PROCESSOR}.cmake")

file(GLOB_RECURSE ARCH_SOURCES ${ARCH_DIR}/*.c ${ARCH_DIR}/**/*.c)
file(GLOB_RECURSE OS_SOURCES ${OS_DIR}/*.c ${OS_DIR}/**/*.c)
file(GLOB_RECURSE LIB_SOURCES src/lib/*.c src/lib/**/.c)

add_library(${PROJECT_NAME} STATIC ${OS_SOURCES} ${LIB_SOURCES} ${ARCH_SOURCES})
