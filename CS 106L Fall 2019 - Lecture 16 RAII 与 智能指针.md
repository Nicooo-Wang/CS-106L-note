[TOC]

# RAII

## WHY 

### code paths

![image-20221019152233175](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019152233175.png)

![image-20221019152340516](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019152340516.png)

``` c++
string EvaluateSalaryAndReturnName(int idNumber)
{
    Employee *e = newEmployee(idNumber);

    if (e->Title == "CEO" || e->Salary() > 100000)
    {
        cout << e->First() << " "
             << e->Last() << " is overpaid" << endl;
    }
    auto result = e->First() + " " + e->Last();

    delete e;
    return result;
}
```

如果在以上23个代码分支中，任意一个分支出错，delete都无法执行，造成内存泄漏。

### 需要申请、释放的资源

![image-20221019154252184](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019154252184.png)

### 程序安全等级分类

![image-20221019154950153](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019154950153.png)

## WHAT IS RAII / CADRE

**Resource Acuisition Is Initialization** / **Constructor Acquires, Destructor Releases**

RAII : 所有的资源申请应该在构造函数完成，所有资源释放应在析构函数完成

![image-20221019160103568](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019160103568.png)

stream类型符合RAII要求，即便没有close()，在对象结束时也会调用析构函数自动释放资源

![image-20221019160252089](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019160252089.png)

不符合RAII

![image-20221019160311587](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019160311587-1666166592879-1.png)

符合RAII，防止内存泄漏

![image-20221019160616957](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019160616957.png)

==lock_guard==实现方式

## HOW - 智能指针

![image-20221019164640016](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019164640016.png)

### unique_ptr

![image-20221019164922474](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019164922474.png)

==unique_ptr==通过==lock_guard==实现不能复制

### shared_ptr

![image-20221019165337815](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019165337815.png)

==shared_ptr==可以对资源进行复制

==shared_ptr==实现原理

![image-20221019165610584](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019165610584.png)

### weak_ptr

![image-20221019170132062](CS 106L Fall 2019 - Lecture 16 RAII 与 智能指针.assets/image-20221019170132062.png)

==weak_ptr==解决==shared_ptr==的循环引用问题





