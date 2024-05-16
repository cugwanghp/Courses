# C++ 复习大纲

[TOC]

---

## 1. C++基础
### **变量和数据类型**
  - 基本数据类型（整型、浮点型、字符型、布尔型）
**示例代码：**
```cpp
#include <iostream>
using namespace std;

int main() {
    int myInt = 10; // 整型变量
    float myFloat = 5.5; // 浮点型变量
    char myChar = 'A'; // 字符型变量
    bool myBool = true; // 布尔型变量
    
    cout << "myInt: " << myInt << endl;
    cout << "myFloat: " << myFloat << endl;
    cout << "myChar: " << myChar << endl;
    cout << "myBool: " << (myBool ? "true" : "false") << endl;

    return 0;
}
```
  - 用户自定义类型（结构体、枚举、联合）
 #### 结构体（Struct）

结构体是一种用户自定义的数据类型，它可以包含不同类型的数据成员。结构体允许将多个相关的数据项作为一个单一的实体来处理。

**示例代码：**
```cpp
#include <iostream>
using namespace std;

// 定义一个结构体
struct Person {
    string name;
    int age;
    string address;
};

int main() {
    // 创建结构体变量
    Person person1;
    person1.name = "John Doe";
    person1.age = 30;
    person1.address = "123 Main St";

    // 输出结构体成员
    cout << "Name: " << person1.name << endl;
    cout << "Age: " << person1.age << endl;
    cout << "Address: " << person1.address << endl;

    return 0;
}
```

#### 枚举（Enum）

枚举是一种用户自定义的数据类型，它用于定义一组命名的整型常量。枚举可以提高代码的可读性和可维护性。

**示例代码：**
```cpp
#include <iostream>
using namespace std;

// 定义一个枚举
enum Color {    //enum class Color
    RED,    // 默认值为 0
    GREEN,  // 默认值为 1
    BLUE    // 默认值为 2
};

int main() {
    // 使用枚举
    Color myColor = GREEN;

    // 输出枚举值
    cout << "My color is: ";
    switch (myColor) {
        case RED:
            cout << "Red" << endl;
            break;
        case GREEN:
            cout << "Green" << endl;
            break;
        case BLUE:
            cout << "Blue" << endl;
            break;
    }

    return 0;
}
```

#### 联合（Union）

联合是一种特殊的数据类型，它允许在相同的内存位置存储不同的数据类型。联合的大小由其最大的成员决定，并且任何时候只能存储一个成员的值。

**示例代码：**
```cpp
#include <iostream>
using namespace std;

// 定义一个联合
union Data {
    int i;
    float f;
    char str[20];
};

int main() {
    // 创建联合变量
    Data data;

    // 使用联合成员
    data.i = 10;
    cout << "data.i : " << data.i << endl;

    data.f = 220.5;
    cout << "data.f : " << data.f << endl;

    strcpy(data.str, "C++ Programming");
    cout << "data.str : " << data.str << endl;

    // 注意：由于联合在任何时候只能存储一个成员的值，因此上面的代码会覆盖之前的值。
    // 最后一个赋值的成员是有效的。

    return 0;
}
```

在上述联合的示例中，我们可以看到联合的成员共享相同的内存空间。因此，当我们给一个成员赋值时，之前存储在其他成员中的值就会被覆盖。联合通常用于节省内存，或者在某些情况下，用于处理不同数据类型的数据。

  - 指针和引用
 #### 指针和引用的区别

1. **定义和初始化**：
   - 指针可以不初始化，可以指向NULL，也可以在程序中改变指向。
   - 引用必须在定义时初始化，并且一旦绑定就不能改变，相当于一个变量的别名。

2. **内存分配**：
   - 指针有自己的内存地址和内存空间，可以进行指针运算。
   - 引用没有自己的内存地址，也不占用额外的内存空间，不能进行引用运算。

3. **空值**：
   - 指针可以指向空（NULL），表示不指向任何对象。
   - 引用不能为空，它必须总是绑定到一个对象。

4. **多级间接**：
   - 指针可以有多级间接，即指向指针的指针。
   - 引用只有一级，不能引用引用。

5. **作为函数参数**：
   - 指针作为函数参数时，函数内部可以改变指针指向的值，也可以改变指针本身的指向。
   - 引用作为函数参数时，函数内部可以改变引用所绑定的值，但不能改变引用本身的绑定。

#### 示例代码

