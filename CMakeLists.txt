# This Version is maintained by spiriMirror 
# https://github.com/spiriMirror
# Using modern CMake to organize the project
cmake_minimum_required(VERSION 3.10)

project(METIS C)

set(METIS_IDXTYPEWIDTH "32" CACHE STRING "Set the width of the idx_t")
set(METIS_REALTYPEWIDTH "64" CACHE STRING "Set the width of the real_t")

add_subdirectory("GKlib")
add_subdirectory("libmetis")