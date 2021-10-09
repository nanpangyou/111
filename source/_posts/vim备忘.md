---
title: vim备忘
date: 2021-09-28 23:11:07
---
# Vim操作方式备忘
---
Command模式

分屏

:vs (vertical split), :sp(split)

全局替换

:% s/带替换内容/替换为/g

---
Visual模式

使用 v 进入

使用 V 选择行

使用 ctrl+v 方块选择

---
编辑模式

ctrl+h 删除上一个字符

ctrl+w 删除上一个单词

ctrl+u 删除当前行

(在终端下 ctrl+a 移动到行首  ctrl+e 移动到行尾 ctrl+b 向前移动  ctrl+f 向后移动)


---
快速切换从insert模式去normal模式

除了esc还可以ctrl+c(有可能中断其他插件)还可以ctrl+[

快速切换从noraml模式去insert模式

使用 gi 快速跳转到你最后一次编辑的地方并进入插入模式

---

### 行间搜索移动

- 使用f{char}可以移动到 char 字符上，t移动到 char 的前一个字符
- 如果第一次没有搜到，可以用分号(;)/逗号(,)继续搜该行的上一个/下一个