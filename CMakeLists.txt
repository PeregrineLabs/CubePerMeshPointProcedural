cmake_minimum_required (VERSION 3.14)
project(HdGpProceduralTest)
find_package(OpenGL REQUIRED)
find_package(pxr REQUIRED)
#find_package(MaterialX)

set(CMAKE_CXX_STANDARD 17)

add_library(CubePerMeshPointProcedural SHARED
        CubePerMeshPointProcedural.cpp)
target_link_libraries(CubePerMeshPointProcedural ${PXR_LIBRARIES})
target_include_directories(CubePerMeshPointProcedural PUBLIC ${PXR_INCLUDE_DIRS})

configure_file(plugInfo.json.in ${CMAKE_CURRENT_BINARY_DIR}/plugInfo.json @ONLY)
