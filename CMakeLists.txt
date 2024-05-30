cmake_minimum_required(VERSION 3.4)
project(Cpp-Software-Design)
option(BUILD_TESTS "Build tests" OFF)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

if(BUILD_TESTS)
    include_directories(.)
    add_library(main STATIC OpenGLCircle.h OpenGLSquare.h DrawAllShapes.h main.cpp)
    enable_testing()
    add_subdirectory(third-party/gtest)
    file(GLOB tests "tests/*.cpp")
    foreach(test ${tests})
         add_executable(check ${test})
         target_link_libraries(check gtest_main gmock_main main)
         add_test(NAME check COMMAND check)
    endforeach(test ${tests})
else()
    set(SOURCES
        Main.cpp
        DrawAllShapes.cpp
        OpenGLCircle.cpp
        OpenGLSquare.cpp
    )
    add_executable(Cpp-Software-Design ${SOURCES})
endif()
