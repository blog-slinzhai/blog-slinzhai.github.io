---
title: Usage of Cmake
date: 2018-10-08 23:17:30
---

简单的cmake命令:
PROJECT(projectname [CXX] [C] [Java])
系统给我们预定义了几个变量<projectname>_BINARY_DIR (或者 PROJECT_BINARY_DIR) 和 <projectname>_SOURCE_DIR (或者 PROJECT_SOURCE_DIR)。

SET(VAR [VALUE] [CACHE TYPE DOCSTRING [FORCE]])

MESSAGE([SEND_ERROR | STATUS | FATAL_ERROR] "Message to display")
SEND_ERROR，产生错误，生成过程被跳过
STATUS，输出前缀为-的信息
FATAL_ERROR，立即终止所有cmake过程

ADD_EXECUTABLE(exename ${SRC_LIST})
