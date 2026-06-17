# 提炼C++课件重点

> 我们C++课程的一个考核要求是写一个课堂实验报告总结，包含每节课的内容，我打算一章一章做，下面我将把老师每章的PPT传给你 ，帮我提炼其中的概念，重点，以及所有知识点，并把其中代码挑出来，显示中文，让我先看一遍，顺便复习。直接在下面显示就可以

可以，没问题。你把第一章的 PPT 发给我后，我会按下面这个结构直接整理在聊天里，方便你先看一遍、复习一遍：

1. **本章核心概念**
2. **本章重点内容**
3. **完整知识点梳理**
4. **易混点 / 考核可能关注点**
5. **PPT 中出现的代码整理**
   - 保留原代码
   - 配中文解释
   - 标出代码体现的知识点
6. **适合写进实验报告总结的表述**

你可以一章一章传，我会尽量帮你整理成“能复习，也能改写进课堂实验报告”的形式。先发第一章 PPT 就行。

> 下面看这个文件夹里的第一章

<details><summary>6 previous messages</summary>

> 我先看一下文件夹里第一章对应的课件文件，然后把内容抽出来整理成中文复习版。
>
> 找到了第一章：`Lecture 1 Introduction to C++.pdf`。我会先提取文本和代码，再按“概念、重点、知识点、代码”整理，尽量贴近老师课件本身。
>
> 我现在用本地 PDF 工具把第一页到最后一页的文字抽出来；如果课件里代码是图片形式，我再做一次页面渲染检查。
>
> 这个运行包里没有直接叫 `pdftotext.exe` 的工具，我换成 Python PDF 库来读取。先确认可用库，再提取内容。
>
> `pypdf` 可用，我会按页提取文本，顺手标出页码，方便后面对应课件内容。
>
> 第一页到第三页已经能读到，第三页有继承和多态示例代码；刚才 PowerShell 输出编码被项目符号卡住了，我切到 UTF-8 输出继续完整提取。
> </details>

下面是第一章 **Lecture 1 Introduction to C++** 的中文整理版，适合先复习，也可以后面改写进课堂实验报告。

**一、本章核心概念**

第一章主要是对 C++ 课程和 C++ 语言本身做总体介绍。

C++ 是在 C 语言基础上扩展出来的高级程序设计语言。它既支持 C 语言中的**过程化程序设计**，也支持以**抽象数据类型、继承、多态**为代表的**面向对象程序设计**。

这门课的目标包括：

- 理解 C++ 的语言特点；
- 掌握 C++ 的基本语法和基础知识；
- 理解面向对象程序设计思想；
- 掌握常见算法设计、编码、调试和开发文档编写能力；
- 学习类、对象、继承、多态等 C++ 核心机制。

**二、本章重点内容**

1. **C++ 的特点**

C++ 适合处理大量数据，并且强调高效率。它既追求代码运行效率，也追求代码结构清晰、表达能力强。

C++ 的优势包括：

- 可以进行过程化编程；
- 可以进行面向对象编程；
- 支持抽象数据类型；
- 支持继承和多态；
- 适合大型程序开发；
- 可用于系统软件、桌面软件、嵌入式系统、游戏、移动应用、云平台、编译器和库函数开发等领域。

2. **C++ 与 C 的关系**

C++ 是 C 语言的扩展，可以看作 C 的超集。很多 C 语言程序可以被 C++ 编译器编译。

二者相同点：

- 判断语句、循环语句、结构体、函数等基本语法相似；
- C++ 保留了 C 语言高效、简洁、跨平台的特点。

C 语言的不足：

- 没有类和对象；
- 不方便写泛型或模板代码；
- 编写大型程序时容易变得复杂；
- 数据和操作数据的函数通常是分离的，数据安全性较弱。

C++ 在 C 的基础上增加了：

- `class` 类；
- `private` / `public` 访问控制；
- 构造函数；
- 成员函数；
- 继承；
- 多态；
- 更强的抽象能力和数据封装能力。

3. **C++ 的设计思想**

课件中总结的 C++ 设计哲学：

- 代码应直接表达程序员的想法和意图；
- 尽可能在编译阶段保证安全；
- 不浪费时间和空间；
- 将复杂结构进行合理分离；
- 给程序员充分的控制权、责任和选择权。

概括为五点：

- 可读性；
- 安全性；
- 高效率；
- 抽象能力；
- 程序员选择权。

**三、过程化程序设计与面向对象程序设计**

**1. 过程化程序设计**

过程化程序设计的核心是“过程”或“函数”。

程序通常被划分为多个函数，数据通过参数传递给函数，由函数读取或修改数据。

特点：

- 关注点是函数或过程；
- 数据和处理数据的函数是分离的；
- 函数可以接收结构体变量或地址并操作其中数据。

缺点：

- 数据安全性不足；
- 任意函数都可能修改数据；
- 与数据相关的函数并不属于数据本身；
- 大型程序中代码组织和维护较困难。

**2. 面向对象程序设计**

面向对象程序设计，简称 OOP，核心思想是用程序模拟现实世界中的对象。

现实世界中的对象通常包含：

- 内部组成部分；
- 对外提供的接口；
- 接口控制内部状态；
- 外部不能随意直接操作内部结构。

课件举了 LCD 投影仪的例子：

投影仪内部有风扇和灯泡，外部有开关接口。如果灯泡打开，风扇也应该自动打开；如果风扇关闭，灯泡也应该自动关闭。也就是说，对象内部的状态变化必须遵守规则，不能被外部随意破坏。

对应到 C++ 中：

- 数据成员相当于对象的内部状态；
- 成员函数相当于对象的接口；
- `private` 可以禁止外部直接访问数据；
- `public` 提供合法操作接口；
- 编译器会检查非法访问，从而提高数据安全性。

面向对象还强调：

- 数据的可靠初始化；
- 对象创建时应处于合法状态；
- 构造函数可以保证对象初始化；
- 继承可以让新类复用已有类的特征；
- 多态可以让同一接口表现出不同对象的行为。

**四、本章完整知识点梳理**

1. C++ 是从 C 语言扩展而来的高级语言。
2. C++ 支持过程化编程和面向对象编程。
3. C++ 的面向对象特征包括抽象、封装、继承、多态。
4. C++ 可用于系统开发、应用开发、嵌入式、游戏、云平台、编译器和库开发。
5. C++ 于 1985 年首次发布。
6. C++ 标准持续更新，课件中提到大约每三年修订一次。
7. TIOBE 指数可以反映编程语言流行度，但不代表语言优劣。
8. C 语言由 Dennis Ritchie 于 1972 年创建。
9. C++ 早期由 Bjarne Stroustrup 于 1983 年左右设计。
10. C 语言特点是快速、简单、跨平台。
11. C 语言缺少类、对象、泛型和大型程序组织机制。
12. C++ 的设计目标是兼顾效率、抽象、安全和灵活性。
13. 过程化程序设计关注函数。
14. 面向对象程序设计关注对象。
15. 过程化程序设计中数据和函数分离。
16. 面向对象程序设计中数据和操作数据的函数绑定在类中。
17. `class` 用于定义类。
18. `private` 表示私有成员，只能在类内部访问。
19. `public` 表示公有成员，可以被外部访问。
20. 构造函数与类同名，用于对象初始化。
21. 成员函数写在类中，用于操作类的数据成员。
22. 继承允许一个类继承另一个类的特征。
23. 多态允许通过基类指针或引用调用派生类的重写函数。
24. `virtual` 用于声明虚函数。
25. `override` 表示派生类重写基类虚函数。
26. 虚析构函数用于通过基类指针删除派生类对象时正确释放资源。
27. 创建 C++ 程序通常经历：写源代码、编译、链接、生成可执行文件。
28. 源代码是程序员编写的 `.cpp` 等文件。
29. 编译把源代码转换为目标代码。
30. 链接把目标代码、库代码和启动代码组合成可执行程序。
31. C++ 源文件常见扩展名有 `.cpp`、`.cc`、`.cxx`、`.C` 等。
32. IDE 可以集成编辑、编译、链接和调试功能。
33. 命令行编译器通常需要手动输入命令完成编译和链接。
34. 早期 C++ 曾通过 `cfront` 转换成 C 代码再编译。
35. 后来的 C++ 编译器可以直接把 C++ 源代码编译成目标代码。

**五、PPT 中的代码整理**

**代码 1：继承与多态示例**

课件中这一段代码展示了基类、派生类、虚函数、函数重写和运行时多态。

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void makeSound() {
        cout << "Animal makes a sound" << endl;
    }

    virtual ~Animal() {} // 虚析构函数
};

class Dog : public Animal {
public:
    void makeSound() override {
        cout << "Dog barks" << endl;
    }
};

class Cat : public Animal {
public:
    void makeSound() override {
        cout << "Cat meows" << endl;
    }
};

int main() {
    Animal* animals[] = {new Dog(), new Cat()};

    for (int i = 0; i < 2; i++) {
        animals[i]->makeSound();
    }

    for (int i = 0; i < 2; i++) {
        delete animals[i];
    }

    return 0;
}
```

中文解释：

- `Animal` 是基类，表示动物。
- `Dog` 和 `Cat` 是派生类，分别表示狗和猫。
- `virtual void makeSound()` 表示 `makeSound` 是虚函数。
- 派生类中使用 `override` 重写基类虚函数。
- `Animal* animals[]` 是基类指针数组，但实际指向的是 `Dog` 和 `Cat` 对象。
- 调用 `animals[i]->makeSound()` 时，程序会根据对象的真实类型调用对应函数。
- 这就是运行时多态。
- `virtual ~Animal()` 是虚析构函数，保证通过基类指针删除派生类对象时行为正确。

运行结果：

```text
Dog barks
Cat meows
```

体现的知识点：

- 类与对象；
- 继承；
- 虚函数；
- 函数重写；
- 基类指针指向派生类对象；
- 运行时多态；
- 动态内存分配；
- 虚析构函数。

**代码 2：C++ 风格输出字符串**

课件中给出 C++ 示例，使用标准库对象输出字符串。

```cpp
#include <iostream>
#include <string>
#include <memory>

int main() {
    auto str = std::make_unique<std::string>("I see you again!");
    std::cout << *str << std::endl;
    return 0;
}
```

中文解释：

- `#include <iostream>` 用于输入输出。
- `#include <string>` 用于使用 `std::string`。
- `#include <memory>` 用于使用 `std::make_unique`。
- `auto` 让编译器自动推导变量类型。
- `std::make_unique<std::string>` 创建一个动态分配的字符串对象。
- `std::cout` 是 C++ 标准输出流。
- `std::endl` 表示换行并刷新缓冲区。
- `*str` 表示取出智能指针指向的字符串内容。

输出结果：

```text
I see you again!
```

体现的知识点：

- C++ 标准输入输出；
- 命名空间 `std`；
- 字符串类 `std::string`；
- `auto` 类型推导；
- 智能指针；
- C++ 比 C 更强调对象和资源管理。

**代码 3：C 风格输出字符串**

课件中也给出了 C 风格写法，用来说明 C++ 兼容 C。

```c
#include "stdio.h"
#include "stdlib.h"

int main() {
    printf("%s", "I see you again!\n");
    return 0;
}
```

中文解释：

- `stdio.h` 提供 `printf` 函数。
- `printf` 是 C 语言中的格式化输出函数。
- `%s` 表示输出字符串。
- 这段代码体现了 C++ 对 C 语言的兼容性。

输出结果：

```text
I see you again!
```

体现的知识点：

- C 风格输入输出；
- C++ 对 C 语言语法的兼容；
- C 与 C++ 编程风格对比。

**代码 4：Date 类定义**

课件中展示了如何把 C 语言中的结构体思想改写为 C++ 类。

```cpp
/* Beginning of Date.h */

class Date {
private:
    int d, m, y;

public:
    Date();

    void get_sys_date();
    void next_day();
};

/* End of Date.h */
```

中文解释：

- `class Date` 定义了一个日期类。
- `private` 中的 `d, m, y` 分别表示日、月、年。
- 私有成员不能被类外部随意访问，增强了数据安全性。
- `public` 中的函数是外部可以调用的接口。
- `Date();` 是构造函数，用于初始化日期对象。
- `get_sys_date()` 可以理解为获取系统日期。
- `next_day()` 可以理解为计算下一天。

体现的知识点：

- `class` 类定义；
- 私有数据成员；
- 公有成员函数；
- 构造函数；
- 数据封装；
- 类是 C++ 面向对象编程的基本单位。

**六、易混点和考核可能关注点**

1. **C++ 不是完全替代 C，而是在 C 基础上扩展**

C++ 保留了 C 的很多语法，但增加了面向对象机制。不能简单理解为“C++ 只是 C 加一点功能”，它也有自己的编程思想。

2. **过程化和面向对象的核心区别**

过程化关注“函数怎么处理数据”。

面向对象关注“对象拥有什么数据，以及对象通过什么接口操作这些数据”。

3. **`struct` 和 `class` 的思想差别**

C 中的结构体主要用于组织数据。

C++ 中的类不仅可以包含数据，还可以包含操作数据的函数，并且可以控制访问权限。

4. **封装的意义**

封装不是简单地把代码放进类里，而是通过 `private` 隐藏内部数据，通过 `public` 提供安全接口。

5. **构造函数的意义**

构造函数保证对象一创建就处于合理状态，避免未初始化或非法状态。

6. **继承和多态的关系**

继承让派生类获得基类特征。

多态让同一个接口在不同派生类对象上表现出不同的行为。

**七、可写进实验报告总结的表述**

本章主要学习了 C++ 语言的基本背景、发展过程、应用领域以及与 C 语言的关系。通过本章学习，我了解到 C++ 是在 C 语言基础上发展而来的高级程序设计语言，它既支持过程化程序设计，也支持面向对象程序设计。C++ 在保持 C 语言高效率和跨平台特点的同时，引入了类、对象、封装、继承和多态等机制，更适合大型程序的设计与开发。

本章还对比了过程化程序设计和面向对象程序设计的区别。过程化程序设计以函数为中心，数据和函数相互分离；而面向对象程序设计以对象为中心，将数据和操作数据的函数封装在类中，提高了程序的安全性、可维护性和可扩展性。通过 `Animal`、`Dog`、`Cat` 的示例，我初步理解了继承、虚函数和运行时多态的作用。

此外，本章还介绍了 C++ 程序从源代码到可执行文件的一般过程，包括编写源代码、编译、链接和生成可执行文件。这为后续学习 C++ 程序结构、类与对象、内存管理等内容打下了基础。

> 下面把上面的内容翻译成英文，因为课堂总结要交英文版

Here is the English version of the Chapter 1 summary.

**Chapter 1: Introduction to C++**

**1. Core Concepts**

This chapter mainly introduces the C++ course and the C++ programming language.

C++ is a high-level programming language extended from the C language. It supports both **procedural programming** and **object-oriented programming**, including important concepts such as **abstract data types, inheritance, and polymorphism**.

The objectives of this course include:

- Understanding the characteristics of C++;
- Mastering the basic syntax and fundamental knowledge of C++;
- Understanding the concept of object-oriented programming;
- Mastering basic object-oriented programming methods;
- Developing the ability to design algorithms, write code, debug programs, and prepare development documents.

**2. Key Points**

C++ is suitable for handling large amounts of data efficiently. It focuses not only on execution efficiency but also on clear structure and strong expressive ability.

The main advantages of C++ include:

- It supports procedural programming;
- It supports object-oriented programming;
- It supports abstract data types;
- It supports inheritance and polymorphism;
- It is suitable for large-scale software development;
- It can be used in system software, desktop applications, embedded systems, games, mobile applications, cloud platforms, compilers, and library development.

**3. Relationship Between C and C++**

C++ is an extension of the C language and can be regarded as a superset of C. Many C programs can be compiled by a C++ compiler.

Similarities between C and C++:

- Decision-making statements, loops, structures, and functions are similar;
- C++ keeps the efficiency, simplicity, and cross-platform features of C.

Weaknesses of C:

- It has no classes or objects;
- It is difficult to write generic or templated code;
- Large programs can become hard to manage;
- Data and functions are usually separated, which makes data less secure.

New features added by C++ include:

- `class`;
- `private` and `public` access control;
- constructors;
- member functions;
- inheritance;
- polymorphism;
- stronger abstraction and encapsulation.

**4. Design Philosophy of C++**

The design philosophy of C++ can be summarized as follows:

- Express ideas and intentions directly in code;
- Enforce safety at compile time whenever possible;
- Avoid wasting time and memory space;
- Separate complex structures clearly;
- Give programmers full control, responsibility, and choice.

In short, C++ emphasizes:

- readability;
- safety;
- efficiency;
- abstraction;
- programmer choice.

**5. Procedural Programming and Object-Oriented Programming**

**Procedural Programming**

Procedural programming focuses on procedures or functions.

A program is usually divided into several functions. Data is passed to functions through parameters, and the functions read or modify the data.

Main features:

- The focus is on functions or procedures;
- Data and functions are separated;
- Functions can receive structure variables or addresses and operate on them.

Drawbacks:

- Data security is weak;
- Any function may modify the data;
- Functions related to the data do not belong to the data itself;
- Large programs may become difficult to organize and maintain.

**Object-Oriented Programming**

Object-oriented programming, or OOP, tries to model real-world objects in programs.

Real-world objects usually have:

- internal parts;
- external interfaces;
- interfaces that control internal states;
- restrictions that prevent outside code from directly changing internal parts.

The PPT uses an LCD projector as an example. A projector has a fan and a lamp. If the lamp is switched on, the fan should also be switched on automatically. If the fan is switched off, the lamp should also be switched off. This means that the internal state of an object must follow certain rules and should not be changed freely from the outside.

In C++:

- data members represent the internal state of an object;
- member functions represent the interface of an object;
- `private` prevents outside code from directly accessing data;
- `public` provides legal interfaces for outside use;
- the compiler checks illegal access and improves data security.

OOP also emphasizes:

- guaranteed initialization of data;
- objects should be in a valid state when created;
- constructors can initialize objects automatically;
- inheritance allows a new class to reuse the features of an existing class;
- polymorphism allows the same interface to have different behaviors for different objects.

**6. Complete Knowledge Points**

1. C++ is a high-level language extended from C.
2. C++ supports both procedural programming and object-oriented programming.
3. Object-oriented features of C++ include abstraction, encapsulation, inheritance, and polymorphism.
4. C++ can be used for system software, application software, embedded systems, games, cloud platforms, compilers, and libraries.
5. C++ was first released in 1985.
6. The C++ standard continues to be updated regularly.
7. The TIOBE index reflects the popularity of programming languages, but it does not represent which language is the best.
8. C was created by Dennis Ritchie in 1972.
9. C++ was developed by Bjarne Stroustrup around 1983.
10. C is fast, simple, and cross-platform.
11. C lacks classes, objects, generic programming, and mechanisms for organizing large programs.
12. C++ aims to balance efficiency, abstraction, safety, and flexibility.
13. Procedural programming focuses on functions.
14. Object-oriented programming focuses on objects.
15. In procedural programming, data and functions are separated.
16. In object-oriented programming, data and functions are combined inside classes.
17. `class` is used to define a class.
18. `private` members can only be accessed inside the class.
19. `public` members can be accessed from outside the class.
20. A constructor has the same name as the class and is used to initialize objects.
21. Member functions are defined inside a class and operate on its data members.
22. Inheritance allows one class to inherit features from another class.
23. Polymorphism allows base-class pointers or references to call overridden functions in derived classes.
24. `virtual` is used to declare a virtual function.
25. `override` means that a derived class overrides a virtual function from the base class.
26. A virtual destructor ensures correct resource release when deleting derived-class objects through base-class pointers.
27. Creating a C++ program usually includes writing source code, compiling, linking, and generating an executable file.
28. Source code is the program file written by the programmer, such as a `.cpp` file.
29. Compilation translates source code into object code.
30. Linking combines object code, library code, and startup code into an executable program.
31. Common C++ source file extensions include `.cpp`, `.cc`, `.cxx`, and `.C`.
32. An IDE can integrate editing, compiling, linking, and debugging.
33. Command-line compilers usually require commands to compile and link programs.
34. Early C++ used `cfront` to translate C++ code into C code before compilation.
35. Later C++ compilers can directly compile C++ source code into object code.

**7. Code from the PPT**

**Example 1: Inheritance and Polymorphism**

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void makeSound() {
        cout << "Animal makes a sound" << endl;
    }

    virtual ~Animal() {} // virtual destructor
};

class Dog : public Animal {
public:
    void makeSound() override {
        cout << "Dog barks" << endl;
    }
};

class Cat : public Animal {
public:
    void makeSound() override {
        cout << "Cat meows" << endl;
    }
};

int main() {
    Animal* animals[] = {new Dog(), new Cat()};

    for (int i = 0; i < 2; i++) {
        animals[i]->makeSound();
    }

    for (int i = 0; i < 2; i++) {
        delete animals[i];
    }

    return 0;
}
```

Explanation:

- `Animal` is the base class.
- `Dog` and `Cat` are derived classes.
- `virtual void makeSound()` declares a virtual function.
- `override` means that the derived class rewrites the virtual function.
- `Animal* animals[]` is an array of base-class pointers, but the pointers actually point to `Dog` and `Cat` objects.
- When `animals[i]->makeSound()` is called, the program calls the correct function according to the real object type.
- This is runtime polymorphism.
- `virtual ~Animal()` is a virtual destructor, which ensures correct deletion through a base-class pointer.

Output:

```text
Dog barks
Cat meows
```

Knowledge points:

- classes and objects;
- inheritance;
- virtual functions;
- function overriding;
- base-class pointer pointing to derived-class object;
- runtime polymorphism;
- dynamic memory allocation;
- virtual destructor.

**Example 2: C++ Style String Output**

```cpp
#include <iostream>
#include <string>
#include <memory>

int main() {
    auto str = std::make_unique<std::string>("I see you again!");
    std::cout << *str << std::endl;
    return 0;
}
```

Explanation:

- `#include <iostream>` is used for input and output.
- `#include <string>` is used for `std::string`.
- `#include <memory>` is used for `std::make_unique`.
- `auto` lets the compiler infer the variable type automatically.
- `std::make_unique<std::string>` creates a dynamically allocated string object.
- `std::cout` is the standard output stream.
- `std::endl` prints a newline and flushes the buffer.
- `*str` gets the string value pointed to by the smart pointer.

Output:

```text
I see you again!
```

Knowledge points:

- standard C++ input and output;
- namespace `std`;
- `std::string`;
- type inference with `auto`;
- smart pointers;
- object-oriented resource management in C++.

**Example 3: C Style String Output**

```c
#include "stdio.h"
#include "stdlib.h"

int main() {
    printf("%s", "I see you again!\n");
    return 0;
}
```

Explanation:

- `stdio.h` provides the `printf` function.
- `printf` is a C-style formatted output function.
- `%s` means outputting a string.
- This code shows that C++ is compatible with C.

Output:

```text
I see you again!
```

Knowledge points:

- C-style input and output;
- compatibility between C++ and C;
- comparison between C and C++ programming styles.

**Example 4: Definition of the Date Class**

```cpp
/* Beginning of Date.h */

class Date {
private:
    int d, m, y;

public:
    Date();

    void get_sys_date();
    void next_day();
};

/* End of Date.h */
```

Explanation:

- `class Date` defines a date class.
- `d`, `m`, and `y` represent day, month, and year.
- These data members are private, so they cannot be accessed directly from outside the class.
- The public functions provide interfaces for outside code.
- `Date();` is a constructor used to initialize a `Date` object.
- `get_sys_date()` can be used to get the system date.
- `next_day()` can be used to calculate the next day.

Knowledge points:

- class definition;
- private data members;
- public member functions;
- constructor;
- encapsulation;
- class as the basic unit of object-oriented programming in C++.

**8. Common Confusing Points**

