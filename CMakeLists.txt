cmake_minimum_required(VERSION 3.18)

project(cray-wo-wrappers C CXX Fortran)

# comment in to use your own modified FindMPI.cmake
#list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/Modules")

add_executable(main main.cpp)
add_executable(mainF main.F90)

# for the HIP experience comment this in and use correct
# CXX compiler
#find_package(hip REQUIRED)
#target_link_libraries(main PUBLIC hip::device)
#target_link_libraries(mainF PUBLIC hip::device)

find_package(MPI REQUIRED)

target_link_libraries(main PUBLIC MPI::MPI_CXX)
target_link_libraries(mainF PUBLIC MPI::MPI_Fortran)

