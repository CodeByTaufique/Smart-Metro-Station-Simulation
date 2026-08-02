cmake_minimum_required(VERSION 3.20)
project(ComputerGraphicsLab VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)

# 1. Mac-specific paths for Homebrew
if(APPLE)
    list(APPEND CMAKE_PREFIX_PATH "/opt/homebrew")
    include_directories(/opt/homebrew/include)
    link_directories(/opt/homebrew/lib)
endif()

# 2. Find necessary packages
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
find_package(GLEW REQUIRED)
find_package(glfw3 REQUIRED)

# 3. Define the library list based on the platform
# This saves you from typing all the frameworks over and over again
if(APPLE)
    set(COMMON_LIBS
            ${OPENGL_LIBRARIES}
            ${GLUT_LIBRARIES}
            GLEW::GLEW
            glfw
            "-framework Cocoa"
            "-framework IOKit"
            "-framework CoreVideo"
    )
else()
    set(COMMON_LIBS
            ${OPENGL_LIBRARIES}
            ${GLUT_LIBRARIES}
            GLEW::GLEW
            glfw
            winmm
    )
endif()


add_executable(Metro Metro.cpp)
target_link_libraries(Metro PRIVATE ${COMMON_LIBS})