#定义一个SRC变量，包含该目录下所有的源文件
aux_source_directory(. SRC_LIST)

#指定生成可执行文件
add_executable(ChatClient ${SRC_LIST})

target_link_libraries(ChatClient pthread)