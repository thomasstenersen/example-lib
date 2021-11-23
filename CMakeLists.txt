#
# Copyright (c) 2021 Nordic Semiconductor ASA
#
# SPDX-License-Identifier: LicenseRef-Nordic-5-Clause
#
cmake_minimum_required(VERSION 3.20.0)

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(NONE)

add_library(mylib STATIC)
target_sources(mylib PRIVATE src/example_lib.c)

# FIXME: Zephyr does not support building only a static library, it will always
# build an `app` target. Therefore we add an empty source file to the target to
# please the build system.
target_sources(app PRIVATE ${ZEPHYR_BASE}/misc/empty_file.c)
