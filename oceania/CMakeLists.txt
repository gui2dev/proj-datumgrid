# CMake build system for proj-datumgrid-oceania releases.

cmake_minimum_required(VERSION 2.6)

project(PROJ_DATUMGRID_OCEANIA)
set(PROJ_DATUMGRID_OCEANIA_VERSION_MAJOR 1)
set(PROJ_DATUMGRID_OCEANIA_VERSION_MINOR 3-prerelease)

set(CPACK_SOURCE_GENERATOR "TGZ;ZIP")
set(CPACK_INCLUDE_TOPLEVEL_DIRECTORY 0)
set(CPACK_SOURCE_PACKAGE_FILE_NAME "proj-datumgrid-oceania-${PROJ_DATUMGRID_OCEANIA_VERSION_MAJOR}.${PROJ_DATUMGRID_OCEANIA_VERSION_MINOR}")
set(CPACK_SOURCE_IGNORE_FILES "/build.*/;/cmake/;/.github/;CMakeLists.txt;.swp$;.*~;${CPACK_SOURCE_IGNORE_FILES}")

include(CPack)

add_custom_target(dist COMMAND ${CMAKE_MAKE_PROGRAM} package_source)
