cmake_minimum_required(VERSION 3.0 FATAL_ERROR)

get_filename_component(APP_NAME ${CMAKE_CURRENT_SOURCE_DIR} NAME)
project(${APP_NAME})

find_package(Torch REQUIRED)
find_package(Eigen3 REQUIRED)
find_package(Boost 1.74.0 REQUIRED)

include_directories(${Boost_INCLUDE_DIRS})
include_directories(${EIGEN3_INCLUDE_DIRS})
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${TORCH_CXX_FLAGS}")

set(source_path "~/Harshal/ML/TD3_simple_env")


#find_package(GLEW REQUIRED)
#include_directories(${GLEW_INCLUDE_DIRS})

add_executable(${PROJECT_NAME} main.cpp)
target_sources(${PROJECT_NAME}
        PRIVATE
        agent.h
        agent.cpp
        model.hpp
        TestEnvironment.h
        )

target_link_libraries(${PROJECT_NAME} "${TORCH_LIBRARIES}" )
#target_link_libraries(${PROJECT_NAME} ${LIB_MUJOCO})
#target_link_libraries(${PROJECT_NAME} ${LIB_GL})
#target_link_libraries(${PROJECT_NAME} ${LIB_GL_static})
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)

