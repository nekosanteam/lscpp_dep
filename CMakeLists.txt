cmake_minimum_required(VERSION 3.11)
PROJECT(dep_utils CXX)
set(C_STANDARD 11)
set(CXX_STANDARD 14)

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
