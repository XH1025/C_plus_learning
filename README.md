# C++笔记

1、C++ 中有四种类型转换：静态转换、动态转换、常量转换和重新解释转换。

### 动态转换（Dynamic Cast）

动态转换通常用于将一个基类指针或引用转换为派生类指针或引用。动态转换在运行时进行类型检查，如果不能进行转换则返回空指针或引发异常。

实例

```c++
class Base {};
class Derived : public Base {};
Base* ptr_base = new Derived;
Derived* ptr_derived = dynamic_cast<Derived*>(ptr_base); // 将基类指针转换为派生类指针
```



### 全局变量

在程序中，局部变量和全局变量的名称可以相同，但是在函数内，局部变量的值会覆盖全局变量的值。下面是一个实例：

## 实例

```c++
#include <iostream> 
using namespace std;  
// 全局变量声明 
int g = 20;  
int main () {  
    // 局部变量声明  
    int g = 10;  
    cout << g;  
    return 0; 
}
```

当上面的代码被编译和执行时，它会产生下列结果：

```
10
```

### 块作用域指的是在代码块内部声明的变量：

## 实例

```c++
#include <iostream>

int main() {
  int a = 10;
  {
    int a = 20; // 块作用域变量
    std::cout << "块变量: " << a << std::endl;
  }
  std::cout << "外部变量: " << a << std::endl;
  return 0;
}
```

以上实例中，内部的代码块中声明了一个名为 a 的变量，它与外部作用域中的变量 a 同名。内部作用域中的变量 a 将覆盖外部作用域中的变量 a，在内部作用域中访问 a 时输出的是20，而在外部作用域中访问 a 时输出的是 10。

当上面的代码被编译和执行时，它会产生下列结果：

```
块变量: 20
外部变量: 10
```
