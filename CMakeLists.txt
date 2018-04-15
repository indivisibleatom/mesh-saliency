cmake_minimum_required (VERSION 2.8)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules")

find_package(Eigen REQUIRED)
#find_package(GLUT REQUIRED)

include_directories(${EIGEN_INCLUDE_DIRS})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -std=gnu++0x")

project (mesh_saliency)

file(GLOB source_list "*.cpp" "*.hpp")

add_executable(mesh_saliency
      ${source_list})

target_link_libraries(mesh_saliency
  GL
  GLU
  GLEW
  glut)
