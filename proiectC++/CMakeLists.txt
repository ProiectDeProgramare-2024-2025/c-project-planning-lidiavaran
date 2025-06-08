cmake_minimum_required(VERSION 3.10)
project(BlogProject CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(SharedBlogLogic
    shared/classes/Post.cpp
    shared/classes/BlogSystem.cpp
)

target_include_directories(SharedBlogLogic PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/shared/classes)

add_executable(app1 app1.cpp)
target_link_libraries(app1 PRIVATE SharedBlogLogic)

add_executable(app2 app2.cpp)
target_link_libraries(app2 PRIVATE SharedBlogLogic)