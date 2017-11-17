cmake_minimum_required(VERSION 3.0.2)



#Some things have order. This must be put in front alone

project(mxnet C CXX)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin") # set output directory

include_directories()

set(PS_LITE_DIR "${PROJECT_SOURCE_DIR}/ps-lite")
set(THIRD_PARTY_DIR "${PROJECT_SOURCE_DIR}/deps")

link_directories(
        "${THIRD_PARTY_DIR}/lib"
)

include_directories(
        "${PROJECT_SOURCE_DIR}/include"
        "${PS_LITE_DIR}/include"
)

add_subdirectory("ps-lite")

file(GLOB src "src/*")


add_executable(Demo ${src})