# 作业 1 : selpg
使用Go实现Linux命令行程序`selpg`
## 概述
Go学习第一次代码作业，用Go语言实现命令行实用程序`selpg`。
### 功能简介
在输入（stdin或文件）的内容中，根据指定`-s [Number]` `-e [Number]`参数，选择指定页码范围内的内容输出，同时可以通过`-d [destPrinter]`将输出内容直接传送到目标打印机进行打印。  
详细说明[在这里](https://www.ibm.com/developerworks/cn/linux/shell/clutil/index.html)

## 参数说明
### 必须参数
`-s [Number]`: 指定开始页码  
`-e [Number]`: 指定结束页码
### 可选参数
`-l [Number]`: 指定每页包含多少行，默认值为72  
`-f` : 忽略`-l`选项，令程序在输入内容中寻找换行符(`\f`)，并作为页面分割的标志。  
`-d [destPrinter]`: 指定目标打印机打印，程序将通过调用`lp -d[destPrinter]`将选择后的内容传至打印机

`[input_File_Name]`: 输入文件名。在所有`-`类型参数后指定。指定后`selpg`将查找并读取该文件。若不指定，则读取`stdin`中的内容作为输入。

## 使用
### 编译命令
`go build selpg.go`
### 运行示例
从文本中读入，输出第一页内容，每页十行  
`./selpg.exe -s 1 -e 1 -l 10 < ./testFiles/readFile.txt` 

