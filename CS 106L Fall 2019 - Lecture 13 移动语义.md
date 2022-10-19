[TOC]

# 移动语义

![image-20221018142101104](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018142101104.png)

以上过程共有六个变量被构造、析构

name1 调用 readNames ，创建names变量，函数结束析构

line17 return 处创建StrVector，拷贝names，在line9通过拷贝构造函数传递给name1，随后析构

name1 在main函数结束后析构

**移动语义**会在拷贝函数生效时，如果右值即将析构，左值将会取右值而代之，**降低一次拷贝、析构、构造的开销**

## 左值与右值

![image-20221018144242896](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018144242896.png)

![image-20221018144449523](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018144449523.png)

![image-20221018144430917](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018144430917.png)

![image-20221018145431906](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018145431906.png)

![image-20221018150255918](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018150255918.png)

## 移动语义成员函数

![image-20221018154917396](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018154917396.png)

![image-20221018154947344](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018154947344.png)

## 移动语义成员函数实现

![image-20221018195728229](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018195728229.png)

![image-20221018195808103](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018195808103.png)

## 性能测试

![image-20221018201600416](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018201600416.png)

![image-20221018201239439](CS 106L Fall 2019 - Lecture 13 移动语义.assets/image-20221018201239439.png)

