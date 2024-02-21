cmake_minimum_required(VERSION 3.10)
project(OpenGLProject)

# Define the output binary
set(EXECUTABLE_NAME "OpenGLProject")

# Declare the executable
add_executable(${EXECUTABLE_NAME} main.cpp)

# Require OpenGL library
#find_package(OpenGL REQUIRED)
#include_directories(${OPENGL_INCLUDE_DIR})
#target_link_libraries(${EXECUTABLE_NAME} ${OPENGL_gl_LIBRARY})
target_link_libraries(${EXECUTABLE_NAME} opengl32)

# Require GLFW3 library
find_package(glfw3 REQUIRED)
target_link_libraries(${EXECUTABLE_NAME} glfw)

# Require GLEW library
find_package(GLEW REQUIRED)
include_directories(${GLEW_INCLUDE_DIRS})
target_link_libraries(${EXECUTABLE_NAME} ${GLEW_LIBRARIES})