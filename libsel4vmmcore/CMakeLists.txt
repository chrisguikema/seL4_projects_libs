#
# Copyright 2019, Data61
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

project(libsel4vmmcore C)

add_compile_options(-std=gnu99)

set(sources src/drivers/virtio_net/virtio_net.c src/util/io.c)

add_library(sel4vmmcore STATIC EXCLUDE_FROM_ALL ${sources})
target_include_directories(sel4vmmcore PUBLIC include)
target_link_libraries(sel4vmmcore Configuration muslc sel4 utils sel4utils platsupport pci ethdrivers sel4pci pci)
