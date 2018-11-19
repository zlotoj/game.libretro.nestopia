cmake_minimum_required(VERSION 3.1)
project(game.libretro.nestopia)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(NESTOPIA_LIB NAMES nestopia_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(NESTOPIA_CUSTOM_BINARY ${NESTOPIA_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} NESTOPIA "")

include(CPack)
