cmake_minimum_required(VERSION 3.15)
project(sampleMLP)

set(CMAKE_CXX_STANDARD 14)

set(SOURCE_FILES sampleMLP.cpp /home/linghu8812/deeplearning/TensorRT-6.0.1.5/samples/common/logger.cpp)
set(INC_DIR /home/linghu8812/deeplearning/TensorRT-6.0.1.5/samples/common
        /home/linghu8812/deeplearning/TensorRT-6.0.1.5/include
        /usr/local/cuda/include)
set(LINK_DIR /home/linghu8812/deeplearning/TensorRT-6.0.1.5/lib
        /usr/local/cuda/lib64)

include_directories(${INC_DIR})
link_directories(${LINK_DIR})
link_libraries(libnvinfer.so libcudart.so.10.0)

add_executable(sampleMLP ${SOURCE_FILES})
target_link_libraries(sampleMLP libnvinfer.so libcudart.so.10.0)
