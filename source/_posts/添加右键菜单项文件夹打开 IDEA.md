---
title: 添加右键菜单项文件夹打开 IDEA
tags:
  - 科普
  - 解决方案
---
具体流程：

1. 进入注册表编辑器：计算机\HKEY_CLASSES_ROOT\Directory\shell\
   (可在上方框内直接输入注册表路径)
2. 右键shell，新建-项，命名为IntelliJ IDEA
3. 点击IntelliJ IDEA项，右键"(默认)"修改值为Open Folder as IntelliJ IDEA Project
4. 右键IntelliJ IDEA项，新建-字符串值，命名为Icon，然后右键修改，填入idea程序的绝对路径
5. 右键IntelliJ IDEA项，新建-项，命名为command,右键"(默认)"修改值为("idea程序的绝对路径" "%1")(注意无括号，有英文双引号，中间有一空格)



