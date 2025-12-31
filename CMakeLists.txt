cmake_minimum_required(VERSION 3.10)
project(HotWords)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# if(NOT CMAKE_BUILD_TYPE)
#     set(CMAKE_BUILD_TYPE "RelWithDebInfo")
# endif()

# message(STATUS "Current Build Type: ${CMAKE_BUILD_TYPE}")
# add_definitions(-DBENCHMARK_MOCK_JIEBA)

include_directories(${CMAKE_SOURCE_DIR}/include) # 头文件
file(GLOB SOURCES "src/*.cpp" "main.cpp")
add_executable(demo ${SOURCES})

# add_compile_options(-Wall -Wextra)
add_compile_options(-Wall -Wextra -O3 -g)
set(CMAKE_C_COMPILER "/usr/bin/gcc")
set(CMAKE_CXX_COMPILER "/usr/bin/g++")

find_package(Threads REQUIRED)
target_link_libraries(demo Threads::Threads)