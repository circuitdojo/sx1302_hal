#
# Copyright (c) 2020 Circuit Dojo
#
# SPDX-License-Identifier: Apache-2.0
#

zephyr_include_directories(inc)

file(WRITE inc/config.h "#ifndef _LORAGW_CONFIGURATION_H\n")
file(APPEND inc/config.h "#define _LORAGW_CONFIGURATION_H\n")
file(APPEND inc/config.h "#define LIBLORAGW_VERSION	\"2.1.0\"\n")
file(APPEND inc/config.h "#define DEBUG_AUX		0\n")
file(APPEND inc/config.h "#define DEBUG_COM		0\n")
file(APPEND inc/config.h "#define DEBUG_MCU		0\n")
file(APPEND inc/config.h "#define DEBUG_I2C		0\n")
file(APPEND inc/config.h "#define DEBUG_REG		0\n")
file(APPEND inc/config.h "#define DEBUG_HAL		0\n")
file(APPEND inc/config.h "#define DEBUG_GPS		0\n")
file(APPEND inc/config.h "#define DEBUG_GPIO	0\n")
file(APPEND inc/config.h "#define DEBUG_LBT		0\n")
file(APPEND inc/config.h "#define DEBUG_RAD		0\n")
file(APPEND inc/config.h "#define DEBUG_CAL		0\n")
file(APPEND inc/config.h "#define DEBUG_SX1302	0\n")
file(APPEND inc/config.h "#define DEBUG_FTIME	0\n")
file(APPEND inc/config.h "#endif\n")

FILE(GLOB c_sources src/*.c)
FILE(GLOB bin_sources src/*.var)

zephyr_library()
zephyr_library_sources(src/loragw_sx1302_rx.c)
zephyr_library_sources(src/loragw_sx1302_timestamp.c)
zephyr_library_sources(src/loragw_sx1302.c)
zephyr_library_sources(src/loragw_hal.c)