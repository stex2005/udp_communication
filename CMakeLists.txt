cmake_minimum_required(VERSION 3.5)

project(udp_communication LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_INSTALL_PREFIX $ENV{HOME}/stefano) #Use this for research code


add_subdirectory(udp_library)

add_executable(udp_server_example main_server.cpp)
add_executable(udp_client_example main_client.cpp)

add_executable(udp main.cpp)
target_link_libraries(udp udp_library)
target_include_directories(udp PUBLIC
                          "${PROJECT_BINARY_DIR}"
                          "${PROJECT_SOURCE_DIR}/udp_library"
                          )