1. C++ is not a complete replacement for C. It extends C and introduces object-oriented programming ideas.
2. Procedural programming focuses on how functions process data, while object-oriented programming focuses on objects and their interfaces.
3. A C structure mainly organizes data, while a C++ class can contain both data and functions.
4. Encapsulation means hiding internal data and providing safe public interfaces.
5. Constructors help ensure that objects are initialized into valid states.
6. Inheritance allows code reuse, while polymorphism allows different objects to respond differently to the same interface.

**9. Summary for the Report**

In this chapter, I learned the basic background, development history, application fields, and main features of the C++ programming language. C++ is a high-level language developed from C. It supports both procedural programming and object-oriented programming. While keeping the efficiency and cross-platform features of C, C++ introduces classes, objects, encapsulation, inheritance, and polymorphism, which makes it more suitable for large-scale software development.

This chapter also compared procedural programming with object-oriented programming. Procedural programming focuses on functions, and data is usually separated from the functions that operate on it. In contrast, object-oriented programming focuses on objects. It encapsulates data and related functions inside classes, improving data security, maintainability, and extensibility. Through the example of `Animal`, `Dog`, and `Cat`, I gained a basic understanding of inheritance, virtual functions, and runtime polymorphism.

In addition, this chapter introduced the general process of creating a C++ program, including writing source code, compiling, linking, and generating executable code. This provides a foundation for later learning about C++ program structure, classes and objects, memory management, and other important topics.

> 下面进行第二章，依旧是先中文再翻译成英文

<details><summary>1 previous message</summary>

> 好的，我们继续第二章。我先读取 `Lecture 2 Basic concepts and structure of C++.pdf`，把课件里的文字和代码抽出来，再先给你中文整理版。
> </details>

下面是第二章 **Lecture 2 Basic Concepts and Structure of C++** 的整理，先中文，后英文。

**中文版**

**一、本章核心概念**

第二章主要介绍 C++ 程序的基本结构，包括如何创建 C++ 程序、`main()` 函数、头文件、命名空间、输入输出、注释、变量、语句、函数声明与函数定义等内容。

本章的重点是让我们先掌握一个 C++ 程序的基本框架，然后再进一步学习循环、类、对象等复杂内容。

**二、本章重点内容**

1. **C++ 程序的基本结构**

一个最基本的 C++ 程序通常包含：

```cpp
#include <iostream>

int main()
{
    using namespace std;

    statements;

    return 0;
}
```

其中：

- `#include <iostream>` 是预处理指令，用于引入输入输出相关功能；
- `int main()` 是主函数头；
- `{}` 中的是函数体；
- 每条完整语句通常以分号 `;` 结束；
- `return 0;` 表示程序正常结束。

C++ 程序从 `main()` 函数开始执行。普通 C++ 程序必须有一个 `main()` 函数。

2. **C++ 区分大小写**

C++ 是大小写敏感的语言。

例如：

```cpp
cout
```

不能写成：

```cpp
Cout
COUT
```

否则编译器会认为它们是不同的标识符。

3. **注释**

C++ 中可以使用 `//` 写单行注释。

```cpp
// This is a comment.
```

注释用于解释代码，编译器会忽略注释内容。

4. **预处理指令与头文件**

```cpp
#include <iostream>
```

表示把 `iostream` 头文件包含进程序中。`iostream` 提供了 `cin`、`cout`、`endl` 等输入输出功能。

常见头文件命名方式：

- 旧式 C++ 头文件：`iostream.h`
- C 语言头文件：`math.h`
- 新式 C++ 头文件：`iostream`
- 转换后的 C 头文件：`cmath`

新式 C++ 头文件通常没有 `.h`，并且相关内容放在 `std` 命名空间中。

5. **命名空间 namespace**

```cpp
using namespace std;
```

表示使用标准命名空间 `std` 中的名称。

如果不写这句，也可以使用完整名称：

```cpp
std::cout << "Hello";
std::cout << std::endl;
```

命名空间的作用是避免名称冲突。例如两个库中都可能有 `wanda()` 函数，可以用：

```cpp
Microflop::wanda();
Piscine::wanda();
```

区分不同命名空间中的函数。

6. **使用 cout 输出**

`cout` 是 C++ 标准输出对象。

```cpp
cout << "Hello C++";
```

`<<` 是插入运算符，表示把右边的内容插入到输出流中。

可以连续输出多个内容：

```cpp
cout << "Now you have " << carrots << " carrots." << endl;
```

7. **endl 与 \n**

`endl` 表示换行，并刷新输出缓冲区。

```cpp
cout << endl;
```

`\n` 也表示换行。

```cpp
cout << "What's next?\n";
```

两者都能换行，但 `endl` 还会刷新缓冲区。

8. **C++ 代码格式**

C++ 中语句结束主要依靠分号，而不是换行。因此一条语句可以分多行写，或者多条语句写在一行。

但推荐代码风格是：

- 每条语句单独一行；
- 函数的左右花括号各占一行；
- 函数体内语句缩进；
- 函数名和括号之间不加空格。

9. **Token 与空白字符**

Token 是代码中不可再分的基本元素，例如关键字、变量名、运算符、括号等。

空格、Tab、换行统称为空白字符，用于分隔 token。

例如：

```cpp
return0;     // 错误
return 0;    // 正确
return(0);   // 正确
intmain();   // 错误
int main();  // 正确
```

10. **cin 输入**

`cin` 是 C++ 标准输入对象。

```cpp
cin >> carrots;
```

`>>` 是提取运算符，表示从输入流中读取数据，并存入变量 `carrots`。

11. **函数**

函数是 C++ 程序的基本模块。一个程序可以由多个函数组成。

函数通常包括：

- 函数返回类型；
- 函数名；
- 参数列表；
- 函数体。

通用形式：

```cpp
type functionname(argumentlist)
{
    statements;
}
```

12. **函数原型**

函数原型用于告诉编译器函数的返回类型和参数类型。

例如：

```cpp
double sqrt(double);
```

表示 `sqrt()` 函数接收一个 `double` 参数，并返回一个 `double` 类型的值。

函数原型只说明接口，函数定义才包含具体实现。

13. **库函数与自定义函数**

C++ 标准库提供了许多函数，例如 `sqrt()`。

如果标准库函数不能满足需求，程序员可以自己定义函数。

14. **void 函数**

`void` 表示函数没有返回值。

```cpp
void simon(int n)
{
    cout << "Simon says touch your toes " << n << " times." << endl;
}
```

调用 `void` 函数时不能把它的结果赋值给变量。

15. **关键字**

关键字是 C++ 语言保留的特殊词，不能用作变量名或函数名。

例如：

```cpp
int
void
return
double
```

`main` 不是关键字，但它是 C++ 程序要求的主函数名，因此不建议把 `main` 当作变量名使用。

**三、PPT 中的代码整理**

**代码 1：第一个 C++ 程序**

```cpp
// myfirst.cpp -- displays a message
#include <iostream>

int main()
{
    using namespace std;

    cout << "Come up and C++ me some time.";
    cout << endl;
    cout << "You won’t regret it!" << endl;

    return 0;
}
```

中文解释：

- `#include <iostream>` 引入输入输出库；
- `int main()` 是程序入口；
- `using namespace std;` 让程序可以直接使用 `cout` 和 `endl`；
- `cout` 用于输出内容；
- `endl` 用于换行；
- `return 0;` 表示程序正常结束。

输出结果：

```text
Come up and C++ me some time.
You won’t regret it!
```

**代码 2：cout 连续输出与 cin 输入**

```cpp
// getinfo.cpp -- input and output
#include <iostream>

int main()
{
    using namespace std;

    int carrots;

    cout << "How many carrots do you have?" << endl;
    cin >> carrots;

    cout << "Here are two more. ";
    carrots = carrots + 2;

    cout << "Now you have " << carrots << " carrots." << endl;

    return 0;
}
```

中文解释：

- `int carrots;` 声明一个整型变量；
- `cin >> carrots;` 从键盘输入一个整数；
- `carrots = carrots + 2;` 将变量值增加 2；
- `cout << ... << carrots << ...` 可以把字符串和变量组合输出。

体现知识点：

- 变量声明；
- 标准输入 `cin`；
- 标准输出 `cout`；
- 赋值语句；
- 连续输出。

**代码 3：使用 sqrt() 库函数**

```cpp
// sqrt.cpp -- using the sqrt() function
#include <iostream>
#include <cmath>

int main()
{
    using namespace std;

    double area;

    cout << "Enter the floor area, in square feet, of your home: ";
    cin >> area;

    double side;
    side = sqrt(area);

    cout << "That’s the equivalent of a square "
         << side
         << " feet to the side."
         << endl;

    cout << "How fascinating!" << endl;

    return 0;
}
```

中文解释：

- `#include <cmath>` 引入数学函数库；
- `sqrt(area)` 用于计算平方根；
- `double` 表示双精度浮点数；
- 该程序输入房屋面积，计算等面积正方形的边长。

注意：PPT 中这段代码最后的 `return 0` 少了分号，实际代码应写成 `return 0;`。

体现知识点：

- 数学库函数；
- 函数原型；
- `double` 类型；
- 输入输出；
- 多行连续输出。

**代码 4：自定义 void 函数**

```cpp
// ourfunc.cpp -- defining your own function
#include <iostream>

void simon(int); // function prototype for simon()

int main()
{
    using namespace std;

    simon(3);

    cout << "Pick an integer: ";
    int count;
    cin >> count;

    simon(count);

    cout << "Done!" << endl;

    return 0;
}

void simon(int n)
{
    using namespace std;

    cout << "Simon says touch your toes "
         << n
         << " times."
         << endl;
}
```

中文解释：

- `void simon(int);` 是函数原型；
- `simon(3);` 调用函数，并把 `3` 传给参数 `n`；
- `void` 表示函数没有返回值；
- `int n` 表示函数接收一个整数参数；
- 函数定义写在 `main()` 之后，但因为前面有函数原型，所以编译器可以识别。

体现知识点：

- 自定义函数；
- 函数原型；
- 函数调用；
- 参数传递；
- `void` 返回类型。

**代码 5：带返回值的自定义函数**

```cpp
// convert.cpp -- converts stone to pounds
#include <iostream>

int stonetolb(int); // function prototype

int main()
{
    using namespace std;

    int stone;

    cout << "Enter the weight in stone: ";
    cin >> stone;

    int pounds = stonetolb(stone);

    cout << stone << " stone = ";
    cout << pounds << " pounds." << endl;

    return 0;
}

int stonetolb(int sts)
{
    return 14 * sts;
}
```

中文解释：

- `int stonetolb(int);` 表示函数接收一个 `int` 参数，并返回一个 `int` 值；
- `stonetolb(stone)` 调用函数，把 stone 转换成 pounds；
- `return 14 * sts;` 返回计算结果；
- 1 stone 等于 14 pounds。

体现知识点：

- 有返回值函数；
- `return` 语句；
- 参数传递；
- 函数调用结果赋值；
- 简单单位转换。

**代码 6：把 using namespace std 放在全局位置**

```cpp
// ourfunc1.cpp -- repositioning the using directive
#include <iostream>

using namespace std;

void simon(int);

int main()
{
    simon(3);

    cout << "Pick an integer: ";
    int count;
    cin >> count;

    simon(count);

    cout << "Done!" << endl;

    return 0;
}

void simon(int n)
{
    cout << "Simon says touch your toes "
         << n
         << " times."
         << endl;
}
```

中文解释：

- `using namespace std;` 放在所有函数外面，会影响本文件中后面的所有函数；
- 因此 `main()` 和 `simon()` 中都可以直接使用 `cout`、`cin`、`endl`；
- 这种写法方便，但大型项目中可能增加命名冲突风险。

**四、易混点**

- `#include <iostream>` 不是普通语句，不需要分号。
- `main()` 是程序入口，不是关键字，但普通程序必须有。
- `cout` 用 `<<`，`cin` 用 `>>`。
- `endl` 和 `\n` 都可以换行，但 `endl` 还会刷新缓冲区。
- 函数原型不是函数定义，它只说明函数接口。
- `void` 函数没有返回值，不能写成 `x = simon(3);`。
- C++ 语句通常以分号结束，换行不能代替分号。
- 关键字不能作为变量名或函数名。

**五、可写进实验报告的英文总结思路**

本章学习了 C++ 程序的基本结构，包括预处理指令、头文件、`main()` 函数、命名空间、输入输出语句、变量声明和函数。通过第一个 C++ 程序，我了解了程序从 `main()` 函数开始执行，每条语句通常以分号结束，并且可以使用 `cout` 输出信息、使用 `cin` 接收键盘输入。

本章还介绍了函数的基本概念。函数是 C++ 程序的重要组成模块，可以分为有返回值函数和无返回值函数。函数原型用于提前告诉编译器函数的返回类型和参数类型，而函数定义则包含函数的具体实现。通过 `simon()` 和 `stonetolb()` 示例，我理解了函数声明、函数调用、参数传递和返回值的基本用法。

---

**English Version**

**1. Core Concepts**

Chapter 2 introduces the basic concepts and structure of a C++ program. It covers how to create a C++ program, the general program format, the `#include` directive, the `main()` function, output with `cout`, comments, `endl`, variables, input with `cin`, and simple functions.

The main purpose of this chapter is to help us understand the basic framework of a C++ program before learning more advanced topics such as loops, classes, and objects.

**2. Key Points**

1. **Basic Structure of a C++ Program**

A simple C++ program usually has the following structure:

```cpp
#include <iostream>

int main()
{
    using namespace std;

    statements;

    return 0;
}
```

Explanation:

- `#include <iostream>` is a preprocessor directive for input and output;
- `int main()` is the function header of the main function;
- the code inside `{}` is the function body;
- each complete statement usually ends with a semicolon;
- `return 0;` means that the program ends successfully.

A C++ program starts execution from the `main()` function.

2. **C++ Is Case Sensitive**

C++ distinguishes uppercase and lowercase letters.

For example, `cout`, `Cout`, and `COUT` are different identifiers.

3. **Comments**

C++ uses `//` for single-line comments.

```cpp
// This is a comment.
```

Comments are ignored by the compiler and are used to explain the code.

4. **Header Files and the #include Directive**

```cpp
#include <iostream>
```

This includes the `iostream` header file, which provides input and output facilities such as `cin`, `cout`, and `endl`.

Common header file styles include:

- old-style C++ header: `iostream.h`;
- C header: `math.h`;
- new-style C++ header: `iostream`;
- converted C header: `cmath`.

New-style C++ headers usually have no `.h` extension and place their contents in the `std` namespace.

5. **Namespace**

```cpp
using namespace std;
```

This directive allows us to use names from the standard namespace directly.

Without it, we can write:

```cpp
std::cout << "Hello";
std::cout << std::endl;
```

Namespaces help avoid name conflicts.

6. **Output with cout**

`cout` is the standard output object in C++.

```cpp
cout << "Hello C++";
```

The `<<` operator inserts data into the output stream.

We can output several items in one statement:

```cpp
cout << "Now you have " << carrots << " carrots." << endl;
```

7. **endl and \n**

`endl` starts a new line and flushes the output buffer.

```cpp
cout << endl;
```

`\n` also starts a new line.

```cpp
cout << "What's next?\n";
```

8. **Source Code Formatting**

In C++, semicolons mark the end of statements, not line breaks. Therefore, one statement can be written on several lines, and several statements can be written on one line.

Recommended style:

- one statement per line;
- braces for a function on separate lines;
- indent statements inside a function;
- no whitespace between a function name and its parentheses.

9. **Tokens and White Space**

Tokens are the smallest indivisible elements in code, such as keywords, identifiers, operators, and parentheses.

White space includes spaces, tabs, and newlines.

Examples:

```cpp
return0;     // invalid
return 0;    // valid
return(0);   // valid
intmain();   // invalid
int main();  // valid
```

10. **Input with cin**

`cin` is the standard input object in C++.

```cpp
cin >> carrots;
```

The `>>` operator extracts data from the input stream and stores it in a variable.

11. **Functions**

Functions are the basic modules of C++ programs.

A function usually includes:

- return type;
- function name;
- argument list;
- function body.

General form:

```cpp
type functionname(argumentlist)
{
    statements;
}
```

12. **Function Prototype**

A function prototype tells the compiler the return type and argument types of a function.

```cpp
double sqrt(double);
```

This means that `sqrt()` takes a `double` argument and returns a `double` value.

A function prototype describes the interface, while a function definition contains the actual code.

13. **Library Functions and User-Defined Functions**

C++ provides many standard library functions, such as `sqrt()`. Programmers can also define their own functions when needed.

14. **void Functions**

`void` means that a function has no return value.

```cpp
void simon(int n)
{
    cout << "Simon says touch your toes " << n << " times." << endl;
}
```

A `void` function cannot be used as a value in an assignment.

15. **Keywords**

Keywords are reserved words in C++ and cannot be used as variable or function names.

Examples:

```cpp
int
void
return
double
```

`main` is not a keyword, but it is the required name of the main function, so it should not be used as a variable name.

**3. Code from the PPT**

**Example 1: First C++ Program**

```cpp
// myfirst.cpp -- displays a message
#include <iostream>

int main()
{
    using namespace std;

    cout << "Come up and C++ me some time.";
    cout << endl;
    cout << "You won’t regret it!" << endl;

    return 0;
}
```

Explanation:

- `#include <iostream>` includes the input and output library;
- `int main()` is the program entry point;
- `using namespace std;` allows direct use of `cout` and `endl`;
- `cout` outputs text;
- `endl` starts a new line;
- `return 0;` means successful program termination.

Output:

```text
Come up and C++ me some time.
You won’t regret it!
```

**Example 2: Input and Output**

```cpp
// getinfo.cpp -- input and output
#include <iostream>

int main()
{
    using namespace std;

    int carrots;

    cout << "How many carrots do you have?" << endl;
    cin >> carrots;

    cout << "Here are two more. ";
    carrots = carrots + 2;

    cout << "Now you have " << carrots << " carrots." << endl;

    return 0;
}
```

Explanation:

- `int carrots;` declares an integer variable;
- `cin >> carrots;` reads an integer from the keyboard;
- `carrots = carrots + 2;` increases the value by 2;
- `cout` can combine strings and variables in one output statement.

**Example 3: Using the sqrt() Function**

```cpp
// sqrt.cpp -- using the sqrt() function
#include <iostream>
#include <cmath>

int main()
{
    using namespace std;

    double area;

    cout << "Enter the floor area, in square feet, of your home: ";
    cin >> area;

    double side;
    side = sqrt(area);

    cout << "That’s the equivalent of a square "
         << side
         << " feet to the side."
         << endl;

    cout << "How fascinating!" << endl;

    return 0;
}
```

Explanation:

- `#include <cmath>` includes mathematical functions;
- `sqrt(area)` calculates the square root of `area`;
- `double` represents a floating-point number;
- the program calculates the side length of a square with the same area.

Note: In the PPT, `return 0` misses a semicolon. The correct form is `return 0;`.

**Example 4: User-Defined void Function**

```cpp
// ourfunc.cpp -- defining your own function
#include <iostream>

void simon(int);

int main()
{
    using namespace std;

    simon(3);

    cout << "Pick an integer: ";
    int count;
    cin >> count;

    simon(count);

    cout << "Done!" << endl;

    return 0;
}

void simon(int n)
{
    using namespace std;

    cout << "Simon says touch your toes "
         << n
         << " times."
         << endl;
}
```

Explanation:

- `void simon(int);` is a function prototype;
- `simon(3);` calls the function and passes `3` to `n`;
- `void` means the function has no return value;
- `int n` means the function takes one integer argument.

**Example 5: User-Defined Function with a Return Value**

```cpp
// convert.cpp -- converts stone to pounds
#include <iostream>

int stonetolb(int);

int main()
{
    using namespace std;

    int stone;

    cout << "Enter the weight in stone: ";
    cin >> stone;

    int pounds = stonetolb(stone);

    cout << stone << " stone = ";
    cout << pounds << " pounds." << endl;

    return 0;
}

int stonetolb(int sts)
{
    return 14 * sts;
}
```

Explanation:

- `int stonetolb(int);` declares a function that takes an `int` and returns an `int`;
- `stonetolb(stone)` converts stones to pounds;
- `return 14 * sts;` returns the result;
- one stone equals 14 pounds.

**Example 6: Placing using namespace std Globally**

```cpp
// ourfunc1.cpp -- repositioning the using directive
#include <iostream>

using namespace std;

void simon(int);

int main()
{
    simon(3);

    cout << "Pick an integer: ";
    int count;
    cin >> count;

    simon(count);

    cout << "Done!" << endl;

    return 0;
}

void simon(int n)
{
    cout << "Simon says touch your toes "
         << n
         << " times."
         << endl;
}
```

Explanation:

- Placing `using namespace std;` outside all functions makes it available to all following functions in the file;
- both `main()` and `simon()` can directly use `cout`, `cin`, and `endl`;
- this is convenient, but in large programs it may increase the risk of name conflicts.

**4. Common Confusing Points**

- `#include <iostream>` is not a normal statement and does not need a semicolon.
- `main()` is the entry point of a program.
- `cout` uses `<<`, while `cin` uses `>>`.
- Both `endl` and `\n` start a new line, but `endl` also flushes the buffer.
- A function prototype is not a function definition.
- A `void` function has no return value.
- C++ statements usually end with semicolons.
- Keywords cannot be used as variable or function names.

**5. Report Summary**

In this chapter, I learned the basic structure of a C++ program, including preprocessor directives, header files, the `main()` function, namespaces, input and output statements, variable declarations, and functions. Through the first C++ program, I understood that program execution starts from the `main()` function, each statement usually ends with a semicolon, and `cout` and `cin` are used for output and input.

This chapter also introduced the basic concept of functions. Functions are important modules in C++ programs. They can be divided into functions with return values and functions without return values. A function prototype tells the compiler the return type and argument types of a function, while a function definition contains the actual implementation. Through the examples of `simon()` and `stonetolb()`, I learned how to declare functions, call functions, pass arguments, and return values.

> 下面进行第三章，依旧是先中文再翻译成英文

<details><summary>1 previous message</summary>

> 继续第三章。我先提取 `Lecture 3 Data Type and Dealing with Data.pdf` 的内容，重点会放在数据类型、变量、常量、类型转换和代码示例上。
> </details>

下面是第三章 **Lecture 3 Data Type and Dealing with Data** 的整理，先中文，后英文。

**中文版**

**一、本章核心概念**

第三章主要讲 C++ 中的数据类型和数据处理。面向对象程序设计的本质之一，就是设计和扩展自己的数据类型。但在自定义类型之前，必须先理解 C++ 内置的数据类型。

C++ 的内置类型主要分为两大类：

- **基本类型**：整数类型、浮点类型、字符类型、布尔类型等；
- **复合类型**：数组、字符串、指针、结构体等，后续章节会详细讲。

本章重点是变量命名、整数类型、字符类型、布尔类型、`const` 常量、浮点数、算术运算符、自动类型转换和强制类型转换。

**二、本章重点内容**

1. **变量的作用**

程序通常需要存储数据。存储一个数据时，需要知道三件事：

- 数据存储在哪里；
- 存储的值是什么；
- 数据属于什么类型。

例如：

```cpp
int count;
count = 5;
```

这表示定义一个整型变量 `count`，并把值 `5` 存入其中。

2. **变量命名规则**

C++ 鼓励使用有意义的变量名，例如 `cost_of_trip` 或 `costOfTrip`。

命名规则：

- 只能使用字母、数字和下划线 `_`；
- 第一个字符不能是数字；
- 区分大小写；
- 不能使用 C++ 关键字；
- 不建议使用以下划线开头的名字，因为有些名称被系统保留；
- C++ 本身不限制变量名长度，但具体平台可能有限制。

示例：

```cpp
int poodle;      // 正确
int Poodle;      // 正确，与 poodle 不同
int POODLE;      // 正确
Int terrier;     // 错误，必须写 int
int my_stars3;   // 正确
int 4ever;       // 错误，不能以数字开头
int double;      // 错误，double 是关键字
int honky-tonk;  // 错误，不能使用连字符
```

3. **bit 与 byte**

