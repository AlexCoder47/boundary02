cmake_minimum_required(VERSION 3.4)
project(Cpp-Software-Design)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SOURCES
    DrawAllShapes.cpp
    Main.cpp
    OpenGLCircle.cpp
    OpenGLSquare.cpp
)

add_executable(Cpp-Software-Design ${SOURCES})
