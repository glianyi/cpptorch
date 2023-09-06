cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
project(cpptorch)

set(CMAKE_C_COMPILER /usr/bin/gcc)
set(CMAKE_CXX_COMPILER /usr/bin/g++)
set(CMAKE_PREFIX_PATH /root/dl/gotorch/cgotorch/linux/libtorch)
find_package(Torch REQUIRED)

set(CMAKE_CXX_FLAGFS "${CMAKE_CXX_FLAGS} ${TORCH_CXX_FLAGS}")
add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} "${TORCH_LIBRARIES}")
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 14)