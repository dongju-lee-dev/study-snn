cmake_minimum_required(VERSION 3.20)
project(study-snn LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

file(GLOB_RECURSE SOURCES "src/*.cpp")

add_executable(study-snn ${SOURCES})

if(CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    target_compile_options(study-snn PRIVATE -stdlib=libc++)
    target_link_options(study-snn PRIVATE -stdlib=libc++)
endif()