`bit` 是计算机存储的最小单位，只能表示 `0` 或 `1`。

8 个 bit 通常组成 1 个 byte。一个 8 位单元可以表示 256 种不同状态。

常见大小关系：

- 8 bit：256 种状态；
- 16 bit：65,536 种状态；
- 32 bit：约 42 亿种状态；
- 64 bit：非常大的数值范围。

C++ 中的 byte 至少要能容纳基本字符集。多数系统中 1 byte = 8 bit，但标准并不强制所有系统都必须如此。

4. **整数类型**

整数是不带小数部分的数字，如 `2`、`-3`、`0`。

C++ 的基本整数类型按宽度大致包括：

```cpp
char
short
int
long
long long
```

每种整数类型都有有符号和无符号版本。

C++ 对整数类型大小有最低要求：

- `short` 至少 16 位；
- `int` 至少和 `short` 一样大；
- `long` 至少 32 位，并且至少和 `int` 一样大；
- `long long` 至少 64 位，并且至少和 `long` 一样大。

5. **sizeof 与 climits**

`sizeof` 用于查看类型或变量占用的字节数。

```cpp
sizeof(int)
sizeof n_short
```

`<climits>` 头文件定义了整数类型的范围常量，例如：

- `INT_MAX`：`int` 最大值；
- `INT_MIN`：`int` 最小值；
- `SHRT_MAX`：`short` 最大值；
- `LONG_MAX`：`long` 最大值；
- `LLONG_MAX`：`long long` 最大值；
- `CHAR_BIT`：一个 byte 中有多少 bit。

6. **初始化**

初始化就是在声明变量时赋初值。

```cpp
int uncles = 5;
int aunts = uncles;
int chairs = aunts + uncles + 4;
```

这比先声明再赋值更直接，也更安全。

7. **无符号整数类型**

无符号类型不能表示负数，但能表示更大的非负数。

```cpp
unsigned short change;
unsigned int rovert;
unsigned quarterback;       // 等价于 unsigned int
unsigned long gone;
unsigned long long lang_lang;
```

如果 `short` 范围是 `-32768` 到 `32767`，那么 `unsigned short` 通常可以表示 `0` 到 `65535`。

8. **整数溢出**

当数值超过类型范围时会发生溢出。例如：

- `short` 最大值 `32767` 再加 1，可能变成 `-32768`；
- `unsigned short` 的 `0` 减 1，可能变成 `65535`。

这说明选择合适的数据类型很重要。

9. **如何选择整数类型**

一般情况下，如果没有特殊需求，使用 `int`。因为 `int` 通常是计算机处理起来最自然、最高效的整数类型。

10. **整型字面值**

C++ 支持三种整数进制写法：

```cpp
42      // 十进制
042     // 八进制
0x42    // 十六进制
```

规则：

- 以 `1-9` 开头：十进制；
- 以 `0` 开头：八进制；
- 以 `0x` 或 `0X` 开头：十六进制。

例如：

```cpp
int chest = 42;    // 十进制 42
int waist = 0x42;  // 十六进制，等于十进制 66
int inseam = 042;  // 八进制，等于十进制 34
```

11. **char 类型**

`char` 用于存储字符，但本质上也是一种整数类型，因为字符在计算机中是用数字编码表示的。

例如 ASCII 编码中：

- `'M'` 的编码是 77；
- `'N'` 的编码是 78；
- `'A'` 的编码是 65；
- `'a'` 的编码是 97。

字符字面值使用单引号：

```cpp
char ch = 'M';
```

字符串使用双引号：

```cpp
"Hello"
```

12. **cout.put() 成员函数**

`cout.put()` 用于输出单个字符。

```cpp
cout.put(ch);
cout.put('!');
```

这里的 `.` 是成员运算符，表示调用对象 `cout` 的成员函数 `put()`。

这是本章中接触到的一个面向对象概念：对象可以通过成员函数完成操作。

13. **转义序列**

转义序列用于表示一些特殊字符。

常见转义序列：

```cpp
\n    换行
\t    制表符
\a    响铃
\b    退格
\"    双引号
\'    单引号
\\    反斜杠
```

示例：

```cpp
cout << "Ben \"Buggsie\" Hacker\nwas here!\n";
```

输出：

```text
Ben "Buggsie" Hacker
was here!
```

14. **signed char 与 unsigned char**

`char` 默认是否有符号由具体实现决定。如果需要明确，可以写：

```cpp
signed char snark;
unsigned char bar;
```

通常：

- `signed char` 范围是 `-128` 到 `127`；
- `unsigned char` 范围是 `0` 到 `255`。

15. **bool 类型**

`bool` 表示布尔值，只能取：

```cpp
true
false
```

示例：

```cpp
bool is_ready = true;
```

C++ 中：

- `true` 可以转换为 `1`；
- `false` 可以转换为 `0`；
- 非零数值转换为 `true`；
- 零转换为 `false`。

```cpp
int ans = true;       // ans = 1
int promise = false;  // promise = 0
bool start = -100;    // true
bool stop = 0;        // false
```

16. **const 常量**

`const` 用于定义符号常量。

```cpp
const int Months = 12;
```

定义后，`Months` 的值不能再被修改。

一般形式：

```cpp
const type name = value;
```

相比 `#define`，`const` 更符合 C++ 风格，也有类型检查。

17. **浮点数**

浮点数用于表示带小数的数值。

C++ 浮点类型包括：

```cpp
float
double
long double
```

浮点数字面值有两种写法：

```cpp
12.34
0.012
1.23e+4
1.23E-4
```

默认浮点常量是 `double` 类型。

后缀规则：

```cpp
1.23f     // float
2.345E28  // double
2.2L      // long double
```

浮点数优点：

- 可以表示小数；
- 可以表示非常大或非常小的数。

缺点：

- 运算通常比整数慢；
- 可能产生精度误差。

18. **算术运算符**

C++ 提供五种基本算术运算符：

```cpp
+   加法
-   减法
*   乘法
/   除法
%   取模
```

示例：

```cpp
int a = 2 + 3;
```

其中 `2` 和 `3` 是操作数，`+` 是运算符，`2 + 3` 是表达式。

19. **运算符优先级与结合性**

乘法、除法、取模优先级高于加法和减法。

```cpp
3 + 4 * 5
```

结果是 `23`，不是 `35`。

当两个运算符优先级相同，例如 `/` 和 `*`，则根据结合性决定计算顺序。通常算术运算符从左到右结合。

```cpp
float logs = 120 / 4 * 5;  // 结果是 150
```

20. **整数除法与浮点除法**

如果 `/` 两边都是整数，执行整数除法，小数部分会被舍弃。

```cpp
5 / 2     // 结果是 2
```

如果至少一个操作数是浮点数，则执行浮点除法。

```cpp
5.0 / 2   // 结果是 2.5
```

21. **取模运算符 %**

`%` 返回整数除法的余数。

```cpp
17 % 5    // 结果是 2
```

注意：`%` 通常用于整数，适合处理单位换算、判断奇偶、循环周期等问题。

22. **类型转换**

C++ 会在以下情况进行类型转换：

- 把一种算术类型赋值给另一种类型变量；
- 表达式中混合不同类型；
- 函数参数传递；
- 显式强制类型转换。

23. **初始化和赋值中的转换**

例如：

```cpp
long so_long;
short thirty = 30;
so_long = thirty;
```

把 `short` 赋给 `long`，通常是安全的，因为范围变大。

但把大范围类型赋给小范围类型可能丢失数据。

24. **列表初始化与窄化转换**

C++11 的 `{}` 初始化不允许窄化转换。

```cpp
char c1 {31325};  // 错误，char 装不下
char c2 {66};     // 正确
```

如果变量不是常量，即使当前值能放入目标类型，也可能不允许：

```cpp
int x = 66;
char c4 = {x};    // 错误，x 不是常量
```

25. **表达式中的自动转换**

在表达式中，`bool`、`char`、`signed char`、`unsigned char`、`short` 通常会先提升为 `int`，这叫整型提升。

```cpp
short chickens = 20;
short ducks = 35;
short fowl = chickens + ducks;
```

计算 `chickens + ducks` 时，两个 `short` 会先转换成 `int`，计算完成后再赋给 `short`。

混合类型运算时，较小类型通常转换为较大类型。例如：

```cpp
6.0 / 2
```

因为 `6.0` 是 `double`，所以 `2` 会转换为 `double`。

26. **强制类型转换**

强制类型转换用于显式指定转换类型。

C 风格：

```cpp
(long) thorn
```

C++ 风格：

```cpp
long(thorn)
```

示例：

```cpp
cout << int('Q');
```

这会输出字符 `'Q'` 对应的整数编码。

27. **auto 自动类型推导**

C++11 引入 `auto`，可以根据初始化值自动推导变量类型。

```cpp
auto n = 100;      // int
auto x = 1.5;      // double
auto y = 1.3e12L;  // long double
```

**三、PPT 中的代码整理**

**代码 1：查看整数类型范围**

```cpp
// limits.cpp -- some integer limits
#include <iostream>
#include <climits>

int main()
{
    using namespace std;

    int n_int = INT_MAX;
    short n_short = SHRT_MAX;
    long n_long = LONG_MAX;
    long long n_llong = LLONG_MAX;

    cout << "int is " << sizeof(int) << " bytes." << endl;
    cout << "short is " << sizeof n_short << " bytes." << endl;
    cout << "long is " << sizeof n_long << " bytes." << endl;
    cout << "long long is " << sizeof n_llong << " bytes." << endl;

    cout << endl;
    cout << "Maximum values:" << endl;
    cout << "int: " << n_int << endl;
    cout << "short: " << n_short << endl;
    cout << "long: " << n_long << endl;
    cout << "long long: " << n_llong << endl << endl;

    cout << "Minimum int value = " << INT_MIN << endl;
    cout << "Bits per byte = " << CHAR_BIT << endl;

    return 0;
}
```

说明：

- `<climits>` 提供整数类型范围；
- `sizeof` 查看类型或变量占用字节数；
- `INT_MAX`、`SHRT_MAX` 等是符号常量；
- 不同系统输出可能不同。

**代码 2：整数溢出**

```cpp
// exceed.cpp -- exceeding some integer limits
#include <iostream>
#define ZERO 0
#include <climits>

int main()
{
    using namespace std;

    short sam = SHRT_MAX;
    unsigned short sue = sam;

    cout << "Sam has " << sam << " dollars and Sue has " << sue;
    cout << " dollars deposited." << endl
         << "Add $1 to each account." << endl << "Now ";

    sam = sam + 1;
    sue = sue + 1;

    cout << "Sam has " << sam << " dollars and Sue has " << sue;
    cout << " dollars deposited.\nPoor Sam!" << endl;

    sam = ZERO;
    sue = ZERO;

    cout << "Sam has " << sam << " dollars and Sue has " << sue;
    cout << " dollars deposited." << endl;
    cout << "Take $1 from each account." << endl << "Now ";

    sam = sam - 1;
    sue = sue - 1;

    cout << "Sam has " << sam << " dollars and Sue has " << sue;
    cout << " dollars deposited." << endl << "Lucky Sue!" << endl;

    return 0;
}
```

说明：

- `short` 超过最大值后会溢出；
- `unsigned short` 小于 0 后会回绕到最大值；
- 展示了有符号整数和无符号整数的区别。

**代码 3：十进制、八进制、十六进制**

```cpp
// hexoct1.cpp -- shows hex and octal literals
#include <iostream>

int main()
{
    using namespace std;

    int chest = 42;
    int waist = 0x42;
    int inseam = 042;

    cout << "Monsieur cuts a striking figure!\n";
    cout << "chest = " << chest << " (42 in decimal)\n";
    cout << "waist = " << waist << " (0x42 in hex)\n";
    cout << "inseam = " << inseam << " (042 in octal)\n";

    return 0;
}
```

输出：

```text
chest = 42
waist = 66
inseam = 34
```

说明：

- `42` 是十进制；
- `0x42` 是十六进制；
- `042` 是八进制；
- `cout` 默认按十进制输出整数。

**代码 4：char 类型输入输出**

```cpp
// chartype.cpp -- the char type
#include <iostream>

int main()
{
    using namespace std;

    char ch;

    cout << "Enter a character: " << endl;
    cin >> ch;

    cout << "Hola! ";
    cout << "Thank you for the " << ch
         << " character." << endl;

    return 0;
}
```

说明：

- `char` 用于存储单个字符；
- `cin >> ch` 从键盘读取一个字符；
- `cout` 输出字符内容。

**代码 5：char 与 int 的关系**

```cpp
// morechar.cpp -- the char type and int type contrasted
#include <iostream>

int main()
{
    using namespace std;

    char ch = 'M';
    int i = ch;

    cout << "The ASCII code for " << ch << " is " << i << endl;
    cout << "Add one to the character code:" << endl;

    ch = ch + 1;
    i = ch;

    cout << "The ASCII code for " << ch << " is " << i << endl;

    cout << "Displaying char ch using cout.put(ch): ";
    cout.put(ch);
    cout.put('!');

    cout << endl << "Done" << endl;

    return 0;
}
```

说明：

- 字符本质上以整数编码存储；
- `'M'` 的 ASCII 码是 77；
- `'M' + 1` 变成 `'N'`；
- `cout.put()` 可以输出单个字符。

**代码 6：转义序列**

```cpp
// bondini.cpp -- using escape sequences
#include <iostream>

int main()
{
    using namespace std;

    cout << "\aOperation \"HyperHype\" is now activated!\n";
    cout << "Enter your agent code:________\b\b\b\b\b\b\b\b";

    long code;
    cin >> code;

    cout << "\aYou entered " << code << "...\n";
    cout << "\aCode verified! Proceed with Plan Z3!\n";

    return 0;
}
```

说明：

- `\a` 表示响铃；
- `\"` 表示输出双引号；
- `\n` 表示换行；
- `\b` 表示退格；
- PPT 中这段代码最后 `return 0` 少了分号，实际应写 `return 0;`。

**四、易混点**

- `char` 是字符类型，但本质上也是整数类型。
- `'A'` 是字符，`"A"` 是字符串。
- `042` 不是十进制 42，而是八进制。
- `0x42` 是十六进制。
- `endl`、`'\n'`、`"\n"` 都可以换行。
- `int` 通常是默认首选整数类型。
- 无符号类型不能表示负数，溢出时可能回绕。
- `const` 常量必须初始化，并且之后不能修改。
- 浮点数可能存在精度误差。
- 整数除法会丢弃小数部分。
- `{}` 列表初始化不允许窄化转换。
- 强制类型转换不会改变原变量，只会生成一个转换后的临时值。

**五、可写进实验报告的中文总结**

本章主要学习了 C++ 中的数据类型和数据处理方法。通过本章学习，我了解了变量用于存储数据，而变量声明中的类型决定了数据的存储方式和取值范围。C++ 提供了多种基本数据类型，包括整数类型、字符类型、布尔类型和浮点类型，不同类型适合不同的数据需求。

本章还介绍了整数类型的大小、取值范围以及有符号和无符号整数的区别。通过 `sizeof` 和 `<climits>`，可以查看不同整数类型在当前系统中的存储大小和范围。通过整数溢出的例子，我认识到选择合适的数据类型对程序的正确性非常重要。

此外，本章学习了字符类型、转义序列、`bool` 类型、`const` 常量、浮点数、算术运算符和类型转换。通过这些内容，我对 C++ 如何存储和处理基本数据有了更清晰的理解，也为后续学习数组、指针、结构体和类等复杂数据类型打下了基础。

---

**English Version**

**1. Core Concepts**

Chapter 3 mainly introduces data types and data handling in C++. One important part of object-oriented programming is designing and extending our own data types. Before creating user-defined types, we need to understand the built-in types provided by C++.

C++ built-in types can be divided into two groups:

- **fundamental types**, such as integers, floating-point numbers, characters, and Boolean values;
- **compound types**, such as arrays, strings, pointers, and structures.

This chapter focuses on variable naming, integer types, character types, Boolean type, `const` constants, floating-point numbers, arithmetic operators, automatic type conversions, and forced type conversions.

**2. Key Points**

1. **Variables**

Programs often need to store data. To store data, a program needs to know:

- where the data is stored;
- what value is stored;
- what type of data is stored.

Example:

```cpp
int count;
count = 5;
```

This declares an integer variable named `count` and stores the value `5` in it.

2. **Rules for Naming Variables**

C++ encourages meaningful variable names, such as `cost_of_trip` or `costOfTrip`.

Rules:

- names can contain letters, digits, and underscores;
- the first character cannot be a digit;
- uppercase and lowercase letters are different;
- C++ keywords cannot be used as names;
- names beginning with underscores may be reserved;
- C++ itself does not limit name length, but some platforms may have limits.

Examples:

```cpp
int poodle;      // valid
int Poodle;      // valid and different from poodle
int POODLE;      // valid
Int terrier;     // invalid
int my_stars3;   // valid
int 4ever;       // invalid
int double;      // invalid
int honky-tonk;  // invalid
```

3. **Bits and Bytes**

A bit is the smallest unit of memory and can represent either `0` or `1`.

A byte usually consists of 8 bits. An 8-bit unit can represent 256 different combinations.

Common ranges:

- 8 bits: 256 combinations;
- 16 bits: 65,536 combinations;
- 32 bits: about 4.29 billion combinations;
- 64 bits: a very large range.

In C++, a byte must be large enough to hold the basic character set. On most systems, one byte is 8 bits.

4. **Integer Types**

Integers are numbers without fractional parts, such as `2`, `-3`, and `0`.

The basic integer types in C++ include:

```cpp
char
short
int
long
long long
```

Each type has signed and unsigned versions.

Minimum size requirements:

- `short` is at least 16 bits;
- `int` is at least as large as `short`;
- `long` is at least 32 bits and at least as large as `int`;
- `long long` is at least 64 bits and at least as large as `long`.

5. **sizeof and climits**

The `sizeof` operator reports the size of a type or variable in bytes.

```cpp
sizeof(int)
sizeof n_short
```

The `<climits>` header defines symbolic constants for integer limits, such as:

- `INT_MAX`;
- `INT_MIN`;
- `SHRT_MAX`;
- `LONG_MAX`;
- `LLONG_MAX`;
- `CHAR_BIT`.

6. **Initialization**

Initialization means assigning a value when declaring a variable.

```cpp
int uncles = 5;
int aunts = uncles;
int chairs = aunts + uncles + 4;
```

7. **Unsigned Integer Types**

Unsigned types cannot store negative values, but they can store larger non-negative values.

```cpp
unsigned short change;
unsigned int rovert;
unsigned quarterback;
unsigned long gone;
unsigned long long lang_lang;
```

If `short` ranges from `-32768` to `32767`, then `unsigned short` usually ranges from `0` to `65535`.

8. **Integer Overflow**

When a value goes beyond the range of its type, overflow occurs.

For example:

- adding 1 to the largest `short` value may produce `-32768`;
- subtracting 1 from an `unsigned short` value of `0` may produce `65535`.

9. **Choosing an Integer Type**

In general, if there is no special reason to choose another type, `int` should be used because it is usually the most natural and efficient integer type for the computer.

10. **Integer Literals**

C++ supports integer literals in three bases:

```cpp
42      // decimal
042     // octal
0x42    // hexadecimal
```

Rules:

- starts with `1-9`: decimal;
- starts with `0`: octal;
- starts with `0x` or `0X`: hexadecimal.

11. **The char Type**

`char` is used to store characters, but it is also an integer type because characters are stored as numeric codes.

Example:

```cpp
char ch = 'M';
```

Character literals use single quotation marks, while strings use double quotation marks.

12. **The cout.put() Member Function**

`cout.put()` outputs a single character.

```cpp
cout.put(ch);
cout.put('!');
```

The dot is the membership operator. It calls the member function `put()` of the object `cout`.

13. **Escape Sequences**

Escape sequences represent special characters.

Common examples:

```cpp
\n    newline
\t    tab
\a    alert
\b    backspace
\"    double quotation mark
\'    single quotation mark
\\    backslash
```

Example:

```cpp
cout << "Ben \"Buggsie\" Hacker\nwas here!\n";
```

Output:

```text
Ben "Buggsie" Hacker
was here!
```

14. **signed char and unsigned char**

The default signedness of `char` depends on the implementation. We can specify it explicitly:

```cpp
signed char snark;
unsigned char bar;
```

Usually:

- `signed char` ranges from `-128` to `127`;
- `unsigned char` ranges from `0` to `255`.

15. **The bool Type**

`bool` represents Boolean values:

```cpp
true
false
```

Example:

```cpp
bool is_ready = true;
```

In C++:

- `true` converts to `1`;
- `false` converts to `0`;
- nonzero values convert to `true`;
- zero converts to `false`.

16. **const Constants**

`const` defines a symbolic constant.

```cpp
const int Months = 12;
```

After initialization, the value of `Months` cannot be changed.

General form:

```cpp
const type name = value;
```

17. **Floating-Point Numbers**

Floating-point numbers represent values with fractional parts.

C++ has three floating-point types:

```cpp
float
double
long double
```

Floating-point literals can be written in decimal notation or E notation:

```cpp
12.34
0.012
1.23e+4
1.23E-4
```

By default, floating-point constants are type `double`.

Suffixes:

```cpp
1.23f     // float
2.345E28  // double
2.2L      // long double
```

Advantages:

- they can represent fractional values;
- they can represent a much wider range of values.

Disadvantages:

- operations may be slower than integer operations;
- precision may be lost.

18. **Arithmetic Operators**

C++ provides five basic arithmetic operators:

```cpp
+   addition
-   subtraction
*   multiplication
/   division
%   modulus
```

19. **Operator Precedence and Associativity**

Multiplication, division, and modulus have higher precedence than addition and subtraction.

```cpp
3 + 4 * 5
```

The result is `23`, not `35`.

When operators have the same precedence, associativity determines the order. Arithmetic operators usually associate from left to right.

20. **Integer Division and Floating-Point Division**

If both operands of `/` are integers, C++ performs integer division.

```cpp
5 / 2     // 2
```

If at least one operand is floating-point, C++ performs floating-point division.

```cpp
5.0 / 2   // 2.5
```

21. **The Modulus Operator**

The `%` operator returns the remainder of integer division.

```cpp
17 % 5    // 2
```

22. **Type Conversions**

C++ performs type conversions when:

- assigning one arithmetic type to another;
- combining mixed types in expressions;
- passing arguments to functions;
- using explicit type casts.

23. **List Initialization and Narrowing**

C++11 list initialization with `{}` does not allow narrowing conversions.

```cpp
char c1 {31325};  // invalid
char c2 {66};     // valid
```

24. **Automatic Conversions in Expressions**

In expressions, `bool`, `char`, `signed char`, `unsigned char`, and `short` are usually promoted to `int`.

```cpp
short chickens = 20;
short ducks = 35;
short fowl = chickens + ducks;
```

The addition is performed using `int`, and the result is then assigned back to `short`.

25. **Type Casts**

A type cast explicitly converts a value to another type.

C-style:

```cpp
(long) thorn
```

C++ style:

```cpp
long(thorn)
```

Example:

```cpp
cout << int('Q');
```

This displays the integer code of the character `'Q'`.

26. **auto Declarations**

C++11 introduced `auto`, which allows the compiler to deduce the type from the initializer.

```cpp
auto n = 100;      // int
auto x = 1.5;      // double
auto y = 1.3e12L;  // long double
```

**3. Code from the PPT**

**Example 1: Integer Limits**

```cpp
// limits.cpp -- some integer limits
#include <iostream>
#include <climits>

int main()
{
    using namespace std;

    int n_int = INT_MAX;
    short n_short = SHRT_MAX;
    long n_long = LONG_MAX;
    long long n_llong = LLONG_MAX;

    cout << "int is " << sizeof(int) << " bytes." << endl;
    cout << "short is " << sizeof n_short << " bytes." << endl;
    cout << "long is " << sizeof n_long << " bytes." << endl;
    cout << "long long is " << sizeof n_llong << " bytes." << endl;

    cout << "Maximum values:" << endl;
    cout << "int: " << n_int << endl;
    cout << "short: " << n_short << endl;
    cout << "long: " << n_long << endl;
    cout << "long long: " << n_llong << endl;

    cout << "Minimum int value = " << INT_MIN << endl;
    cout << "Bits per byte = " << CHAR_BIT << endl;

    return 0;
}
```

