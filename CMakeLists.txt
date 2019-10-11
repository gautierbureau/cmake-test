message("toto1")

cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

message("toto2")
#message(${CMAKE_INSTALL_PREFIX})

project(cmake-test)

message(${CMAKE_INSTALL_PREFIX})

message("toto3")

set(foo_sources foo.cpp)

set(foo_headers foo.hpp)

add_library(foo SHARED ${foo_sources})

set(main_sources
    main.cpp
   )

add_executable(main ${main_sources})
target_link_libraries(main foo)

message("toto4")

install(TARGETS foo DESTINATION ${CMAKE_INSTALL_PREFIX}/lib CONFIGURATIONS Release)
install(TARGETS main DESTINATION ${CMAKE_INSTALL_PREFIX}/bin CONFIGURATIONS Release)
install(FILES ${foo_headers} DESTINATION ${CMAKE_INSTALL_PREFIX}/include CONFIGURATIONS Release)