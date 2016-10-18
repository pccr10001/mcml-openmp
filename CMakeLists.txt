cmake_minimum_required(VERSION 3.6)
project(mcml)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -qopenmp")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c++11 -qopenmp")
set(CMAKE_C_STANDARD_INCLUDE_DIRECTORIES "/opt/intel/compilers_and_libraries_2017.0.102/mac/compiler/include/")
set(CMAKE_C_COMPILER "/opt/intel/compilers_and_libraries/mac/bin/icpc")
set(CMAKE_CXX_COMPILER "/opt/intel/compilers_and_libraries/mac/bin/icpc")
LINK_DIRECTORIES("/opt/intel/compilers_and_libraries_2017.0.102/mac/compiler/lib/")

add_executable(mcml ${SOURCE_FILES} mcmlmain.c mcmlgo.c mcmlnr.c mcmlio.c mcml.h)
TARGET_LINK_LIBRARIES(mcml libiomp5.dylib)
