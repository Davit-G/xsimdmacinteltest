cmake_minimum_required(VERSION 3.15)
project (CMakeHelloWorld)

include (FetchContent)

#version number
set (CMakeHelloWorld_VERSION_MAJOR 1)
set (CMakeHelloWorld_VERSION_MINOR 0)

FetchContent_Declare (xsimd 
    GIT_REPOSITORY https://github.com/xtensor-stack/xsimd.git
    GIT_TAG origin/master)
FetchContent_MakeAvailable (xsimd)


#indicate the entry point for the executable
add_executable (CMakeHelloWorld HelloWorld.cpp)

target_link_libraries(CMakeHelloWorld PRIVATE
    xsimd
)

# install (TARGETS CMakeHelloWorld DESTINATION bin)
