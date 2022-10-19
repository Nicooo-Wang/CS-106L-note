[TOC]

# namespaces

 **避免命名冲突**

![image-20221019091904907](CS 106L Fall 2019 - Lecture 14 继承.assets/image-20221019091904907.png)

 如果文件b引用了a.h && a.h中使用了using namespace xxx; b中将强行导入该namespace。

通常将using namespace用在cpp 文件中。最好的解决方案为 using std:: cout。可以逐个导入 namespace中的函数

# 虚类

![image-20221019095410053](CS 106L Fall 2019 - Lecture 14 继承.assets/image-20221019095410053.png)

纯虚类继承后需要重写方法

 