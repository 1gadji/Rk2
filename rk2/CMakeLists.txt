cmake_minimum_required(VERSION 3.22)

project(example)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(ex1 ${CMAKE_CURRENT_SOURCE_DIR}/ConceptualExample01.cpp)
add_library(ex2 ${CMAKE_CURRENT_SOURCE_DIR}/ConceptualExample02.cpp)
add_library(ex3 ${CMAKE_CURRENT_SOURCE_DIR}/ConceptualExample03.cpp)
add_executable(example ${CMAKE_CURRENT_SOURCE_DIR}/Program.cpp)

target_link_libraries(example ex1)
target_link_libraries(example ex2)
target_link_libraries(example ex3)


install(TARGETS example RUNTIME DESTINATION bin)

include(CPack.cmake)
