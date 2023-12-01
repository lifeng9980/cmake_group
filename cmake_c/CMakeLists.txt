


include_directories($(CMAKE_CURRENT_SOURCE_DIR)/include)

aux_source_directory(. SRC_LIST)
message("===== SRC_LIST = ${SRC_LIST} ========")

add_executable(app_c ${SRC_LIST})