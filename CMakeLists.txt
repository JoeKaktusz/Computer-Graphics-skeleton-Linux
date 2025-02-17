cmake_minimum_required(VERSION 3.10)
project(openGLApp)

# Set OpenGL version
set(CMAKE_CXX_STANDARD 17)

# Include directories
include_directories(${PROJECT_SOURCE_DIR}/include)

# Include source files
set(SRC_DIR ${PROJECT_SOURCE_DIR}/src)

# Recursively collect all source files
file(GLOB_RECURSE SOURCES ${SRC_DIR}/*.cpp ${SRC_DIR}/*.c)
file(GLOB_RECURSE HEADERS ${SRC_DIR}/*.h ${SRC_DIR}/*.hpp)

# Add the executable
# add_executable(${PROJECT_NAME} glad.c framework.cpp framework.h lodepng.cpp lodepng.h GreenTriangleNaked.cpp)
add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})

# Link libraries
target_link_libraries(${PROJECT_NAME} glfw dl GL)
