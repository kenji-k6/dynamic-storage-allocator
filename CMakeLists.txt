cmake_minimum_required(VERSION 3.15)
project(mdriver LANGUAGES C)

# Compiler options
set(CMAKE_VERBOSE_MAKEFILE ON)
set(CMAKE_C_COMPILER gcc)
set(CMAKE_C_FLAGS_DEBUG "-O0 -Werror -Wall -Wextra -Wpedantic -ggdb3 -fsanitize=address,undefined -fsanitize-undefined-trap-on-error")
set(CMAKE_C_FLAGS_RELEASE "-O3 -Wall -march=native")

add_executable(mdriver
        src/mdriver.c
        src/mm.c
        src/memlib.c
        src/fsecs.c
        src/fcyc.c
        src/clock.c
        src/ftimer.c)


target_include_directories(mdriver PRIVATE
        ${CMAKE_SOURCE_DIR}/include
)