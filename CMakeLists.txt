cmake_minimum_required(VERSION 2.8)
project(rofi-json-dict)



# Plugin

find_package(PkgConfig)
pkg_search_module(GLIB2 REQUIRED glib-2.0)
pkg_search_module(CAIRO REQUIRED cairo)
pkg_search_module(JSONC REQUIRED json-c)

pkg_get_variable(ROFI_PLUGINS_DIR rofi pluginsdir)

include_directories(
    include
    ${GLIB2_INCLUDE_DIRS}
    ${CAIRO_INCLUDE_DIRS}
    ${JSONC_INCLUDE_DIRS}
)

file(GLOB SRC "src/*.c")

add_library(jsondict SHARED ${SRC})
set_target_properties(jsondict PROPERTIES PREFIX "")

target_link_libraries(jsondict
    ${GLIB2_LIBRARIES}
    ${CAIRO_LIBRARIES}
    ${JSONC_LIBRARIES}
)

install(TARGETS jsondict DESTINATION ${ROFI_PLUGINS_DIR})
