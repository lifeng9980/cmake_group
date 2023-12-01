# 设置可执行二进制文件输出路径
message("CMAKE_CURRENT_SOURCE_DIR=== ${CMAKE_CURRENT_SOURCE_DIR} =========") 
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)

# set(SRC_LIST add.c div.c main.c mult.c sub.c)
# add_executable(app ${SRC_LIST})

# 包含当前工程路径
# include_directories(${CMAKE_CURRENT_SOURCE_DIR})

# 搜索 CMake所在路径 下的源文件
# aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR} SRC_LIST)
aux_source_directory(. SRC_LIST)
message("===============${SRC_LIST} =========") 

# 目标包含路径
# target_include_directories(app ${PROJECT_SOURCE_DIR})

# 搜索当前目录的src目录下所有的源文件，并存储到变量中
# file(GLOB MAIN_SRC ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)
# file(GLOB_RECURSE MAIN_SRC ${CMAKE_CURRENT_SOURCE_DIR}/*.c)     # 递归搜索
file(GLOB MAIN_SRC ${CMAKE_CURRENT_SOURCE_DIR}/*.c)
# file(GLOB_RECURSE MAIN_SRC_2 ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)
message("===============  ${MAIN_SRC}  =========") 
file(GLOB MAIN_HEAD ${CMAKE_CURRENT_SOURCE_DIR}/include/*.h)
message("===============  ${MAIN_HEAD} =========") 

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

#生成二进制目标
add_executable(app ${MAIN_SRC})