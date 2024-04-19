
find_library(FLAG_UDP_FLAG libudp_library)
if(NOT FLAG_UDP_FLAG)
  message(STATUS "UDP library not found")
  file(GLOB UDP_SOURCES *.cpp)
  add_library(udp_library STATIC
     ${UDP_SOURCES}
      )
  target_link_libraries(udp_library)
  install (TARGETS udp_library DESTINATION bin)
endif()
