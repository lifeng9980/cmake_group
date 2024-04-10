message("Warn Top log begin")
cmake_minimum_required(VERSION 3.10)
project(cmake_group)

# set(CMAKE_CXX_STANDARD 11)

# 嵌套能力：顶层设置的变量可以给子节点使用，前提是在 add_subdirectory 命令前
set(MY_VARIABLE "Hello from top-level CMakeLists.txt")
message("MY_VARIABLE === ${MY_VARIABLE}")

# add_subdirectory(cmake_c)
add_subdirectory(cmake_cpp)
add_subdirectory(cmake_libuse)

message("Warn Top log quit")


# message("Info Begin cmake test")
# foreach(item RANGE 5)
#     message(STATUS "当前遍历的值为: ${item}" )
# endforeach()

# # 创建 list
# set(WORD a b c d)
# set(NAME ace sabo luffy)
# # 遍历 list
# foreach(item IN LISTS WORD NAME)
#     message(STATUS "当前遍历的值为: ${item}" )
# endforeach()
