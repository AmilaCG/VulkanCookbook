cmake_minimum_required(VERSION 3.29)

file(TO_CMAKE_PATH $ENV{VCPKG_ROOT} vcpkg_path)
set(CMAKE_TOOLCHAIN_FILE "${vcpkg_path}/scripts/buildsystems/vcpkg.cmake")

project(Chapter01)
include(CMake/CommonMacros.txt)

SETUP_APP(Ch01_Sample01_CMake "Chapter 01")

find_package(glfw3 CONFIG REQUIRED)

target_link_libraries(${PROJECT_NAME} PRIVATE
        glfw)