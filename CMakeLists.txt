cmake_minimum_required(VERSION 3.12)
project(Clion)

set(CMAKE_CXX_STANDARD 17)

set(BOOSTROOT "/home/preet/devenv/boost_1_67_0/")
set(Boost_USE_STATIC_LIBS ON)
find_package(Boost 1.67.0 COMPONENTS system filesystem regex REQUIRED)

if (Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS})
    message(STATUS "Boost_INCLUDE_DIRS: ${Boost_INCLUDE_DIRS}")
    message(STATUS "Boost_LIBRARIES: ${Boost_LIBRARIES}")
    message(STATUS "Boost_VERSION: ${Boost_VERSION}")
endif ()

add_executable(Clion main.cpp)

if (Boost_FOUND)
    target_link_libraries(Clion ${Boost_LIBRARIES})
endif ()