**指针示例代码：**
```cpp
#include <iostream>
using namespace std;

void pointerExample(int* ptr) {
    *ptr = 20; // 改变指针指向的值
    ptr = NULL; // 改变指针本身的指向
}

int main() {
    int var = 10;
    int* ptr = &var;
    cout << "Before function call, var: " << var << endl;
    pointerExample(ptr);
    cout << "After function call, var: " << var << endl; // var 的值被改变
    if (ptr == NULL) {
        cout << "ptr is now NULL" << endl; // 函数内部改变了指针的指向
    }
    return 0;
}
```

**引用示例代码：**
```cpp
#include <iostream>
using namespace std;

void referenceExample(int& ref) {
    ref = 20; // 改变引用所绑定的值
    // ref = NULL; // 错误，引用不能为空
}

int main() {
    int var = 10;
    int& ref = var;
    cout << "Before function call, var: " << var << endl;
    referenceExample(ref);
    cout << "After function call, var: " << var << endl; // var 的值被改变
    // if (ref == NULL) { // 错误，引用不能为空
    //     cout << "ref is now NULL" << endl;
    // }
    return 0;
}
```

在上述代码中，`pointerExample` 函数接收一个指针参数，并在函数内部改变了指针指向的值，同时也改变了指针本身的指向（虽然这在实际中不常见）。而 `referenceExample` 函数接收一个引用参数，并在函数内部改变了引用所绑定的值，但不能改变引用本身的绑定。

### **操作符和表达式**
  - 算术操作符
  - 关系和逻辑操作符
  - 位操作符
  - 赋值操作符
  - 条件操作符（三元操作符）
  - 操作符优先级和结合性
### **控制结构**
  - 顺序结构
  - 选择结构（if, switch）
  - 循环结构（for, while, do-while）
  - 跳转语句（break, continue, goto）

## 2. 函数
### **函数定义和声明**
  - 函数原型
  - 函数参数和返回值
  - 默认参数
### **函数重载**
  - 同名函数不同参数列表
### **内联函数**
  - 提高小函数的执行效率
### **递归函数**
  - 函数调用自身

## 3. 类和对象
### **类的定义**
  - 成员变量和成员函数
  - 访问修饰符（public, private, protected）
### **对象的创建和使用**
  - 对象的声明和初始化
  - 对象的生命周期
### **构造函数和析构函数**
  - 构造函数的种类（默认、拷贝、移动）
  - 析构函数的作用
### **静态成员**
  - 静态成员变量
  - 静态成员函数

## 4. 继承和多态
### **继承**
  - 单一继承
  - 多重继承
  - 继承的访问控制
### **多态**
  - 虚函数
  - 纯虚函数和抽象类
  - 运行时多态（动态绑定）
  - 函数重写（override）

## 5. 模板
### **函数模板**
  - 模板参数
  - 模板函数的使用
### **类模板**
  - 模板类的定义和使用
  - 模板特化

## 6. 标准模板库（STL）
### **容器**
  - 序列容器（vector, list, deque, array）
  - 关联容器（set, multiset, map, multimap）
  - 容器适配器（stack, queue, priority_queue）
### **迭代器**
  - 迭代器的种类（输入、输出、前向、双向、随机访问）
  - 迭代器的使用
### **算法**
  - 常用算法（排序、查找、遍历、合并、分割）
  - 算法的使用
### **函数对象**
  - 函数对象的定义和使用
  - 预定义函数对象

## 7. 异常处理
### **异常的概念**
  - 异常的抛出和捕获
  - 异常的传播
### **异常类**
  - 自定义异常类
  - 标准异常类

## 8. C++11/14/17/20新特性
- **自动类型推导（auto）**
- **右值引用和移动语义**
- **智能指针（unique_ptr, shared_ptr, weak_ptr）**
- **Lambda表达式**
- **并发API**
- **其他语言特性**

## 9. 文件操作
### **文件流**
  - ifstream, ofstream, fstream
  - 文件的打开、读写、关闭
### **文件操作**
  - 文件指针
  - 文件的随机访问

## 10. 内存管理
### **动态内存分配**
  - new, delete
  - new[] , delete[]
### **内存泄漏和智能指针**
  - 内存泄漏的原因和预防
  - 智能指针的使用

## 11. 多线程编程
### **线程的创建和管理**
  - std::thread
  - 线程的同步（mutex, lock, condition_variable）
### **线程间的通信**
  - 原子操作
  - 线程间的数据共享和保护

## 12. 性能优化
### **代码优化**
  - 循环优化
  - 内存访问优化
### **算法优化**
  - 选择合适的算法和数据结构
### **编译器优化**
  - 编译器优化选项

