list(APPEND CMAKE_MODULE_PATH ${ZEPHYR_BASE}/modules/nanopb)
include(nanopb)

zephyr_nanopb_sources(zephyr_spotify
    zephyr_spotify/authentication.proto
    zephyr_spotify/clienttoken.proto
    zephyr_spotify/connect.proto
    zephyr_spotify/connectivity.proto
    zephyr_spotify/keyexchange.proto
    zephyr_spotify/login5.proto
    zephyr_spotify/mercury.proto
    zephyr_spotify/metadata.proto
    zephyr_spotify/playlist4.proto
    zephyr_spotify/spirc.proto
)

target_include_directories(zephyr_spotify PUBLIC ${CMAKE_CURRENT_BINARY_DIR})
target_include_directories(zephyr_spotify PUBLIC ${ZEPHYR_NANOPB_MODULE_DIR})
add_dependencies(zephyr_spotify nanopb_generated_headers)
