cmake_minimum_required(VERSION 3.28)
project(cpptime VERSION 1.0.0 LANGUAGES CXX)

# echo requires at least C++20
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
include(GNUInstallDirs)

# Add targets
add_library(cpptime INTERFACE)
target_include_directories(
  cpptime
  INTERFACE $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/>
            $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
)
# Add cpptime install targets
install(DIRECTORY ${PROJECT_SOURCE_DIR}/
        DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})
