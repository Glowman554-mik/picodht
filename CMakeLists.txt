add_library(picodht INTERFACE)
target_include_directories(picodht INTERFACE ${CMAKE_CURRENT_LIST_DIR})
target_link_libraries(picodht INTERFACE
	hardware_clocks
    hardware_dma
    hardware_pio
)
target_sources(picodht INTERFACE
    ${CMAKE_CURRENT_LIST_DIR}/dht.c
    ${CMAKE_CURRENT_LIST_DIR}/dht.h
)
pico_generate_pio_header(picodht ${CMAKE_CURRENT_LIST_DIR}/dht.pio)
