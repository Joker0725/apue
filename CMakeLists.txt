# 指定所需 CMake 的最低版本
cmake_minimum_required(VERSION 3.10)
# 定义项目名称
project(APUE)

# 设置 C 编译标准和相关选项
set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)
# 添加常用的编译定义，例如定义 LINUX 平台和启用 GNU 扩展源
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -DLINUX -D_GNU_SOURCE")

# 指定头文件搜索路径。APUE 的头文件通常在 include 目录下
include_directories(include)

# 添加子目录，CMake 将进入这些目录继续处理其中的 CMakeLists.txt
add_subdirectory(lib)
add_subdirectory(intro)