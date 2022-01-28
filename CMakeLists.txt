cmake_minimum_required(VERSION 3.0)
project(gdk)

add_library(gdk STATIC sampgdk.c sampgdk.h)

target_include_directories(gdk PUBLIC ${PROJECT_SOURCE_DIR} sdk)
target_link_libraries(gdk PUBLIC sdk)
