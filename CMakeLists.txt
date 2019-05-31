project (mpsolve)
cmake_minimum_required(VERSION 3.13)

set (CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

find_package (GMP REQUIRED)

include_directories (
  ${GMP_INCLUDES}
  ${CMAKE_CURRENT_SOURCE_DIR}/include
  ${CMAKE_CURRENT_BINARY_DIR}/include
)

set (MPS_USE_BUILTIN_COMPLEX 1)
configure_file (include/mps/mt.h.in include/mps/mt.h @ONLY)

add_subdirectory (src)
