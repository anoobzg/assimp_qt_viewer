cmake_minimum_required(VERSION 3.15)

project(AssimpQtViewer)

include(cmake/entry/desktop-cpp.cmake)
__install_conan_requirements(MSVC_RUNTIME "static")

find_package(assimp)
find_package(stb)

add_library(assimp INTERFACE)
target_link_libraries(assimp INTERFACE stb::stb assimp::assimp)
add_subdirectory(assimp_qt_viewer)