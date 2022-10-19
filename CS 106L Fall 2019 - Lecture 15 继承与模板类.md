[TOC]

# 继承

![image-20221019100729217](CS 106L Fall 2019 - Lecture 15 继承与模板类.assets/image-20221019100729217.png)

1. 纯虚函数：派生类必须提供实现。
2. 非纯（普通）虚函数：派生类可以生成自己的实现方式，若不提供则使用基类的实现方式。
3. 普通函数：表明派生类不应该更改该实现。

![image-20221019100947786](CS 106L Fall 2019 - Lecture 15 继承与模板类.assets/image-20221019100947786.png)

基类析构函数需要写成 虚函数形式，不然会有内存泄露风险

![image-20221019105213647](CS 106L Fall 2019 - Lecture 15 继承与模板类.assets/image-20221019105213647.png)

## 继承类示例

![image-20221019110604222](CS 106L Fall 2019 - Lecture 15 继承与模板类.assets/image-20221019110604222.png)

![image-20221019110614840](CS 106L Fall 2019 - Lecture 15 继承与模板类.assets/image-20221019110614840.png)

```c++
int main()
{
	Tea t;
	t.make();		//调用子类接口
	t.Drink::make(); //调用父类接口
}
```

## Template 与 继承类 比较

![image-20221019123851654](CS 106L Fall 2019 - Lecture 15 继承与模板类.assets/image-20221019123851654.png)

# Template Class

vector list 的实现方式

![image-20221019132536108](CS 106L Fall 2019 - Lecture 15 继承与模板类.assets/image-20221019132536108.png)

