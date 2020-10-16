cmake_minimum_required(VERSION 3.5)

if (UNIX)
    # cuda compiler path for linux, incase cmake cant see path variables
    set(CMAKE_CUDA_COMPILER /usr/local/cuda/bin/nvcc)
endif (UNIX)

if (WIN32)
    # also incase cmake cant see path variables
    # adjust this wrt the version of the cuda toolkit you have installed
    set(C:/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v11.1/bin/nvcc)

endif(WIN32)

project(cuonly LANGUAGES CUDA)

set(CMAKE_CUDA_STANDARD 14)
set(CMAKE_CUDA_STANDARD_REQUIRED ON)

include_directories(${CMAKE_CUDA_TOOLKIT_INCLUDE_DIRECTORIES})

add_executable(cuda_bfs #project name
kernel.cu) #cuda file name
