cmake_minimum_required(VERSION 3.25)
#项目名称
project(CppProject)
#设置C++标准
set(CMAKE_CXX_STANDARD 17)
#强制使用该C++标准
#set(CMAKE_CXX_STANDARD_REQUIRED True)

#将头文件目录包含到项目
include_directories(inc)

#收集源代码
file(GLOB SOURCES "src/*.cpp")
#生成可执行文件
add_executable(my_exe ${SOURCES})

#设置静态链接库目录
link_directories(lib)
#生成静态链接库
add_library(my_lib STATIC ${SOURCES})
# 链接静态链接库
target_link_libraries(my_exe my_lib)

# 设置可执行文件输出目录
set(EXECUTABLE_OUTPUT_PATH bin)

# 设置静态链接库输出目录
set(LIBRARY_OUTPUT_PATH lib)