This program uses `<climits>` and `sizeof` to show the sizes and limits of integer types.

**Example 2: Integer Overflow**

```cpp
// exceed.cpp -- exceeding some integer limits
#include <iostream>
#define ZERO 0
#include <climits>

int main()
{
    using namespace std;

    short sam = SHRT_MAX;
    unsigned short sue = sam;

    sam = sam + 1;
    sue = sue + 1;

    sam = ZERO;
    sue = ZERO;

    sam = sam - 1;
    sue = sue - 1;

    return 0;
}
```

This program shows overflow and wraparound behavior for signed and unsigned integers.

**Example 3: Decimal, Octal, and Hexadecimal Literals**

```cpp
// hexoct1.cpp -- shows hex and octal literals
#include <iostream>

int main()
{
    using namespace std;

    int chest = 42;
    int waist = 0x42;
    int inseam = 042;

    cout << "chest = " << chest << endl;
    cout << "waist = " << waist << endl;
    cout << "inseam = " << inseam << endl;

    return 0;
}
```

Output:

```text
chest = 42
waist = 66
inseam = 34
```

**Example 4: The char Type**

```cpp
// chartype.cpp -- the char type
#include <iostream>

int main()
{
    using namespace std;

    char ch;

    cout << "Enter a character: " << endl;
    cin >> ch;

    cout << "Hola! ";
    cout << "Thank you for the " << ch
         << " character." << endl;

    return 0;
}
```

This program reads and outputs a single character.

**Example 5: char and int**

```cpp
// morechar.cpp -- the char type and int type contrasted
#include <iostream>

int main()
{
    using namespace std;

    char ch = 'M';
    int i = ch;

    cout << "The ASCII code for " << ch << " is " << i << endl;

    ch = ch + 1;
    i = ch;

    cout << "The ASCII code for " << ch << " is " << i << endl;

    cout.put(ch);
    cout.put('!');

    return 0;
}
```

This program shows that characters are stored as integer codes.

**Example 6: Escape Sequences**

```cpp
// bondini.cpp -- using escape sequences
#include <iostream>

int main()
{
    using namespace std;

    cout << "\aOperation \"HyperHype\" is now activated!\n";
    cout << "Enter your agent code:________\b\b\b\b\b\b\b\b";

    long code;
    cin >> code;

    cout << "\aYou entered " << code << "...\n";
    cout << "\aCode verified! Proceed with Plan Z3!\n";

    return 0;
}
```

This program uses escape sequences such as `\a`, `\"`, `\n`, and `\b`.

**4. Common Confusing Points**

- `char` stores characters, but it is also an integer type.
- `'A'` is a character, while `"A"` is a string.
- `042` is octal, not decimal.
- `0x42` is hexadecimal.
- `endl`, `'\n'`, and `"\n"` can all start a new line.
- `int` is usually the default choice for integers.
- Unsigned types cannot represent negative values.
- A `const` constant must be initialized and cannot be changed later.
- Floating-point numbers may lose precision.
- Integer division discards the fractional part.
- List initialization does not allow narrowing conversions.
- Type casts do not change the original variable; they create a converted value.

**5. Report Summary**

In this chapter, I learned about data types and data handling in C++. Variables are used to store data, and the type of a variable determines how the data is stored and what range of values it can represent. C++ provides several fundamental data types, including integer types, character types, Boolean type, and floating-point types.

This chapter also introduced the sizes and ranges of integer types, as well as the difference between signed and unsigned integers. By using `sizeof` and `<climits>`, we can check the storage size and limits of integer types on the current system. The integer overflow example helped me understand why choosing an appropriate data type is important for program correctness.

In addition, I learned about character types, escape sequences, the `bool` type, `const` constants, floating-point numbers, arithmetic operators, and type conversions. These concepts helped me understand how C++ stores and processes basic data, and they provide a foundation for learning more complex data types such as arrays, pointers, structures, and classes.

> 下面进行第四章，依旧是先中文再翻译成英文

<details><summary>1 previous message</summary>

> 继续第四章。我来读取 `Lecture 4 Compound Data Types.pdf`，这一章通常内容会比较密：数组、字符串、结构体、共用体、枚举、指针和动态内存，我会按知识点和代码分清楚。
> </details>

下面是第四章 **Lecture 4 Compound Data Types** 的整理，先中文，后英文。

**中文版**

**一、本章核心概念**

第四章主要学习 C++ 的复合数据类型。复合数据类型是在基本类型基础上构造出来的更复杂的数据形式，用来表示更丰富的数据结构。

本章涉及：

- 数组 `array`
- C 风格字符串
- `string` 类字符串
- `getline()` 和 `get()` 输入
- 结构体 `struct`
- 共用体 `union`
- 枚举 `enum`
- 指针 `pointer`
- `new` 和 `delete` 动态内存管理
- 动态数组
- 自动、静态、动态存储的基本概念
- `vector` 和 `array` 类的引入

**二、本章重点内容**

1. **C++ 中的数据类型分类**

C++ 数据类型可以分为三类：

```cpp
// Basic Data Types
int, float, double, char, bool, void

// Derived Data Types
array, pointer, reference, function

// User Defined Data Types
class, structure, union, typedef, using
```

基本类型用于表示简单数据，派生类型和用户自定义类型可以组织更复杂的数据。

2. **静态类型语言与动态类型语言**

C++ 是编译型、静态类型语言。变量在编译阶段就需要确定类型。

```cpp
int a = 2;
string b = "Dynamic Typing";
int d = 10;
d = "Hello"; // 错误，C++ 中 int 变量不能变成 string
```

静态类型语言的特点：

- 执行效率更高；
- 程序结构更容易理解；
- 编译器能提前检查类型错误。

Python 是动态类型语言，变量类型可以在运行时根据值改变。

3. **C++ 标准库 std**

C++ 标准库提供了很多现成类型和功能。使用时需要包含对应头文件。

```cpp
#include <string>    // std::string
#include <utility>   // std::pair
#include <iostream>  // std::cout, std::endl
```

标准库中的名称通常位于 `std` 命名空间中。

```cpp
std::cout << "Hello" << std::endl;
```

虽然可以写：

```cpp
using namespace std;
```

但大型程序中不推荐滥用，因为可能引起命名冲突。

4. **std::pair**

`std::pair` 可以把两个值组合在一起。

```cpp
#include <utility>

std::pair<double, double> point{0.0, 3.0};
```

这里 `point` 表示一个由两个 `double` 值组成的对象。

5. **数组**

数组可以存放多个相同类型的值。

声明格式：

```cpp
typeName arrayName[arraySize];
```

例如：

```cpp
int numbers[10];
double scores[5];
```

数组声明需要说明三件事：

- 每个元素的类型；
- 数组名；
- 元素个数。

注意：

- `arraySize` 必须是整数常量或常量表达式；
- 数组下标从 `0` 开始；
- 编译器通常不会检查数组下标是否越界；
- 使用越界下标可能导致不可预测结果。

6. **数组初始化**

数组只能在定义时整体初始化。

```cpp
int quantity[4] = {3, 4, 5, 6};
```

以下写法不允许：

```cpp
int numbers[3];
numbers = quantity;        // 错误，数组不能整体赋值
numbers[3] = {3, 4, 5};    // 错误，不能这样重新初始化
```

7. **C 风格字符串**

字符串是一串连续存储的字符。

C 风格字符串以空字符 `'\0'` 结尾，用来标记字符串结束。

```cpp
char cityname1[7] = {'W', 'e', 'i', ' ', 'H', 'a', 'i'};       // 不是字符串
char cityname2[8] = {'W', 'e', 'i', ' ', 'H', 'a', 'i', '\0'}; // 是字符串
char cityname3[9] = "Qing Dao";
char cityname4[] = "Ji Nan";
```

注意：字符串字面值会自动在末尾添加 `'\0'`。

8. **cin 读取 C 风格字符串的问题**

```cpp
cin >> name;
```

这种方式以空白字符作为结束标志，所以只能读取一个单词。遇到空格、Tab 或换行就停止。

另外，如果输入内容超过字符数组容量，可能造成数组越界。

9. **getline() 与 get()**

`getline()` 可以读取一整行，并丢弃换行符。

```cpp
cin.getline(name, 20);
```

`get()` 也可以读取一整行，但它会把换行符留在输入队列中。

```cpp
cin.get(name1, ArSize);
cin.get();                 // 读取并丢弃换行符
cin.get(name2, ArSize);
```

也可以链式调用：

```cpp
cin.get(name, ArSize).get();
```

10. **string 类**

C++ 标准库提供了 `string` 类，比 C 风格字符串更方便安全。

使用前需要：

```cpp
#include <string>
```

`string` 对象可以像普通变量一样使用：

```cpp
string str1;
string str2 = "ShanXi";
cin >> str1;
cout << str2;
cout << str2[2];
```

`string` 支持：

- 初始化；
- 赋值；
- 拼接；
- 追加；
- 下标访问。

```cpp
str1 = str2;
str3 = str1 + str2;
str1 += str2;
```

而字符数组不能直接整体赋值：

```cpp
charr1 = charr2; // 错误
```

C 风格字符串需要用函数：

```cpp
strcpy(charr1, charr2);
strcat(charr1, ", ShanDong");
```

11. **结构体 struct**

结构体可以把不同类型的数据组合到一起。

```cpp
struct student
{
    char name[20];
    int age;
    float weight;
};
```

定义结构体变量：

```cpp
student wang;
```

访问成员使用点运算符 `.`：

```cpp
wang.age = 18;
wang.weight = 55;
```

结构体初始化：

```cpp
student Li = {"Li Ming", 17, 50};
```

结构体声明可以放在函数内部，也可以放在函数外部。放在函数外部时，后面的多个函数都可以使用这个类型。

12. **结构体的特点**

结构体是用户自定义类型，可以像内置类型一样使用：

- 可以定义结构体变量；
- 可以把结构体作为函数参数；
- 可以把结构体作为函数返回值；
- 可以用 `=` 给同类型结构体赋值。

```cpp
student student1;
student student2 = {"Li Ming", 17, 50};

student1 = student2;
```

13. **结构体应用示例**

```cpp
struct BJTUWeihaiID {
    string name;
    int idNumber;
};

BJTUWeihaiID id;
id.name = "WangMing";
id.idNumber = 25123456;
```

统一初始化：

```cpp
BJTUWeihaiID wm = {"WangMing", 25123456};
BJTUWeihaiID zl {"ZhangLiang", 25123457};
```

结构体可以嵌套：

```cpp
struct Point {
    double x;
    double y;
};

struct Circle {
    Point center;
    double radius;
};

Circle circle{{0.0, 0.0}, 200};
```

14. **共用体 union**

共用体可以存放不同类型的数据，但同一时间只能保存其中一种。

```cpp
union value
{
    int int_val;
    long long_val;
    double double_val;
};
```

使用：

```cpp
value va;
va.int_val = 10;
va.double_val = 1.5; // 原来的 int 值会失效
```

共用体节省内存，但使用时要清楚当前有效成员是哪一个。

15. **枚举 enum**

枚举用于定义一组符号常量。

```cpp
enum colors {red, orange, yellow, green, blue};
```

这会创建一个新类型 `colors`，并让：

```cpp
red = 0
orange = 1
yellow = 2
green = 3
blue = 4
```

使用：

```cpp
colors col;
col = blue; // 正确
col = 6;    // 错误，6 不是枚举量
```

16. **指针 pointer**

指针是存储地址的变量。

普通变量存储值，指针变量存储地址。

取地址运算符：

```cpp
&number
```

解引用运算符：

```cpp
*p_updates
```

示例：

```cpp
int updates = 6;
int * p_updates;
p_updates = &updates;

*p_updates = *p_updates + 1;
```

执行后，`updates` 的值会变成 `7`。

17. **指针声明与初始化**

```cpp
int * pt;
int weight = 5;
pt = &weight;
```

也可以声明时初始化：

```cpp
int * pt = &weight;
```

注意：声明指针只是创建了一个存放地址的变量，并没有自动创建它指向的数据。

危险写法：

```cpp
long * fellow;
*fellow = 223323; // 错误，fellow 没有指向有效地址
```

使用指针前必须让它指向确定、合法的地址。

18. **new 动态分配内存**

`new` 可以在程序运行时申请内存。

```cpp
int * pn = new int;
*pn = 100;
```

一般形式：

```cpp
typeName * pointer_name = new typeName;
```

这块内存没有变量名，只能通过指针访问。

19. **delete 释放内存**

用 `new` 申请的内存应该用 `delete` 释放。

```cpp
int * pt = new int;
delete pt;
```

注意：

```cpp
int weight;
int * pi = &weight;
delete pi; // 错误，weight 不是 new 创建的
```

`delete` 释放的是指针指向的内存，不是指针变量本身。

20. **动态数组**

`new` 可以在运行时创建数组。

```cpp
int * numbers = new int[10];
```

释放动态数组必须使用：

```cpp
delete [] numbers;
```

注意匹配规则：

```cpp
int * pt = new int;
delete pt;        // 正确

int * ps = new int[20];
delete [] ps;     // 正确
```

不能混用：

```cpp
delete [] pt; // 错误
delete ps;    // 错误
```

**三、PPT 中的代码整理**

**代码 1：C 风格字符串与 strlen()**

```cpp
#include <iostream>
#include <cstring>

int main()
{
    using namespace std;

    const int Size = 20;
    char name1[Size];
    char name2[Size] = "C++Programming";

    cout << "The course for this semester is " << name2;

    name2[3] = '\0';

    cout << ".\nHere are the first 3 characters of the course name: "
         << name2 << endl;

    cout << "What were the relevant courses from last semester?" << endl;
    cin >> name1;

    cout << "Well, \"" << name1 << "\" is the relevant course. ";
    cout << "The course " << name1 << " has "
         << strlen(name1) << " letters and is stored\n";

    cout << "in an array of " << sizeof(name1) << " bytes.\n\n";

    return 0;
}
```

知识点：

- C 风格字符串以 `'\0'` 结束；
- `strlen()` 计算字符串实际长度，不包括 `'\0'`；
- `sizeof(name1)` 得到整个数组的字节数；
- 修改中间字符为 `'\0'` 会提前结束字符串。

**代码 2：cin 读取字符串**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    const int ArSize = 10;
    char name[ArSize];

    cout << "Enter your name:\n";
    cin >> name;

    cout << "Your name is " << name << ".\n";

    return 0;
}
```

知识点：

- `cin >> name` 只读取一个单词；
- 输入过长可能造成越界；
- 字符数组大小必须考虑结尾的 `'\0'`。

**代码 3：getline() 读取一整行**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    const int ArSize = 10;
    char name[ArSize];

    cout << "Enter your name:\n";
    cin.getline(name, ArSize);

    cout << "Your name is " << name << ".\n";

    return 0;
}
```

知识点：

- `getline()` 可以读取包含空格的一整行；
- 最多读取 `ArSize - 1` 个字符；
- 自动在末尾添加 `'\0'`。

**代码 4：get() 链式读取**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    const int ArSize = 10;
    char name1[ArSize];
    char name2[ArSize];

    cout << "Enter your name1:\n";
    cin.get(name1, ArSize).get();

    cout << "Enter your name2:\n";
    cin.get(name2, ArSize).get();

    cout << "The name1 is " << name1 << endl;
    cout << "The name2 is " << name2 << endl;

    return 0;
}
```

知识点：

- `get(name, size)` 读取一行但保留换行符；
- 后面的 `.get()` 用来读取并丢弃换行符；
- 这是成员函数链式调用。

**代码 5：string 类**

```cpp
#include <iostream>
#include <string>

int main()
{
    using namespace std;

    char charr1[10];
    char charr2[10] = "WeiHai";

    string str1;
    string str2 = "ShanXi";

    cout << "Please enter the province name where "
         << charr2 << " City is located:";
    cin >> charr1;

    cout << "Please enter a city name in "
         << str2 << " Province:";
    cin >> str1;

    cout << "\nThis is " << charr2 << ", "
         << charr1 << " province.\n";

    cout << "This is " << str1 << ", "
         << str2 << " province.\n\n";

    cout << "The second letter in " << charr1
         << " is " << charr1[1] << endl;

    cout << "The third letter in " << str2
         << " is " << str2[2] << endl;

    return 0;
}
```

知识点：

- `string` 使用更方便；
- 字符数组和 `string` 都可以用下标访问字符；
- `string` 可以直接赋值、拼接和输出。

**代码 6：结构体**

```cpp
#include <iostream>
#include <string>
using namespace std;

struct BJTUWeihaiID {
    string name;
    int idNumber;
};

BJTUWeihaiID issueNewID()
{
    BJTUWeihaiID id {"WangMing", 25123456};
    return id;
}

int main()
{
    BJTUWeihaiID wm {"WangMing", 25123456};

    cout << wm.name << endl;
    cout << wm.idNumber << endl;

    return 0;
}
```

知识点：

- `struct` 把多个相关数据组合成一个新类型；
- 使用 `.` 访问字段；
- 结构体可以作为函数返回值；
- 支持列表初始化。

**代码 7：共用体**

```cpp
#include <iostream>
using namespace std;

union value
{
    int int_val;
    long long_val;
    double double_val;
};

int main()
{
    value va;

    va.int_val = 10;
    cout << va.int_val << endl;

    va.double_val = 1.5;
    cout << va.double_val << endl;

    return 0;
}
```

知识点：

- `union` 多个成员共享同一块内存；
- 同一时间只有一个成员有效；
- 后写入的成员会覆盖之前的内容。

**代码 8：枚举**

```cpp
#include <iostream>
using namespace std;

enum colors {red, orange, yellow, green, blue};

int main()
{
    colors col;

    col = blue;

    cout << col << endl;

    return 0;
}
```

知识点：

- `enum` 创建符号常量集合；
- 默认从 `0` 开始编号；
- 枚举变量只能直接赋枚举量。

**代码 9：使用 & 查看地址**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    int number = 2;
    double weight = 3.5;

    cout << "number = " << number;
    cout << " and number address = " << &number << endl;

    cout << "weight value = " << weight;
    cout << " and weight address = " << &weight << endl;

    return 0;
}
```

知识点：

- `&` 可以获取变量地址；
- 不同变量存储在不同内存位置。

**代码 10：指针变量**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    int updates = 6;
    int * p_updates;

    p_updates = &updates;

    cout << "Values: updates = " << updates;
    cout << ", *p_updates = " << *p_updates << endl;

    cout << "Addresses: &updates = " << &updates << endl;
    cout << "p_updates = " << p_updates << endl;

    *p_updates = *p_updates + 1;

    cout << "Now updates = " << updates << endl;

    return 0;
}
```

知识点：

- 指针保存地址；
- `*p_updates` 表示访问指针指向的值；
- 通过指针可以修改原变量。

**代码 11：new 动态申请内存**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    int days = 100;
    int * pt = new int;

    *pt = 100;

    cout << "days value = " << days
         << ": location " << &days << endl;

    cout << "int value = " << *pt
         << ": location = " << pt << endl;

    cout << "size of pt = " << sizeof(pt)
         << ": size of *pt = " << sizeof(*pt) << endl;

    delete pt;

    return 0;
}
```

知识点：

- `new int` 在运行时申请一块 `int` 大小的内存；
- 指针 `pt` 保存这块内存的地址；
- `*pt` 访问这块内存中的值；
- 使用完后应 `delete pt`。

**代码 12：动态数组**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    double * p3 = new double[3];

    p3[0] = 0.2;
    p3[1] = 0.3;
    p3[2] = 0.4;

    cout << "p3[1] is " << p3[1] << ".\n";

    p3 = p3 + 1;

    cout << "Now p3[0] is " << p3[0] << " and ";
    cout << "p3[1] is " << p3[1] << ".\n";

    p3 = p3 - 1;

    delete [] p3;

    return 0;
}
```

知识点：

- `new double[3]` 创建动态数组；
- 指针可以像数组名一样使用下标；
- `p3 = p3 + 1` 会让指针指向下一个元素；
- 释放数组必须使用 `delete [] p3`；
- 删除前要把指针恢复到数组起始位置。

**四、易混点**

- 字符数组不是一定就是字符串，只有以 `'\0'` 结尾才是 C 风格字符串。
- `cin >> char数组` 只能读一个单词，不能读包含空格的一整行。
- `getline()` 会丢弃换行符，`get()` 会留下换行符。
- 字符数组不能整体赋值，`string` 可以整体赋值。
- `strlen()` 是字符串长度，`sizeof()` 是数组占用字节数。
- 结构体可以保存多种类型，数组只能保存同一种类型。
- 共用体同一时间只能保存一个成员。
- 枚举量默认从 0 开始。
- 指针存地址，普通变量存值。
- 使用 `*` 解引用前，指针必须指向合法地址。
- `new` 和 `delete` 要配对，`new[]` 和 `delete[]` 要配对。
- 动态数组释放前，指针应指回数组开头。

**五、可写进实验报告的中文总结**

本章主要学习了 C++ 中的复合数据类型，包括数组、字符串、结构体、共用体、枚举和指针。数组可以存储多个相同类型的数据，而结构体可以把不同类型的数据组合成一个整体。通过结构体的学习，我理解了用户自定义类型的基本思想，这也为后续学习类和对象奠定了基础。

本章还比较了 C 风格字符串和 C++ `string` 类。C 风格字符串本质上是以空字符 `'\0'` 结尾的字符数组，使用时需要注意数组大小和输入越界问题；而 `string` 类提供了更方便的赋值、拼接和访问方式，更适合 C++ 程序设计。

此外，本章重点学习了指针和动态内存管理。指针用于存储变量地址，可以通过解引用访问或修改地址中的数据。`new` 和 `delete` 可以在程序运行时动态申请和释放内存，动态数组则可以在运行时决定数组大小。通过这些内容，我初步理解了 C++ 中内存管理的基本机制。

---

**English Version**

**1. Core Concepts**

Chapter 4 introduces compound data types in C++. Compound data types are built from basic types and are used to represent more complex data.

This chapter covers:

- arrays;
- C-style strings;
- `string` class strings;
- `getline()` and `get()` methods;
- structures;
- unions;
- enumerations;
- pointers;
- dynamic memory management with `new` and `delete`;
- dynamic arrays;
- automatic, static, and dynamic storage;
- an introduction to `vector` and `array`.

**2. Key Points**

C++ data types can be divided into three groups:

```cpp
// Basic Data Types
int, float, double, char, bool, void

// Derived Data Types
array, pointer, reference, function

// User Defined Data Types
class, structure, union, typedef, using
```

C++ is a compiled and statically typed language. This means that variable types are checked before machine code is generated.

```cpp
int d = 10;
d = "Hello"; // error in C++
```

Static typing is usually more efficient, easier to understand, and better for error checking.

The C++ standard library provides many useful types and functions. To use them, we include the related header files:

```cpp
#include <string>
#include <utility>
#include <iostream>
```

Standard library names are usually placed in the `std` namespace.

```cpp
std::cout << "Hello" << std::endl;
```

**Arrays**

An array stores several values of the same type.

```cpp
typeName arrayName[arraySize];
```

Example:

```cpp
int numbers[10];
```

An array declaration specifies the element type, the array name, and the number of elements. The array size must be a constant expression. Array subscripts start from `0`, and programmers must avoid using invalid subscripts.

**C-Style Strings**

A C-style string is a character array ending with the null character `'\0'`.

```cpp
char cityname1[7] = {'W', 'e', 'i', ' ', 'H', 'a', 'i'};       // not a string
char cityname2[8] = {'W', 'e', 'i', ' ', 'H', 'a', 'i', '\0'}; // a string
char cityname3[9] = "Qing Dao";
char cityname4[] = "Ji Nan";
```

Using `cin >> name` reads only one word and may cause overflow if the input is too long.

`getline()` reads a whole line and discards the newline character.

```cpp
cin.getline(name, 20);
```

`get()` reads a line but leaves the newline character in the input queue.

```cpp
cin.get(name1, ArSize);
cin.get();
cin.get(name2, ArSize);
```

**The string Class**

The C++ `string` class is easier and safer than C-style strings.

```cpp
#include <string>

