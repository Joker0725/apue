# 同样，使用 GLOB 收集当前目录下所有的 .c 示例源文件
file(GLOB INTRO_SOURCES "*.c")

# 循环处理每一个源文件
foreach(source_file ${INTRO_SOURCES})
    # 从完整的文件路径中提取出文件名（不包含扩展名），例如 "hello.c" -> "hello"
    get_filename_component(example_name ${source_file} NAME_WE)
    
    # 为这个示例源文件创建一个同名的可执行文件
    add_executable(${example_name} ${source_file})
    
    # 将可执行文件与 lib 目录下创建的 apue 库链接起来
    target_link_libraries(${example_name} apue)
endforeach()