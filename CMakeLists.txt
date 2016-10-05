cmake_minimum_required (VERSION 2.8)


# Custom modules
set (CMAKE_MODULE_PATH "${CMAKE_INSTALL_PREFIX}/share/cmake/Modules" ${CMAKE_MODULE_PATH})


# Platform
include (platform)
initialize_platform ()


# Install
include (platform/install)


# Tests
include (platform/tests)
add_project_tests_main_target ()


# Documentation
include (platform/doxygen)
add_project_documentation_main_target ()


# 3rdparty
add_subdirectory (libunrar)
add_subdirectory (liquiddb)

set (exceptions OFF)
#set (deprecated-functions OFF)
add_subdirectory (libtorrent)
