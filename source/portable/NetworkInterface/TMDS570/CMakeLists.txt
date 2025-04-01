cmake_minimum_required(VERSION 3.13)
enable_language(ASM)

add_library(freertos_plus_tcp_network_if STATIC)
target_sources(freertos_plus_tcp_network_if PRIVATE NetworkInterface.c)
message(${CMAKE_SOURCE_DIR})
target_include_directories(freertos_plus_tcp_network_if PUBLIC .)

target_link_libraries(freertos_plus_tcp_network_if 
    PUBLIC
        freertos_plus_tcp
        freertos_plus_tcp_port
        freertos_plus_tcp_network_if_common
        tmdx570_hal
    PRIVATE
        freertos_kernel
)
