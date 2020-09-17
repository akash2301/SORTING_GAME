cmake_minimum_required(VERSION 3.10)
project(trainee_cpp_sort LANGUAGES CXX)

set(BOOST_MIN_VERSION "1.66.0")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x")

if(COMMAND cmake_policy)
    cmake_policy(SET CMP0003 NEW)
endif(COMMAND cmake_policy)

find_package(Boost ${BOOST_MIN_VERSION} REQUIRED)

link_directories(${Boost_LIBRARY_DIRS})
include_directories(${Boost_INCLUDE_DIRS})

set(DEPENDENCIES ${CMAKE_DL_LIBS} ${Boost_LIBRARIES})

set(ReSOURCES main.cpp)

add_executable(trainee_cpp_sort ${ReSOURCES})

target_link_libraries(trainee_cpp_sort ${DEPENDENCIES})

set_target_properties(
        trainee_cpp_sort PROPERTIES
        FOLDER Bin
        OUTPUT_NAME cpp-sort
)