string str1;
string str2 = "ShanXi";
```

A `string` object supports assignment, concatenation, appending, output, input, and subscript access.

```cpp
str1 = str2;
str3 = str1 + str2;
str1 += str2;
```

**Structures**

A structure can store values of different types together.

```cpp
struct student
{
    char name[20];
    int age;
    float weight;
};
```

A structure variable can be created and initialized:

```cpp
student Li = {"Li Ming", 17, 50};
```

Members are accessed with the dot operator:

```cpp
Li.age = 17;
```

Structures can be passed to functions, returned from functions, and assigned to other structures of the same type.

**Unions**

A union can hold different data types, but only one member is valid at a time.

```cpp
union value
{
    int int_val;
    long long_val;
    double double_val;
};
```

If a new member is assigned, the previous value is overwritten.

**Enumerations**

An enumeration creates a new type and a set of symbolic constants.

```cpp
enum colors {red, orange, yellow, green, blue};
```

By default, the enumerators have integer values starting from `0`.

```cpp
colors col;
col = blue; // valid
col = 6;    // invalid
```

**Pointers**

A pointer is a variable that stores an address.

```cpp
int updates = 6;
int * p_updates = &updates;
```

The address-of operator `&` gets the address of a variable. The dereference operator `*` accesses the value stored at that address.

```cpp
*p_updates = *p_updates + 1;
```

Pointers must be initialized before being dereferenced.

```cpp
long * fellow;
*fellow = 223323; // dangerous and invalid
```

**new and delete**

`new` allocates memory during runtime.

```cpp
int * pn = new int;
*pn = 100;
```

Memory allocated by `new` should be released with `delete`.

```cpp
delete pn;
```

Dynamic arrays are created with `new[]` and released with `delete[]`.

```cpp
int * numbers = new int[10];
delete [] numbers;
```

**3. Code from the PPT**

**Example 1: C-Style Strings**

```cpp
#include <iostream>
#include <cstring>

int main()
{
    using namespace std;

    const int Size = 20;
    char name1[Size];
    char name2[Size] = "C++Programming";

    cout << "The course for this semester is " << name2;

    name2[3] = '\0';

    cout << ".\nHere are the first 3 characters of the course name: "
         << name2 << endl;

    cin >> name1;

    cout << "The course " << name1 << " has "
         << strlen(name1) << " letters and is stored\n";

    cout << "in an array of " << sizeof(name1) << " bytes.\n";

    return 0;
}
```

This example shows that C-style strings end with `'\0'`. `strlen()` gives the string length, while `sizeof()` gives the size of the array.

**Example 2: getline()**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    const int ArSize = 10;
    char name[ArSize];

    cout << "Enter your name:\n";
    cin.getline(name, ArSize);

    cout << "Your name is " << name << ".\n";

    return 0;
}
```

This program reads a whole line into a character array.

**Example 3: get()**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    const int ArSize = 10;
    char name1[ArSize];
    char name2[ArSize];

    cin.get(name1, ArSize).get();
    cin.get(name2, ArSize).get();

    cout << "The name1 is " << name1 << endl;
    cout << "The name2 is " << name2 << endl;

    return 0;
}
```

This example uses chained member function calls. The second `.get()` removes the newline character.

**Example 4: The string Class**

```cpp
#include <iostream>
#include <string>

int main()
{
    using namespace std;

    char charr1[10];
    char charr2[10] = "WeiHai";

    string str1;
    string str2 = "ShanXi";

    cin >> charr1;
    cin >> str1;

    cout << charr2 << ", " << charr1 << endl;
    cout << str1 << ", " << str2 << endl;

    cout << charr1[1] << endl;
    cout << str2[2] << endl;

    return 0;
}
```

This program compares character arrays with `string` objects.

**Example 5: Structure**

```cpp
#include <iostream>
#include <string>
using namespace std;

struct BJTUWeihaiID {
    string name;
    int idNumber;
};

BJTUWeihaiID issueNewID()
{
    BJTUWeihaiID id {"WangMing", 25123456};
    return id;
}

int main()
{
    BJTUWeihaiID wm {"WangMing", 25123456};

    cout << wm.name << endl;
    cout << wm.idNumber << endl;

    return 0;
}
```

This example shows how a structure bundles related data into a new type.

**Example 6: Union**

```cpp
#include <iostream>
using namespace std;

union value
{
    int int_val;
    long long_val;
    double double_val;
};

int main()
{
    value va;

    va.int_val = 10;
    cout << va.int_val << endl;

    va.double_val = 1.5;
    cout << va.double_val << endl;

    return 0;
}
```

A union shares memory among all its members, so only one member is valid at a time.

**Example 7: Enumeration**

```cpp
#include <iostream>
using namespace std;

enum colors {red, orange, yellow, green, blue};

int main()
{
    colors col = blue;
    cout << col << endl;

    return 0;
}
```

This example defines symbolic constants with `enum`.

**Example 8: Pointers**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    int updates = 6;
    int * p_updates;

    p_updates = &updates;

    cout << "updates = " << updates << endl;
    cout << "*p_updates = " << *p_updates << endl;

    *p_updates = *p_updates + 1;

    cout << "Now updates = " << updates << endl;

    return 0;
}
```

This program shows that a pointer stores an address and can modify the value at that address.

**Example 9: Dynamic Memory**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    int * pt = new int;

    *pt = 100;

    cout << "int value = " << *pt
         << ": location = " << pt << endl;

    delete pt;

    return 0;
}
```

This program allocates memory with `new` and releases it with `delete`.

**Example 10: Dynamic Array**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    double * p3 = new double[3];

    p3[0] = 0.2;
    p3[1] = 0.3;
    p3[2] = 0.4;

    cout << "p3[1] is " << p3[1] << ".\n";

    p3 = p3 + 1;

    cout << "Now p3[0] is " << p3[0] << " and ";
    cout << "p3[1] is " << p3[1] << ".\n";

    p3 = p3 - 1;

    delete [] p3;

    return 0;
}
```

This example creates a dynamic array and shows pointer arithmetic.

**4. Common Confusing Points**

- A character array is a C-style string only if it ends with `'\0'`.
- `cin >> name` reads only one word.
- `getline()` discards the newline, while `get()` leaves it in the input queue.
- Character arrays cannot be assigned as a whole, but `string` objects can.
- `strlen()` gives the string length, while `sizeof()` gives the array size.
- Arrays store elements of the same type, while structures can store different types.
- A union can hold only one valid member at a time.
- Enumeration values start from `0` by default.
- Pointers store addresses, not ordinary values.
- A pointer must be initialized before dereferencing.
- `new` must match `delete`, and `new[]` must match `delete[]`.

**5. Report Summary**

In this chapter, I learned about compound data types in C++, including arrays, strings, structures, unions, enumerations, and pointers. Arrays can store multiple values of the same type, while structures can combine different types of data into one unit. Through structures, I gained a basic understanding of user-defined types, which provides a foundation for learning classes and objects later.

This chapter also compared C-style strings with the C++ `string` class. A C-style string is a character array ending with the null character `'\0'`, so programmers must pay attention to array size and input overflow. The `string` class is easier and safer to use because it supports assignment, concatenation, and character access directly.

In addition, this chapter introduced pointers and dynamic memory management. A pointer stores the address of a value, and the dereference operator can be used to access or modify that value. The `new` and `delete` operators allow programs to allocate and release memory at runtime. Dynamic arrays make it possible to decide the array size while the program is running. These topics helped me understand the basic mechanism of memory management in C++.

> 下面进行第五章，依旧是先中文再翻译成英文

<details><summary>1 previous message</summary>

> 继续第五章。我先读取 `Lecture 5 Loops and Relational Expressions.pdf`，这一章会重点整理循环结构、关系表达式、自增自减、数组/字符串循环处理这些内容。
> </details>

下面是第五章 **Lecture 5 Loops and Relational Expressions** 的整理，先中文，后英文。

**中文版**

**一、本章核心概念**

第五章主要学习 C++ 中的循环结构和关系表达式。循环用于重复执行某些操作，关系表达式用于判断条件是否成立。本章涉及 `for` 循环、`while` 循环、`do while` 循环、范围 `for` 循环、关系运算符、字符输入、哨兵字符以及 `cin.get()` 的使用。

C++ 提供的主要循环结构有：

```cpp
for
while
do while
```

其中 `for` 和 `while` 是入口条件循环，先判断条件，再决定是否执行循环体；`do while` 是出口条件循环，先执行循环体，再判断是否继续。

**二、本章重点内容**

1. **for 循环**

`for` 循环适合执行次数比较明确的重复操作。

基本格式：

```cpp
for (initialization; test-expression; update-expression)
    body;
```

完整形式：

```cpp
for (int i = 0; i < 10; i++)
{
    cout << i << endl;
}
```

`for` 循环通常包含四个步骤：

- 初始化循环变量；
- 判断循环条件；
- 执行循环体；
- 更新循环变量。

例如：

```cpp
for (int i = 0; i < 5; i++)
{
    cout << i << endl;
}
```

执行过程：

- `int i = 0`：初始化；
- `i < 5`：判断是否继续循环；
- `cout << i`：执行循环体；
- `i++`：更新变量；
- 重复判断，直到条件为假。

2. **while 循环**

`while` 循环只有测试条件和循环体。

基本格式：

```cpp
while (test-condition)
    body;
```

示例：

```cpp
int i = 0;

while (i < 5)
{
    cout << i << endl;
    i++;
}
```

执行过程：

- 先判断 `i < 5`；
- 如果为真，执行循环体；
- 执行后再次判断；
- 条件为假时退出循环。

`while` 适合循环次数不确定，但结束条件明确的情况。

3. **for 与 while 的关系**

在 C++ 中，`for` 和 `while` 本质上可以互相转换。

`for` 循环：

```cpp
for (init-expression; test-expression; update-expression)
{
    statement;
}
```

可以改写为：

```cpp
init-expression;

while (test-expression)
{
    statement;
    update-expression;
}
```

`while` 循环：

```cpp
while (test-expression)
{
    body;
}
```

也可以写成：

```cpp
for (; test-expression; )
{
    body;
}
```

它们都是**入口条件循环**。如果一开始条件就是假的，循环体一次也不会执行。

4. **do while 循环**

`do while` 是出口条件循环。

基本格式：

```cpp
do
{
    body;
}
while (test-expression);
```

示例：

```cpp
int i = 0;

do
{
    cout << i << endl;
    i++;
}
while (i < 5);
```

特点：

- 先执行循环体；
- 再判断条件；
- 因此循环体至少执行一次。

适合需要先执行一次操作，再根据结果决定是否继续的情况。

5. **范围 for 循环**

C++11 引入了范围 `for` 循环，用于遍历数组或容器中的每个元素。

基本格式：

```cpp
for (type variable : collection)
{
    body;
}
```

示例：

```cpp
int numbers[4] = {2, 4, 5, 6};

for (int x : numbers)
{
    cout << x << endl;
}
```

这里 `x` 会依次代表数组中的每个元素。

范围 `for` 也可以用于初始化列表：

```cpp
for (int x : {3, 5, 2, 8, 6})
{
    cout << x << " ";
}

cout << '\n';
```

优点：

- 代码简洁；
- 不需要手动控制下标；
- 适合遍历整个数组或容器。

6. **关系运算符**

关系表达式用于比较两个值，结果为 `true` 或 `false`。

常见关系运算符：

```cpp
>     大于
>=    大于等于
==    等于
<=    小于等于
<     小于
!=    不等于
```

示例：

```cpp
while (ch != '#')
{
    cout << ch;
}
```

这里 `ch != '#'` 表示只要 `ch` 不是 `#`，循环就继续。

注意：

```cpp
==   判断是否相等
=    赋值
```

不要把 `==` 和 `=` 混淆。

7. **自增和自减运算符**

本章涉及 `++` 和 `--`。

```cpp
++count;
count++;
--count;
count--;
```

含义：

- `++count` 或 `count++`：让 `count` 增加 1；
- `--count` 或 `count--`：让 `count` 减少 1。

在单独作为语句时，前置和后置效果通常相同：

```cpp
count++;
++count;
```

都表示 `count = count + 1;`。

8. **组合赋值运算符**

组合赋值运算符可以简化表达式。

```cpp
x += 2;   // x = x + 2
x -= 2;   // x = x - 2
x *= 2;   // x = x * 2
x /= 2;   // x = x / 2
x %= 2;   // x = x % 2
```

它们常用于循环中的变量更新。

9. **复合语句，也叫代码块**

如果循环体包含多条语句，需要使用 `{}` 包起来。

```cpp
while (ch != '#')
{
    cout << ch;
    ++count;
    cin.get(ch);
}
```

花括号中的多条语句被看作一个整体。

10. **逗号运算符**

逗号运算符可以在一个表达式位置放多个表达式，常用于 `for` 循环中。

```cpp
for (int i = 0, j = 10; i < j; i++, j--)
{
    cout << i << " " << j << endl;
}
```

它可以同时初始化或更新多个变量。

11. **循环与文本输入**

逐字符读取文本是常见任务。程序需要知道什么时候停止读取。

一种常见方法是使用**哨兵字符**。哨兵字符是一个特殊字符，用来表示输入结束。

例如使用 `#` 作为停止标志：

```cpp
while (ch != '#')
{
    ...
}
```

当用户输入 `#` 时，循环结束。

12. **直接使用 cin 读取字符的问题**

使用：

```cpp
cin >> ch;
```

读取 `char` 时，`cin` 会跳过空格、制表符和换行符。

因此，如果输入中有空格，这些空格不会被读取，也不会被计数。

另一个特点是：`cin` 输入是缓冲的。用户输入的字符通常要等按下 Enter 后才会送给程序处理。

13. **cin.get(char)**

如果需要逐个读取所有字符，包括空格、Tab 和换行，应使用：

```cpp
cin.get(ch);
```

示例：

```cpp
cin.get(ch);

while (ch != '#')
{
    cout << ch;
    ++count;
    cin.get(ch);
}
```

`cin.get(ch)` 会读取下一个字符，即使它是空格或换行符。

14. **cin.get() 无参数形式**

`cin.get()` 也可以不带参数，返回输入中的下一个字符。

```cpp
ch = cin.get();
```

这种形式类似 C 语言中的 `getchar()`。

输出单个字符可以使用：

```cpp
cout.put(ch);
```

它类似 C 语言中的 `putchar()`。

15. **typedef**

本章主题中提到 `typedef`。`typedef` 用于给已有类型起别名。

```cpp
typedef unsigned int uint;
```

之后可以写：

```cpp
uint age;
```

它等价于：

```cpp
unsigned int age;
```

在现代 C++ 中，也常用 `using` 来定义类型别名：

```cpp
using uint = unsigned int;
```

16. **嵌套循环与二维数组**

嵌套循环是指一个循环内部还有另一个循环，常用于处理二维数组。

示例：

```cpp
int matrix[2][3] = {
    {1, 2, 3},
    {4, 5, 6}
};

for (int i = 0; i < 2; i++)
{
    for (int j = 0; j < 3; j++)
    {
        cout << matrix[i][j] << " ";
    }
    cout << endl;
}
```

外层循环控制行，内层循环控制列。

**三、PPT 中的代码整理**

**代码 1：使用 while 和 cin 逐字符读取**

```cpp
// reading chars with a while loop
#include <iostream>

int main()
{
    using namespace std;

    char ch;
    int count = 0;

    cout << "Enter characters; enter # to quit:\n";

    cin >> ch;

    while (ch != '#')
    {
        cout << ch;
        ++count;
        cin >> ch;
    }

    cout << endl << count << " characters read\n";

    return 0;
}
```

中文解释：

- `char ch;` 用于保存输入字符；
- `int count = 0;` 用于统计读取的字符数量；
- `#` 是哨兵字符，表示输入结束；
- `while (ch != '#')` 表示只要没有读到 `#` 就继续循环；
- `++count` 每读取一个字符，计数加 1；
- `cin >> ch` 会跳过空格和换行。

局限：

- 不能读取空格、Tab 和换行；
- 输入内容是缓冲的，通常按 Enter 后程序才处理。

**代码 2：使用 cin.get(ch) 逐字符读取**

```cpp
// using cin.get(char)
#include <iostream>

int main()
{
    using namespace std;

    char ch;
    int count = 0;

    cout << "Enter characters; enter # to quit:\n";

    cin.get(ch);

    while (ch != '#')
    {
        cout << ch;
        ++count;
        cin.get(ch);
    }

    cout << endl << count << " characters read\n";

    return 0;
}
```

中文解释：

- `cin.get(ch)` 会读取下一个字符；
- 它不会跳过空格、Tab 或换行；
- 因此更适合逐字符处理文本；
- `#` 仍然作为结束输入的哨兵字符；
- `count` 统计所有读取到的字符，包括空格和换行。

**代码 3：范围 for 循环遍历数组**

```cpp
#include <iostream>

int main()
{
    int numbers[4] = {2, 4, 5, 6};

    for (int x : numbers)
    {
        std::cout << x << std::endl;
    }

    for (int x : {3, 5, 2, 8, 6})
    {
        std::cout << x << " ";
    }

    std::cout << '\n';

    return 0;
}
```

中文解释：

- `for (int x : numbers)` 会依次取出数组中的每个元素；
- 每次循环中，`x` 表示当前元素；
- 范围 `for` 适合遍历整个数组；
- 第二个循环遍历初始化列表 `{3, 5, 2, 8, 6}`。

**四、易混点**

- `for` 和 `while` 都是入口条件循环，条件一开始为假时，循环体一次也不执行。
- `do while` 是出口条件循环，循环体至少执行一次。
- `while (ch != '#')` 中的 `!=` 是“不等于”，不是赋值。
- `cin >> ch` 会跳过空格和换行。
- `cin.get(ch)` 会读取空格和换行。
- `cin.get()` 无参数形式会返回下一个字符。
- `++count` 表示计数加 1。
- 多条循环语句必须放在 `{}` 中。
- 范围 `for` 适合遍历整个数组或容器，但不适合需要精确控制下标的情况。
- 嵌套循环常用于二维数组，外层控制行，内层控制列。

**五、可写进实验报告的中文总结**

本章主要学习了 C++ 中的循环结构和关系表达式。循环结构可以让程序重复执行某些操作，常见形式包括 `for` 循环、`while` 循环和 `do while` 循环。其中 `for` 和 `while` 都是入口条件循环，会先判断条件再执行循环体；而 `do while` 是出口条件循环，循环体至少会执行一次。

本章还学习了关系运算符、自增自减运算符、组合赋值运算符以及复合语句。这些内容常与循环结合使用，用来控制循环变量、判断循环是否继续以及组织多条循环语句。通过范围 `for` 循环，我了解了 C++11 中遍历数组和容器的更简洁方式。

此外，本章重点介绍了字符输入与循环的结合。直接使用 `cin >> ch` 读取字符时会跳过空格和换行，而 `cin.get(ch)` 可以读取包括空格、Tab 和换行在内的所有字符。因此，在逐字符处理文本时，`cin.get(ch)` 更加合适。通过本章学习，我掌握了循环控制和文本输入处理的基本方法。

---

**English Version**

**1. Core Concepts**

Chapter 5 mainly introduces loops and relational expressions in C++. Loops are used to repeat actions, and relational expressions are used to test whether a condition is true or false.

C++ provides three main loop structures:

```cpp
for
while
do while
```

The `for` loop and the `while` loop are entry-condition loops, which means that the test condition is evaluated before the loop body is executed. The `do while` loop is an exit-condition loop, which means that the loop body is executed before the condition is tested.

**2. Key Points**

1. **The for Loop**

A `for` loop is useful when the number of repetitions is relatively clear.

General form:

```cpp
for (initialization; test-expression; update-expression)
    body;
```

Example:

```cpp
for (int i = 0; i < 5; i++)
{
    cout << i << endl;
}
```

A `for` loop usually includes four steps:

- initialize a value;
- test whether the loop should continue;
- execute the loop body;
- update the value used in the test.

2. **The while Loop**

A `while` loop has a test condition and a loop body.

General form:

```cpp
while (test-condition)
    body;
```

Example:

```cpp
int i = 0;

while (i < 5)
{
    cout << i << endl;
    i++;
}
```

The condition is tested first. If it is true, the body is executed. The process repeats until the condition becomes false.

3. **for Versus while**

In C++, `for` and `while` loops are essentially equivalent.

A `for` loop:

```cpp
for (init-expression; test-expression; update-expression)
{
    statement;
}
```

can be rewritten as:

```cpp
init-expression;

while (test-expression)
{
    statement;
    update-expression;
}
```

A `while` loop:

```cpp
while (test-expression)
{
    body;
}
```

can be rewritten as:

```cpp
for (; test-expression; )
{
    body;
}
```

Both are entry-condition loops. If the condition is false at the beginning, the loop body will not be executed.

4. **The do while Loop**

The `do while` loop is an exit-condition loop.

General form:

```cpp
do
{
    body;
}
while (test-expression);
```

Example:

```cpp
int i = 0;

do
{
    cout << i << endl;
    i++;
}
while (i < 5);
```

The loop body is executed first, and then the condition is tested. Therefore, a `do while` loop always executes at least once.

5. **The Range-Based for Loop**

C++11 introduced the range-based `for` loop. It is used to process every element in an array or container.

Example:

```cpp
int numbers[4] = {2, 4, 5, 6};

for (int x : numbers)
{
    cout << x << endl;
}
```

The variable `x` represents each element of the array in turn.

It can also be used with an initialization list:

```cpp
for (int x : {3, 5, 2, 8, 6})
{
    cout << x << " ";
}

cout << '\n';
```

6. **Relational Operators**

Relational operators compare two values and produce either `true` or `false`.

Common relational operators:

```cpp
>     greater than
>=    greater than or equal to
==    equal to
<=    less than or equal to
<     less than
!=    not equal to
```

Example:

```cpp
while (ch != '#')
{
    cout << ch;
}
```

Here `ch != '#'` means that the loop continues as long as `ch` is not `#`.

7. **Increment and Decrement Operators**

The increment and decrement operators are:

```cpp
++count;
count++;
--count;
count--;
```

They increase or decrease a variable by 1.

When used as independent statements, prefix and postfix forms usually have the same result.

8. **Compound Assignment Operators**

Compound assignment operators simplify assignment expressions.

```cpp
x += 2;   // x = x + 2
x -= 2;   // x = x - 2
x *= 2;   // x = x * 2
x /= 2;   // x = x / 2
x %= 2;   // x = x % 2
```

They are often used to update loop variables.

9. **Compound Statements**

If a loop body contains more than one statement, braces are needed.

```cpp
while (ch != '#')
{
    cout << ch;
    ++count;
    cin.get(ch);
}
```

The statements inside the braces form one block.

10. **The Comma Operator**

The comma operator allows several expressions to appear where one expression is expected. It is often used in `for` loops.

```cpp
for (int i = 0, j = 10; i < j; i++, j--)
{
    cout << i << " " << j << endl;
}
```

11. **Loops and Text Input**

Reading text character by character is an important task. A program needs a way to know when to stop reading.

A common method is to use a sentinel character. For example, `#` can be used as a stop sign.

```cpp
while (ch != '#')
{
    ...
}
```

12. **Using cin for Character Input**

When reading `char` values, `cin >> ch` skips spaces, tabs, and newlines.

```cpp
cin >> ch;
```

Therefore, spaces in the input are not read or counted. Also, input to `cin` is buffered, so characters are usually sent to the program only after the user presses Enter.

13. **Using cin.get(char)**

To read every character, including spaces, tabs, and newlines, use:

```cpp
cin.get(ch);
```

Example:

