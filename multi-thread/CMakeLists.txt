cmake_minimum_required(VERSION 3.0.0)
project(multi_thread VERSION 0.1.0)
set(CMAKE_CXX_STANDARD 11)
find_package(Threads REQUIRED)
include(CTest)
enable_testing()

add_executable(multi_thread src/main.cpp)
target_link_libraries(multi_thread Threads::Threads)

add_executable(data_list src/data_list.cpp)
target_link_libraries(data_list Threads::Threads)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
