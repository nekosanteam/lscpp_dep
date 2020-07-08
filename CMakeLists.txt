cmake_minimum_required(VERSION 3.11)
set(CMAKE_C_STANDARD   11)
set(CMAKE_C_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD   14)
set(CMAKE_CXX_EXTENSIONS OFF)
PROJECT(dep_utils CXX)

set(CMAKE_C_FLAGS   "-Wall -Wextra -pedantic -Wc++-compat -O2 ")
set(CMAKE_CXX_FLAGS "-Wall -Wextra -pedantic -Weffc++ -Wabi=2 -O2 ")
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_library(idep OBJECT
  idep_adep.cpp
  idep_altab.cpp
  idep_alutil.cpp
  idep_binrel.cpp
  idep_cdep.cpp
  idep_fdepitr.cpp
  idep_ldep.cpp
  idep_namea.cpp
  idep_nimap.cpp
  idep_string.cpp
  idep_tokitr.cpp
  )

add_executable(adep adep.cpp)
target_link_libraries(adep PRIVATE idep)
add_executable(cdep cdep.cpp)
target_link_libraries(cdep PRIVATE idep)
add_executable(ldep ldep.cpp)
target_link_libraries(ldep PRIVATE idep)
