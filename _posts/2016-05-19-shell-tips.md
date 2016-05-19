---
layout: post
title:  "shell 要点"
date:   16/5/19 上午11:15
---

### shell单引号双引号
双引号中的变量会替换，单引号不做转化

### tee
读取标准输入的数据,并将其内容输出成文件

### 重定向是倒序解析
cat < file > file 清空file
cat < file >> file 一直重复加入file初始内容

### 分支
[], [[]]

### 内置字符串处理
`${#x}` 取字符串长度 