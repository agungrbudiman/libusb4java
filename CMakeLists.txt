cmake_minimum_required(VERSION 2.8)

project(usb4java C)
set(PROJECT_VERSION 1.3.1)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/.cmake/Modules/")

SET(JAVA_INCLUDE_PATH "$ENV{JAVA_HOME}/include")
SET(JAVA_INCLUDE_PATH2 "$ENV{JAVA_HOME}/include/darwin")
SET(JAVA_AWT_INCLUDE_PATH NotNeeded)

find_package(JNI REQUIRED)
find_package(LibUsb REQUIRED)

include_directories(${JNI_INCLUDE_DIRS})
include_directories(${LibUsb_INCLUDE_DIRS})

if(CMAKE_COMPILER_IS_GNUCC)
    add_definitions(-Wall -Werror -std=c99)
endif()

add_subdirectory(src)
