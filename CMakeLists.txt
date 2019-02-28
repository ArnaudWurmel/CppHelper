cmake_minimum_required(VERSION 3.10)
project(CppHelper)

set(CMAKE_CXX_STANDARD 17)

set(SOURCES_CPP
        Subclasses/String.cpp
        )
set(INCLUDE_FILES
        ${PROJECT_SOURCE_DIR}/Subclasses/String.hh
        )

add_library(CppHelper
        ${SOURCES_CPP} ${INCLUDE_FILES}
        )

file(MAKE_DIRECTORY ${CMAKE_BINARY_DIR}/include)
add_custom_command(TARGET CppHelper POST_BUILD COMMAND cp ${INCLUDE_FILES} ${CMAKE_BINARY_DIR}/include)