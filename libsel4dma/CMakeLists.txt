#
# Copyright 2018, Data61
# Commonwealth Scientific and Industrial Research Organisation (CSIRO)
# ABN 41 687 119 230.
#
# This software may be distributed and modified according to the terms of
# the BSD 2-Clause license. Note that NO WARRANTY is provided.
# See "LICENSE_BSD2.txt" for details.
#
# @TAG(DATA61_BSD)
#

cmake_minimum_required(VERSION 3.8.2)

project(libsel4dma C)

add_compile_options(-std=gnu99)

file(GLOB sources src/*.c)

add_library(sel4dma STATIC EXCLUDE_FROM_ALL ${sources})
target_include_directories(sel4dma PUBLIC include)
target_link_libraries(sel4dma Configuration muslc platsupport)
