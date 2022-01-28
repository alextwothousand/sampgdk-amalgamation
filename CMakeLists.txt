cmake_minimum_required(VERSION 3.0)
project(gdk)

add_library(gdk STATIC sampgdk.c sampgdk.h)

target_include_directories(gdk PUBLIC ${PROJECT_SOURCE_DIR} sdk)
target_link_libraries(gdk PUBLIC sdk)
target_compile_options(gdk PRIVATE -m32)

if(CMAKE_COMPILER_IS_GNUCC OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
	set_property(TARGET gdk APPEND_STRING PROPERTY COMPILE_FLAGS " -m32")
	set_property(TARGET gdk APPEND_STRING PROPERTY LINK_FLAGS    " -m32")
endif()
