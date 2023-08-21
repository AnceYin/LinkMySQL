cmake_minimum_required(VERSION 3.5)

project(LinkMySQL)

# 设置编译器标准
set(CMAKE_CXX_STANDARD 20)
# set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 添加包含目录
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# 添加链接库的目录
link_directories(${CMAKE_CURRENT_SOURCE_DIR}/lib)

# 添加可执行文件或库
add_executable(${PROJECT_NAME} src/interface.cpp)

# 链接动态库
target_link_libraries(${PROJECT_NAME} mysqlcppconn)