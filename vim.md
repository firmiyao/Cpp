<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [进入vim](#%E8%BF%9B%E5%85%A5vim)
- [技巧：](#%E6%8A%80%E5%B7%A7)
- [插入模式](#%E6%8F%92%E5%85%A5%E6%A8%A1%E5%BC%8F)
  - [纠错技巧](#%E7%BA%A0%E9%94%99%E6%8A%80%E5%B7%A7)
- [退出vim](#%E9%80%80%E5%87%BAvim)
- [Visual（可视）模式](#visual%E5%8F%AF%E8%A7%86%E6%A8%A1%E5%BC%8F)
- [普通模式技巧](#%E6%99%AE%E9%80%9A%E6%A8%A1%E5%BC%8F%E6%8A%80%E5%B7%A7)
  - [单词之间移动](#%E5%8D%95%E8%AF%8D%E4%B9%8B%E9%97%B4%E7%A7%BB%E5%8A%A8)
  - [行间搜索](#%E8%A1%8C%E9%97%B4%E6%90%9C%E7%B4%A2)
  - [vim水平移动](#vim%E6%B0%B4%E5%B9%B3%E7%A7%BB%E5%8A%A8)
  - [vim页面移动（过多）](#vim%E9%A1%B5%E9%9D%A2%E7%A7%BB%E5%8A%A8%E8%BF%87%E5%A4%9A)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 进入vim

+ 输入vim命令进入vim
+ 进去之后是**normal模式**
+ 使用`:q`可以退出vim，需要在normal模式下。



# 技巧：

+ 行号显式：set nu
+ 语法高亮：syntax on

# 插入模式

+ 使用`i(insert)`进入编辑模式，开始输入文字
+ **i表示(insert)，在当前字符前插入；**
+ **I：insert before line，在行首插入。**
+ **a表示(appen)，在当前字符后插入；**
+ **A：append after line，在行尾插入。**
+ **o表示(open a line below)，重写开一行；**
+ **A：append a line above，在上面新开一行**



## 纠错技巧

**在插入模式的前提下：**

+ **ctrl + h：删除前一个字符**
+ **ctrl + w：删除前一个单词**
+ **ctrl + u：删除当前行**



# 退出vim

+ 使用`Esc`又可以回到normal模式。
+ 使用**wq**保存并退出



# Visual（可视）模式

+ 普通模式下使用**v**进入visual选择
+ 使用**V**选择行
+ 使用**ctrl + v**进行方块选择
+ 进入visual模式后，可以使用方向键移动，但是是在小写模式下。



# 普通模式技巧

+ gi：快速跳转到最后一次编辑的地方并且进入插入模式

## 单词之间移动

+ w/W：移动到下一个word/WORD开头
+ e/E：移动到以下以一word/WORD尾
+ b/B：移动到上一个word/WORD开头
+ word指一非空白符号分割的单词，WORD是以空白符号分割的单词



## 行间搜索

+ **f{char}：可以移动到char字符上，t(untill)移动到char的前一个字符（从前往后）**
+ **如果第一次没搜到可以使用`;/,`继续搜索改行的下一个/上一个**

+ **F表示反过来搜索前面的字符**



## vim水平移动

+ **0移动到行首第一个字符，^移动到第一个非空白字符**
+ **$移动到行尾，g_移动到行尾非空白字符**
+ **记住0he$就差不多了**



## vim页面移动（过多）

+ **gg/G移动到文件开头和结尾，可以使用ctrl  + o 快速返回**

+ **H/M/L :跳转到屏幕的开头(head)，中间(middle)，结尾(Lower)，记住是屏幕**

+ **ctrl + u  ctrl + f：上下翻页（upforw/forward）。zz把屏幕放置为中间。**



## 删除

+ **vim在normal模式下使用x快速删除一个字符**
+ **使用d（delete）配合文本对象快速删除一个单词：daw，会把单词和空白删除，diw只删除单词**
+ **dt(char)：delete to的意思，一直删除到字符**
+ **d和x都可以搭配数字来执行，比如2dd，表示删除两行；2xx表示删除两个字符。**



## vim快速修改

+ **r：replace；可以替换一个字符**
+ R：进入插入模式，并且替换当前字符
+ **c：change；配合文本对象，我们可以快速进行修改**
+ C：删除整行并进入插入模式
+ ct<char>：删除到到某个字符前，并进入插入模式
+ caw：删除某个单词，并进入插入模式；daw也是删除单词，但是还是normal模式
+ **s：substitute；删除当前字符并进入插入模式，可以配合数字使用，比如：4s：表示删除后面4个字符并进入插入模式**
+ S：删除整行并且进入插入模式



## vim查询

+ 使用/或者?进行前向或者反向搜索
+ 使用n/N跳转到下一个或者上一个匹配
+ 是用*或者#进行当前单词的前向和后向匹配

+ set hls：highlight search，搜索内容高亮
+ set incsearch：增量搜索，每添加一个单词就搜索并高亮