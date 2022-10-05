cmake_minimum_required(VERSION 3.2)
set(-DCMAKE_TOOLCHAIN_FILE=G:/dev/vcpkg/scripts/buildsystems/vcpkg.cmake)

project(LearnOpenGL)

set(CMAKE_CXX_STANDARD 17)

find_package(glfw3 CONFIG REQUIRED)
find_package(glad CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)

include_directories("${PROJECT_SOURCE_DIR}/include")

aux_source_directory(./src SRCS)

add_executable(MyOpenGL ${SRCS})

target_link_libraries(MyOpenGL PRIVATE glad::glad)
target_link_libraries(MyOpenGL PRIVATE glfw)
target_link_libraries(MyOpenGL PRIVATE glm::glm)