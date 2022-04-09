zephyr_include_directories(include)

FILE(GLOB c_sources lib/*.c)

zephyr_library()
zephyr_library_sources(${c_sources})