```cpp
cin.get(ch);

while (ch != '#')
{
    cout << ch;
    ++count;
    cin.get(ch);
}
```

This method is better for character-by-character text processing.

14. **Another Version of cin.get()**

The no-argument version of `cin.get()` returns the next character from the input.

```cpp
ch = cin.get();
```

It works similarly to C’s `getchar()`.

To output a single character, use:

```cpp
cout.put(ch);
```

It works similarly to C’s `putchar()`.

15. **typedef**

`typedef` creates an alias for an existing type.

```cpp
typedef unsigned int uint;
```

Then we can write:

```cpp
uint age;
```

In modern C++, `using` is also commonly used:

```cpp
using uint = unsigned int;
```

16. **Nested Loops and Two-Dimensional Arrays**

Nested loops are often used to process two-dimensional arrays.

```cpp
int matrix[2][3] = {
    {1, 2, 3},
    {4, 5, 6}
};

for (int i = 0; i < 2; i++)
{
    for (int j = 0; j < 3; j++)
    {
        cout << matrix[i][j] << " ";
    }
    cout << endl;
}
```

The outer loop controls rows, and the inner loop controls columns.

**3. Code from the PPT**

**Example 1: Reading Characters with while and cin**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    char ch;
    int count = 0;

    cout << "Enter characters; enter # to quit:\n";

    cin >> ch;

    while (ch != '#')
    {
        cout << ch;
        ++count;
        cin >> ch;
    }

    cout << endl << count << " characters read\n";

    return 0;
}
```

Explanation:

- `ch` stores the input character;
- `count` counts the number of characters read;
- `#` is the sentinel character;
- `while (ch != '#')` keeps the loop running until `#` is entered;
- `cin >> ch` skips spaces and newlines.

**Example 2: Reading Characters with cin.get(ch)**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    char ch;
    int count = 0;

    cout << "Enter characters; enter # to quit:\n";

    cin.get(ch);

    while (ch != '#')
    {
        cout << ch;
        ++count;
        cin.get(ch);
    }

    cout << endl << count << " characters read\n";

    return 0;
}
```

Explanation:

- `cin.get(ch)` reads the next character;
- it reads spaces, tabs, and newlines;
- `#` is used to stop the loop;
- `count` counts all characters read before `#`.

**Example 3: Range-Based for Loop**

```cpp
#include <iostream>

int main()
{
    int numbers[4] = {2, 4, 5, 6};

    for (int x : numbers)
    {
        std::cout << x << std::endl;
    }

    for (int x : {3, 5, 2, 8, 6})
    {
        std::cout << x << " ";
    }

    std::cout << '\n';

    return 0;
}
```

Explanation:

- `for (int x : numbers)` visits each element in the array;
- `x` represents the current element;
- the second loop visits each value in the initialization list.

**4. Common Confusing Points**

- `for` and `while` are entry-condition loops.
- `do while` is an exit-condition loop and always runs at least once.
- `!=` means “not equal to.”
- `==` tests equality, while `=` assigns a value.
- `cin >> ch` skips spaces and newlines.
- `cin.get(ch)` reads spaces and newlines.
- `++count` increases `count` by 1.
- Multiple statements in a loop body should be placed inside braces.
- A range-based `for` loop is useful for visiting all elements.
- Nested loops are commonly used with two-dimensional arrays.

**5. Report Summary**

In this chapter, I learned about loops and relational expressions in C++. Loops allow a program to repeat actions, and common loop structures include the `for` loop, the `while` loop, and the `do while` loop. The `for` and `while` loops are entry-condition loops, so their conditions are tested before the loop body is executed. The `do while` loop is an exit-condition loop, so its body is executed at least once.

This chapter also introduced relational operators, increment and decrement operators, compound assignment operators, and compound statements. These concepts are often used together with loops to control loop variables, test loop conditions, and organize multiple statements inside a loop body. The range-based `for` loop introduced in C++11 provides a simpler way to process every element in an array or container.

In addition, this chapter explained how loops can be combined with character input. When using `cin >> ch`, spaces and newlines are skipped. In contrast, `cin.get(ch)` reads every character, including spaces, tabs, and newlines. Therefore, `cin.get(ch)` is more suitable for character-by-character text processing. Through this chapter, I learned the basic methods of loop control and text input handling in C++.

> 下面进行第六章，依旧是先中文再翻译成英文

<details><summary>1 previous message</summary>

> 继续第六章。我先读取 `Lecture 6 Branching Statements and Logical Operators.pdf`，这一章主要会围绕 `if`、`if else`、逻辑运算符、字符函数、条件运算符、`switch`、`break/continue` 和文件输入输出展开。
> </details>

下面是第六章 **Lecture 6 Branching Statements and Logical Operators** 的整理，先中文，后英文。

**中文版**

**一、本章核心概念**

第六章主要学习 C++ 中的分支语句和逻辑运算符。分支语句用于让程序根据不同条件选择不同的执行路径，逻辑运算符用于组合多个判断条件。

本章主要内容包括：

- `if` 语句
- `if else` 语句
- `if else if else` 多分支结构
- 逻辑运算符 `&&`、`||`、`!`
- `<cctype>` 字符处理函数库
- 条件运算符 `?:`
- `switch` 语句
- `break` 和 `continue`
- 数字读取循环
- 基本文件输入输出

**二、本章重点内容**

1. **if 语句**

`if` 用于判断一个条件是否成立。如果条件为真，就执行对应语句；如果条件为假，就跳过该语句。

基本格式：

```cpp
if (test-condition)
    statement;
```

示例：

```cpp
if (ch == ' ')
    ++spaces;
```

说明：

- `ch == ' '` 判断字符是否为空格；
- 如果是空格，`spaces` 加 1；
- 如果不是空格，则不执行 `++spaces`。

在 C++ 中，条件表达式会被转换为 `bool` 类型：

- `0` 表示 `false`；
- 非零值表示 `true`。

2. **if else 语句**

`if else` 用于二选一。

基本格式：

```cpp
if (test-condition)
    statement1;
else
    statement2;
```

如果条件为真，执行 `statement1`；否则执行 `statement2`。

示例：

```cpp
if (score >= 60)
    cout << "Pass";
else
    cout << "Fail";
```

3. **if else if else 多分支结构**

当程序需要从多个选项中选择一个时，可以使用多分支结构。

```cpp
if (test-condition1)
    statement1;
else if (test-condition2)
    statement2;
else
    statement3;
```

示例：

```cpp
if (score >= 90)
    cout << "A";
else if (score >= 80)
    cout << "B";
else if (score >= 60)
    cout << "C";
else
    cout << "Fail";
```

4. **逻辑表达式**

C++ 提供三个逻辑运算符：

```cpp
&&    逻辑与，and
||    逻辑或，or
!     逻辑非，not
```

逻辑与 `&&`：

只有两个条件都为真时，结果才为真。

```cpp
if (age >= 18 && age <= 60)
```

逻辑或 `||`：

只要有一个条件为真，结果就为真。

```cpp
if (ch == 'y' || ch == 'Y')
```

逻辑非 `!`：

把真变假，把假变真。

```cpp
if (!finished)
```

5. **使用逻辑运算符判断字符范围**

例如判断一个字符是否为英文字母：

```cpp
if ((ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z'))
```

含义：

- 如果 `ch` 在 `'a'` 到 `'z'` 之间，说明是小写字母；
- 或者 `ch` 在 `'A'` 到 `'Z'` 之间，说明是大写字母；
- 两种情况满足一种即可。

6. **cctype 字符函数库**

`<cctype>` 提供了许多字符判断函数，比手写条件更简洁。

常用函数：

```cpp
isalpha(ch)   判断是否为字母
isdigit(ch)   判断是否为数字
isspace(ch)   判断是否为空白字符
ispunct(ch)   判断是否为标点符号
```

示例：

```cpp
if (isalpha(ch))
    chars++;
else if (isspace(ch))
    whitespace++;
else if (isdigit(ch))
    digits++;
else if (ispunct(ch))
    punct++;
else
    others++;
```

7. **条件运算符 ?:**

条件运算符是 C++ 中唯一需要三个操作数的运算符。

基本格式：

```cpp
expression1 ? expression2 : expression3
```

含义：

- 如果 `expression1` 为真，整个表达式的值为 `expression2`；
- 否则，整个表达式的值为 `expression3`。

示例：

```cpp
int max = a > b ? a : b;
```

等价于：

```cpp
if (a > b)
    max = a;
else
    max = b;
```

课件示例：

```cpp
3 > 2 ? 5 : 6    // 结果是 5
3 == 2 ? 4 : 9   // 结果是 9
```

8. **switch 语句**

`switch` 适合从多个固定选项中选择一个执行。

基本格式：

```cpp
switch (integer-expression)
{
    case label1:
        statement;
        break;
    case label2:
        statement;
        break;
    default:
        statement;
}
```

说明：

- `switch` 后面的表达式通常是整数类型或枚举类型；
- `case` 后面是标签值；
- 如果匹配某个 `case`，程序从该位置开始执行；
- `default` 是没有匹配项时执行的部分；
- `break` 用于跳出 `switch`。

9. **使用枚举作为 switch 标签**

枚举可以定义一组相关常量。

```cpp
enum {first, second, third, fourth};
```

默认值为：

```cpp
first = 0
second = 1
third = 2
fourth = 3
```

可以在 `switch` 中使用：

```cpp
switch (snumber)
{
    case first:
        cout << "Your choice is the first.\n";
        break;
    case second:
        cout << "Your choice is the second.\n";
        break;
}
```

10. **break 和 continue**

`break` 可以用于循环和 `switch`，作用是立即跳出当前循环或 `switch`。

```cpp
while (true)
{
    if (x == 0)
        break;
}
```

`continue` 只能用于循环，作用是跳过本轮循环剩余语句，直接进入下一轮循环。

```cpp
for (int i = 0; i < 10; i++)
{
    if (i == 5)
        continue;

    cout << i << endl;
}
```

11. **数字读取循环**

当程序想读取一系列数字时，如果用户输入的不是数字，`cin` 会发生输入失败。

例如：

```cpp
int n;
cin >> n;
```

如果用户输入单词而不是数字，会发生：

- `n` 的值保持不变；
- 错误输入仍留在输入队列中；
- `cin` 设置错误标志；
- `cin` 转换为 `bool` 时返回 `false`。

因此，可以利用这一点结束数字读取循环。

如果之后还想继续输入，需要调用：

```cpp
cin.clear();
```

它可以清除错误状态。

12. **基本文件输出**

C++ 使用 `<fstream>` 进行文件输入输出。

控制台输出使用：

```cpp
#include <iostream>
cout << data;
```

文件输出使用：

```cpp
#include <fstream>
ofstream outFile;
outFile.open("data.txt");
outFile << data;
outFile.close();
```

文件输出和 `cout` 很相似：

- `cout` 是控制台输出对象；
- `ofstream` 是文件输出对象；
- 都可以使用 `<<` 输出数据；
- 文件使用完后应调用 `close()` 关闭。

**三、PPT 中的代码整理**

**代码 1：使用 if 统计空格和字符数**

```cpp
// using the if statement
#include <iostream>

int main()
{
    using std::cin;
    using std::cout;

    char ch;
    int spaces = 0;
    int total = 0;

    cin.get(ch);

    while (ch != '.')
    {
        if (ch == ' ')
            ++spaces;

        ++total;
        cin.get(ch);
    }

    cout << spaces << " spaces, " << total;
    cout << " characters total in sentence\n";

    return 0;
}
```

中文解释：

- 程序逐字符读取输入；
- 遇到句号 `.` 时停止；
- `if (ch == ' ')` 判断当前字符是否为空格；
- `spaces` 统计空格数；
- `total` 统计总字符数；
- `cin.get(ch)` 可以读取空格。

示例输入：

```text
abc def 123.
```

输出：

```text
2 spaces, 11 characters total in sentence
```

体现知识点：

- `if` 判断；
- `while` 循环；
- 字符输入；
- 计数器变量；
- 空格字符判断。

**代码 2：使用 cctype 统计字符类型**

```cpp
// using the ctype.h library
#include <iostream>
#include <cctype>

int main()
{
    using namespace std;

    cout << "Enter text for analysis, and type @"
            " to terminate input.\n";

    char ch;
    int whitespace = 0;
    int digits = 0;
    int chars = 0;
    int punct = 0;
    int others = 0;

    cin.get(ch);

    while (ch != '@')
    {
        if (isalpha(ch))
            chars++;
        else if (isspace(ch))
            whitespace++;
        else if (isdigit(ch))
            digits++;
        else if (ispunct(ch))
            punct++;
        else
            others++;

        cin.get(ch);
    }

    cout << chars << " letters, "
         << whitespace << " whitespace, "
         << digits << " digits, "
         << punct << " punctuations, "
         << others << " others.\n";

    return 0;
}
```

中文解释：

- 输入以 `@` 作为结束标志；
- `isalpha(ch)` 判断字母；
- `isspace(ch)` 判断空白字符；
- `isdigit(ch)` 判断数字；
- `ispunct(ch)` 判断标点；
- `else` 统计其他字符；
- 使用 `else if` 可以让每个字符只被归入一类。

体现知识点：

- `<cctype>` 字符函数；
- 多分支判断；
- 哨兵字符；
- 字符分类统计。

**代码 3：使用 enum 和 switch**

```cpp
// using enum
#include <iostream>

// create named constants for 0 - 3
enum {first, second, third, fourth};

int main()
{
    using namespace std;

    cout << "Enter serial number (0-3): ";

    int snumber;
    cin >> snumber;

    while (snumber >= first && snumber <= fourth)
    {
        switch (snumber)
        {
            case first:
                cout << "Your choice is the first.\n";
                break;
            case second:
                cout << "Your choice is the second.\n";
                break;
            case third:
                cout << "Your choice is the third.\n";
                break;
            case fourth:
                cout << "Your choice is the fourth.\n";
                break;
        }

        cout << "Enter serial number (0-3): ";
        cin >> snumber;
    }

    cout << "Bye\n";

    return 0;
}
```

中文解释：

- `enum {first, second, third, fourth};` 定义四个枚举常量；
- 它们默认对应 `0`、`1`、`2`、`3`；
- `while` 判断输入是否在合法范围内；
- `switch` 根据输入执行不同分支；
- 每个 `case` 后使用 `break` 防止继续执行后面的分支。

输入示例：

```text
2
```

输出：

```text
Your choice is the third.
```

体现知识点：

- 枚举常量；
- `switch` 多分支选择；
- `case` 标签；
- `break`；
- 逻辑与 `&&`。

**代码 4：基本文件输出示例**

课件主要讲了文件输出步骤，可以整理成如下代码：

```cpp
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;

    ofstream outFile;

    outFile.open("result.txt");

    outFile << "This is a file output example." << endl;
    outFile << "C++ can write data to text files." << endl;

    outFile.close();

    return 0;
}
```

中文解释：

- `#include <fstream>` 引入文件输入输出库；
- `ofstream` 表示输出文件流；
- `outFile.open("result.txt")` 打开文件；
- `outFile << ...` 向文件写入内容；
- `outFile.close()` 关闭文件。

体现知识点：

- 文件输出；
- `ofstream` 对象；
- `open()` 方法；
- `close()` 方法；
- `<<` 同样可用于文件流。

**四、易混点**

- `if` 只控制它后面的一条语句；多条语句必须用 `{}` 包起来。
- `==` 是判断相等，`=` 是赋值。
- `&&` 要求两个条件都为真。
- `||` 只要求至少一个条件为真。
- `!` 表示逻辑取反。
- `else` 总是和离它最近且尚未匹配的 `if` 配对。
- `switch` 通常用于整数、字符或枚举类型，不适合直接判断范围。
- `case` 后如果没有 `break`，程序会继续执行后面的 `case`。
- `continue` 只能用于循环，不能用于 `switch` 单独跳出。
- `cin` 读取数字失败后，需要 `cin.clear()` 清除错误状态。
- 文件输出要包含 `<fstream>`，并在使用完后关闭文件。

**五、可写进实验报告的中文总结**

本章主要学习了 C++ 中的分支语句和逻辑运算符。通过 `if`、`if else` 和 `if else if else` 结构，程序可以根据不同条件执行不同语句，从而实现选择控制。逻辑运算符 `&&`、`||` 和 `!` 可以把多个条件组合起来，使条件判断更加灵活。

本章还学习了 `<cctype>` 字符函数库，它提供了判断字母、数字、空白字符和标点符号的函数，使字符分类处理更加方便。通过字符统计程序，我理解了如何结合循环、分支语句和字符函数完成文本分析。

此外，本章介绍了条件运算符 `?:`、`switch` 多分支语句、`break` 和 `continue` 的用法，以及数字读取循环和基本文件输出。通过这些内容，我掌握了 C++ 中选择结构、逻辑判断和简单文件操作的基本方法。

---

**English Version**

**1. Core Concepts**

Chapter 6 mainly introduces branching statements and logical operators in C++. Branching statements allow a program to choose different execution paths according to different conditions. Logical operators are used to combine or modify conditions.

This chapter covers:

- the `if` statement;
- the `if else` statement;
- the `if else if else` construction;
- logical operators `&&`, `||`, and `!`;
- the `<cctype>` library of character functions;
- the conditional operator `?:`;
- the `switch` statement;
- the `break` and `continue` statements;
- number-reading loops;
- basic file input and output.

**2. Key Points**

The `if` statement executes a statement only when a condition is true.

```cpp
if (test-condition)
    statement;
```

Example:

```cpp
if (ch == ' ')
    ++spaces;
```

In C++, a test condition is converted to a Boolean value. Zero means `false`, and nonzero means `true`.

The `if else` statement chooses one of two branches.

```cpp
if (test-condition)
    statement1;
else
    statement2;
```

The `if else if else` construction is used for multiple choices.

```cpp
if (test-condition1)
    statement1;
else if (test-condition2)
    statement2;
else
    statement3;
```

C++ provides three logical operators:

```cpp
&&    logical AND
||    logical OR
!     logical NOT
```

`&&` is true only when both conditions are true. `||` is true when at least one condition is true. `!` reverses a Boolean value.

Example:

```cpp
if ((ch >= 'a' && ch <= 'z') || (ch >= 'A' && ch <= 'Z'))
```

This expression checks whether `ch` is an alphabetic character.

The `<cctype>` library provides character-related functions:

```cpp
isalpha(ch)   checks whether ch is a letter
isdigit(ch)   checks whether ch is a digit
isspace(ch)   checks whether ch is whitespace
ispunct(ch)   checks whether ch is punctuation
```

The conditional operator `?:` is the only C++ operator that takes three operands.

```cpp
expression1 ? expression2 : expression3
```

If `expression1` is true, the whole expression has the value of `expression2`; otherwise, it has the value of `expression3`.

Example:

```cpp
int max = a > b ? a : b;
```

The `switch` statement handles selection from a list of choices.

```cpp
switch (integer-expression)
{
    case label1:
        statement;
        break;
    case label2:
        statement;
        break;
    default:
        statement;
}
```

The `break` statement exits a loop or a `switch` statement. The `continue` statement skips the rest of the current loop body and starts the next loop cycle.

When reading numbers, if the user enters non-numeric input, `cin` fails. In this case:

- the variable is left unchanged;
- the wrong input remains in the input queue;
- an error flag is set;
- `cin` returns `false` when converted to `bool`.

The error flag can be reset with:

```cpp
cin.clear();
```

For file output, C++ uses the `<fstream>` header and the `ofstream` class.

```cpp
#include <fstream>

ofstream outFile;
outFile.open("result.txt");
outFile << "Hello file!" << endl;
outFile.close();
```

**3. Code from the PPT**

**Example 1: Counting Spaces with if**

```cpp
#include <iostream>

int main()
{
    using std::cin;
    using std::cout;

    char ch;
    int spaces = 0;
    int total = 0;

    cin.get(ch);

    while (ch != '.')
    {
        if (ch == ' ')
            ++spaces;

        ++total;
        cin.get(ch);
    }

    cout << spaces << " spaces, " << total;
    cout << " characters total in sentence\n";

    return 0;
}
```

Explanation:

- the program reads characters one by one;
- it stops when it reads a period;
- `if (ch == ' ')` checks whether the character is a space;
- `spaces` counts spaces;
- `total` counts all characters.

**Example 2: Character Classification with cctype**

```cpp
#include <iostream>
#include <cctype>

int main()
{
    using namespace std;

    cout << "Enter text for analysis, and type @"
            " to terminate input.\n";

    char ch;
    int whitespace = 0;
    int digits = 0;
    int chars = 0;
    int punct = 0;
    int others = 0;

    cin.get(ch);

    while (ch != '@')
    {
        if (isalpha(ch))
            chars++;
        else if (isspace(ch))
            whitespace++;
        else if (isdigit(ch))
            digits++;
        else if (ispunct(ch))
            punct++;
        else
            others++;

        cin.get(ch);
    }

    cout << chars << " letters, "
         << whitespace << " whitespace, "
         << digits << " digits, "
         << punct << " punctuations, "
         << others << " others.\n";

    return 0;
}
```

Explanation:

- `@` is used as the sentinel character;
- `isalpha()` checks letters;
- `isspace()` checks whitespace;
- `isdigit()` checks digits;
- `ispunct()` checks punctuation;
- `else` counts other characters.

**Example 3: enum and switch**

```cpp
#include <iostream>

enum {first, second, third, fourth};

int main()
{
    using namespace std;

    cout << "Enter serial number (0-3): ";

    int snumber;
    cin >> snumber;

    while (snumber >= first && snumber <= fourth)
    {
        switch (snumber)
        {
            case first:
                cout << "Your choice is the first.\n";
                break;
            case second:
                cout << "Your choice is the second.\n";
                break;
            case third:
                cout << "Your choice is the third.\n";
                break;
            case fourth:
                cout << "Your choice is the fourth.\n";
                break;
        }

        cout << "Enter serial number (0-3): ";
        cin >> snumber;
    }

    cout << "Bye\n";

    return 0;
}
```

Explanation:

- the enumeration constants represent values from `0` to `3`;
- the `while` loop checks whether the input is valid;
- the `switch` statement selects the corresponding output;
- `break` prevents fall-through to the next case.

**Example 4: Basic File Output**

```cpp
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;

    ofstream outFile;

    outFile.open("result.txt");

    outFile << "This is a file output example." << endl;
    outFile << "C++ can write data to text files." << endl;

    outFile.close();

    return 0;
}
```

Explanation:

- `<fstream>` provides file input and output;
- `ofstream` is used for file output;
- `open()` connects the stream object to a file;
- `<<` writes data to the file;
- `close()` closes the file.

**4. Common Confusing Points**

- `if` controls only one statement unless braces are used.
- `==` tests equality, while `=` assigns a value.
- `&&` requires both conditions to be true.
- `||` requires at least one condition to be true.
- `!` reverses a condition.
- `else` matches the nearest unmatched `if`.
- `switch` is suitable for fixed integer, character, or enumeration choices.
- Without `break`, execution continues into the next `case`.
- `continue` is used only in loops.
- After failed numeric input, `cin.clear()` is needed to reset the error flag.
- File output requires `<fstream>` and should be closed after use.

**5. Report Summary**

In this chapter, I learned about branching statements and logical operators in C++. With `if`, `if else`, and `if else if else`, a program can execute different statements according to different conditions. Logical operators such as `&&`, `||`, and `!` make condition testing more flexible by combining or modifying Boolean expressions.

This chapter also introduced the `<cctype>` character function library, which provides useful functions for checking letters, digits, whitespace, and punctuation. Through the character analysis example, I learned how to combine loops, branching statements, and character functions to process text input.

In addition, I learned the conditional operator `?:`, the `switch` statement, and the use of `break` and `continue`. The chapter also introduced number-reading loops and basic file output. These topics helped me understand selection control, logical judgment, and simple file operations in C++.

> 下面进行第七章，依旧是先中文再翻译成英文

<details><summary>1 previous message</summary>

