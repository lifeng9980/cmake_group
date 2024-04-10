message("=== [PROJECT_SOURCE_DIR]       == ${PROJECT_SOURCE_DIR} ===")
message("=== [CMAKE_CURRENT_SOURCE_DIR] == ${CMAKE_CURRENT_SOURCE_DIR} ===")

# aux_source_directory(./src SRC_LIST)
file(GLOB SRC_LIST ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)
message("=== [SRC_LIST] == ${SRC_LIST} ===")

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# 库文件输出路径 LIBRARY_OUTPUT_PATH
set(LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib)
message("=== [LIBRARY_OUTPUT_PATH]      == ${LIBRARY_OUTPUT_PATH} ===")

# 可执行文件输出路径 EXECUTABLE_OUTPUT_PATH

# 生成库,静态/动态目标不能同名，需要分步
# add_library(calc STATIC ${SRC_LIST})
# add_library(calc SHARED ${SRC_LIST})


# 同时生成静态和动态库，将 libcalc_shared.so 重命名为libcalc.so
add_library(calc STATIC ${SRC_LIST})
add_library(calc_shared SHARED ${SRC_LIST})
SET_TARGET_PROPERTIES (calc_shared PROPERTIES OUTPUT_NAME "calc")