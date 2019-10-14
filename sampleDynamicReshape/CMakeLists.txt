cmake_minimum_required(VERSION 3.15)
project(sampleDynamicReshape)

set(CMAKE_CXX_STANDARD 14)

set(SOURCE_FILES sampleDynamicReshape.cpp /home/linghu8812/deeplearning/TensorRT-6.0.1.5/samples/common/logger.cpp)
set(INC_DIR /home/linghu8812/deeplearning/TensorRT-6.0.1.5/samples/common
        /home/linghu8812/deeplearning/TensorRT-6.0.1.5/include
        /usr/local/cuda/include)
set(LINK_DIR /home/linghu8812/deeplearning/TensorRT-6.0.1.5/lib
        /usr/local/cuda/lib64)

include_directories(${INC_DIR})
link_directories(${LINK_DIR})
link_libraries(libnvinfer.so libnvonnxparser.so libcudart.so.10.0)

add_executable(sampleDynamicReshape ${SOURCE_FILES})
target_link_libraries(sampleDynamicReshape libnvinfer.so libnvonnxparser.so libcudart.so.10.0)
