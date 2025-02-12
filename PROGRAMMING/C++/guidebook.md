# C++ GUIDEBOOK

## Table of Contents

- [Functions](#functions)
- [Memory Management](#memory-management)
- [Methods (Member Functions)](#methods-member-functions)
- [OOP Concepts](#oop-concepts)
- [Standard Template Library (STL)](#standards-template-library-stl)
- [Control Flow](#control-flow)
- [Input/Output](#inputoutput)
- [Error Handling](#error-handling)
- [Concurrency](#concurrency)
- [Templates](#templates)

## BASIC SYNTAX

- `<<` output & left shift operator for operations
- `'\n'` better option to end lines rather than `std::endl`
- `std::endl` end line, will flush output buffer
- `::` scope resolution operator

### Variables

### Const

Keyword that specifies a variable's value should remain constant (tells compiler to prevent anything from modifying it)

- essentally "read-only" for variables
- constants should be used as often as possible

### Namespaces

Namespaces allows 2 or more entities to share the same name, as long as these are in different namespaces.

```cpp
namespace first {
    int x = 1;
}

namespace second {
    int x = 2;
}

int main() {
    int x = 0;

    std::cout << first::x;
    std::cout << second::x;

    return 0;
}
```

when using `using namespace` in a specific entity, the specified namespace will be used by default.

### Typedef and type aliases

Keyword used to create an aditional name (alias) for another data type.

```cpp
// pairlist_t alias given to datatype below
typedef std::vector<std::pair<std::string, int>> pairlist_t; // naming convention _t
typedef int number_t;
typedef std::string text_t;
using letter_t = char; 

int main() {

    // type alias + variable declaration, assign value if needed
    pairlist_t pairlist; 
    number_t number = 20;
    text_t text = 'hello';
    letter_t letter = 't';
    return 0;
}
```

> typedef is now largely replaced by the `using` keyword, use `using` instead. More suitable for templates.

### Arithmetic operators

returns the result of specific arithmetic operations.

**equals & addition**

`students += 1; (students + 1)`
`students++; (increment by +1)`

**substraction**

`students = students -1;`
`students -=1;`
`students--; (decrement by -1)`

**multiply**

`students = students * 2;`
`students *= 2;`

**division**

`students = students / 2;`
`students /= 2;`

**modulus operator**

Get remainder of any division.

`students % 2`

> Order of precedence: 1. parenthesis, 2. multiplication & division, 3. addition & substraction

## HEADER"FILES"

- `<iostream>` - functions for basic input and output operations.
- `#pragma once` - causes the current header file to be included only once in a single compilation. (tricky and not very reliable)
- 

## FUNCTIONS

### Basic function

```cpp
// Syntax: return_type function_name(parameter_list) { function_body }
int add(int a, int b) {
return a + b;
}
```

### Inline function

Defined with the inline keyword for performance optimization.

```cpp
inline int multiply(int a, int b) {
    return a * b;
}
```

### Function overloading

Multiple functions with the same name but different parameters.

```cpp
int calculate(int a, int b) {
    return a + b;
}

double calculate(double a, double b) {
    return a * b;
}
```

### Lambda function

```cpp
auto lambda = [](int a, int b) { return a + b; };
std::cout << lambda(3, 5);
```

### Checklist

- [ ] Decide return type and parameters.
- [ ] Use const reference parameters (`const T&`) for non-primitive types to avoid copies.
- [ ] Inline for small functions to reduce overhead.

## Memory Management

Smart pointers and move semantics should be used where possible as alternatives to manual memory management. Keep manual memory management to tasks involving data structures

### CASE 1: Allocating single object

```cpp
int* ptr = new int(42); // Allocate memory for an integer and initialize it
delete ptr; // Deallocate memory
```

### CASE 2: Allocating arrays

```cpp
int* arr = new int[5]; // Allocate array of 5 integers
delete[] arr; // Deallocate array
```

### CASE 3: Smart pointers

```cpp
#include <memory>
std::unique_ptr<int> uptr = std::make_unique<int>(42); // Automatically deallocated
std::shared_ptr<int> sptr = std::make_shared<int>(42); // Shared ownership
```

### Move semantics

### Checklist - good practice

- [ ] Always pair`new` with`delete`.
- [ ] Prefer smart pointers for automatic memory management.
- [ ] Avoid raw pointers unless necessary.

## Methods (Member functions)

### Instance Method

```cpp
class MyClass {
public:
    void greet() {
        std::cout << "Hello, World!" << std::endl;
    }
};
```

### Static Method

Shared by all instances; no need for an object to call it.

```cpp
class MyClass {
public:
    static void greet() {
        std::cout << "Hello from a static method!" << std::endl;
    }
};
```

### Const Method

Guarantees that the method won't modify the object.

```cpp
class MyClass {
    int value;
public:
    int getValue() const {
        return value;
    }
};
```

### Checklist - Keep in mind

- [ ] Use `const` for methods that don't modify the object.
- [ ] Use `static` for utility functions that don't need object data.

## OOP - Concepts

### Classes

```cpp
class MyClass {
private:
    int value;

public:
    MyClass(int val) : value(val) {} // Constructor
    ~MyClass() {} // Destructor
};
```

### Inheritance

```cpp
class Base {
public:
    void show() {
        std::cout << "Base class" << std::endl;
    }
};

class Derived : public Base {
public:
    void show() {
        std::cout << "Derived class" << std::endl;
    }
};
```

### Polymorphism

```cpp
class Base {
public:
    virtual void display() {
        std::cout << "Base display" << std::endl;
    }
};

class Derived : public Base {
public:
    void display() override {
        std::cout << "Derived display" << std::endl;
    }
};
```

### Checklist - good practices

- [ ] Always define destructors as virtual for base classes in polymorphic hierarchies.
- [ ] Prefer composition over inheritance for better flexibility.

## Standards Template Library (stl)

### Vectors

```cpp
#include <vector>
std::vector<int> vec = {1, 2, 3};
vec.push_back(4);
vec.pop_back();
```

### Maps

```cpp
#include <map>
std::map<int, std::string> myMap = {{1, "One"}, {2, "Two"}};
myMap[3] = "Three";
```

### Iterators

```cpp
for (auto it = vec.begin(); it != vec.end(); ++it) {
    std::cout << *it << " ";
}
```

## Control Flow

### Conditionals

```cpp
if (x > 0) {
    std::cout << "Positive";
} else {
    std::cout << "Non-positive";
}
```

### Loops

```cpp
for (int i = 0; i < 10; ++i) {
    std::cout << i << " ";
}

while (x > 0) {
    x--;
}

do {
    x++;
} while (x < 10);
```

### Switch Case

```cpp
switch (x) {
    case 1: std::cout << "One"; break;
    case 2: std::cout << "Two"; break;
    default: std::cout << "Other"; break;
}
```

## Input/Output

### File handling

```cpp
#include <fstream>
std::ofstream outFile("output.txt");
outFile << "Hello, file!";
outFile.close();
```

### Console input/output

```cpp
std::cout << "Enter value: ";
std::cin >> value;
```

## Error handling

### Try-catch

```cpp
try {
    throw std::runtime_error("An error occurred");
} catch (const std::exception& e) {
    std::cerr << e.what() << std::endl;
}
```

## Concurrency

### Basic threading

```cpp
#include <thread>
void task() {
    std::cout << "Thread running" << std::endl;
}

std::thread t1(task);
t1.join();
```

## Templates

Allows to write reusable and generic code that can work with any data type.

- enable type-independent programming
- useful for functions or classes that perform the same operations regardless of the data type.

### Function templates

**Syntax:**

```cpp
template <typename T>
T add(T a, T b) {
    return a + b;
}
```

- `template <typename T>` <typename T>: Declares a template with a type parameter `T`.
- `T:` Represents a placeholder for a data type that will be specified when the function is called.

**Usage:**

```cpp
std::cout << add<int>(3, 5);       // Outputs: 8
std::cout << add<double>(2.5, 3.5); // Outputs: 6.0
```

- The compiler generates a separate version of the function for each data type used.
- Templates support multiple type parameters

### Class templates

Can define a blueprint for a class that can operate on any data type.

**Syntax:**

```cpp
template <typename T>
class MyClass {
    T value;
public:
    MyClass(T v) : value(v) {}
    void display() {
        std::cout << "Value: " << value << std::endl;
    }
};
```

**Usage:**

```cpp
MyClass<int> obj1(42);
obj1.display(); // Outputs: Value: 42

MyClass<std::string> obj2("Hello");
obj2.display(); // Outputs: Value: Hello
```

- multiple type parameters can be specified

### Template specialization

Used to define a custom implementation for a specific data type

Example: specialized class template

```cpp
template <typename T>
class MyClass {
public:
    void display() {
        std::cout << "Generic template" << std::endl;
    }
};

// Specialization for int
template <>
class MyClass<int> {
public:
    void display() {
        std::cout << "Specialized template for int" << std::endl;
    }
};
```

**Usage:**

```cpp
MyClass<double> obj1;
obj1.display(); // Outputs: Generic template

MyClass<int> obj2;
obj2.display(); // Outputs: Specialized template for int
```

- When using a template, the compiler generates a specific version of the template code for the specified data type(s).
- This process is known as **template instantiation** .

### Template constraints (C++20)

Use **concepts** to constrain template types, ensuring they meet certain requirements

```cpp
#include <concepts>

template <std::integral T> // Restricts T to integral types
T add(T a, T b) {
    return a + b;
}
```

###
