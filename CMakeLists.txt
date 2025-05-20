cmake_minimum_required(VERSION 4.0)
project(MyEngine)

set(CMAKE_CXX_STANDARD 17)

# GLFW
add_subdirectory(libs/glfw)
include_directories(libs/glfw/include)

# GLAD
add_library(glad libs/glad/src/glad.c)
target_include_directories(glad PUBLIC libs/glad/include)

# stb_image (если нужно)
# include_directories(libs/stb)

add_executable(MyEngine main.cpp)
target_link_libraries(MyEngine glfw glad)
