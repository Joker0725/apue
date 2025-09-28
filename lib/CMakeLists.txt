# 使用 file GLOB 命令自动收集当前目录下所有的 .c 源文件
file(GLOB LIB_SOURCES "*.c")

# 创建静态库目标
# 目标名称为 `apue`，STATIC 表示静态库，源文件列表为上面收集的 LIB_SOURCES
add_library(apue STATIC ${LIB_SOURCES})

# 为这个库目标设置头文件包含路径。
# 这里使用 PUBLIC 属性，意味着链接此库的目标（如 intro 下的可执行文件）也会自动获得这个头文件路径
target_include_directories(apue PUBLIC ${CMAKE_SOURCE_DIR}/include)