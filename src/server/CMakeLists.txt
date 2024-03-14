#定义一个SRC变量，包含该目录下所有的源文件
aux_source_directory(. SRC_LIST)
#把db目录里的源文件也包含了
aux_source_directory(./db DB_LIST)
aux_source_directory(./model MODEL_LIST)
aux_source_directory(./redis REDIS_LIST)

add_executable(ChatServer ${SRC_LIST} ${DB_LIST} ${MODEL_LIST} ${REDIS_LIST})

target_link_libraries(ChatServer muduo_net muduo_base mysqlclient  hiredis pthread)