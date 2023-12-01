message("=== ${PROJECT_SOURCE_DIR} ===")
message("=== ${CMAKE_CURRENT_SOURCE_DIR} ===")

# aux_source_directory(./src SRC_LIST)
file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)
message("=== ${SRC_LIST} ===")

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# 库文件输出路径 LIBRARY_OUTPUT_PATH
set(LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib)
message("=== ${LIBRARY_OUTPUT_PATH} ===")

# 可执行文件输出路径 EXECUTABLE_OUTPUT_PATH

# 生成库
add_library(calc STATIC ${SRC_LIST})
# add_library(calc SHARED ${SRC_LIST})
