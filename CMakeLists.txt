cmake_minimum_required(VERSION 3.1)
project(game.libretro.pcem)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(PCEM_LIB NAMES pcem_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(PCEM_CUSTOM_BINARY ${PCEM_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} PCEM "")

include(CPack)
