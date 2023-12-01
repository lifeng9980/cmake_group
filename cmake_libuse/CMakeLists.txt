# 源文件指定
file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)
# 头文件指定
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# 指定链接库目录
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)

# 链接静态库
# link_libraries(calc)

add_executable(libuse ${SRC_LIST})
# 链接动态库，在生成可执行目标之后
target_link_libraries(libuse pthread calc)

# 设置可执行文件输出路径
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)

message("cmake_libuse == ${PROJECT_BINARY_DIR} ====")
message("cmake_libuse == ${CMAKE_CURRENT_BINARY_DIR} =====")
message("cmake_libuse == ${CMAKE_BINARY_DIR} =====")

# my_subdirectory/CMakeLists.txt
message(STATUS "Variable from top-level: ${MY_VARIABLE}")