> 继续第七章。我先读取 `Lecture 7 Functions-C++s Programming Modulesb.pdf`，这一章通常是函数的核心章节，我会重点整理函数原型、参数传递、数组/结构/字符串作为参数、递归、函数指针等。
> </details>

下面是第七章 **Lecture 7 Functions: C++'s Programming Modules** 的整理，先中文，后英文。

**中文版**

**一、本章核心概念**

第七章主要学习 C++ 中的函数。函数是 C++ 程序的基本模块，可以把复杂程序分解成多个相对独立的小功能，从而提高代码的可读性、复用性和可维护性。

本章内容包括：

- 函数定义、函数原型和函数调用
- 按值传递参数
- 函数处理数组
- 使用 `const` 指针参数
- 函数处理 C 风格字符串
- 函数处理结构体
- 函数处理 `string` 类对象
- 内联函数
- 引用变量
- 按引用传递参数
- 默认参数
- 函数重载
- 函数模板
- 函数模板特化

C++ 相比 C 增加了许多函数相关特性，如内联函数、引用传递、默认参数、函数重载和函数模板。

**二、本章重点内容**

1. **使用函数的三个步骤**

使用一个 C++ 函数通常需要三步：

```cpp
void simple();   // 函数原型

simple();        // 函数调用

void simple()    // 函数定义
{
    ...
}
```

函数原型告诉编译器函数的接口，函数调用执行函数，函数定义说明函数具体做什么。

2. **函数定义**

没有返回值的函数使用 `void`：

```cpp
void functionName(parameterList)
{
    statements;
    return; // 可选
}
```

有返回值的函数需要指定返回类型，并使用 `return` 返回结果：

```cpp
typeName functionName(parameterList)
{
    statements;
    return value;
}
```

例如：

```cpp
double vcube(double x)
{
    return x * x * x;
}
```

3. **函数原型**

函数原型描述函数接口，包括：

- 返回值类型；
- 函数名；
- 参数个数；
- 参数类型。

示例：

```cpp
double vcube(double x);
```

函数原型是语句，末尾必须有分号。

函数原型的作用：

- 让编译器正确处理函数返回值；
- 检查函数调用时参数个数是否正确；
- 检查参数类型是否正确；
- 必要时进行合理类型转换。

4. **C++ 函数原型与 C 的区别**

在 C++ 中：

```cpp
void say_hi();
```

表示函数没有参数。

而在 ANSI C 中，空括号表示没有说明参数列表。

C++ 中如果不想指定参数列表，可以写：

```cpp
void say_bye(...);
```

但这种写法通常只用于和 C 中可变参数函数交互，例如 `printf()`。

5. **按值传递**

C++ 默认按值传递参数。也就是说，函数得到的是实参值的副本，而不是原变量本身。

```cpp
double volume = vcube(len);
```

如果 `len` 的值是 `3`，那么函数参数 `x` 得到的是 `3` 的副本。函数中修改 `x` 不会影响 `len`。

6. **多个参数**

函数可以有多个参数，用逗号分隔。

```cpp
func(a1, a2);
```

函数原型也要写清楚参数类型：

```cpp
int add(int a, int b);
```

7. **函数与数组**

数组作为函数参数时，传递的是数组第一个元素的地址。

```cpp
int average(int arr[], int n);
```

这里 `arr` 实际上相当于指针。因为数组本身不携带长度信息，所以通常还要传入数组元素个数 `n`。

示例：

```cpp
int ave = average(scores, ArSize);
```

8. **函数与 C 风格字符串**

C 风格字符串可以用三种形式表示：

```cpp
char ghost[15] = "galloping";
char * str = "galumphing";
"gamboling"
```

它们作为参数传递时，本质上都是传递第一个字符的地址，即 `char *`。

C 风格字符串和普通字符数组的区别是：字符串以 `'\0'` 作为结束标志。

9. **函数与结构体**

结构体可以像普通变量一样传递给函数。

数组名代表数组首元素地址，但结构体名只是结构体变量名。如果需要结构体地址，需要使用 `&`。

```cpp
struct student
{
    string name;
    float grade[3];
};

student s;
```

结构体可以：

- 按值传递给函数；
- 作为函数返回值；
- 用赋值运算符赋给同类型结构体。

10. **函数与 string 对象**

`string` 类对象更像结构体或类对象，而不像 C 风格字符数组。

可以定义 `string` 数组：

```cpp
string list[SIZE];
```

也可以把 `string` 数组传给函数：

```cpp
void display(const string color[], int n);
```

其中 `const` 表示函数不会修改数组内容。

11. **函数与对象**

C++ 类对象可以按值传递，也可以通过指针传递。

- 按值传递：函数操作的是原对象的副本；
- 传递对象指针：函数可以操作原对象。

这和结构体的处理方式相似。

12. **函数指针**

函数和数据一样，也有地址。函数地址是函数机器代码开始的位置。

使用函数指针可以：

- 获取函数地址；
- 声明指向函数的指针；
- 通过函数指针调用函数。

这种机制可以让一个函数在不同时间调用不同的函数，提高程序灵活性。

13. **内联函数**

内联函数用于提高程序运行速度。

普通函数调用需要跳转到函数地址执行，执行完再跳回原位置。内联函数则由编译器把函数代码直接插入到调用位置，减少函数调用开销。

定义方式：

```cpp
inline double square(double x)
{
    return x * x;
}
```

优点：

- 执行速度可能更快。

缺点：

- 如果调用很多次，代码会被复制多份，增加程序体积。

适合内联的函数通常很短。如果函数体很长，就不适合写成内联函数。

14. **引用变量**

引用是变量的别名。

```cpp
int Age = 17;
int & StudentAge = Age;
```

这里 `StudentAge` 是 `Age` 的另一个名字。修改 `StudentAge` 就等于修改 `Age`。

引用特点：

- 定义时必须初始化；
- 初始化后不能再引用其他变量；
- 引用不是新变量，而是已有变量的别名。

注意：

```cpp
int & StudentAge = Age;
```

这里的 `&` 表示引用类型，不是取地址。

而：

```cpp
&StudentAge
```

这里的 `&` 表示取地址。

15. **按引用传递**

引用最常见用途是作为函数参数。

```cpp
void swap(int &a, int &b)
{
    int temp = a;
    a = b;
    b = temp;
}
```

按引用传递时，函数中的参数是调用函数中变量的别名，因此可以直接修改原变量。

对比：

- 按值传递：函数处理副本；
- 按引用传递：函数处理原变量。

16. **默认参数**

默认参数是在函数调用时省略某个参数时自动使用的值。

```cpp
void fun(int n = 1);
```

调用：

```cpp
fun();
```

等价于：

```cpp
fun(1);
```

默认参数必须在函数原型中指定。

默认参数可以减少函数重载数量，在类设计中特别常用。

17. **函数重载**

函数重载，也叫函数多态，指多个函数可以使用同一个名字，但参数列表必须不同。

函数特征标包括：

- 参数个数；
- 参数类型；
- 参数顺序。

示例：

```cpp
void print(const char * str, int width);
void print(double d, int width);
void print(long l, int width);
void print(int i, int width);
void print(const char * str);
```

调用时，编译器根据实参匹配对应函数：

```cpp
print("Apples", 15);
print("Pear");
print(20.0, 10);
print(100, 8);
print(123L, 15);
```

注意：不要滥用函数重载。它适合用于功能相似但数据类型不同的函数。

18. **函数模板**

函数模板用于通用程序设计，可以让同一套算法适用于不同类型。

示例：

```cpp
template <typename T>
void Swap(T &a, T &b)
{
    T temp;
    temp = a;
    a = b;
    b = temp;
}
```

当调用：

```cpp
Swap(i, j);
Swap(x, y);
```

编译器会根据参数类型自动生成对应版本：

```cpp
void Swap(int &, int &);
void Swap(double &, double &);
```

模板的优点：

- 减少重复代码；
- 提高代码可靠性；
- 适合同一算法处理多种类型。

模板不会让最终可执行程序一定变小，因为编译器仍会为不同类型生成不同函数版本。

**三、PPT 中的代码整理**

**代码 1：函数定义、原型和调用**

```cpp
// defining, prototyping, and calling a function
#include <iostream>

void simple(); // function prototype

int main()
{
    using namespace std;

    cout << "main() will call the simple() function:\n";
    simple();
    cout << "main() is finished with the simple() function.\n";

    return 0;
}

void simple()
{
    using namespace std;

    cout << "The simple() is a simple function.\n";
}
```

说明：

- `void simple();` 是函数原型；
- `simple();` 是函数调用；
- `void simple() { ... }` 是函数定义；
- `void` 表示函数没有返回值。

**代码 2：函数原型与返回值**

```cpp
#include <iostream>

void number(int);
double vcube(double x);

int main()
{
    using namespace std;

    number(3);

    cout << "Give me the length of side: ";
    double len;
    cin >> len;

    double volume = vcube(len);

    cout << "A " << len << "-foot cube has a volume of ";
    cout << volume << " cubic feet.\n";

    return 0;
}

void number(int n)
{
    using namespace std;

    for (int i = 0; i < n; i++)
        cout << "hello!";

    cout << endl;
}

double vcube(double x)
{
    return x * x * x;
}
```

说明：

- `number(int)` 没有返回值；
- `vcube(double)` 返回一个 `double`；
- 参数默认按值传递；
- `return x * x * x;` 返回立方体体积。

**代码 3：函数处理数组**

```cpp
#include <iostream>

const int ArSize = 6;

int average(int arr[], int n);

int main()
{
    using namespace std;

    int scores[ArSize] = {80, 90, 85, 70, 75, 60};

    int ave = average(scores, ArSize);

    cout << "Average is " << ave << "\n";

    return 0;
}

int average(int arr[], int n)
{
    int total = 0;

    for (int i = 0; i < n; i++)
        total = total + arr[i];

    return int(total / n);
}
```

说明：

- 数组作为参数时传递首元素地址；
- `n` 表示数组元素个数；
- 函数中可用 `arr[i]` 访问数组元素；
- 返回平均值。

**代码 4：函数处理结构体**

```cpp
#include <iostream>
#include <string>

#define N_QUIZS 3

using namespace std;

struct quiz_grade
{
    string name;
    float grade[N_QUIZS];
};

quiz_grade average(quiz_grade n);
void show_agrade(quiz_grade n);

int main()
{
    quiz_grade ng;

    ng.name = "Zhao";
    ng.grade[0] = 4.5;
    ng.grade[1] = 5.0;

    quiz_grade ave_g = average(ng);

    for (int i = 0; i < N_QUIZS - 1; i++)
    {
        cout << ng.name << "'s N" << i + 1
             << " score is " << ng.grade[i] << ".\n";
    }

    show_agrade(ave_g);

    return 0;
}

quiz_grade average(quiz_grade n)
{
    quiz_grade ngaverage;
    float navg = 0.0;

    for (int i = 0; i < N_QUIZS - 1; i++)
    {
        navg += n.grade[i];
    }

    ngaverage.grade[N_QUIZS - 1] = navg / (N_QUIZS - 1);
    ngaverage.name = n.name;

    return ngaverage;
}

void show_agrade(quiz_grade n)
{
    cout << n.name << "'s average score is "
         << n.grade[2] << ".\n";
}
```

说明：

- `quiz_grade` 是结构体类型；
- 结构体可以作为函数参数；
- 结构体也可以作为函数返回值；
- 此处 `average()` 返回一个包含平均分的新结构体。

**代码 5：函数处理 string 对象数组**

```cpp
#include <iostream>
#include <string>

using namespace std;

const int SIZE = 2;

void display(const string color[], int n);

int main()
{
    string list[SIZE];

    cout << "Enter your " << SIZE << " favorite colors:\n";

    for (int i = 0; i < SIZE; i++)
    {
        cout << i + 1 << ": ";
        getline(cin, list[i]);
    }

    cout << "Your list:\n";
    display(list, SIZE);

    return 0;
}

void display(const string sa[], int n)
{
    for (int i = 0; i < n; i++)
        cout << i + 1 << ": " << sa[i] << endl;
}
```

说明：

- `string list[SIZE]` 是字符串对象数组；
- `getline(cin, list[i])` 读取一整行；
- `const string sa[]` 表示函数不修改数组内容；
- `display()` 用于显示数组中的字符串。

**代码 6：内联函数**

```cpp
#include <iostream>

inline double square(double x)
{
    return x * x;
}

int main()
{
    using namespace std;

    double a, b;
    double c = 2.0;

    a = square(3.0);
    b = square(1.5 + 2.5);

    cout << "a = " << a << "\nb = " << b << "\n";
    cout << "c = " << c;
    cout << ", c squared = " << square(c++) << "\n";
    cout << "Now c = " << c << "\n";

    return 0;
}
```

说明：

- `inline` 请求编译器将函数代码插入调用处；
- `square()` 计算平方；
- 内联函数适合短小、频繁调用的函数。

**代码 7：引用变量**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    int Age = 17;
    int & StudentAge = Age;

    cout << "Age = " << Age;
    cout << ", StudentAge = " << StudentAge << endl;

    StudentAge++;

    cout << "Age = " << Age;
    cout << ", StudentAge = " << StudentAge << endl;

    cout << "Age address = " << &Age;
    cout << ", StudentAge address = " << &StudentAge << endl;

    return 0;
}
```

说明：

- `StudentAge` 是 `Age` 的引用；
- 修改 `StudentAge` 等于修改 `Age`；
- 两者地址相同；
- 引用必须在声明时初始化。

**代码 8：函数模板**

```cpp
#include <iostream>

template <typename T>
void Swap(T &a, T &b);

int main()
{
    using namespace std;

    int i = 10, j = 20;

    cout << "i, j = " << i << ", " << j << ".\n";
    cout << "Using compiler-generated int swapper:\n";

    Swap(i, j);

    cout << "Now i, j = " << i << ", " << j << ".\n";

    double x = 2.5, y = 3.6;

    cout << "x, y = " << x << ", " << y << ".\n";
    cout << "Using compiler-generated double swapper:\n";

    Swap(x, y);

    cout << "Now x, y = " << x << ", " << y << ".\n";

    return 0;
}

template <typename T>
void Swap(T &a, T &b)
{
    T temp;

    temp = a;
    a = b;
    b = temp;
}
```

说明：

- `template <typename T>` 定义函数模板；
- `T` 表示任意类型；
- `Swap(int &, int &)` 和 `Swap(double &, double &)` 会由编译器自动生成；
- 参数使用引用，因此可以修改原变量。

**四、易混点**

- 函数原型末尾必须有分号，函数定义末尾不加分号。
- `void` 函数没有返回值。
- 按值传递不会修改原变量。
- 数组作为函数参数时传递的是地址，不是整个数组副本。
- C 风格字符串作为参数时本质上传递 `char *`。
- 结构体可以按值传递和返回，但大结构体按值传递可能效率较低。
- `const` 参数可以防止函数修改传入数据。
- 引用必须在声明时初始化。
- 按引用传递可以修改原变量。
- 默认参数应写在函数原型中。
- 函数重载不能只靠返回类型不同来区分。
- 函数模板适合同一算法处理不同类型。

**五、可写进实验报告的中文总结**

本章主要学习了 C++ 中函数的基本概念和高级特性。函数是 C++ 程序的重要模块，使用函数可以将复杂问题分解为多个小任务，从而提高程序的结构化程度和可维护性。通过函数原型、函数定义和函数调用的学习，我掌握了函数的基本使用方法。

本章还学习了函数参数传递方式。C++ 默认按值传递参数，函数只处理实参的副本；而按引用传递可以让函数直接操作原变量。数组、C 风格字符串、结构体和 `string` 对象都可以作为函数参数，其中数组和字符串通常以地址形式传递，结构体和对象既可以按值传递，也可以通过指针或引用传递。

此外，本章介绍了 C++ 的重要函数特性，包括内联函数、默认参数、函数重载和函数模板。内联函数可以减少函数调用开销，默认参数提高了函数调用的灵活性，函数重载允许多个函数使用同一名称，函数模板则支持通用程序设计。通过这些内容，我进一步理解了 C++ 函数机制的灵活性和强大表达能力。

---

**English Version**

**1. Core Concepts**

Chapter 7 mainly introduces functions in C++. Functions are the basic programming modules of C++. They help divide a complex program into smaller tasks, making the program easier to read, reuse, and maintain.

This chapter covers:

- function definitions, prototypes, and calls;
- passing arguments by value;
- functions that process arrays;
- `const` pointer parameters;
- functions that process C-style strings;
- functions that process structures;
- functions that process `string` class objects;
- inline functions;
- reference variables;
- passing arguments by reference;
- default arguments;
- function overloading;
- function templates;
- function template specializations.

C++ adds several function features beyond C, including inline functions, reference parameters, default arguments, function overloading, and function templates.

**2. Key Points**

To use a C++ function, we usually need three steps:

```cpp
void simple();   // function prototype

simple();        // function call

void simple()    // function definition
{
    ...
}
```

A function prototype tells the compiler the function interface. A function call executes the function. A function definition describes what the function does.

A function without a return value uses `void`:

```cpp
void functionName(parameterList)
{
    statements;
}
```

A function with a return value specifies a return type and uses `return`:

```cpp
typeName functionName(parameterList)
{
    statements;
    return value;
}
```

Example:

```cpp
double vcube(double x)
{
    return x * x * x;
}
```

A function prototype includes the return type, function name, number of arguments, and argument types.

```cpp
double vcube(double x);
```

Function prototypes help the compiler check return values, argument numbers, and argument types.

C++ normally passes arguments by value. This means the function receives a copy of the argument value, not the original variable.

```cpp
double volume = vcube(len);
```

If the function changes its parameter, the original variable `len` is not changed.

A function can have multiple arguments:

```cpp
func(a1, a2);
```

When an array is passed to a function, the address of the first element is passed.

```cpp
int average(int arr[], int n);
```

Because an array does not carry its size information, the number of elements is usually passed as a separate argument.

C-style strings are also passed as addresses. These forms can all be passed to string-processing functions:

```cpp
char ghost[15] = "galloping";
char * str = "galumphing";
"gamboling"
```

A C-style string differs from a regular character array because it ends with the null character `'\0'`.

Structures can be passed to functions like ordinary variables. They can also be returned from functions and assigned to other structures of the same type.

```cpp
struct student
{
    string name;
    float grade[3];
};
```

A `string` object is more like a structure or class object than a C-style character array. We can create an array of `string` objects and pass it to a function.

```cpp
void display(const string color[], int n);
```

The `const` keyword means the function will not modify the array elements.

Functions also have addresses. A function pointer stores the address of a function and can be used to call different functions at different times.

Inline functions are designed to reduce function call overhead.

```cpp
inline double square(double x)
{
    return x * x;
}
```

The compiler may replace the function call with the function code itself. Inline functions can be faster, but they may increase program size.

A reference is an alias for an existing variable.

```cpp
int Age = 17;
int & StudentAge = Age;
```

`StudentAge` and `Age` refer to the same variable. A reference must be initialized when declared.

References are often used as function parameters.

```cpp
void swap(int &a, int &b)
{
    int temp = a;
    a = b;
    b = temp;
}
```

Passing by reference allows the function to modify the original variables.

A default argument is a value used automatically when an argument is omitted.

```cpp
void fun(int n = 1);
```

Then:

```cpp
fun();
```

is the same as:

```cpp
fun(1);
```

Function overloading allows several functions to have the same name but different argument lists.

```cpp
void print(const char * str, int width);
void print(double d, int width);
void print(int i, int width);
void print(const char * str);
```

The compiler chooses the correct function according to the function signature. The signature includes the number, types, and order of arguments.

Function templates support generic programming.

```cpp
template <typename T>
void Swap(T &a, T &b)
{
    T temp;
    temp = a;
    a = b;
    b = temp;
}
```

The compiler generates specific versions of the function according to the argument types used.

**3. Code from the PPT**

**Example 1: Function Prototype, Call, and Definition**

```cpp
#include <iostream>

void simple();

int main()
{
    using namespace std;

    cout << "main() will call the simple() function:\n";
    simple();
    cout << "main() is finished with the simple() function.\n";

    return 0;
}

void simple()
{
    using namespace std;

    cout << "The simple() is a simple function.\n";
}
```

This example shows the three basic parts of using a function: prototype, call, and definition.

**Example 2: Function with Arguments and Return Value**

```cpp
#include <iostream>

void number(int);
double vcube(double x);

int main()
{
    using namespace std;

    number(3);

    cout << "Give me the length of side: ";
    double len;
    cin >> len;

    double volume = vcube(len);

    cout << "A " << len << "-foot cube has a volume of ";
    cout << volume << " cubic feet.\n";

    return 0;
}

void number(int n)
{
    using namespace std;

    for (int i = 0; i < n; i++)
        cout << "hello!";

    cout << endl;
}

double vcube(double x)
{
    return x * x * x;
}
```

`number()` has no return value, while `vcube()` returns a `double`.

**Example 3: Function Processing an Array**

```cpp
#include <iostream>

const int ArSize = 6;

int average(int arr[], int n);

int main()
{
    using namespace std;

    int scores[ArSize] = {80, 90, 85, 70, 75, 60};

    int ave = average(scores, ArSize);

    cout << "Average is " << ave << "\n";

    return 0;
}

int average(int arr[], int n)
{
    int total = 0;

    for (int i = 0; i < n; i++)
        total = total + arr[i];

    return int(total / n);
}
```

The array argument is passed as an address, and `n` gives the number of elements.

**Example 4: Function Processing a Structure**

```cpp
#include <iostream>
#include <string>

#define N_QUIZS 3

using namespace std;

struct quiz_grade
{
    string name;
    float grade[N_QUIZS];
};

quiz_grade average(quiz_grade n);
void show_agrade(quiz_grade n);

int main()
{
    quiz_grade ng;

    ng.name = "Zhao";
    ng.grade[0] = 4.5;
    ng.grade[1] = 5.0;

    quiz_grade ave_g = average(ng);

    show_agrade(ave_g);

    return 0;
}

quiz_grade average(quiz_grade n)
{
    quiz_grade ngaverage;
    float navg = 0.0;

    for (int i = 0; i < N_QUIZS - 1; i++)
        navg += n.grade[i];

    ngaverage.grade[N_QUIZS - 1] = navg / (N_QUIZS - 1);
    ngaverage.name = n.name;

    return ngaverage;
}

void show_agrade(quiz_grade n)
{
    cout << n.name << "'s average score is "
         << n.grade[2] << ".\n";
}
```

This example shows that structures can be passed to and returned from functions.

**Example 5: Function Processing string Objects**

```cpp
#include <iostream>
#include <string>

using namespace std;

const int SIZE = 2;

void display(const string color[], int n);

int main()
{
    string list[SIZE];

    cout << "Enter your " << SIZE << " favorite colors:\n";

    for (int i = 0; i < SIZE; i++)
    {
        cout << i + 1 << ": ";
        getline(cin, list[i]);
    }

    cout << "Your list:\n";
    display(list, SIZE);

    return 0;
}

void display(const string sa[], int n)
{
    for (int i = 0; i < n; i++)
        cout << i + 1 << ": " << sa[i] << endl;
}
```

This example passes an array of `string` objects to a function.

**Example 6: Inline Function**

```cpp
#include <iostream>

inline double square(double x)
{
    return x * x;
}

int main()
{
    using namespace std;

    double a, b;
    double c = 2.0;

    a = square(3.0);
    b = square(1.5 + 2.5);

    cout << "a = " << a << "\nb = " << b << "\n";
    cout << "c = " << c;
    cout << ", c squared = " << square(c++) << "\n";
    cout << "Now c = " << c << "\n";

    return 0;
}
```

The `inline` keyword suggests replacing the function call with the function body.

**Example 7: Reference Variable**

```cpp
#include <iostream>

int main()
{
    using namespace std;

    int Age = 17;
    int & StudentAge = Age;

    cout << "Age = " << Age;
    cout << ", StudentAge = " << StudentAge << endl;

    StudentAge++;

    cout << "Age = " << Age;
    cout << ", StudentAge = " << StudentAge << endl;

    cout << "Age address = " << &Age;
    cout << ", StudentAge address = " << &StudentAge << endl;

    return 0;
}
```

`StudentAge` is an alias for `Age`, so both names refer to the same variable.

**Example 8: Function Template**

```cpp
#include <iostream>

