cmake_minimum_required(VERSION 3.8 FATAL_ERROR)

project(find-peaks)
enable_language(CXX)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)


add_library(find-peaks STATIC example.cpp PeakFinder.cpp)
target_include_directories(find-peaks  PRIVATE ${CMAKE_SOURCE_DIR}/)
target_include_directories (
  ${PROJECT_NAME}
  INTERFACE $<BUILD_INTERFACE:${${PROJECT_NAME}_SOURCE_DIR}>
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>)



