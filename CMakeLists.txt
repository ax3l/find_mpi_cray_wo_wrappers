cmake_minimum_required(VERSION 3.18)

project(cray-wo-wrappers)

list(APPEND CMAKE_MODULE_PATH "${openPMD_SOURCE_DIR}/Modules")

add_executable(main main.cpp)

find_package(MPI REQUIRED)

target_link_libraries(main PUBLIC MPI::MPI_C MPI::MPI_CXX)