template <typename T>
void Swap(T &a, T &b);

int main()
{
    using namespace std;

    int i = 10, j = 20;
    Swap(i, j);

    double x = 2.5, y = 3.6;
    Swap(x, y);

    return 0;
}

template <typename T>
void Swap(T &a, T &b)
{
    T temp;

    temp = a;
    a = b;
    b = temp;
}
```

The template lets the same swapping algorithm work with different data types.

**4. Common Confusing Points**

- A function prototype ends with a semicolon, but a function definition does not.
- A `void` function has no return value.
- Passing by value does not change the original variable.
- Passing an array to a function passes its address.
- A C-style string is passed as `char *`.
- Structures can be passed and returned by value.
- `const` parameters prevent modification.
- A reference must be initialized when declared.
- Passing by reference allows the function to modify the original variable.
- Default arguments should be specified in the prototype.
- Function overloading cannot be based only on return type.
- Function templates are useful when the same algorithm applies to different types.

**5. Report Summary**

In this chapter, I learned the basic concepts and advanced features of functions in C++. Functions are important programming modules that help divide complex problems into smaller tasks. By learning function prototypes, function definitions, and function calls, I understood how to define and use functions correctly.

This chapter also introduced different ways of passing function arguments. C++ normally passes arguments by value, so the function works with copies of the original values. Passing by reference allows a function to work directly with the original variables. Arrays, C-style strings, structures, and `string` objects can all be used as function arguments. Arrays and strings are usually passed as addresses, while structures and objects can be passed by value, pointer, or reference.

In addition, I learned several important C++ function features, including inline functions, default arguments, function overloading, and function templates. Inline functions can reduce function call overhead, default arguments make function calls more flexible, function overloading allows several functions to share the same name, and function templates support generic programming. These features show the flexibility and expressive power of C++ functions.

> 下面进行第八章，依旧是先中文再翻译成英文

<details><summary>1 previous message</summary>

> 继续第八章。我先读取 `Lecture 8 Memory Models and Namespaces.pdf`，这一章会把变量作用域、存储持续性、链接性、命名空间这些偏“程序组织和内存模型”的内容整理清楚。
> </details>

下面是第八章 **Lecture 8 Memory Models and Namespaces** 的整理，先中文，后英文。

**中文版**

**一、本章核心概念**

第八章主要学习 C++ 的内存模型和命名空间。随着程序规模变大，程序通常会被拆分成多个源文件分别编译，然后再链接成最终的可执行程序。因此，本章重点讨论：

- 程序的分离编译；
- 头文件的组织方式；
- 存储持续性；
- 作用域；
- 链接性；
- 动态存储；
- 命名空间。

这些内容主要用于理解变量、函数和类型在程序中的“可见范围”和“生命周期”。

**二、本章重点内容**

1. **分离编译**

C++ 允许把一个程序拆分成多个文件。每个源文件可以单独编译，最后再链接成完整程序。

一个较好的程序组织方式通常包括三部分：

- 头文件：存放结构体声明、类声明、函数原型、常量、模板等；
- 函数实现文件：存放函数定义；
- 主程序文件：调用这些函数。

例如：

```cpp
// ctft.h
struct ctemp;
struct ftemp;
ftemp ctemp_to_ftemp(ctemp);
void showftemp(ctemp, ftemp);
```

```cpp
// file1.cpp
#include "ctft.h"
// function definitions
```

```cpp
// file2.cpp
#include "ctft.h"
// main function
```

这样组织的优点：

- 修改一个源文件时，只需重新编译该文件；
- 相同函数可以被多个程序复用；
- 更符合面向对象程序设计中“类型定义”和“操作实现”分离的思想。

2. **头文件中通常放什么**

头文件中常见内容包括：

- 函数原型；
- `#define` 或 `const` 定义的符号常量；
- 结构体声明；
- 类声明；
- 模板声明；
- 内联函数。

通常不应该把普通函数定义或变量定义放进头文件，除非函数是 `inline`。

3. **#include <...> 和 #include "..." 的区别**

```cpp
#include <iostream>
```

尖括号通常用于标准库或系统库头文件。编译器会优先在系统标准路径中查找。

```cpp
#include "ctft.h"
```

双引号通常用于用户自定义头文件。编译器会优先在当前源文件所在目录查找，如果找不到，再去系统路径中查找。

4. **头文件保护**

为了避免同一个头文件被重复包含，可以使用：

```cpp
#ifndef CTFT_H
#define CTFT_H

// header file contents

#endif
```

含义：

- 如果 `CTFT_H` 没有被定义，就处理中间内容；
- 然后定义 `CTFT_H`；
- 如果以后再次包含该头文件，中间内容会被跳过。

这可以避免重复声明导致的错误。

5. **摄氏温度转华氏温度示例**

头文件：

```cpp
#ifndef CTFT_H
#define CTFT_H

struct ctemp
{
    double ctemperature;
};

struct ftemp
{
    double ftemperature;
};

ftemp ctemp_to_ftemp(ctemp);
void showftemp(ctemp, ftemp);

#endif
```

函数实现文件：

```cpp
#include <iostream>
#include "ctft.h"

ftemp ctemp_to_ftemp(ctemp ct)
{
    ftemp ft;
    ft.ftemperature = (ct.ctemperature * 9 / 5) + 32;
    return ft;
}

void showftemp(ctemp ct, ftemp ft)
{
    using namespace std;

    cout << "Celsius temperature = "
         << ct.ctemperature << "\n";

    cout << "Fahrenheit temperature = "
         << ft.ftemperature << "\n";
}
```

主程序文件：

```cpp
#include <iostream>
#include "ctft.h"

int main()
{
    using namespace std;

    ctemp ctv;
    ftemp ftv;

    cout << "Enter the Celsius temperature value: ";
    cin >> ctv.ctemperature;

    ftv = ctemp_to_ftemp(ctv);

    showftemp(ctv, ftv);

    return 0;
}
```

说明：

- `ctft.h` 提供结构体和函数原型；
- 函数实现文件负责温度转换和输出；
- 主程序文件负责输入并调用函数；
- 这体现了分离编译和模块化设计思想。

6. **存储持续性**

存储持续性指数据在内存中存在多久。

C++ 主要有以下几种存储持续性：

**自动存储持续性**

函数内部或代码块内部定义的普通变量通常具有自动存储持续性。

```cpp
void f()
{
    int x = 1;
}
```

特点：

- 进入函数或代码块时创建；
- 离开函数或代码块时销毁；
- 函数参数也属于自动存储持续性。

**静态存储持续性**

函数外部定义的变量，或使用 `static` 定义的变量，具有静态存储持续性。

```cpp
int globalValue = 10;

void f()
{
    static int count = 0;
}
```

特点：

- 程序运行期间一直存在；
- 生命周期从程序开始到程序结束。

**线程存储持续性**

C++11 引入 `thread_local`，用于多线程程序。

```cpp
thread_local int value;
```

特点：

- 变量在线程存在期间一直存在；
- 每个线程拥有自己的变量副本。

**动态存储持续性**

使用 `new` 分配的内存具有动态存储持续性。

```cpp
int * p = new int;
delete p;
```

特点：

- 由程序员在运行时申请；
- 使用 `delete` 释放；
- 如果不释放，可能造成内存泄漏；
- 这块区域也称为自由存储区或堆。

7. **作用域**

作用域描述一个名字在程序中哪里可见。

**局部作用域，也叫块作用域**

在函数或 `{}` 代码块中定义的变量，只能在该块中使用。

```cpp
void f1()
{
    int x = 1;
}

void f2()
{
    // x 在这里不可见
}
```

**全局作用域，也叫文件作用域**

在函数外部定义的变量，从定义位置开始到文件末尾都可见。

```cpp
int x = 1;

void f1()
{
    x = x + 1;
}

void f2()
{
    int y = x + 1;
}
```

**函数原型作用域**

函数原型中参数名只在括号内部有效，因此参数名可以省略。

```cpp
void func(int);
void func(int n);
```

这两个原型在接口意义上等价。

**类作用域**

类中声明的成员具有类作用域。

**命名空间作用域**

命名空间中声明的变量、函数、结构体、类等具有命名空间作用域。

8. **链接性**

链接性描述一个名字是否可以在不同文件之间共享。

常见链接性包括：

- 无链接性：自动变量通常没有链接性，只能在局部使用；
- 内部链接性：名字只能在当前文件中共享；
- 外部链接性：名字可以跨文件共享。

作用域关注“在哪里可见”，链接性关注“能不能跨文件共享”。

9. **命名空间**

命名空间用于组织名字，避免命名冲突。

C++ 中的名字可以指：

- 变量；
- 函数；
- 结构体；
- 枚举；
- 类；
- 类成员或结构体成员。

命名空间可以创建一个新的声明区域。

```cpp
namespace Wang
{
    int age;
    void score();

    struct exercise
    {
        int content;
        int count;
    };
}

namespace Li
{
    int birthday;

    struct score
    {
        int course;
    };

    char grade;
}
```

不同命名空间中可以有相同名字，它们互不冲突。

10. **作用域解析运算符 ::**

访问命名空间中的成员，可以使用 `::`。

```cpp
Wang::age = 18;
Li::score n1;
```

其中：

- `Wang::age` 表示 `Wang` 命名空间中的 `age`；
- `Li::score` 表示 `Li` 命名空间中的结构体类型 `score`。

如果要访问全局变量，也可以使用：

```cpp
::age
```

11. **using 声明**

`using` 声明只引入命名空间中的一个名字。

```cpp
using Wang::age;
```

之后可以直接写：

```cpp
cin >> age;
```

这里的 `age` 指的是 `Wang::age`。

示例：

```cpp
namespace Wang
{
    int age;
}

char age;

int main()
{
    using namespace std;
    using Wang::age;

    cin >> age;    // Wang::age
    cin >> ::age;  // global age

    return 0;
}
```

注意：如果局部区域已经通过 `using Wang::age` 引入了 `age`，就不能再声明另一个局部变量 `age`，否则会冲突。

12. **using 指令**

`using namespace` 会引入整个命名空间中的所有名字。

```cpp
using namespace Wang;
using namespace std;
```

区别：

```cpp
using Wang::age;       // 只引入 age
using namespace Wang;  // 引入 Wang 中所有名字
```

`using namespace std;` 很方便，但大型程序中可能造成命名冲突，所以更推荐在需要时使用 `std::cout`、`std::cin` 等限定名。

**三、PPT 中的代码整理**

**代码 1：头文件保护与结构体/函数原型**

```cpp
#ifndef COORDIN_H
#define COORDIN_H

struct polar
{
    double distance;
    double angle;
};

struct rect
{
    double x;
    double y;
};

polar rect_to_polar(rect xypos);
void show_polar(polar dapos);

#endif
```

说明：

- `#ifndef`、`#define`、`#endif` 防止头文件重复包含；
- `polar` 和 `rect` 是结构体类型；
- 头文件中放函数原型；
- 不在头文件中放普通函数定义。

**代码 2：摄氏温度转华氏温度头文件**

```cpp
#ifndef CTFT_H
#define CTFT_H

struct ctemp
{
    double ctemperature;
};

struct ftemp
{
    double ftemperature;
};

ftemp ctemp_to_ftemp(ctemp);
void showftemp(ctemp, ftemp);

#endif
```

说明：

- `ctemp` 表示摄氏温度；
- `ftemp` 表示华氏温度；
- `ctemp_to_ftemp()` 负责转换；
- `showftemp()` 负责显示。

**代码 3：主程序文件**

```cpp
#include <iostream>
#include "ctft.h"

int main()
{
    using namespace std;

    ctemp ctv;
    ftemp ftv;

    cout << "Enter the Celsius temperature value: ";
    cin >> ctv.ctemperature;

    ftv = ctemp_to_ftemp(ctv);

    showftemp(ctv, ftv);

    return 0;
}
```

说明：

- 使用 `#include "ctft.h"` 引入自定义头文件；
- 主程序只负责输入和函数调用；
- 不需要知道函数内部具体如何实现。

**代码 4：函数实现文件**

```cpp
#include <iostream>
#include "ctft.h"

ftemp ctemp_to_ftemp(ctemp ct)
{
    ftemp ft;

    ft.ftemperature = (ct.ctemperature * 9 / 5) + 32;

    return ft;
}

void showftemp(ctemp ct, ftemp ft)
{
    using namespace std;

    cout << "Celsius temperature = "
         << ct.ctemperature << "\n";

    cout << "Fahrenheit temperature = "
         << ft.ftemperature << "\n";
}
```

说明：

- 函数定义放在 `.cpp` 文件中；
- `ctemp_to_ftemp()` 返回结构体；
- `showftemp()` 输出两个结构体中的数据。

**代码 5：作用域示例**

```cpp
void f1()
{
    int x = 1;
}

void f2()
{
    int y;
    // y = x + 1; // 错误，x 只在 f1 中可见
}
```

说明：

- `x` 是局部变量；
- 它只在 `f1()` 内有效；
- `f2()` 不能访问它。

```cpp
int x = 1;

void f1()
{
    x = x + 1;
}

void f2()
{
    int y;
    y = x + 1;
}
```

说明：

- `x` 是全局变量；
- 在定义之后，本文件中的函数都可以访问它。

**代码 6：命名空间定义**

```cpp
namespace Wang
{
    int age;

    void score();

    struct exercise
    {
        int content;
        int count;
    };
}

namespace Li
{
    int birthday;

    struct score
    {
        int course;
    };

    char grade;
}
```

说明：

- `Wang` 和 `Li` 是两个命名空间；
- 它们各自形成独立的声明区域；
- 相同名字在不同命名空间中不会冲突。

**代码 7：using 声明引入单个名字**

```cpp
#include <iostream>

namespace Wang
{
    int age;

    void score(int &);

    struct exercise
    {
        int content;
        int count;
    };
}

char age;

int main()
{
    using namespace std;
    using Wang::age;

    cin >> age;
    cout << "age = " << age << "\n";

    cin >> ::age;
    cout << "global age = " << ::age << "\n";

    return 0;
}
```

说明：

- `using Wang::age;` 将 `Wang::age` 引入当前局部区域；
- `age` 表示 `Wang::age`；
- `::age` 表示全局变量 `age`；
- `::` 是作用域解析运算符。

**代码 8：using 声明放在全局区域**

```cpp
#include <iostream>

void display();

namespace Wang
{
    int age;

    void score(int &);

    struct exercise
    {
        int content;
        int count;
    };
}

using Wang::age;
using namespace std;

int main()
{
    cin >> age;
    display();

    return 0;
}

void display()
{
    cout << "age = " << age << "\n";
}
```

说明：

- `using Wang::age;` 放在函数外部，因此 `age` 被引入全局命名空间；
- `main()` 和 `display()` 都可以直接使用 `age`；
- 这里的 `age` 指的是 `Wang::age`。

**四、易混点**

- 头文件通常放声明，不放普通函数定义。
- 自定义头文件通常使用 `#include "file.h"`。
- 标准库头文件通常使用 `#include <iostream>`。
- `#ifndef` 头文件保护可以防止重复包含。
- 自动变量离开代码块就销毁。
- 静态变量在整个程序运行期间存在。
- `new` 分配的内存属于动态存储，必须用 `delete` 释放。
- 作用域决定名字在哪里可见。
- 链接性决定名字能不能跨文件共享。
- 局部变量没有链接性。
- 命名空间可以避免名字冲突。
- `Wang::age` 是限定名，`age` 是非限定名。
- `using Wang::age` 只引入一个名字。
- `using namespace Wang` 引入整个命名空间。

**五、可写进实验报告的中文总结**

本章主要学习了 C++ 的内存模型和命名空间。通过分离编译的学习，我了解了大型程序通常会被拆分为头文件、函数实现文件和主程序文件。头文件主要保存类型声明、函数原型和常量定义，源文件保存函数实现，这种方式有利于模块化设计和代码复用。

本章还介绍了存储持续性、作用域和链接性的概念。存储持续性决定变量在内存中存在多久，作用域决定变量名在程序中哪里可见，链接性决定名字是否可以在不同文件之间共享。通过这些概念，我对局部变量、全局变量、静态变量和动态内存有了更清晰的理解。

此外，本章学习了 C++ 命名空间机制。命名空间可以把变量、函数、结构体和类组织在不同的声明区域中，从而避免大型程序中的命名冲突。通过 `::`、`using` 声明和 `using namespace` 指令，我掌握了访问命名空间成员的基本方法。

---

**English Version**

**1. Core Concepts**

Chapter 8 mainly introduces memory models and namespaces in C++. As programs become larger, they are often divided into several source files. These files can be compiled separately and then linked into one executable program.

This chapter focuses on:

- separate compilation;
- header file organization;
- storage duration;
- scope;
- linkage;
- dynamic storage;
- namespaces.

These concepts help explain where names are visible and how long variables remain in memory.

**2. Key Points**

C++ allows a program to be divided into separate files. Each source file can be compiled separately, and then all object files can be linked together.

A useful organization usually includes three parts:

- a header file containing structure declarations, class declarations, function prototypes, constants, and templates;
- a source file containing function definitions;
- a source file containing the main program that calls the functions.

Header files commonly contain:

- function prototypes;
- symbolic constants defined with `#define` or `const`;
- structure declarations;
- class declarations;
- template declarations;
- inline functions.

Ordinary function definitions and variable definitions should usually not be placed in header files unless the function is inline.

There is a difference between angle brackets and quotation marks in `#include`.

```cpp
#include <iostream>
```

Angle brackets are usually used for standard library or system headers.

```cpp
#include "ctft.h"
```

Quotation marks are usually used for user-defined headers. The compiler first searches the current source file directory, then system paths.

Header guards prevent a header file from being included more than once.

```cpp
#ifndef CTFT_H
#define CTFT_H

// header contents

#endif
```

Storage duration describes how long data remains in memory.

Automatic storage duration applies to ordinary variables declared inside functions or blocks. They are created when execution enters the block and destroyed when execution leaves it.

Static storage duration applies to variables defined outside functions or declared with `static`. They persist during the whole program execution.

Thread storage duration was introduced in C++11 with `thread_local`. Such variables persist as long as the thread exists.

Dynamic storage duration applies to memory allocated with `new`. It remains until released with `delete` or until the program ends.

Scope describes where a name is visible.

A local variable has block scope and can only be used inside the block where it is declared.

A global variable has file scope and can be used from its declaration point to the end of the file.

Names in function prototypes have function prototype scope. Class members have class scope, and names declared in a namespace have namespace scope.

Linkage describes whether a name can be shared across translation units.

- Automatic variables have no linkage.
- Names with internal linkage can be shared within one file.
- Names with external linkage can be shared across files.

Namespaces help avoid name conflicts by creating separate declarative regions.

```cpp
namespace Wang
{
    int age;
    void score();

    struct exercise
    {
        int content;
        int count;
    };
}
```

To access a name in a namespace, use the scope-resolution operator `::`.

```cpp
Wang::age = 18;
```

A `using` declaration introduces one name.

```cpp
using Wang::age;
```

A `using` directive introduces all names in a namespace.

```cpp
using namespace Wang;
```

**3. Code from the PPT**

**Example 1: Header Guard and Function Prototypes**

```cpp
#ifndef COORDIN_H
#define COORDIN_H

struct polar
{
    double distance;
    double angle;
};

struct rect
{
    double x;
    double y;
};

polar rect_to_polar(rect xypos);
void show_polar(polar dapos);

#endif
```

This example shows a header guard, structure declarations, and function prototypes.

**Example 2: Temperature Conversion Header**

```cpp
#ifndef CTFT_H
#define CTFT_H

struct ctemp
{
    double ctemperature;
};

struct ftemp
{
    double ftemperature;
};

ftemp ctemp_to_ftemp(ctemp);
void showftemp(ctemp, ftemp);

#endif
```

This header defines two structures and two function prototypes.

**Example 3: Main Source File**

```cpp
#include <iostream>
#include "ctft.h"

int main()
{
    using namespace std;

    ctemp ctv;
    ftemp ftv;

    cout << "Enter the Celsius temperature value: ";
    cin >> ctv.ctemperature;

    ftv = ctemp_to_ftemp(ctv);

    showftemp(ctv, ftv);

    return 0;
}
```

The main file includes the header and calls the functions.

**Example 4: Function Implementation File**

```cpp
#include <iostream>
#include "ctft.h"

ftemp ctemp_to_ftemp(ctemp ct)
{
    ftemp ft;

    ft.ftemperature = (ct.ctemperature * 9 / 5) + 32;

    return ft;
}

void showftemp(ctemp ct, ftemp ft)
{
    using namespace std;

    cout << "Celsius temperature = "
         << ct.ctemperature << "\n";

    cout << "Fahrenheit temperature = "
         << ft.ftemperature << "\n";
}
```

This source file contains the actual function definitions.

**Example 5: Scope**

```cpp
void f1()
{
    int x = 1;
}

void f2()
{
    int y;
    // y = x + 1; // error
}
```

`x` is local to `f1()` and cannot be used in `f2()`.

```cpp
int x = 1;

void f1()
{
    x = x + 1;
}

void f2()
{
    int y;
    y = x + 1;
}
```

Here `x` is global and can be used by both functions.

**Example 6: Namespace Definition**

```cpp
namespace Wang
{
    int age;

    void score();

    struct exercise
    {
        int content;
        int count;
    };
}

namespace Li
{
    int birthday;

    struct score
    {
        int course;
    };

    char grade;
}
```

The two namespaces create separate declarative regions.

**Example 7: using Declaration**

```cpp
#include <iostream>

namespace Wang
{
    int age;

    void score(int &);

    struct exercise
    {
        int content;
        int count;
    };
}

char age;

int main()
{
    using namespace std;
    using Wang::age;

    cin >> age;
    cout << "age = " << age << "\n";

    cin >> ::age;
    cout << "global age = " << ::age << "\n";

    return 0;
}
```

`age` refers to `Wang::age`, while `::age` refers to the global variable.

**Example 8: using Declaration at Global Level**

```cpp
#include <iostream>

void display();

namespace Wang
{
    int age;

    void score(int &);

    struct exercise
    {
        int content;
        int count;
    };
}

using Wang::age;
using namespace std;

int main()
{
    cin >> age;
    display();

    return 0;
}

void display()
{
    cout << "age = " << age << "\n";
}
```

The `using` declaration is placed at global level, so `age` can be used by both `main()` and `display()`.

**4. Common Confusing Points**

- Header files usually contain declarations, not ordinary function definitions.
- User-defined headers usually use `#include "file.h"`.
- Standard headers usually use `#include <iostream>`.
- Header guards prevent repeated inclusion.
- Automatic variables are destroyed when leaving their block.
- Static variables exist during the whole program execution.
- Memory allocated with `new` must be released with `delete`.
- Scope controls where a name is visible.
- Linkage controls whether a name can be shared across files.
- Local variables have no linkage.
- Namespaces help avoid name conflicts.
- `Wang::age` is a qualified name.
- `using Wang::age` introduces one name.
- `using namespace Wang` introduces all names in the namespace.

**5. Report Summary**

In this chapter, I learned about memory models and namespaces in C++. Through separate compilation, I understood that large programs are usually divided into header files, implementation files, and main program files. Header files mainly contain type declarations, function prototypes, and constant definitions, while source files contain function implementations. This organization improves modularity and code reuse.

This chapter also introduced storage duration, scope, and linkage. Storage duration determines how long a variable exists in memory, scope determines where a name is visible, and linkage determines whether a name can be shared across different files. These concepts helped me better understand local variables, global variables, static variables, and dynamic memory.

In addition, I learned about namespaces in C++. Namespaces organize variables, functions, structures, and classes into separate declarative regions, helping avoid name conflicts in large programs. By using the scope-resolution operator `::`, using declarations, and using directives, I learned how to access names inside namespaces.