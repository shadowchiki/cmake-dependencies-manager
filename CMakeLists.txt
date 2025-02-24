cmake_minimum_required(VERSION 3.21)
project(cmake-dependencies-manager)

include(FetchContent)
FetchContent_Declare(
  googletest
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG release-1.12.1)
FetchContent_MakeAvailable(googletest)
enable_testing()

add_executable(cmake-dependencies-manager main.cpp)
target_include_directories(
  cmake-dependencies-manager
  PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/
  PUBLIC ${CMAKE_SOURCE_DIR}/)
