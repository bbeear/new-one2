cmake_minimum_required(VERSION 3.25)
project(base)

set(CMAKE_CXX_STANDARD 17)
# 遍历项目根目录下所有的 .cpp 文件

#add_executable (base main.cpp )

# 遍历项目根目录下所有的 .cpp 文件

file (GLOB files *.cpp)

foreach (file ${files})

    string(REGEX REPLACE ".+/(.+)\\..*" "\\1" exe ${file})

    add_executable (${exe} ${file})

    message (\ \ \ \ --\ src/${exe}.cpp\ will\ be\ compiled\ to\ bin/${exe})

endforeach ()