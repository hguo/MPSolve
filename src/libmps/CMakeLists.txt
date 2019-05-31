file (GLOB_RECURSE libmps_sources *.c *.cpp *.l)

add_library (libmps SHARED ${libmps_sources})
target_compile_definitions (libmps PRIVATE "_MPS_PRIVATE" "HAVE_GETLINE")
target_link_libraries (libmps ${GMP_LIBRARIES})
