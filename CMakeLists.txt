if(CONFIG_SPOTIFY)
    zephyr_library_named(zephyr_spotify)

    add_subdirectory(lib)
    add_subdirectory(protobuf)

    zephyr_syscall_include_directories(include)
    zephyr_include_directories(include)
endif() # CONFIG_SPOTIFY
