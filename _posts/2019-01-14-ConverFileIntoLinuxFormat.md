---
title: Remove '\r' on Linux
date: 2019-01-14 10:43:30
---

#1
方法1： 
在命令模式下:输入:%s/^M//g 然后,回车即可替换

注,其中”^M”的输入,分别是“Ctrl+v”、“Ctrl+M”键生成的

#方法2:

使用vi打开文本文件 
vi dos.txt 
命令模式下输入 
:set fileformat=unix 
:w

#方法3:

使用sed 工具 
sed ’s/^M//’ filename > tmp_filename

#方法4:

既然window下的回车符多了‘\r’，那么当然通过删除‘\r’ ，也可以实现： 
tr -d ‘\r’
