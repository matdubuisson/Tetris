cmake_minimum_required(VERSION 4.2)

project(TETRIS CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED true)

find_package(SDL3 REQUIRED)

add_executable(${PROJECT_NAME})

target_sources(${PROJECT_NAME}
  PRIVATE
    main.cc
)

target_link_libraries(${PROJECT_NAME}
  PRIVATE
    SDL3::SDL3
)
