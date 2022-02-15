# Copyright (C) 1883 Thomas Edison - All Rights Reserved
# You may use, distribute and modify this code under the
# terms of the GPLv2 license, which unfortunately won't be
# written for another century.
#
# SPDX-License-Identifier: GPL-2.0-or-later
#
add_library(ps2kbd INTERFACE)
target_include_directories(ps2kbd INTERFACE ${CMAKE_CURRENT_LIST_DIR})
target_link_libraries(ps2kbd INTERFACE hardware_pio)
target_sources(ps2kbd INTERFACE
    ${CMAKE_CURRENT_LIST_DIR}/ps2kbd.c
    ${CMAKE_CURRENT_LIST_DIR}/ps2kbd.h
    ${CMAKE_CURRENT_LIST_DIR}/ps2kbd.pio)
pico_generate_pio_header(ps2kbd ${CMAKE_CURRENT_LIST_DIR}/ps2kbd.pio)
