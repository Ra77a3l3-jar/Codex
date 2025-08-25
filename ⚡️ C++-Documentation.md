# ⚡️ C++ Documentation
*Version: C++20/23 | Last Updated: December 2024*

C++ is a powerful, high-performance programming language that combines the efficiency of low-level programming with the convenience of high-level features. Originally developed by Bjarne Stroustrup as an extension of C, modern C++ has evolved into a sophisticated language supporting multiple programming paradigms including procedural, object-oriented, and generic programming.

## 📚 Table of Contents

1. [🚀 Introduction & Setup](#-introduction--setup)
   - [What is C++?](#what-is-c)
   - [Why Use C++?](#why-use-c)
   - [Installation and Setup](#installation-and-setup)
   - [Development Environment](#development-environment)
   - [Hello World Example](#hello-world-example)

2. [🔤 Basic Syntax & Structure](#-basic-syntax--structure)
   - [Program Structure](#program-structure)
   - [Comments](#comments)
   - [Namespaces](#namespaces)
   - [Headers and Includes](#headers-and-includes)

3. [📊 Data Types & Variables](#-data-types--variables)
   - [Fundamental Data Types](#fundamental-data-types)
   - [Variable Declaration](#variable-declaration)
   - [Type Inference (auto)](#type-inference-auto)
   - [Constants and Literals](#constants-and-literals)

4. [🎯 Control Structures](#-control-structures)
   - [Conditional Statements](#conditional-statements)
   - [Loops](#loops)
   - [Switch Statements](#switch-statements)
   - [Jump Statements](#jump-statements)

5. [🔧 Functions](#-functions)
   - [Function Declaration and Definition](#function-declaration-and-definition)
   - [Parameters and Arguments](#parameters-and-arguments)
   - [Function Overloading](#function-overloading)
   - [Lambda Functions](#lambda-functions)

6. [🏗️ Object-Oriented Programming](#️-object-oriented-programming)
   - [Classes and Objects](#classes-and-objects)
   - [Constructors and Destructors](#constructors-and-destructors)
   - [Inheritance](#inheritance)
   - [Polymorphism](#polymorphism)
   - [Encapsulation](#encapsulation)

7. [🧠 Memory Management](#-memory-management)
   - [Stack vs Heap](#stack-vs-heap)
   - [Pointers and References](#pointers-and-references)
   - [Smart Pointers](#smart-pointers)
   - [RAII Principle](#raii-principle)

8. [📦 Templates & Generic Programming](#-templates--generic-programming)
   - [Function Templates](#function-templates)
   - [Class Templates](#class-templates)
   - [Template Specialization](#template-specialization)
   - [Concepts (C++20)](#concepts-c20)

9. [🌊 STL - Standard Template Library](#-stl---standard-template-library)
   - [Containers](#containers)
   - [Iterators](#iterators)
   - [Algorithms](#algorithms)
   - [Function Objects](#function-objects)

10. [⚠️ Error Handling](#️-error-handling)
    - [Exceptions](#exceptions)
    - [Error Codes](#error-codes)
    - [RAII and Exception Safety](#raii-and-exception-safety)
    - [Modern Error Handling](#modern-error-handling)

11. [🔄 Modern C++ Features](#-modern-c-features)
    - [Move Semantics](#move-semantics)
    - [Range-based Loops](#range-based-loops)
    - [Structured Bindings](#structured-bindings)
    - [Modules (C++20)](#modules-c20)
    - [Coroutines (C++20)](#coroutines-c20)

12. [⚡ Concurrency & Parallelism](#-concurrency--parallelism)
    - [Threads](#threads)
    - [Synchronization](#synchronization)
    - [Atomic Operations](#atomic-operations)
    - [Parallel Algorithms](#parallel-algorithms)

13. [🚀 Real-World Applications](#-real-world-applications)
    - [Project 1: File Manager](#project-1-file-manager)
    - [Project 2: HTTP Client](#project-2-http-client)
    - [Project 3: Game Engine Basics](#project-3-game-engine-basics)
    - [Industry Use Cases](#industry-use-cases)

14. [📖 Appendices](#-appendices)
    - [Glossary](#glossary)
    - [Quick Reference Card](#quick-reference-card)
    - [Further Reading](#further-reading)
    - [Community Resources](#community-resources)
    - [Contributing Guidelines](#contributing-guidelines)

---

## 🚀 Introduction & Setup

**📊 Chapter 1 of 14**

🎯 **Learning Objectives:**
- Understand what C++ is and its applications
- Set up a development environment
- Write and compile your first C++ program
- Understand the basic structure of C++ programs

⏱️ **Estimated Reading Time:** 15 minutes

### What is C++?

C++ is a general-purpose programming language created by Bjarne Stroustrup at Bell Labs starting in 1979. It was designed as an extension of the C programming language, which is why it was originally called "C with Classes." The "++" operator in C increments a variable, symbolizing the evolution from C.

Key characteristics of C++:

- **System Programming**: Direct hardware control and memory management
- **Object-Oriented**: Supports classes, inheritance, polymorphism, and encapsulation
- **Generic Programming**: Templates allow code reuse across different data types
- **High Performance**: Compiled language with minimal runtime overhead
- **Multi-Paradigm**: Supports procedural, object-oriented, and generic programming styles

### Why Use C++?

C++ is chosen for applications where performance, control, and flexibility are paramount:

**Performance**: C++ compiles to highly optimized machine code, making it ideal for performance-critical applications like games, real-time systems, and high-frequency trading platforms.

**Control**: Direct memory management and hardware access capabilities make C++ perfect for system programming, embedded systems, and device drivers.

**Versatility**: From web browsers (Chrome, Firefox) to operating systems (Windows, macOS components) to games (Unreal Engine), C++ powers diverse applications.

**Industry Standard**: Major companies like Google, Microsoft, Facebook, and Amazon rely heavily on C++ for their core systems.

### Installation and Setup

#### Windows

**Option 1: Visual Studio Community (Recommended)**

1. Download Visual Studio Community from Microsoft's website
2. During installation, select "Desktop development with C++"
3. Ensure C++20/23 support is included

**Option 2: MinGW-w64**

1. Download MinGW-w64 from the official website
2. Add the bin directory to your system PATH
3. Verify installation: `g++ --version`

#### macOS

**Using Xcode Command Line Tools:**

```bash
xcode-select --install
```

**Using Homebrew:**

```bash
brew install gcc
```

#### Linux (Ubuntu/Debian)

```bash
sudo apt update
sudo apt install build-essential
sudo apt install g++-11  # For C++20/23 features
```

### Development Environment

**Popular IDEs and Editors:**

1. **Visual Studio** (Windows) - Excellent debugging and IntelliSense
2. **CLion** (Cross-platform) - JetBrains' powerful C++ IDE
3. **Visual Studio Code** - Lightweight with C++ extensions
4. **Qt Creator** - Great for Qt development
5. **Code::Blocks** - Free, cross-platform IDE

**Essential Compiler Flags:**

```bash
g++ -std=c++20 -Wall -Wextra -O2 program.cpp -o program
```

- `-std=c++20`: Use C++20 standard
- `-Wall -Wextra`: Enable comprehensive warnings
- `-O2`: Optimization level 2

### Hello World Example

Let's write your first C++ program:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

**Compilation and Execution:**

```bash
g++ -std=c++20 hello.cpp -o hello
./hello
```

**Output:**
```
Hello, World!
```

**Explanation:**
- `#include <iostream>`: Includes input/output stream library
- `int main()`: Entry point of every C++ program
- `std::cout`: Standard output stream
- `<<`: Stream insertion operator
- `std::endl`: Inserts newline and flushes the buffer
- `return 0`: Indicates successful program termination

### 💡 Code Examples

**Example 1: Basic Input/Output**

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name;
    int age;

    std::cout << "Enter your name: ";
    std::getline(std::cin, name);

    std::cout << "Enter your age: ";
    std::cin >> age;

    std::cout << "Hello, " << name << "! You are " << age << " years old." << std::endl;

    return 0;
}
```

**Example 2: Multiple Files**

*main.cpp:*
```cpp
#include <iostream>
#include "greeting.h"

int main() {
    greet("C++ Developer");
    return 0;
}
```

*greeting.h:*
```cpp
#ifndef GREETING_H
#define GREETING_H

void greet(const std::string& name);

#endif
```

*greeting.cpp:*
```cpp
#include <iostream>
#include "greeting.h"

void greet(const std::string& name) {
    std::cout << "Welcome to C++, " << name << "!" << std::endl;
}
```

**Compilation:**
```bash
g++ -std=c++20 main.cpp greeting.cpp -o program
```

### ⚠️ Common Pitfalls

1. **Forgetting Headers**: Always include necessary headers (`<iostream>`, `<string>`, etc.)
2. **Missing Semicolons**: Every statement must end with a semicolon
3. **Case Sensitivity**: C++ is case-sensitive; `Main` ≠ `main`
4. **Uninitialized Variables**: Always initialize variables before use

### ✅ Best Practices

1. **Use Modern C++**: Prefer C++20/23 features over legacy approaches
2. **Consistent Naming**: Use consistent naming conventions (camelCase, snake_case)
3. **Include Guards**: Always use header guards or `#pragma once`
4. **Compiler Warnings**: Enable and fix all compiler warnings
5. **Code Organization**: Separate declarations (.h) from definitions (.cpp)

### 🏋️ Exercises

#### 🏋️ Exercise 1: Personal Information Program
**Difficulty:** 🟢 Beginner
**Estimated Time:** 10 minutes

Create a program that asks for the user's name, age, and favorite programming language, then displays a personalized message.

<details>
<summary>💡 Click to see hints</summary>

- Use `std::getline()` for strings with spaces
- Use `std::cin` for simple inputs
- Remember to handle the newline after numeric input

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <string>

int main() {
    std::string name, language;
    int age;

    std::cout << "What's your name? ";
    std::getline(std::cin, name);

    std::cout << "How old are you? ";
    std::cin >> age;
    std::cin.ignore(); // Clear the newline from buffer

    std::cout << "What's your favorite programming language? ";
    std::getline(std::cin, language);

    std::cout << "\nHi " << name << "!" << std::endl;
    std::cout << "At " << age << " years old, it's great that you're learning "
              << language << "!" << std::endl;

    return 0;
}
```

**Explanation:**
- `std::getline()` reads entire lines including spaces
- `std::cin.ignore()` clears the newline character left by `std::cin >> age`
- String concatenation using the `<<` operator
- `\n` and `std::endl` both create new lines (endl also flushes the buffer)

</details>

[Back to top](#-c-documentation)

---

## 🔤 Basic Syntax & Structure

**📊 Chapter 2 of 14**

🎯 **Learning Objectives:**
- Master C++ program structure and organization
- Understand commenting conventions
- Learn namespace usage and management
- Grasp header file concepts and include directives

⏱️ **Estimated Reading Time:** 20 minutes

### Program Structure

Every C++ program follows a specific structure that the compiler expects:

```cpp
// 1. Preprocessor directives
#include <iostream>
#include <string>

// 2. Namespace declarations
using namespace std;

// 3. Global declarations
const int MAX_SIZE = 100;

// 4. Function prototypes
void displayMessage();
int calculate(int a, int b);

// 5. Main function
int main() {
    // Program execution starts here
    displayMessage();
    int result = calculate(10, 20);
    cout << "Result: " << result << endl;
    return 0;
}

// 6. Function definitions
void displayMessage() {
    cout << "Welcome to C++!" << endl;
}

int calculate(int a, int b) {
    return a + b;
}
```

**Key Components:**

1. **Preprocessor Directives**: Instructions processed before compilation
2. **Declarations**: Function prototypes, global variables, constants
3. **Main Function**: Program entry point (required)
4. **Function Definitions**: Implementation of declared functions

### Comments

Comments are crucial for code documentation and maintenance:

**Single-line Comments:**
```cpp
// This is a single-line comment
int age = 25; // Comment at end of line
```

**Multi-line Comments:**
```cpp
/*
 * This is a multi-line comment
 * Useful for longer explanations
 * or temporarily disabling code
 */
```

**Documentation Comments:**
```cpp
/**
 * @brief Calculates the factorial of a number
 * @param n The number to calculate factorial for
 * @return The factorial of n
 */
int factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}
```

### Namespaces

Namespaces prevent naming conflicts and organize code:

**Standard Namespace:**
```cpp
#include <iostream>

int main() {
    // Explicit namespace usage
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

**Using Declarations:**
```cpp
#include <iostream>
using std::cout;
using std::endl;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

**Using Directive (Use with caution):**
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "Hello, World!" << endl;
    return 0;
}
```

**Custom Namespaces:**
```cpp
namespace MathUtils {
    const double PI = 3.14159;

    double circleArea(double radius) {
        return PI * radius * radius;
    }
}

namespace StringUtils {
    bool isEmpty(const std::string& str) {
        return str.empty();
    }
}

int main() {
    double area = MathUtils::circleArea(5.0);
    bool empty = StringUtils::isEmpty("");
    return 0;
}
```

**Nested Namespaces (C++17):**
```cpp
// Old way
namespace Company {
    namespace Project {
        namespace Module {
            void function() { }
        }
    }
}

// New way (C++17)
namespace Company::Project::Module {
    void function() { }
}
```

### Headers and Includes

**System Headers:**
```cpp
#include <iostream>  // Input/output streams
#include <string>    // String class
#include <vector>    // Dynamic arrays
#include <algorithm> // Standard algorithms
#include <memory>    // Smart pointers
```

**User-defined Headers:**
```cpp
#include "myheader.h"    // Local header file
#include "utils/math.h"  // Header in subdirectory
```

**Header File Best Practices:**

*math_utils.h:*
```cpp
#ifndef MATH_UTILS_H  // Include guard
#define MATH_UTILS_H

#include <cmath>

namespace MathUtils {
    // Function declarations
    double power(double base, double exponent);
    double squareRoot(double number);

    // Inline functions (defined in header)
    inline double square(double x) {
        return x * x;
    }

    // Template functions (must be in header)
    template<typename T>
    T maximum(T a, T b) {
        return (a > b) ? a : b;
    }
}

#endif // MATH_UTILS_H
```

*math_utils.cpp:*
```cpp
#include "math_utils.h"

namespace MathUtils {
    double power(double base, double exponent) {
        return std::pow(base, exponent);
    }

    double squareRoot(double number) {
        if (number < 0) {
            throw std::invalid_argument("Cannot calculate square root of negative number");
        }
        return std::sqrt(number);
    }
}
```

**Modern Alternative - Pragma Once:**
```cpp
#pragma once  // Simpler than include guards

#include <string>

class Student {
    // Class definition
};
```

### 💡 Code Examples

**Example 1: Organized Program Structure**

```cpp
#include <iostream>
#include <string>
#include <vector>

// Constants
const int MAX_STUDENTS = 100;

// Function prototypes
void displayMenu();
int getUserChoice();
void processChoice(int choice);

int main() {
    displayMenu();
    int choice = getUserChoice();
    processChoice(choice);
    return 0;
}

void displayMenu() {
    std::cout << "=== Student Management System ===" << std::endl;
    std::cout << "1. Add Student" << std::endl;
    std::cout << "2. View Students" << std::endl;
    std::cout << "3. Exit" << std::endl;
}

int getUserChoice() {
    int choice;
    std::cout << "Enter your choice: ";
    std::cin >> choice;
    return choice;
}

void processChoice(int choice) {
    switch(choice) {
        case 1:
            std::cout << "Adding student..." << std::endl;
            break;
        case 2:
            std::cout << "Displaying students..." << std::endl;
            break;
        case 3:
            std::cout << "Goodbye!" << std::endl;
            break;
        default:
            std::cout << "Invalid choice!" << std::endl;
    }
}
```

**Example 2: Namespace Organization**

```cpp
#include <iostream>
#include <string>

namespace Graphics {
    struct Point {
        double x, y;
    };

    void drawLine(const Point& start, const Point& end) {
        std::cout << "Drawing line from (" << start.x << "," << start.y
                  << ") to (" << end.x << "," << end.y << ")" << std::endl;
    }
}

namespace Audio {
    void playSound(const std::string& filename) {
        std::cout << "Playing sound: " << filename << std::endl;
    }

    void stopSound() {
        std::cout << "Stopping sound" << std::endl;
    }
}

int main() {
    Graphics::Point start{0, 0};
    Graphics::Point end{10, 10};
    Graphics::drawLine(start, end);

    Audio::playSound("background.mp3");
    Audio::stopSound();

    return 0;
}
```

### ⚠️ Common Pitfalls

1. **Using namespace std in Headers**: Never use `using namespace std;` in header files
2. **Missing Include Guards**: Can cause multiple definition errors
3. **Circular Dependencies**: Header A includes B, B includes A
4. **Including Implementation Files**: Never include .cpp files
5. **Forgetting Function Prototypes**: Functions must be declared before use

### ✅ Best Practices

1. **Minimize using Directives**: Prefer explicit namespace qualification
2. **Organize Headers**: Group related functionality in logical headers
3. **Use Include Guards**: Protect against multiple inclusions
4. **Forward Declarations**: Use when possible to reduce compilation time
5. **Consistent File Organization**: Maintain consistent project structure

### 🏋️ Exercises

#### 🏋️ Exercise 1: Calculator with Namespaces
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 20 minutes

Create a calculator program using separate namespaces for basic operations (add, subtract, multiply, divide) and advanced operations (power, square root). Organize the code into multiple files.

<details>
<summary>💡 Click to see hints</summary>

- Create separate header files for basic and advanced operations
- Use proper include guards
- Keep function implementations in .cpp files
- Use namespace qualification in main()

</details>

<details>
<summary>✅ Click to see solution</summary>

*basic_operations.h:*
```cpp
#pragma once

namespace BasicOps {
    double add(double a, double b);
    double subtract(double a, double b);
    double multiply(double a, double b);
    double divide(double a, double b);
}
```

*basic_operations.cpp:*
```cpp
#include "basic_operations.h"
#include <stdexcept>

namespace BasicOps {
    double add(double a, double b) {
        return a + b;
    }

    double subtract(double a, double b) {
        return a - b;
    }

    double multiply(double a, double b) {
        return a * b;
    }

    double divide(double a, double b) {
        if (b == 0) {
            throw std::runtime_error("Division by zero!");
        }
        return a / b;
    }
}
```

*advanced_operations.h:*
```cpp
#pragma once

namespace AdvancedOps {
    double power(double base, double exponent);
    double squareRoot(double number);
    double factorial(int n);
}
```

*advanced_operations.cpp:*
```cpp
#include "advanced_operations.h"
#include <cmath>
#include <stdexcept>

namespace AdvancedOps {
    double power(double base, double exponent) {
        return std::pow(base, exponent);
    }

    double squareRoot(double number) {
        if (number < 0) {
            throw std::runtime_error("Cannot calculate square root of negative number!");
        }
        return std::sqrt(number);
    }

    double factorial(int n) {
        if (n < 0) {
            throw std::runtime_error("Factorial of negative number is undefined!");
        }
        if (n <= 1) return 1;
        return n * factorial(n - 1);
    }
}
```

*main.cpp:*
```cpp
#include <iostream>
#include "basic_operations.h"
#include "advanced_operations.h"

int main() {
    try {
        // Basic operations
        std::cout << "Basic Operations:" << std::endl;
        std::cout << "10 + 5 = " << BasicOps::add(10, 5) << std::endl;
        std::cout << "10 - 5 = " << BasicOps::subtract(10, 5) << std::endl;
        std::cout << "10 * 5 = " << BasicOps::multiply(10, 5) << std::endl;
        std::cout << "10 / 5 = " << BasicOps::divide(10, 5) << std::endl;

        // Advanced operations
        std::cout << "\nAdvanced Operations:" << std::endl;
        std::cout << "2^8 = " << AdvancedOps::power(2, 8) << std::endl;
        std::cout << "√25 = " << AdvancedOps::squareRoot(25) << std::endl;
        std::cout << "5! = " << AdvancedOps::factorial(5) << std::endl;

    } catch (const std::exception& e) {
        std::cerr << "Error: " << e.what() << std::endl;
    }

    return 0;
}
```

**Explanation:**
- Separated functionality into logical namespaces
- Used pragma once for simpler header protection
- Implemented proper error handling with exceptions
- Maintained clean separation between interface (.h) and implementation (.cpp)
- Used const references and appropriate parameter types

</details>

[Back to top](#-c-documentation)

---

## 📊 Data Types & Variables

**📊 Chapter 3 of 14**

🎯 **Learning Objectives:**
- Master fundamental C++ data types and their characteristics
- Understand variable declaration, initialization, and scope
- Learn modern C++ type inference with auto
- Explore constants, literals, and type safety

⏱️ **Estimated Reading Time:** 25 minutes

📋 **Prerequisites:** Basic understanding of computer memory and number systems

### Fundamental Data Types

C++ provides several built-in data types, each optimized for different use cases:

#### Integer Types

```cpp
#include <iostream>
#include <climits>

int main() {
    // Basic integer types
    short s = 32767;           // At least 16 bits
    int i = 2147483647;        // At least 16 bits (usually 32)
    long l = 2147483647L;      // At least 32 bits
    long long ll = 9223372036854775807LL; // At least 64 bits

    // Unsigned variants
    unsigned short us = 65535;
    unsigned int ui = 4294967295U;
    unsigned long ul = 4294967295UL;
    unsigned long long ull = 18446744073709551615ULL;

    // Display sizes
    std::cout << "Size of int: " << sizeof(int) << " bytes" << std::endl;
    std::cout << "Range of int: " << INT_MIN << " to " << INT_MAX << std::endl;

    return 0;
}
```

#### Fixed-width Integer Types (C++11)

```cpp
#include <cstdint>
#include <iostream>

int main() {
    // Exact width types
    std::int8_t  i8 = -128;        // Exactly 8 bits
    std::int16_t i16 = -32768;     // Exactly 16 bits
    std::int32_t i32 = -2147483648; // Exactly 32 bits
    std::int64_t i64 = -9223372036854775808LL; // Exactly 64 bits

    // Unsigned variants
    std::uint8_t  u8 = 255;
    std::uint16_t u16 = 65535;
    std::uint32_t u32 = 4294967295U;
    std::uint64_t u64 = 18446744073709551615ULL;

    // Fast types (at least N bits, optimized for speed)
    std::int_fast32_t fast32 = 100;
    std::uint_fast16_t ufast16 = 200;

    std::cout << "int8_t: " << static_cast<int>(i8) << std::endl;
    std::cout << "uint64_t: " << u64 << std::endl;

    return 0;
}
```

#### Floating-Point Types

```cpp
#include <iostream>
#include <iomanip>
#include <cfloat>

int main() {
    float f = 3.14159f;        // Single precision (usually 32 bits)
    double d = 3.14159265359;  // Double precision (usually 64 bits)
    long double ld = 3.14159265358979323846L; // Extended precision

    // Scientific notation
    double scientific = 1.23e-4; // 0.000123
    double large = 6.022e23;     // Avogadro's number

    // Special values
    double positive_inf = 1.0 / 0.0;
    double negative_inf = -1.0 / 0.0;
    double nan_value = 0.0 / 0.0;

    std::cout << std::fixed << std::setprecision(10);
    std::cout << "Float: " << f << std::endl;
    std::cout << "Double: " << d << std::endl;
    std::cout << "Long double: " << ld << std::endl;

    std::cout << "Float precision: " << FLT_DIG << " digits" << std::endl;
    std::cout << "Double precision: " << DBL_DIG << " digits" << std::endl;

    return 0;
}
```

#### Character Types

```cpp
#include <iostream>

int main() {
    char c = 'A';              // Single character
    char16_t c16 = u'π';       // UTF-16 character
    char32_t c32 = U'🌟';      // UTF-32 character
    wchar_t wc = L'Ω';         // Wide character

    // Character codes
    std::cout << "Character 'A': " << c << std::endl;
    std::cout << "ASCII value: " << static_cast<int>(c) << std::endl;

    // Escape sequences
    char newline = '\n';
    char tab = '\t';
    char backslash = '\\';
    char quote = '\"';

    std::cout << "Escape sequences:\n";
    std::cout << "Newline: [" << newline << "]" << std::endl;
    std::cout << "Tab: [" << tab << "]" << std::endl;
    std::cout << "Quote: " << quote << std::endl;

    return 0;
}
```

#### Boolean Type

```cpp
#include <iostream>

int main() {
    bool isTrue = true;
    bool isFalse = false;

    // Boolean from expressions
    bool comparison = (10 > 5);
    bool logical = (true && false);

    // Boolean output
    std::cout << std::boolalpha; // Print true/false instead of 1/0
    std::cout << "isTrue: " << isTrue << std::endl;
    std::cout << "isFalse: " << isFalse << std::endl;
    std::cout << "10 > 5: " << comparison << std::endl;
    std::cout << "true && false: " << logical << std::endl;

    return 0;
}
```

### Variable Declaration

#### Basic Declaration and Initialization

```cpp
#include <iostream>

int main() {
    // Declaration without initialization (dangerous!)
    int uninitialized; // Contains garbage value

    // Declaration with initialization
    int initialized = 42;

    // Copy initialization
    int copy_init = 10;

    // Direct initialization
    int direct_init(20);

    // List initialization (C++11) - preferred
    int list_init{30};
    int list_init2{}; // Zero-initialized

    // Multiple declarations
    int a = 1, b = 2, c = 3;

    std::cout << "Initialized: " << initialized << std::endl;
    std::cout << "Direct init: " << direct_init << std::endl;
    std::cout << "List init: " << list_init << std::endl;
    std::cout << "Zero init: " << list_init2 << std::endl;

    return 0;
}
```

#### Variable Scope and Lifetime

```cpp
#include <iostream>

// Global scope
int global_var = 100;

void function() {
    // Function scope
    int local_var = 50;

    {
        // Block scope
        int block_var = 25;
        std::cout << "Block scope: " << block_var << std::endl;
    } // block_var destroyed here

    // std::cout << block_var; // Error: block_var not accessible
    std::cout << "Function scope: " << local_var << std::endl;
}

int main() {
    std::cout << "Global scope: " << global_var << std::endl;
    function();

    // Static variables
    for (int i = 0; i < 3; ++i) {
        static int counter = 0; // Initialized only once
        counter++;
        std::cout << "Counter: " << counter << std::endl;
    }

    return 0;
}
```

### Type Inference (auto)

C++11 introduced the `auto` keyword for automatic type deduction:

```cpp
#include <iostream>
#include <vector>
#include <map>
#include <string>

int main() {
    // Basic auto usage
    auto number = 42;           // int
    auto pi = 3.14159;          // double
    auto character = 'A';       // char
    auto text = "Hello";        // const char*
    auto cpp_string = std::string("C++"); // std::string

    // Auto with complex types
    auto vec = std::vector<int>{1, 2, 3, 4, 5};
    auto map = std::map<std::string, int>{{"one", 1}, {"two", 2}};

    // Auto with iterators
    for (auto it = vec.begin(); it != vec.end(); ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;

    // Auto with references
    int value = 10;
    auto& ref = value;          // int&
    const auto& const_ref = value; // const int&

    // Auto with pointers
    auto* ptr = &value;         // int*

    // decltype for exact type deduction
    int x = 5;
    decltype(x) y = x;          // y is exactly the same type as x

    return 0;
}
```

#### Auto Best Practices

```cpp
#include <iostream>
#include <vector>
#include <memory>

class Widget {
public:
    void display() const { std::cout << "Widget displayed" << std::endl; }
};

int main() {
    // Good uses of auto
    auto vec = std::vector<int>{1, 2, 3};
    auto ptr = std::make_unique<Widget>();

    // Range-based for loops
    for (const auto& element : vec) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    // Lambda expressions
    auto lambda = [](int x, int y) { return x + y; };
    auto result = lambda(5, 3);

    // Avoid when type is not obvious
    auto mystery = getSomeValue(); // What type is this?

    // Better to be explicit in such cases
    std::string name = getUserName();
    double price = calculatePrice();

    return 0;
}
```

### Constants and Literals

#### Constants

```cpp
#include <iostream>

int main() {
    // const keyword
    const int MAX_SIZE = 100;
    const double PI = 3.14159;

    // const with pointers
    int value = 10;
    const int* ptr_to_const = &value;    // Pointer to const int
    int* const const_ptr = &value;       // Const pointer to int
    const int* const const_ptr_to_const = &value; // Const pointer to const int

    // constexpr for compile-time constants (C++11)
    constexpr int COMPILE_TIME_CONST = 50;
    constexpr double EULER = 2.71828;

    // constexpr functions
    constexpr int square(int x) {
        return x * x;
    }

    constexpr int result = square(5); // Computed at compile time

    std::cout << "MAX_SIZE: " << MAX_SIZE << std::endl;
    std::cout << "Square of 5: " << result << std::endl;

    return 0;
}
```

#### Literals

```cpp
#include <iostream>
#include <string>

int main() {
    // Integer literals
    int decimal = 42;
    int octal = 052;        // Octal (starts with 0)
    int hex = 0x2A;         // Hexadecimal (starts with 0x)
    int binary = 0b101010;  // Binary (C++14, starts with 0b)

    // Digit separators (C++14)
    long long big_number = 1'000'000'000;
    int binary_sep = 0b1010'1010;

    // Floating-point literals
    double d1 = 3.14;
    double d2 = 3.14e2;     // Scientific notation
    float f = 3.14f;        // Float suffix
    long double ld = 3.14L; // Long double suffix

    // Character literals
    char c = 'A';
    wchar_t wc = L'Ω';
    char16_t c16 = u'π';
    char32_t c32 = U'🌟';

    // String literals
    const char* cstr = "C-style string";
    std::string str = "C++ string";
    std::wstring wstr = L"Wide string";
    std::u16string u16str = u"UTF-16 string";
    std::u32string u32str = U"UTF-32 string";

    // Raw string literals (C++11)
    std::string raw = R"(This is a raw string
    with newlines and "quotes"
    and backslashes \\ preserved)";

    // User-defined literals (C++11)
    using namespace std::string_literals;
    auto cpp_string = "Hello"s;  // std::string, not const char*

    std::cout << "Decimal: " << decimal << std::endl;
    std::cout << "Hex: " << hex << std::endl;
    std::cout << "Binary: " << binary << std::endl;
    std::cout << "Big number: " << big_number << std::endl;

    return 0;
}
```

### 💡 Code Examples

**Example 1: Type System Demonstration**

```cpp
#include <iostream>
#include <typeinfo>
#include <string>

template<typename T>
void printTypeInfo(const T& value) {
    std::cout << "Value: " << value
              << ", Type: " << typeid(T).name()
              << ", Size: " << sizeof(T) << " bytes" << std::endl;
}

int main() {
    // Different numeric types
    auto small_int = 42;
    auto large_int = 42L;
    auto unsigned_int = 42U;
    auto float_val = 42.0f;
    auto double_val = 42.0;

    printTypeInfo(small_int);
    printTypeInfo(large_int);
    printTypeInfo(unsigned_int);
    printTypeInfo(float_val);
    printTypeInfo(double_val);

    // Character types
    auto character = 'A';
    auto string_literal = "Hello";
    auto cpp_string = std::string("World");

    printTypeInfo(character);
    printTypeInfo(string_literal);
    printTypeInfo(cpp_string);

    return 0;
}
```

**Example 2: Modern Variable Initialization**

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <initializer_list>

class Person {
private:
    std::string name;
    int age;

public:
    // Constructor with initializer list
    Person(const std::string& n, int a) : name(n), age(a) {}

    // Constructor for brace initialization
    Person(std::initializer_list<std::string> names) {
        if (names.size() > 0) {
            name = *names.begin();
        }
        age = 0;
    }

    void display() const {
        std::cout << "Name: " << name << ", Age: " << age << std::endl;
    }
};

int main() {
    // Various initialization methods

    // Fundamental types
    int a{42};              // Uniform initialization
    int b = {42};           // Copy-list initialization
    int c(42);              // Direct initialization
    int d = 42;             // Copy initialization

    // Container initialization
    std::vector<int> vec1{1, 2, 3, 4, 5};
    std::vector<int> vec2(5, 10); // 5 elements, all value 10

    // Object initialization
    Person person1{"Alice", 30};
    Person person2{"Bob", 25};
    Person person3{"Charlie"}; // Uses initializer_list constructor

    // Auto with initialization
    auto list = {1, 2, 3, 4, 5}; // std::initializer_list<int>
    auto vector = std::vector{1, 2, 3, 4, 5}; // std::vector<int>

    std::cout << "Variables initialized successfully:" << std::endl;
    std::cout << "a = " << a << ", b = " << b << ", c = " << c << ", d = " << d << std::endl;

    std::cout << "Vector contents: ";
    for (const auto& element : vec1) {
        std::cout << element << " ";
    }
    std::cout << std::endl;

    person1.display();
    person2.display();
    person3.display();

    return 0;
}
```

### ⚠️ Common Pitfalls

1. **Uninitialized Variables**: Always initialize variables before use
2. **Integer Overflow**: Be aware of type limits and potential overflow
3. **Floating-Point Precision**: Avoid direct equality comparisons with floats
4. **Implicit Conversions**: Be careful with automatic type conversions
5. **Auto Abuse**: Don't use auto when type clarity is important

### ✅ Best Practices

1. **Always Initialize**: Use list initialization `{}` when possible
2. **Choose Appropriate Types**: Use fixed-width types for guaranteed sizes
3. **Use const**: Make variables const when they shouldn't change
4. **Prefer constexpr**: Use constexpr for compile-time constants
5. **Be Explicit**: Don't rely too heavily on auto when type matters

### 🏋️ Exercises

#### 🏋️ Exercise 1: Data Type Explorer
**Difficulty:** 🟢 Beginner
**Estimated Time:** 15 minutes

Create a program that demonstrates the size and range of different data types, including integer types, floating-point types, and character types.

<details>
<summary>💡 Click to see hints</summary>

- Use `sizeof()` operator to get type sizes
- Include `<climits>` and `<cfloat>` for type limits
- Use `std::numeric_limits` for more comprehensive type information
- Format output nicely with `std::setw()` from `<iomanip>`

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <iomanip>
#include <climits>
#include <cfloat>
#include <limits>
#include <cstdint>

template<typename T>
void printTypeInfo(const std::string& typeName) {
    std::cout << std::left << std::setw(20) << typeName;
    std::cout << std::right << std::setw(10) << sizeof(T) << " bytes";

    if constexpr (std::numeric_limits<T>::is_integer) {
        std::cout << std::setw(25) << std::numeric_limits<T>::min();
        std::cout << std::setw(25) << std::numeric_limits<T>::max();
    } else if constexpr (std::is_floating_point_v<T>) {
        std::cout << std::setw(15) << std::numeric_limits<T>::digits10 << " digits";
        std::cout << std::setw(15) << std::numeric_limits<T>::min();
        std::cout << std::setw(15) << std::numeric_limits<T>::max();
    }
    std::cout << std::endl;
}

int main() {
    std::cout << "=== C++ Data Types Information ===" << std::endl << std::endl;

    // Header
    std::cout << std::left << std::setw(20) << "Type";
    std::cout << std::right << std::setw(10) << "Size";
    std::cout << std::setw(25) << "Min Value";
    std::cout << std::setw(25) << "Max Value" << std::endl;
    std::cout << std::string(80, '-') << std::endl;

    // Integer types
    std::cout << "Integer Types:" << std::endl;
    printTypeInfo<char>("char");
    printTypeInfo<short>("short");
    printTypeInfo<int>("int");
    printTypeInfo<long>("long");
    printTypeInfo<long long>("long long");
    printTypeInfo<unsigned char>("unsigned char");
    printTypeInfo<unsigned short>("unsigned short");
    printTypeInfo<unsigned int>("unsigned int");
    printTypeInfo<unsigned long>("unsigned long");
    printTypeInfo<unsigned long long>("unsigned long long");

    std::cout << std::endl;

    // Fixed-width integer types
    std::cout << "Fixed-width Integer Types:" << std::endl;
    printTypeInfo<std::int8_t>("int8_t");
    printTypeInfo<std::int16_t>("int16_t");
    printTypeInfo<std::int32_t>("int32_t");
    printTypeInfo<std::int64_t>("int64_t");
    printTypeInfo<std::uint8_t>("uint8_t");
    printTypeInfo<std::uint16_t>("uint16_t");
    printTypeInfo<std::uint32_t>("uint32_t");
    printTypeInfo<std::uint64_t>("uint64_t");

    std::cout << std::endl;

    // Floating-point types
    std::cout << std::left << std::setw(20) << "Type";
    std::cout << std::right << std::setw(10) << "Size";
    std::cout << std::setw(15) << "Precision";
    std::cout << std::setw(15) << "Min Value";
    std::cout << std::setw(15) << "Max Value" << std::endl;
    std::cout << std::string(80, '-') << std::endl;

    std::cout << "Floating-point Types:" << std::endl;
    printTypeInfo<float>("float");
    printTypeInfo<double>("double");
    printTypeInfo<long double>("long double");

    std::cout << std::endl;

    // Boolean and character
    std::cout << "Other Types:" << std::endl;
    printTypeInfo<bool>("bool");
    printTypeInfo<wchar_t>("wchar_t");
    printTypeInfo<char16_t>("char16_t");
    printTypeInfo<char32_t>("char32_t");

    return 0;
}
```

**Explanation:**
- Template function `printTypeInfo` handles different types generically
- `constexpr if` (C++17) allows compile-time branching based on type traits
- `std::numeric_limits` provides comprehensive type information
- Proper formatting using `<iomanip>` manipulators
- Demonstrates both traditional and fixed-width integer types
- Shows precision information for floating-point types

</details>

#### 🏋️ Exercise 2: Advanced Variable Initialization
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 25 minutes

Create a comprehensive example that demonstrates different initialization techniques, including list initialization, auto type deduction, and const/constexpr usage.

<details>
<summary>💡 Click to see hints</summary>

- Use various initialization syntaxes
- Demonstrate narrowing conversion prevention with list initialization
- Show constexpr functions and variables
- Include examples with containers and custom classes
- Use auto in different contexts

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <array>
#include <initializer_list>

// Constexpr function for compile-time computation
constexpr int fibonacci(int n) {
    if (n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

// Class demonstrating various initialization methods
class Rectangle {
private:
    double width, height;

public:
    // Constructor with member initializer list
    constexpr Rectangle(double w, double h) : width(w), height(h) {}

    // Constructor from initializer list
    Rectangle(std::initializer_list<double> dims) {
        auto it = dims.begin();
        width = (it != dims.end()) ? *it++ : 0.0;
        height = (it != dims.end()) ? *it : 0.0;
    }

    constexpr double area() const { return width * height; }
    constexpr double perimeter() const { return 2 * (width + height); }

    void display() const {
        std::cout << "Rectangle: " << width << "x" << height
                  << ", Area: " << area() << ", Perimeter: " << perimeter() << std::endl;
    }
};

int main() {
    std::cout << "=== Advanced Variable Initialization ===" << std::endl << std::endl;

    // 1. Basic initialization methods
    std::cout << "1. Basic Initialization Methods:" << std::endl;

    int a = 10;              // Copy initialization
    int b(20);              // Direct initialization
    int c{30};              // List initialization (C++11)
    int d = {40};           // Copy-list initialization

    // List initialization prevents narrowing
    // double to int conversion
    // int narrow{3.14}; // Error: narrowing conversion

    std::cout << "a = " << a << ", b = " << b << ", c = " << c << ", d = " << d << std::endl;
    std::cout << std::endl;

    // 2. Auto type deduction
    std::cout << "2. Auto Type Deduction:" << std::endl;

    auto int_val = 42;                    // int
    auto double_val = 3.14;               // double
    auto char_val = 'A';                  // char
    auto string_val = std::string("C++"); // std::string
    auto list_val = {1, 2, 3, 4, 5};     // std::initializer_list<int>

    // Auto with references and const
    const int original = 100;
    auto copy = original;           // int (const removed)
    auto& ref = original;           // const int& (reference to const)
    const auto& const_ref = original; // const int&

    std::cout << "Auto-deduced values:" << std::endl;
    std::cout << "int_val: " << int_val << std::endl;
    std::cout << "double_val: " << double_val << std::endl;
    std::cout << "char_val: " << char_val << std::endl;
    std::cout << "string_val: " << string_val << std::endl;
    std::cout << std::endl;

    // 3. Container initialization
    std::cout << "3. Container Initialization:" << std::endl;

    // Vector initialization methods
    std::vector<int> vec1{1, 2, 3, 4, 5};           // List initialization
    std::vector<int> vec2(5, 10);                   // 5 elements, all value 10
    std::vector<int> vec3(vec1.begin(), vec1.end()); // Range initialization
    auto vec4 = std::vector<int>{10, 20, 30};       // Auto with explicit type

    // Array initialization
    std::array<int, 5> arr1{1, 2, 3, 4, 5};
    std::array<int, 5> arr2{};                      // Zero-initialized

    std::cout << "vec1: ";
    for (const auto& val : vec1) std::cout << val << " ";
    std::cout << std::endl;

    std::cout << "vec2: ";
    for (const auto& val : vec2) std::cout << val << " ";
    std::cout << std::endl;
    std::cout << std::endl;

    // 4. Const and constexpr
    std::cout << "4. Const and Constexpr:" << std::endl;

    const int runtime_const = rand() % 100;     // Runtime constant
    constexpr int compile_const = 42;           // Compile-time constant
    constexpr int fib_10 = fibonacci(10);       // Computed at compile time

    // Constexpr with objects
    constexpr Rectangle rect1(5.0, 3.0);
    constexpr auto area1 = rect1.area();        // Computed at compile time

    std::cout << "Runtime const: " << runtime_const << std::endl;
    std::cout << "Compile-time const: " << compile_const << std::endl;
    std::cout << "Fibonacci(10): " << fib_10 << std::endl;
    std::cout << "Rectangle area (compile-time): " << area1 << std::endl;
    std::cout << std::endl;

    // 5. Complex object initialization
    std::cout << "5. Complex Object Initialization:" << std::endl;

    Rectangle rect2{10.0, 7.0};               // List initialization
    Rectangle rect3(15.0, 12.0);              // Direct initialization
    Rectangle rect4{8.5, 6.5};                // Using initializer_list constructor
    auto rect5 = Rectangle(20.0, 15.0);       // Auto with explicit construction

    rect2.display();
    rect3.display();
    rect4.display();
    rect5.display();
    std::cout << std::endl;

    // 6. Modern initialization patterns
    std::cout << "6. Modern Initialization Patterns:" << std::endl;

    // Structured binding (C++17)
    auto [width, height] = std::make_pair(25.0, 18.0);
    std::cout << "Structured binding: width = " << width << ", height = " << height << std::endl;

    // Lambda with auto
    auto multiply = [](auto a, auto b) { return a * b; };
    auto result1 = multiply(5, 3);       // int * int
    auto result2 = multiply(2.5, 4.0);   // double * double

    std::cout << "Lambda results: " << result1 << ", " << result2 << std::endl;

    // Auto with function pointers
    auto func_ptr = &fibonacci;
    auto fib_result = func_ptr(8);
    std::cout << "Function pointer result: " << fib_result << std::endl;

    return 0;
}
```

**Explanation:**
- Comprehensive demonstration of all initialization methods
- Constexpr functions computed at compile time for better performance
- Template-like behavior with auto in lambdas
- Structured binding for tuple/pair decomposition
- Proper use of const vs constexpr for different scenarios
- Modern C++ features integrated naturally
- Prevention of narrowing conversions with list initialization

</details>

[Back to top](#-c-documentation)

---

## 🎯 Control Structures

**📊 Chapter 4 of 14**

🎯 **Learning Objectives:**
- Master conditional statements and their modern variants
- Understand different loop types and their appropriate use cases
- Learn switch statements and pattern matching
- Explore jump statements and control flow management

⏱️ **Estimated Reading Time:** 20 minutes

📋 **Prerequisites:** Basic understanding of boolean expressions and operators

### Conditional Statements

#### Basic if-else Statements

```cpp
#include <iostream>
#include <string>

int main() {
    int score = 85;

    // Simple if statement
    if (score >= 90) {
        std::cout << "Excellent!" << std::endl;
    }

    // if-else statement
    if (score >= 70) {
        std::cout << "Good job!" << std::endl;
    } else {
        std::cout << "Need improvement" << std::endl;
    }

    // if-else if-else chain
    std::string grade;
    if (score >= 90) {
        grade = "A";
    } else if (score >= 80) {
        grade = "B";
    } else if (score >= 70) {
        grade = "C";
    } else if (score >= 60) {
        grade = "D";
    } else {
        grade = "F";
    }

    std::cout << "Grade: " << grade << std::endl;

    return 0;
}
```

#### Conditional Operator (Ternary)

```cpp
#include <iostream>
#include <algorithm>

int main() {
    int a = 10, b = 20;

    // Simple ternary operator
    int max_val = (a > b) ? a : b;
    std::cout << "Maximum: " << max_val << std::endl;

    // Nested ternary (use sparingly)
    int x = 5, y = 3, z = 8;
    int max_three = (x > y) ? ((x > z) ? x : z) : ((y > z) ? y : z);
    std::cout << "Maximum of three: " << max_three << std::endl;

    // Better alternative using std::max
    int max_better = std::max({x, y, z});
    std::cout << "Maximum (using std::max): " << max_better << std::endl;

    // Ternary with different types
    bool is_positive = true;
    auto result = is_positive ? 42 : -42;
    std::cout << "Result: " << result << std::endl;

    return 0;
}
```

#### if with Initializer (C++17)

```cpp
#include <iostream>
#include <map>
#include <string>

int main() {
    std::map<std::string, int> ages = {
        {"Alice", 30},
        {"Bob", 25},
        {"Charlie", 35}
    };

    // if with initializer - variable scope limited to if block
    if (auto it = ages.find("Alice"); it != ages.end()) {
        std::cout << "Alice's age: " << it->second << std::endl;
    } else {
        std::cout << "Alice not found" << std::endl;
    }

    // Multiple conditions with initializer
    if (auto [inserted, success] = ages.insert({"David", 28}); success) {
        std::cout << "David added successfully" << std::endl;
    } else {
        std::cout << "David already exists" << std::endl;
    }

    return 0;
}
```

### Loops

#### For Loops

```cpp
#include <iostream>
#include <vector>
#include <string>

int main() {
    // Traditional for loop
    std::cout << "Traditional for loop:" << std::endl;
    for (int i = 0; i < 5; ++i) {
        std::cout << i << " ";
    }
    std::cout << std::endl;

    // Multiple variables in for loop
    std::cout << "Multiple variables:" << std::endl;
    for (int i = 0, j = 10; i < 5; ++i, --j) {
        std::cout << "i=" << i << ", j=" << j << std::endl;
    }

    // Range-based for loop (C++11)
    std::vector<std::string> names = {"Alice", "Bob", "Charlie"};

    std::cout << "Range-based for loop:" << std::endl;
    for (const auto& name : names) {
        std::cout << name << std::endl;
    }

    // Range-based for with index (C++20)
    std::cout << "With index:" << std::endl;
    for (auto&& [index, name] : std::views::enumerate(names)) {
        std::cout << index << ": " << name << std::endl;
    }

    // Range-based for with modification
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    for (auto& num : numbers) {
        num *= 2; // Modify elements
    }

    std::cout << "Modified numbers: ";
    for (const auto& num : numbers) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

#### While Loops

```cpp
#include <iostream>
#include <random>

int main() {
    // Basic while loop
    int count = 0;
    while (count < 5) {
        std::cout << "Count: " << count << std::endl;
        ++count;
    }

    // while with complex condition
    std::random_device rd;
    std::mt19937 gen(rd());
    std::uniform_int_distribution<> dis(1, 10);

    int target = 7;
    int attempts = 0;
    int guess;

    while ((guess = dis(gen)) != target && attempts < 10) {
        std::cout << "Attempt " << ++attempts << ": guessed " << guess << std::endl;
    }

    if (guess == target) {
        std::cout << "Found target " << target << " in " << attempts << " attempts!" << std::endl;
    } else {
        std::cout << "Target not found in 10 attempts" << std::endl;
    }

    return 0;
}
```

#### Do-While Loops

```cpp
#include <iostream>
#include <string>

int main() {
    // Basic do-while loop
    int number;
    do {
        std::cout << "Enter a positive number (0 to quit): ";
        std::cin >> number;

        if (number > 0) {
            std::cout << "You entered: " << number << std::endl;
        }
    } while (number != 0);

    std::cout << "Goodbye!" << std::endl;

    // Menu system example
    char choice;
    do {
        std::cout << "\n=== Menu ===" << std::endl;
        std::cout << "1. Option A" << std::endl;
        std::cout << "2. Option B" << std::endl;
        std::cout << "3. Option C" << std::endl;
        std::cout << "q. Quit" << std::endl;
        std::cout << "Enter choice: ";
        std::cin >> choice;

        switch (choice) {
            case '1':
                std::cout << "You chose Option A" << std::endl;
                break;
            case '2':
                std::cout << "You chose Option B" << std::endl;
                break;
            case '3':
                std::cout << "You chose Option C" << std::endl;
                break;
            case 'q':
            case 'Q':
                std::cout << "Quitting..." << std::endl;
                break;
            default:
                std::cout << "Invalid choice!" << std::endl;
        }
    } while (choice != 'q' && choice != 'Q');

    return 0;
}
```

### Switch Statements

#### Basic Switch Statement

```cpp
#include <iostream>

enum class Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
};

int main() {
    Day today = Day::WEDNESDAY;

    // Traditional switch statement
    switch (today) {
        case Day::MONDAY:
            std::cout << "Start of work week" << std::endl;
            break;
        case Day::TUESDAY:
        case Day::WEDNESDAY:
        case Day::THURSDAY:
            std::cout << "Middle of work week" << std::endl;
            break;
        case Day::FRIDAY:
            std::cout << "End of work week!" << std::endl;
            break;
        case Day::SATURDAY:
        case Day::SUNDAY:
            std::cout << "Weekend!" << std::endl;
            break;
        default:
            std::cout << "Invalid day" << std::endl;
    }

    return 0;
}
```

#### Switch with Initializer (C++17)

```cpp
#include <iostream>
#include <string>

enum class Status { SUCCESS, WARNING, ERROR };

Status processData(const std::string& data) {
    if (data.empty()) return Status::ERROR;
    if (data.size() > 100) return Status::WARNING;
    return Status::SUCCESS;
}

int main() {
    std::string input = "Some data to process";

    // Switch with initializer
    switch (auto status = processData(input); status) {
        case Status::SUCCESS:
            std::cout << "Data processed successfully" << std::endl;
            break;
        case Status::WARNING:
            std::cout << "Data processed with warnings" << std::endl;
            break;
        case Status::ERROR:
            std::cout << "Failed to process data" << std::endl;
            break;
    }

    return 0;
}
```

#### Modern Switch Alternative - if constexpr

```cpp
#include <iostream>
#include <type_traits>

template<typename T>
void processType(const T& value) {
    if constexpr (std::is_integral_v<T>) {
        std::cout << "Processing integer: " << value << std::endl;
    } else if constexpr (std::is_floating_point_v<T>) {
        std::cout << "Processing floating-point: " << value << std::endl;
    } else if constexpr (std::is_same_v<T, std::string>) {
        std::cout << "Processing string: " << value << std::endl;
    } else {
        std::cout << "Processing unknown type" << std::endl;
    }
}

int main() {
    processType(42);
    processType(3.14);
    processType(std::string("Hello"));

    return 0;
}
```

### Jump Statements

#### Break and Continue

```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    std::cout << "Using continue to skip even numbers:" << std::endl;
    for (const auto& num : numbers) {
        if (num % 2 == 0) {
            continue; // Skip even numbers
        }
        std::cout << num << " ";
    }
    std::cout << std::endl;

    std::cout << "Using break to stop at first number > 5:" << std::endl;
    for (const auto& num : numbers) {
        if (num > 5) {
            break; // Stop when we find a number greater than 5
        }
        std::cout << num << " ";
    }
    std::cout << std::endl;

    // Nested loop control
    std::cout << "Nested loop with labeled break equivalent:" << std::endl;
    bool found = false;
    for (int i = 1; i <= 3 && !found; ++i) {
        for (int j = 1; j <= 3; ++j) {
            std::cout << "(" << i << "," << j << ") ";
            if (i == 2 && j == 2) {
                found = true;
                break; // Break inner loop
            }
        }
        std::cout << std::endl;
    }

    return 0;
}
```

#### Goto Statement (Use Sparingly)

```cpp
#include <iostream>

int main() {
    int attempts = 0;
    const int max_attempts = 3;

retry:
    attempts++;
    std::cout << "Attempt " << attempts << std::endl;

    // Simulate some operation that might fail
    if (attempts < max_attempts) {
        std::cout << "Operation failed, retrying..." << std::endl;
        goto retry; // Jump back to retry label
    }

    std::cout << "Maximum attempts reached" << std::endl;

    // Better alternative using loops
    std::cout << "\nBetter approach using loop:" << std::endl;
    for (int i = 1; i <= max_attempts; ++i) {
        std::cout << "Attempt " << i << std::endl;
        if (i < max_attempts) {
            std::cout << "Operation failed, retrying..." << std::endl;
        }
    }
    std::cout << "Maximum attempts reached" << std::endl;

    return 0;
}
```

### 💡 Code Examples

**Example 1: Grade Calculator with Multiple Control Structures**

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <numeric>
#include <iomanip>

class GradeCalculator {
private:
    std::vector<double> grades;

public:
    void addGrade(double grade) {
        if (grade >= 0.0 && grade <= 100.0) {
            grades.push_back(grade);
        } else {
            std::cout << "Invalid grade: " << grade << " (must be 0-100)" << std::endl;
        }
    }

    double calculateAverage() const {
        if (grades.empty()) return 0.0;
        return std::accumulate(grades.begin(), grades.end(), 0.0) / grades.size();
    }

    char getLetterGrade(double average) const {
        if (average >= 90) return 'A';
        else if (average >= 80) return 'B';
        else if (average >= 70) return 'C';
        else if (average >= 60) return 'D';
        else return 'F';
    }

    void displayReport() const {
        if (grades.empty()) {
            std::cout << "No grades recorded." << std::endl;
            return;
        }

        std::cout << "\n=== Grade Report ===" << std::endl;
        std::cout << "Individual Grades: ";
        for (const auto& grade : grades) {
            std::cout << grade << " ";
        }
        std::cout << std::endl;

        double average = calculateAverage();
        char letter = getLetterGrade(average);

        std::cout << std::fixed << std::setprecision(2);
        std::cout << "Average: " << average << std::endl;
        std::cout << "Letter Grade: " << letter << std::endl;

        // Switch statement for grade description
        switch (letter) {
            case 'A':
                std::cout << "Excellent work!" << std::endl;
                break;
            case 'B':
                std::cout << "Good job!" << std::endl;
                break;
            case 'C':
                std::cout << "Satisfactory performance" << std::endl;
                break;
            case 'D':
                std::cout << "Needs improvement" << std::endl;
                break;
            case 'F':
                std::cout << "Failing - seek help" << std::endl;
                break;
        }
    }
};

int main() {
    GradeCalculator calculator;

    // Input grades with validation loop
    std::cout << "Enter grades (0-100), enter -1 to finish:" << std::endl;

    double grade;
    while (std::cin >> grade && grade != -1) {
        calculator.addGrade(grade);
    }

    calculator.displayReport();

    return 0;
}
```

**Example 2: Advanced Loop Patterns**

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
#include <ranges>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    // 1. Range-based for with filtering (C++20)
    std::cout << "Even numbers using ranges:" << std::endl;
    for (auto even : numbers | std::views::filter([](int n) { return n % 2 == 0; })) {
        std::cout << even << " ";
    }
    std::cout << std::endl;

    // 2. Traditional for with custom step
    std::cout << "Every 2nd element:" << std::endl;
    for (size_t i = 0; i < numbers.size(); i += 2) {
        std::cout << numbers[i] << " ";
    }
    std::cout << std::endl;

    // 3. Reverse iteration
    std::cout << "Reverse order:" << std::endl;
    for (auto it = numbers.rbegin(); it != numbers.rend(); ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;

    // 4. Iterator-based loop with early termination
    std::cout << "Find first number > 5:" << std::endl;
    for (auto it = numbers.begin(); it != numbers.end(); ++it) {
        if (*it > 5) {
            std::cout << "Found: " << *it << " at position "
                      << std::distance(numbers.begin(), it) << std::endl;
            break;
        }
    }

    // 5. Nested loops with break control
    std::cout << "2D grid search:" << std::endl;
    std::vector<std::vector<int>> grid = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int target = 5;
    bool found = false;

    for (size_t i = 0; i < grid.size() && !found; ++i) {
        for (size_t j = 0; j < grid[i].size(); ++j) {
            if (grid[i][j] == target) {
                std::cout << "Found " << target << " at position ("
                          << i << ", " << j << ")" << std::endl;
                found = true;
                break;
            }
        }
    }

    return 0;
}
```

### ⚠️ Common Pitfalls

1. **Missing Break in Switch**: Forgetting break statements causes fall-through
2. **Infinite Loops**: Not updating loop condition variables
3. **Off-by-One Errors**: Incorrect loop bounds (< vs <=)
4. **Modifying Collection While Iterating**: Can invalidate iterators
5. **Goto Overuse**: Creates spaghetti code, use structured alternatives

### ✅ Best Practices

1. **Use Range-Based For**: Prefer range-based for loops when possible
2. **Initialize in Conditions**: Use C++17 if/switch initializers
3. **Avoid Deep Nesting**: Extract complex logic into functions
4. **Use Break Flags**: Better than goto for nested loop control
5. **Prefer Algorithms**: Use STL algorithms over manual loops when appropriate

### 🏋️ Exercises

#### 🏋️ Exercise 1: Number Pattern Generator
**Difficulty:** 🟢 Beginner
**Estimated Time:** 15 minutes

Create a program that generates different number patterns using various loop types. Include patterns like triangles, diamonds, and spirals.

<details>
<summary>💡 Click to see hints</summary>

- Use nested loops for 2D patterns
- Combine different loop types (for, while)
- Use modulo operator for repeating patterns
- Control spacing with conditional statements

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <iomanip>

class PatternGenerator {
public:
    static void printTriangle(int height) {
        std::cout << "Right Triangle (height " << height << "):" << std::endl;
        for (int i = 1; i <= height; ++i) {
            for (int j = 1; j <= i; ++j) {
                std::cout << "* ";
            }
            std::cout << std::endl;
        }
        std::cout << std::endl;
    }

    static void printPyramid(int height) {
        std::cout << "Pyramid (height " << height << "):" << std::endl;
        for (int i = 1; i <= height; ++i) {
            // Print spaces
            for (int j = 1; j <= height - i; ++j) {
                std::cout << " ";
            }
            // Print stars
            for (int j = 1; j <= 2 * i - 1; ++j) {
                std::cout << "*";
            }
            std::cout << std::endl;
        }
        std::cout << std::endl;
    }

    static void printDiamond(int size) {
        std::cout << "Diamond (size " << size << "):" << std::endl;

        // Upper half (including middle)
        for (int i = 1; i <= size; ++i) {
            for (int j = 1; j <= size - i; ++j) {
                std::cout << " ";
            }
            for (int j = 1; j <= 2 * i - 1; ++j) {
                std::cout << "*";
            }
            std::cout << std::endl;
        }

        // Lower half
        for (int i = size - 1; i >= 1; --i) {
            for (int j = 1; j <= size - i; ++j) {
                std::cout << " ";
            }
            for (int j = 1; j <= 2 * i - 1; ++j) {
                std::cout << "*";
            }
            std::cout << std::endl;
        }
        std::cout << std::endl;
    }

    static void printNumberSpiral(int size) {
        std::cout << "Number Spiral (" << size << "x" << size << "):" << std::endl;

        // Create 2D array
        std::vector<std::vector<int>> matrix(size, std::vector<int>(size, 0));

        int num = 1;
        int top = 0, bottom = size - 1, left = 0, right = size - 1;

        while (top <= bottom && left <= right) {
            // Fill top row
            for (int col = left; col <= right; ++col) {
                matrix[top][col] = num++;
            }
            top++;

            // Fill right column
            for (int row = top; row <= bottom; ++row) {
                matrix[row][right] = num++;
            }
            right--;

            // Fill bottom row
            if (top <= bottom) {
                for (int col = right; col >= left; --col) {
                    matrix[bottom][col] = num++;
                }
                bottom--;
            }

            // Fill left column
            if (left <= right) {
                for (int row = bottom; row >= top; --row) {
                    matrix[row][left] = num++;
                }
                left++;
            }
        }

        // Print the matrix
        for (const auto& row : matrix) {
            for (int val : row) {
                std::cout << std::setw(3) << val;
            }
            std::cout << std::endl;
        }
        std::cout << std::endl;
    }

    static void printCheckerboard(int size) {
        std::cout << "Checkerboard (" << size << "x" << size << "):" << std::endl;
        for (int i = 0; i < size; ++i) {
            for (int j = 0; j < size; ++j) {
                if ((i + j) % 2 == 0) {
                    std::cout << "■ ";
                } else {
                    std::cout << "□ ";
                }
            }
            std::cout << std::endl;
        }
        std::cout << std::endl;
    }
};

int main() {
    std::cout << "=== Pattern Generator ===" << std::endl << std::endl;

    int choice;
    do {
        std::cout << "Choose a pattern:" << std::endl;
        std::cout << "1. Right Triangle" << std::endl;
        std::cout << "2. Pyramid" << std::endl;
        std::cout << "3. Diamond" << std::endl;
        std::cout << "4. Number Spiral" << std::endl;
        std::cout << "5. Checkerboard" << std::endl;
        std::cout << "0. Exit" << std::endl;
        std::cout << "Enter choice (0-5): ";

        std::cin >> choice;

        if (choice >= 1 && choice <= 5) {
            int size;
            std::cout << "Enter size: ";
            std::cin >> size;

            if (size > 0 && size <= 20) {
                std::cout << std::endl;

                switch (choice) {
                    case 1:
                        PatternGenerator::printTriangle(size);
                        break;
                    case 2:
                        PatternGenerator::printPyramid(size);
                        break;
                    case 3:
                        PatternGenerator::printDiamond(size);
                        break;
                    case 4:
                        PatternGenerator::printNumberSpiral(size);
                        break;
                    case 5:
                        PatternGenerator::printCheckerboard(size);
                        break;
                }
            } else {
                std::cout << "Size must be between 1 and 20" << std::endl;
            }
        } else if (choice != 0) {
            std::cout << "Invalid choice!" << std::endl;
        }

        std::cout << std::endl;

    } while (choice != 0);

    std::cout << "Goodbye!" << std::endl;

    return 0;
}
```

**Explanation:**
- Demonstrates various nested loop patterns
- Uses different control structures (for, while, do-while, switch)
- Shows practical applications of loop control (break, continue)
- Includes input validation and user interaction
- Combines mathematical logic with control flow
- Uses modern C++ features like range-based for loops

</details>

#### 🏋️ Exercise 2: Advanced Control Flow
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 30 minutes

Create a text-based game that uses advanced control structures including nested loops, switch statements with fall-through, and complex conditional logic.

<details>
<summary>💡 Click to see hints</summary>

- Use enums for game states
- Implement state machines with switch statements
- Use nested loops for game board management
- Include input validation loops
- Use early returns and break/continue strategically

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <vector>
#include <random>
#include <algorithm>
#include <limits>

enum class GameState {
    MENU,
    PLAYING,
    GAME_OVER,
    EXIT
};

enum class CellState {
    EMPTY,
    MINE,
    REVEALED,
    FLAGGED
};

class Minesweeper {
private:
    int width, height, mines;
    std::vector<std::vector<CellState>> board;
    std::vector<std::vector<int>> mineCount;
    std::vector<std::vector<bool>> revealed;
    GameState currentState;
    bool gameWon;

public:
    Minesweeper(int w = 10, int h = 10, int m = 15)
        : width(w), height(h), mines(m), currentState(GameState::MENU), gameWon(false) {
        initializeBoard();
    }

    void run() {
        while (currentState != GameState::EXIT) {
            switch (currentState) {
                case GameState::MENU:
                    showMenu();
                    break;
                case GameState::PLAYING:
                    playGame();
                    break;
                case GameState::GAME_OVER:
                    showGameOver();
                    break;
                case GameState::EXIT:
                    break;
            }
        }
    }

private:
    void initializeBoard() {
        board.assign(height, std::vector<CellState>(width, CellState::EMPTY));
        mineCount.assign(height, std::vector<int>(width, 0));
        revealed.assign(height, std::vector<bool>(width, false));

        placeMines();
        calculateMineNumbers();
    }

    void placeMines() {
        std::random_device rd;
        std::mt19937 gen(rd());
        std::uniform_int_distribution<> rowDist(0, height - 1);
        std::uniform_int_distribution<> colDist(0, width - 1);

        int placedMines = 0;
        while (placedMines < mines) {
            int row = rowDist(gen);
            int col = colDist(gen);

            if (board[row][col] != CellState::MINE) {
                board[row][col] = CellState::MINE;
                placedMines++;
            }
        }
    }

    void calculateMineNumbers() {
        for (int i = 0; i < height; ++i) {
            for (int j = 0; j < width; ++j) {
                if (board[i][j] != CellState::MINE) {
                    int count = 0;
                    for (int di = -1; di <= 1; ++di) {
                        for (int dj = -1; dj <= 1; ++dj) {
                            int ni = i + di, nj = j + dj;
                            if (isValid(ni, nj) && board[ni][nj] == CellState::MINE) {
                                count++;
                            }
                        }
                    }
                    mineCount[i][j] = count;
                }
            }
        }
    }

    bool isValid(int row, int col) {
        return row >= 0 && row < height && col >= 0 && col < width;
    }

    void showMenu() {
        std::cout << "\n=== MINESWEEPER ===" << std::endl;
        std::cout << "1. New Game (Easy: 10x10, 15 mines)" << std::endl;
        std::cout << "2. New Game (Medium: 15x15, 35 mines)" << std::endl;
        std::cout << "3. New Game (Hard: 20x20, 80 mines)" << std::endl;
        std::cout << "4. Custom Game" << std::endl;
        std::cout << "5. Exit" << std::endl;
        std::cout << "Choose option: ";

        int choice;
        if (std::cin >> choice) {
            switch (choice) {
                case 1:
                    setupGame(10, 10, 15);
                    currentState = GameState::PLAYING;
                    break;
                case 2:
                    setupGame(15, 15, 35);
                    currentState = GameState::PLAYING;
                    break;
                case 3:
                    setupGame(20, 20, 80);
                    currentState = GameState::PLAYING;
                    break;
                case 4:
                    if (setupCustomGame()) {
                        currentState = GameState::PLAYING;
                    }
                    break;
                case 5:
                    currentState = GameState::EXIT;
                    break;
                default:
                    std::cout << "Invalid choice!" << std::endl;
            }
        } else {
            std::cin.clear();
            std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            std::cout << "Invalid input!" << std::endl;
        }
    }

    bool setupCustomGame() {
        int w, h, m;
        std::cout << "Enter width (5-25): ";
        if (!(std::cin >> w) || w < 5 || w > 25) {
            std::cout << "Invalid width!" << std::endl;
            return false;
        }

        std::cout << "Enter height (5-25): ";
        if (!(std::cin >> h) || h < 5 || h > 25) {
            std::cout << "Invalid height!" << std::endl;
            return false;
        }

        int maxMines = (w * h) / 3;
        std::cout << "Enter number of mines (1-" << maxMines << "): ";
        if (!(std::cin >> m) || m < 1 || m > maxMines) {
            std::cout << "Invalid number of mines!" << std::endl;
            return false;
        }

        setupGame(w, h, m);
        return true;
    }

    void setupGame(int w, int h, int m) {
        width = w;
        height = h;
        mines = m;
        gameWon = false;
        initializeBoard();
    }

    void playGame() {
        displayBoard();

        std::cout << "\nEnter command (r/f row col) or 'q' to quit: ";
        std::string command;
        int row, col;

        if (std::cin >> command) {
            if (command == "q" || command == "quit") {
                currentState = GameState::MENU;
                return;
            } else if ((command == "r" || command == "f") &&
                       std::cin >> row >> col &&
                       isValid(row - 1, col - 1)) {
                row--; col--; // Convert to 0-based indexing

                if (command == "r") {
                    if (revealCell(row, col)) {
                        if (checkWin()) {
                            gameWon = true;
                            currentState = GameState::GAME_OVER;
                        }
                    } else {
                        gameWon = false;
                        currentState = GameState::GAME_OVER;
                    }
                } else if (command == "f") {
                    flagCell(row, col);
                }
            } else {
                std::cout << "Invalid command! Use 'r row col' to reveal or 'f row col' to flag" << std::endl;
                std::cin.clear();
                std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
            }
        }
    }

    void displayBoard() {
        std::cout << "\n   ";
        for (int j = 0; j < width; ++j) {
            std::cout << std::setw(3) << (j + 1);
        }
        std::cout << std::endl;

        for (int i = 0; i < height; ++i) {
            std::cout << std::setw(2) << (i + 1) << " ";
            for (int j = 0; j < width; ++j) {
                if (!revealed[i][j]) {
                    if (board[i][j] == CellState::FLAGGED) {
                        std::cout << " F ";
                    } else {
                        std::cout << " . ";
                    }
                } else {
                    if (board[i][j] == CellState::MINE) {
                        std::cout << " * ";
                    } else if (mineCount[i][j] == 0) {
                        std::cout << "   ";
                    } else {
                        std::cout << " " << mineCount[i][j] << " ";
                    }
                }
            }
            std::cout << std::endl;
        }
    }

    bool revealCell(int row, int col) {
        if (!isValid(row, col) || revealed[row][col] || board[row][col] == CellState::FLAGGED) {
            return true;
        }

        revealed[row][col] = true;

        if (board[row][col] == CellState::MINE) {
            return false; // Game over
        }

        // Auto-reveal adjacent cells if mine count is 0
        if (mineCount[row][col] == 0) {
            for (int di = -1; di <= 1; ++di) {
                for (int dj = -1; dj <= 1; ++dj) {
                    revealCell(row + di, col + dj);
                }
            }
        }

        return true;
    }

    void flagCell(int row, int col) {
        if (!isValid(row, col) || revealed[row][col]) {
            return;
        }

        board[row][col] = (board[row][col] == CellState::FLAGGED)
                         ? CellState::EMPTY
                         : CellState::FLAGGED;
    }

    bool checkWin() {
        int revealedCount = 0;
        for (int i = 0; i < height; ++i) {
            for (int j = 0; j < width; ++j) {
                if (revealed[i][j] && board[i][j] != CellState::MINE) {
                    revealedCount++;
                }
            }
        }
        return revealedCount == (width * height - mines);
    }

    void showGameOver() {
        // Reveal all mines
        for (int i = 0; i < height; ++i) {
            for (int j = 0; j < width; ++j) {
                if (board[i][j] == CellState::MINE) {
                    revealed[i][j] = true;
                }
            }
        }

        displayBoard();

        if (gameWon) {
            std::cout << "\n🎉 Congratulations! You won! 🎉" << std::endl;
        } else {
            std::cout << "\n💥 Game Over! You hit a mine! 💥" << std::endl;
        }

        std::cout << "\nPress Enter to continue...";
        std::cin.ignore();
        std::cin.get();
        currentState = GameState::MENU;
    }
};

int main() {
    Minesweeper game;
    game.run();
    return 0;
}
```

**Explanation:**
- Complex state machine using enums and switch statements
- Nested loops for board management and mine placement
- Multiple control structures working together
- Input validation with error handling
- Early returns and break/continue for flow control
- Recursive cell revelation using nested loops
- Game logic combining all control structure types

</details>

[Back to top](#-c-documentation)

---

## 🔧 Functions

**📊 Chapter 5 of 14**

🎯 **Learning Objectives:**
- Master function declaration, definition, and calling conventions
- Understand parameter passing mechanisms and return values
- Learn function overloading and template functions
- Explore modern C++ function features like lambdas and auto return types

⏱️ **Estimated Reading Time:** 25 minutes

📋 **Prerequisites:** Understanding of basic C++ syntax and data types

### Function Declaration and Definition

#### Basic Function Structure

```cpp
#include <iostream>

// Function declaration (prototype)
int add(int a, int b);
void greet(const std::string& name);
double calculateArea(double radius);

int main() {
    // Function calls
    int result = add(5, 3);
    std::cout << "5 + 3 = " << result << std::endl;

    greet("Alice");

    double area = calculateArea(2.5);
    std::cout << "Area of circle: " << area << std::endl;

    return 0;
}

// Function definitions
int add(int a, int b) {
    return a + b;
}

void greet(const std::string& name) {
    std::cout << "Hello, " << name << "!" << std::endl;
}

double calculateArea(double radius) {
    const double PI = 3.14159;
    return PI * radius * radius;
}
```

#### Default Parameters

```cpp
#include <iostream>
#include <string>

// Functions with default parameters
void createWindow(int width = 800, int height = 600,
                 const std::string& title = "Default Window") {
    std::cout << "Creating window: " << width << "x" << height
              << " - " << title << std::endl;
}

// Default parameters must be rightmost
int power(int base, int exponent = 2) {
    int result = 1;
    for (int i = 0; i < exponent; ++i) {
        result *= base;
    }
    return result;
}

int main() {
    // Various ways to call functions with default parameters
    createWindow();                           // Uses all defaults
    createWindow(1024);                       // Width specified
    createWindow(1024, 768);                  // Width and height
    createWindow(1920, 1080, "Main Window");  // All parameters

    std::cout << "2^2 = " << power(2) << std::endl;        // Uses default exponent
    std::cout << "2^8 = " << power(2, 8) << std::endl;     // Explicit exponent

    return 0;
}
```

### Parameters and Arguments

#### Pass by Value vs Pass by Reference

```cpp
#include <iostream>
#include <vector>

// Pass by value - creates a copy
void modifyValue(int x) {
    x = 100;  // Only modifies the local copy
    std::cout << "Inside modifyValue: x = " << x << std::endl;
}

// Pass by reference - operates on original
void modifyReference(int& x) {
    x = 100;  // Modifies the original variable
    std::cout << "Inside modifyReference: x = " << x << std::endl;
}

// Pass by const reference - efficient, read-only
void printVector(const std::vector<int>& vec) {
    std::cout << "Vector contents: ";
    for (const auto& element : vec) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
    // vec.push_back(42); // Error: cannot modify const reference
}

// Pass by pointer
void modifyPointer(int* x) {
    if (x != nullptr) {
        *x = 200;
    }
}

int main() {
    int value = 10;
    std::cout << "Original value: " << value << std::endl;

    modifyValue(value);
    std::cout << "After modifyValue: " << value << std::endl;

    modifyReference(value);
    std::cout << "After modifyReference: " << value << std::endl;

    modifyPointer(&value);
    std::cout << "After modifyPointer: " << value << std::endl;

    std::vector<int> numbers = {1, 2, 3, 4, 5};
    printVector(numbers); // Efficient - no copy made

    return 0;
}
```

#### Function Return Types

```cpp
#include <iostream>
#include <vector>
#include <optional>
#include <tuple>

// Traditional return
int multiply(int a, int b) {
    return a * b;
}

// Auto return type deduction (C++14)
auto divide(double a, double b) {
    return a / b;  // Returns double
}

// Trailing return type (C++11)
auto concatenate(const std::string& a, const std::string& b) -> std::string {
    return a + b;
}

// Multiple return values using tuple (C++11)
std::tuple<int, int, int> findMinMaxSum(const std::vector<int>& vec) {
    if (vec.empty()) {
        return {0, 0, 0};
    }

    int min_val = vec[0], max_val = vec[0], sum = 0;
    for (int val : vec) {
        if (val < min_val) min_val = val;
        if (val > max_val) max_val = val;
        sum += val;
    }

    return {min_val, max_val, sum};
}

// Optional return type (C++17)
std::optional<double> safeDivide(double a, double b) {
    if (b == 0) {
        return std::nullopt;  // No value
    }
    return a / b;
}

int main() {
    std::cout << "multiply(6, 7) = " << multiply(6, 7) << std::endl;
    std::cout << "divide(10.0, 3.0) = " << divide(10.0, 3.0) << std::endl;
    std::cout << "concatenate result: " << concatenate("Hello, ", "World!") << std::endl;

    // Structured binding with tuple (C++17)
    std::vector<int> numbers = {3, 1, 4, 1, 5, 9, 2};
    auto [min_val, max_val, sum] = findMinMaxSum(numbers);
    std::cout << "Min: " << min_val << ", Max: " << max_val << ", Sum: " << sum << std::endl;

    // Using optional
    if (auto result = safeDivide(10, 2); result.has_value()) {
        std::cout << "Safe division result: " << result.value() << std::endl;
    }

    if (auto result = safeDivide(10, 0); !result.has_value()) {
        std::cout << "Division by zero detected!" << std::endl;
    }

    return 0;
}
```

### Function Overloading

```cpp
#include <iostream>
#include <string>
#include <vector>

class Calculator {
public:
    // Overloaded functions - same name, different parameters

    // Different number of parameters
    int add(int a, int b) {
        std::cout << "Adding two integers: ";
        return a + b;
    }

    int add(int a, int b, int c) {
        std::cout << "Adding three integers: ";
        return a + b + c;
    }

    // Different parameter types
    double add(double a, double b) {
        std::cout << "Adding two doubles: ";
        return a + b;
    }

    std::string add(const std::string& a, const std::string& b) {
        std::cout << "Concatenating strings: ";
        return a + b;
    }

    // Different const-ness
    void print() {
        std::cout << "Non-const print" << std::endl;
    }

    void print() const {
        std::cout << "Const print" << std::endl;
    }

    // Template function overload
    template<typename T>
    T add(const std::vector<T>& values) {
        std::cout << "Adding vector elements: ";
        T sum = T{}; // Zero initialization
        for (const auto& val : values) {
            sum += val;
        }
        return sum;
    }
};

int main() {
    Calculator calc;

    std::cout << calc.add(5, 3) << std::endl;
    std::cout << calc.add(1, 2, 3) << std::endl;
    std::cout << calc.add(2.5, 3.7) << std::endl;
    std::cout << calc.add(std::string("Hello, "), std::string("World!")) << std::endl;

    std::vector<int> int_vec = {1, 2, 3, 4, 5};
    std::vector<double> double_vec = {1.1, 2.2, 3.3};

    std::cout << calc.add(int_vec) << std::endl;
    std::cout << calc.add(double_vec) << std::endl;

    calc.print();
    const Calculator const_calc;
    const_calc.print();

    return 0;
}
```

### Lambda Functions

#### Basic Lambda Syntax

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <functional>

int main() {
    // Basic lambda syntax: [capture](parameters) -> return_type { body }

    // Simple lambda
    auto hello = []() {
        std::cout << "Hello from lambda!" << std::endl;
    };
    hello();

    // Lambda with parameters
    auto add = [](int a, int b) {
        return a + b;
    };
    std::cout << "Lambda add: " << add(5, 3) << std::endl;

    // Lambda with explicit return type
    auto divide = [](double a, double b) -> double {
        return (b != 0) ? a / b : 0.0;
    };
    std::cout << "Lambda divide: " << divide(10, 3) << std::endl;

    // Using lambdas with STL algorithms
    std::vector<int> numbers = {5, 2, 8, 1, 9, 3};

    // Sort in ascending order
    std::sort(numbers.begin(), numbers.end(), [](int a, int b) {
        return a < b;
    });

    std::cout << "Sorted ascending: ";
    for (int n : numbers) std::cout << n << " ";
    std::cout << std::endl;

    // Count elements greater than 5
    int count = std::count_if(numbers.begin(), numbers.end(), [](int n) {
        return n > 5;
    });
    std::cout << "Numbers > 5: " << count << std::endl;

    return 0;
}
```

#### Lambda Captures

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <functional>

int main() {
    int multiplier = 3;
    int offset = 10;

    // Capture by value
    auto lambda1 = [multiplier](int x) {
        return x * multiplier;  // multiplier is copied
    };

    // Capture by reference
    auto lambda2 = [&offset](int x) {
        offset += x;  // Can modify original offset
        return offset;
    };

    // Capture all by value
    auto lambda3 = [=](int x) {
        return x * multiplier + offset;  // Both copied
    };

    // Capture all by reference
    auto lambda4 = [&](int x) {
        multiplier += 1;  // Modifies original
        return x * multiplier;
    };

    // Mixed capture
    auto lambda5 = [multiplier, &offset](int x) {
        offset += x;  // Reference capture
        return x * multiplier + offset;  // Value capture
    };

    // Mutable lambda (allows modification of captured values)
    auto lambda6 = [multiplier](int x) mutable {
        multiplier += 1;  // Modifies the copy
        return x * multiplier;
    };

    std::cout << "Original values - multiplier: " << multiplier << ", offset: " << offset << std::endl;

    std::cout << "lambda1(5): " << lambda1(5) << std::endl;
    std::cout << "lambda2(2): " << lambda2(2) << std::endl;
    std::cout << "After lambda2 - offset: " << offset << std::endl;

    std::cout << "lambda4(4): " << lambda4(4) << std::endl;
    std::cout << "After lambda4 - multiplier: " << multiplier << std::endl;

    // Generic lambda (C++14)
    auto generic_lambda = [](auto a, auto b) {
        return a + b;
    };

    std::cout << "Generic lambda (int): " << generic_lambda(5, 3) << std::endl;
    std::cout << "Generic lambda (double): " << generic_lambda(2.5, 3.7) << std::endl;
    std::cout << "Generic lambda (string): " << generic_lambda(std::string("Hello "), std::string("World")) << std::endl;

    return 0;
}
```

### 💡 Code Examples

**Example 1: Advanced Function Features**

```cpp
#include <iostream>
#include <vector>
#include <functional>
#include <memory>
#include <optional>
#include <variant>

// Function template with constraints (C++20 concept simulation)
template<typename T>
std::enable_if_t<std::is_arithmetic_v<T>, T>
clamp(T value, T min_val, T max_val) {
    return std::min(std::max(value, min_val), max_val);
}

// Function object (functor)
class Accumulator {
private:
    int sum = 0;

public:
    int operator()(int value) {
        sum += value;
        return sum;
    }

    int getSum() const { return sum; }
};

// Higher-order function
template<typename Container, typename Func>
auto transform_container(const Container& container, Func func) {
    std::vector<std::invoke_result_t<Func, typename Container::value_type>> result;
    result.reserve(container.size());

    for (const auto& item : container) {
        result.push_back(func(item));
    }

    return result;
}

// Variadic template function
template<typename... Args>
auto sum_all(Args... args) {
    return (args + ...); // C++17 fold expression
}

// Function with std::function parameter
void processData(const std::vector<int>& data, std::function<void(int)> processor) {
    for (int value : data) {
        processor(value);
    }
}

int main() {
    std::cout << "=== Advanced Function Features ===" << std::endl;

    // 1. Template function usage
    std::cout << "Clamp 15 between 10-20: " << clamp(15, 10, 20) << std::endl;
    std::cout << "Clamp 5 between 10-20: " << clamp(5, 10, 20) << std::endl;
    std::cout << "Clamp 25 between 10-20: " << clamp(25, 10, 20) << std::endl;

    // 2. Function object
    Accumulator acc;
    std::cout << "Accumulator: " << acc(10) << " -> " << acc(20) << " -> " << acc(5) << std::endl;

    // 3. Higher-order function
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    auto squared = transform_container(numbers, [](int x) { return x * x; });

    std::cout << "Original: ";
    for (int n : numbers) std::cout << n << " ";
    std::cout << std::endl;

    std::cout << "Squared: ";
    for (int n : squared) std::cout << n << " ";
    std::cout << std::endl;

    // 4. Variadic template
    std::cout << "Sum of 1,2,3,4,5: " << sum_all(1, 2, 3, 4, 5) << std::endl;
    std::cout << "Sum of 1.5,2.5,3.5: " << sum_all(1.5, 2.5, 3.5) << std::endl;

    // 5. std::function usage
    std::vector<int> data = {10, 20, 30, 40, 50};

    std::cout << "Processing with lambda: ";
    processData(data, [](int x) { std::cout << x * 2 << " "; });
    std::cout << std::endl;

    std::cout << "Processing with function object: ";
    Accumulator processor;
    processData(data, std::ref(processor));
    std::cout << "Final sum: " << processor.getSum() << std::endl;

    return 0;
}
```

### ⚠️ Common Pitfalls

1. **Function Overloading Ambiguity**: Be careful with implicit conversions
2. **Dangling References**: Don't return references to local variables
3. **Lambda Capture Issues**: Understand value vs reference captures
4. **Default Parameter Placement**: Must be rightmost parameters
5. **Template Function Instantiation**: Errors only appear at instantiation

### ✅ Best Practices

1. **Use const References**: For large objects passed as parameters
2. **Prefer Auto**: Let compiler deduce return types when appropriate
3. **RAII in Functions**: Use smart pointers for dynamic allocation
4. **Single Responsibility**: Each function should have one clear purpose
5. **Meaningful Names**: Function names should describe what they do

### 🏋️ Exercises

#### 🏋️ Exercise 1: Function Library
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 30 minutes

Create a mathematical function library that demonstrates function overloading, templates, and lambda usage.

<details>
<summary>💡 Click to see hints</summary>

- Create overloaded functions for different numeric types
- Use templates for generic operations
- Include lambda functions for complex operations
- Add utility functions using std::function
- Include error handling with optional return types

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <vector>
#include <functional>
#include <optional>
#include <cmath>
#include <algorithm>
#include <numeric>

namespace MathLib {

    // Overloaded power functions
    int power(int base, int exponent) {
        int result = 1;
        for (int i = 0; i < exponent; ++i) {
            result *= base;
        }
        return result;
    }

    double power(double base, double exponent) {
        return std::pow(base, exponent);
    }

    // Template function for generic operations
    template<typename T>
    T factorial(T n) {
        static_assert(std::is_integral_v<T>, "Factorial requires integral type");
        if (n < 0) return T{};
        if (n <= 1) return T{1};
        return n * factorial(n - 1);
    }

    // Template for container statistics
    template<typename Container>
    class Statistics {
    public:
        using ValueType = typename Container::value_type;

        static ValueType sum(const Container& data) {
            return std::accumulate(data.begin(), data.end(), ValueType{});
        }

        static std::optional<ValueType> mean(const Container& data) {
            if (data.empty()) return std::nullopt;
            return static_cast<ValueType>(sum(data)) / data.size();
        }

        static std::optional<ValueType> median(Container data) {
            if (data.empty()) return std::nullopt;

            std::sort(data.begin(), data.end());
            size_t size = data.size();

            if (size % 2 == 0) {
                return (data[size/2 - 1] + data[size/2]) / 2;
            } else {
                return data[size/2];
            }
        }

        static std::optional<ValueType> mode(const Container& data) {
            if (data.empty()) return std::nullopt;

            std::map<ValueType, int> frequency;
            for (const auto& value : data) {
                frequency[value]++;
            }

            auto max_freq = std::max_element(frequency.begin(), frequency.end(),
                [](const auto& a, const auto& b) {
                    return a.second < b.second;
                });

            return max_freq->first;
        }
    };

    // Higher-order functions
    template<typename Container, typename UnaryOp>
    auto apply_operation(const Container& data, UnaryOp op) {
        std::vector<std::invoke_result_t<UnaryOp, typename Container::value_type>> result;
        result.reserve(data.size());

        std::transform(data.begin(), data.end(), std::back_inserter(result), op);
        return result;
    }

    template<typename Container, typename BinaryOp>
    auto reduce(const Container& data, BinaryOp op, typename Container::value_type init = {}) {
        return std::accumulate(data.begin(), data.end(), init, op);
    }

    // Function composition
    template<typename F1, typename F2>
    auto compose(F1 f1, F2 f2) {
        return [f1, f2](auto x) { return f1(f2(x)); };
    }

    // Predefined lambda functions
    namespace Lambdas {
        auto square = [](auto x) { return x * x; };
        auto cube = [](auto x) { return x * x * x; };
        auto double_val = [](auto x) { return x * 2; };
        auto add_one = [](auto x) { return x + 1; };

        auto is_even = [](auto x) { return x % 2 == 0; };
        auto is_prime = [](int n) {
            if (n < 2) return false;
            for (int i = 2; i * i <= n; ++i) {
                if (n % i == 0) return false;
            }
            return true;
        };
    }

    // Advanced mathematical operations
    class AdvancedMath {
    public:
        // Function that accepts various callable types
        template<typename Func>
        static double integrate(Func f, double a, double b, int n = 1000) {
            double h = (b - a) / n;
            double sum = 0.0;

            for (int i = 0; i < n; ++i) {
                double x = a + i * h;
                sum += f(x) * h;
            }

            return sum;
        }

        // Newton's method for finding roots
        template<typename Func, typename Derivative>
        static std::optional<double> findRoot(Func f, Derivative df, double initial_guess,
                                            double tolerance = 1e-6, int max_iterations = 100) {
            double x = initial_guess;

            for (int i = 0; i < max_iterations; ++i) {
                double fx = f(x);
                double dfx = df(x);

                if (std::abs(fx) < tolerance) {
                    return x;
                }

                if (std::abs(dfx) < tolerance) {
                    return std::nullopt; // Derivative too small
                }

                x = x - fx / dfx;
            }

            return std::nullopt; // Did not converge
        }
    };
}

int main() {
    using namespace MathLib;

    std::cout << "=== Mathematical Function Library Demo ===" << std::endl;

    // 1. Function overloading
    std::cout << "1. Function Overloading:" << std::endl;
    std::cout << "power(2, 8) = " << power(2, 8) << std::endl;
    std::cout << "power(2.5, 3.0) = " << power(2.5, 3.0) << std::endl;

    // 2. Template functions
    std::cout << "\n2. Template Functions:" << std::endl;
    std::cout << "factorial(5) = " << factorial(5) << std::endl;
    std::cout << "factorial(10L) = " << factorial(10L) << std::endl;

    // 3. Container statistics
    std::cout << "\n3. Container Statistics:" << std::endl;
    std::vector<double> data = {1.5, 2.3, 3.7, 2.3, 4.1, 1.9, 3.7, 2.8};

    if (auto mean_val = Statistics<std::vector<double>>::mean(data)) {
        std::cout << "Mean: " << *mean_val << std::endl;
    }

    if (auto median_val = Statistics<std::vector<double>>::median(data)) {
        std::cout << "Median: " << *median_val << std::endl;
    }

    // 4. Higher-order functions
    std::cout << "\n4. Higher-order Functions:" << std::endl;
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    auto squared = apply_operation(numbers, Lambdas::square);
    auto cubed = apply_operation(numbers, Lambdas::cube);

    std::cout << "Original: ";
    for (int n : numbers) std::cout << n << " ";
    std::cout << std::endl;

    std::cout << "Squared: ";
    for (auto n : squared) std::cout << n << " ";
    std::cout << std::endl;

    std::cout << "Cubed: ";
    for (auto n : cubed) std::cout << n << " ";
    std::cout << std::endl;

    // 5. Function composition
    std::cout << "\n5. Function Composition:" << std::endl;
    auto square_then_double = compose(Lambdas::double_val, Lambdas::square);
    std::cout << "square_then_double(5) = " << square_then_double(5) << std::endl;

    // 6. Reduction operations
    std::cout << "\n6. Reduction Operations:" << std::endl;
    auto sum = reduce(numbers, std::plus<int>());
    auto product = reduce(numbers, std::multiplies<int>(), 1);

    std::cout << "Sum: " << sum << std::endl;
    std::cout << "Product: " << product << std::endl;

    // 7. Advanced mathematical operations
    std::cout << "\n7. Advanced Operations:" << std::endl;

    // Integration of x^2 from 0 to 2
    auto f = [](double x) { return x * x; };
    double integral = AdvancedMath::integrate(f, 0.0, 2.0);
    std::cout << "∫₀² x² dx ≈ " << integral << " (exact: 8/3 = " << 8.0/3.0 << ")" << std::endl;

    // Find root of x^2 - 2 = 0 (should be √2)
    auto g = [](double x) { return x * x - 2.0; };
    auto dg = [](double x) { return 2.0 * x; };

    if (auto root = AdvancedMath::findRoot(g, dg, 1.0)) {
        std::cout << "Root of x² - 2 = 0: " << *root << " (√2 = " << std::sqrt(2) << ")" << std::endl;
    }

    return 0;
}
```

**Explanation:**
- Comprehensive demonstration of function overloading with different types
- Template functions with type constraints and static assertions
- Generic container operations using templates
- Higher-order functions that accept other functions as parameters
- Function composition and lambda usage
- Advanced mathematical operations using numerical methods
- Proper error handling with std::optional
- Modern C++ features like auto return type deduction

</details>

[Back to top](#-c-documentation)

---

## 🏗️ Object-Oriented Programming

**📊 Chapter 6 of 14**

🎯 **Learning Objectives:**
- Master class and object creation and manipulation
- Understand constructors, destructors, and object lifecycle
- Learn inheritance hierarchies and virtual functions
- Explore polymorphism and dynamic binding
- Implement proper encapsulation and access control

⏱️ **Estimated Reading Time:** 35 minutes

📋 **Prerequisites:** Understanding of functions and basic C++ syntax

### Classes and Objects

#### Basic Class Structure

```cpp
#include <iostream>
#include <string>

class Person {
private:
    std::string name;
    int age;

public:
    // Constructor
    Person(const std::string& n, int a) : name(n), age(a) {
        std::cout << "Person constructor called for " << name << std::endl;
    }

    // Destructor
    ~Person() {
        std::cout << "Person destructor called for " << name << std::endl;
    }

    // Member functions (methods)
    void introduce() const {
        std::cout << "Hi, I'm " << name << " and I'm " << age << " years old." << std::endl;
    }

    // Getters (accessors)
    std::string getName() const { return name; }
    int getAge() const { return age; }

    // Setters (mutators)
    void setName(const std::string& n) { name = n; }
    void setAge(int a) {
        if (a >= 0) {
            age = a;
        }
    }

    // Static members
    static int population;

    static int getPopulation() {
        return population;
    }

    static void displayInfo() {
        std::cout << "This is the Person class with " << population << " instances." << std::endl;
    }
};

// Static member definition (must be outside class)
int Person::population = 0;

int main() {
    std::cout << "=== Basic Class and Object Demo ===" << std::endl;

    // Creating objects
    Person alice("Alice", 25);
    Person bob("Bob", 30);

    // Using member functions
    alice.introduce();
    bob.introduce();

    // Using getters and setters
    std::cout << alice.getName() << " is " << alice.getAge() << " years old." << std::endl;
    alice.setAge(26);
    std::cout << "After birthday: " << alice.getName() << " is " << alice.getAge() << " years old." << std::endl;

    // Static members
    Person::displayInfo();

    return 0;
}
```

### Constructors and Destructors

#### Constructor Types and Usage

```cpp
#include <iostream>
#include <string>
#include <vector>

class BankAccount {
private:
    std::string accountNumber;
    std::string ownerName;
    double balance;

public:
    // Default constructor
    BankAccount() : accountNumber("000000"), ownerName("Unknown"), balance(0.0) {
        std::cout << "Default constructor called" << std::endl;
    }

    // Parameterized constructor
    BankAccount(const std::string& accNum, const std::string& name, double initialBalance = 0.0)
        : accountNumber(accNum), ownerName(name), balance(initialBalance) {
        std::cout << "Parameterized constructor called for " << ownerName << std::endl;
    }

    // Copy constructor
    BankAccount(const BankAccount& other)
        : accountNumber(other.accountNumber + "_COPY"),
          ownerName(other.ownerName),
          balance(other.balance) {
        std::cout << "Copy constructor called for " << ownerName << std::endl;
    }

    // Move constructor (C++11)
    BankAccount(BankAccount&& other) noexcept
        : accountNumber(std::move(other.accountNumber)),
          ownerName(std::move(other.ownerName)),
          balance(other.balance) {
        other.balance = 0.0;
        std::cout << "Move constructor called for " << ownerName << std::endl;
    }

    // Copy assignment operator
    BankAccount& operator=(const BankAccount& other) {
        if (this != &other) {
            accountNumber = other.accountNumber + "_ASSIGNED";
            ownerName = other.ownerName;
            balance = other.balance;
            std::cout << "Copy assignment operator called for " << ownerName << std::endl;
        }
        return *this;
    }

    // Move assignment operator (C++11)
    BankAccount& operator=(BankAccount&& other) noexcept {
        if (this != &other) {
            accountNumber = std::move(other.accountNumber);
            ownerName = std::move(other.ownerName);
            balance = other.balance;
            other.balance = 0.0;
            std::cout << "Move assignment operator called for " << ownerName << std::endl;
        }
        return *this;
    }

    // Destructor
    ~BankAccount() {
        std::cout << "Destructor called for " << ownerName << " (Account: " << accountNumber << ")" << std::endl;
    }

    // Member functions
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            std::cout << ownerName << " deposited $" << amount << ". New balance: $" << balance << std::endl;
        }
    }

    bool withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            std::cout << ownerName << " withdrew $" << amount << ". New balance: $" << balance << std::endl;
            return true;
        }
        std::cout << "Insufficient funds for withdrawal of $" << amount << std::endl;
        return false;
    }

    void displayInfo() const {
        std::cout << "Account: " << accountNumber << ", Owner: " << ownerName
                  << ", Balance: $" << balance << std::endl;
    }

    // Getters
    double getBalance() const { return balance; }
    std::string getOwnerName() const { return ownerName; }
    std::string getAccountNumber() const { return accountNumber; }
};

int main() {
    std::cout << "=== Constructor and Destructor Demo ===" << std::endl;

    // Default constructor
    BankAccount account1;
    account1.displayInfo();

    // Parameterized constructor
    BankAccount account2("12345", "Alice Johnson", 1000.0);
    account2.displayInfo();

    // Copy constructor
    BankAccount account3 = account2;  // Copy constructor
    account3.displayInfo();

    // Copy assignment
    BankAccount account4;
    account4 = account2;  // Copy assignment operator
    account4.displayInfo();

    // Demonstrate operations
    account2.deposit(500.0);
    account2.withdraw(200.0);
    account2.displayInfo();

    // Move constructor example
    std::vector<BankAccount> accounts;
    accounts.push_back(BankAccount("67890", "Bob Smith", 2000.0));  // Move constructor called

    return 0;
}
```

### Inheritance

#### Basic Inheritance

```cpp
#include <iostream>
#include <string>
#include <memory>

// Base class
class Animal {
protected:
    std::string name;
    int age;

public:
    Animal(const std::string& n, int a) : name(n), age(a) {
        std::cout << "Animal constructor: " << name << std::endl;
    }

    virtual ~Animal() {  // Virtual destructor for proper cleanup
        std::cout << "Animal destructor: " << name << std::endl;
    }

    // Virtual functions for polymorphism
    virtual void makeSound() const {
        std::cout << name << " makes a generic animal sound" << std::endl;
    }

    virtual void move() const {
        std::cout << name << " moves around" << std::endl;
    }

    // Non-virtual function
    void sleep() const {
        std::cout << name << " is sleeping" << std::endl;
    }

    // Pure virtual function makes this an abstract class
    virtual void displayInfo() const = 0;

    // Getters
    std::string getName() const { return name; }
    int getAge() const { return age; }
};

// Derived class 1
class Dog : public Animal {
private:
    std::string breed;

public:
    Dog(const std::string& n, int a, const std::string& b)
        : Animal(n, a), breed(b) {
        std::cout << "Dog constructor: " << name << " (" << breed << ")" << std::endl;
    }

    ~Dog() override {
        std::cout << "Dog destructor: " << name << std::endl;
    }

    // Override virtual functions
    void makeSound() const override {
        std::cout << name << " barks: Woof! Woof!" << std::endl;
    }

    void move() const override {
        std::cout << name << " runs on four legs" << std::endl;
    }

    void displayInfo() const override {
        std::cout << "Dog - Name: " << name << ", Age: " << age
                  << ", Breed: " << breed << std::endl;
    }

    // Dog-specific function
    void fetch() const {
        std::cout << name << " fetches the ball!" << std::endl;
    }

    std::string getBreed() const { return breed; }
};

// Derived class 2
class Bird : public Animal {
private:
    double wingspan;
    bool canFly;

public:
    Bird(const std::string& n, int a, double ws, bool fly)
        : Animal(n, a), wingspan(ws), canFly(fly) {
        std::cout << "Bird constructor: " << name << std::endl;
    }

    ~Bird() override {
        std::cout << "Bird destructor: " << name << std::endl;
    }

    void makeSound() const override {
        std::cout << name << " chirps: Tweet! Tweet!" << std::endl;
    }

    void move() const override {
        if (canFly) {
            std::cout << name << " flies through the air" << std::endl;
        } else {
            std::cout << name << " hops on the ground" << std::endl;
        }
    }

    void displayInfo() const override {
        std::cout << "Bird - Name: " << name << ", Age: " << age
                  << ", Wingspan: " << wingspan << "cm, Can fly: "
                  << (canFly ? "Yes" : "No") << std::endl;
    }

    // Bird-specific function
    void fly() const {
        if (canFly) {
            std::cout << name << " soars through the sky!" << std::endl;
        } else {
            std::cout << name << " cannot fly" << std::endl;
        }
    }

    double getWingspan() const { return wingspan; }
    bool getCanFly() const { return canFly; }
};

// Multiple inheritance example
class Pet {
protected:
    std::string ownerName;

public:
    Pet(const std::string& owner) : ownerName(owner) {
        std::cout << "Pet constructor: Owner is " << owner << std::endl;
    }

    virtual ~Pet() {
        std::cout << "Pet destructor" << std::endl;
    }

    virtual void playWithOwner() const {
        std::cout << "Playing with owner " << ownerName << std::endl;
    }

    std::string getOwner() const { return ownerName; }
};

// Multiple inheritance
class PetDog : public Dog, public Pet {
public:
    PetDog(const std::string& n, int a, const std::string& b, const std::string& owner)
        : Dog(n, a, b), Pet(owner) {
        std::cout << "PetDog constructor: " << name << std::endl;
    }

    ~PetDog() override {
        std::cout << "PetDog destructor: " << name << std::endl;
    }

    void playWithOwner() const override {
        std::cout << name << " plays fetch with " << ownerName << std::endl;
    }

    // Override to show pet information too
    void displayInfo() const override {
        Dog::displayInfo();
        std::cout << "Owner: " << ownerName << std::endl;
    }
};

int main() {
    std::cout << "=== Inheritance Demo ===" << std::endl;

    // Cannot instantiate abstract Animal class
    // Animal animal("Generic", 5);  // Error!

    Dog dog("Buddy", 3, "Golden Retriever");
    dog.displayInfo();
    dog.makeSound();
    dog.move();
    dog.fetch();
    dog.sleep();  // Inherited from Animal

    std::cout << std::endl;

    Bird bird("Tweety", 2, 15.5, true);
    bird.displayInfo();
    bird.makeSound();
    bird.move();
    bird.fly();
    bird.sleep();  // Inherited from Animal

    std::cout << std::endl;

    // Multiple inheritance
    PetDog petDog("Max", 4, "Labrador", "John Smith");
    petDog.displayInfo();
    petDog.makeSound();
    petDog.playWithOwner();

    return 0;
}
```

### Polymorphism

#### Dynamic Polymorphism with Virtual Functions

```cpp
#include <iostream>
#include <vector>
#include <memory>

// Abstract base class for shapes
class Shape {
public:
    virtual ~Shape() = default;

    // Pure virtual functions
    virtual double area() const = 0;
    virtual double perimeter() const = 0;
    virtual void draw() const = 0;

    // Virtual function with implementation
    virtual void displayInfo() const {
        std::cout << "Area: " << area() << ", Perimeter: " << perimeter() << std::endl;
    }
};

class Circle : public Shape {
private:
    double radius;
    static inline const double PI = 3.14159265359;

public:
    Circle(double r) : radius(r) {}

    double area() const override {
        return PI * radius * radius;
    }

    double perimeter() const override {
        return 2 * PI * radius;
    }

    void draw() const override {
        std::cout << "Drawing a circle with radius " << radius << std::endl;
    }

    void displayInfo() const override {
        std::cout << "Circle - Radius: " << radius << ", ";
        Shape::displayInfo();
    }
};

class Rectangle : public Shape {
private:
    double width, height;

public:
    Rectangle(double w, double h) : width(w), height(h) {}

    double area() const override {
        return width * height;
    }

    double perimeter() const override {
        return 2 * (width + height);
    }

    void draw() const override {
        std::cout << "Drawing a rectangle " << width << "x" << height << std::endl;
    }

    void displayInfo() const override {
        std::cout << "Rectangle - Width: " << width << ", Height: " << height << ", ";
        Shape::displayInfo();
    }
};

class Triangle : public Shape {
private:
    double side1, side2, side3;

public:
    Triangle(double s1, double s2, double s3) : side1(s1), side2(s2), side3(s3) {}

    double area() const override {
        // Using Heron's formula
        double s = (side1 + side2 + side3) / 2;
        return std::sqrt(s * (s - side1) * (s - side2) * (s - side3));
    }

    double perimeter() const override {
        return side1 + side2 + side3;
    }

    void draw() const override {
        std::cout << "Drawing a triangle with sides " << side1 << ", " << side2 << ", " << side3 << std::endl;
    }

    void displayInfo() const override {
        std::cout << "Triangle - Sides: " << side1 << ", " << side2 << ", " << side3 << ", ";
        Shape::displayInfo();
    }
};

// Function that works with any shape (polymorphism)
void processShape(const Shape& shape) {
    shape.draw();
    shape.displayInfo();
    std::cout << std::endl;
}

// Factory pattern using polymorphism
class ShapeFactory {
public:
    enum class ShapeType { CIRCLE, RECTANGLE, TRIANGLE };

    static std::unique_ptr<Shape> createShape(ShapeType type) {
        switch (type) {
            case ShapeType::CIRCLE:
                return std::make_unique<Circle>(5.0);
            case ShapeType::RECTANGLE:
                return std::make_unique<Rectangle>(4.0, 6.0);
            case ShapeType::TRIANGLE:
                return std::make_unique<Triangle>(3.0, 4.0, 5.0);
        }
        return nullptr;
    }
};

int main() {
    std::cout << "=== Polymorphism Demo ===" << std::endl;

    // Create shapes
    std::vector<std::unique_ptr<Shape>> shapes;
    shapes.push_back(std::make_unique<Circle>(3.0));
    shapes.push_back(std::make_unique<Rectangle>(4.0, 5.0));
    shapes.push_back(std::make_unique<Triangle>(3.0, 4.0, 5.0));

    // Polymorphic behavior - same interface, different implementations
    std::cout << "Processing shapes polymorphically:" << std::endl;
    for (const auto& shape : shapes) {
        processShape(*shape);
    }

    // Calculate total area
    double totalArea = 0.0;
    for (const auto& shape : shapes) {
        totalArea += shape->area();
    }
    std::cout << "Total area of all shapes: " << totalArea << std::endl;

    // Using factory pattern
    std::cout << "\nUsing Shape Factory:" << std::endl;
    auto factoryCircle = ShapeFactory::createShape(ShapeFactory::ShapeType::CIRCLE);
    auto factoryRect = ShapeFactory::createShape(ShapeFactory::ShapeType::RECTANGLE);

    processShape(*factoryCircle);
    processShape(*factoryRect);

    return 0;
}
```

### Encapsulation

#### Advanced Encapsulation Techniques

```cpp
#include <iostream>
#include <string>
#include <stdexcept>
#include <vector>

class Temperature {
private:
    double celsius;

    // Private helper function
    bool isValidTemperature(double temp) const {
        return temp >= -273.15; // Absolute zero in Celsius
    }

public:
    // Constructor with validation
    explicit Temperature(double temp = 0.0) {
        if (!isValidTemperature(temp)) {
            throw std::invalid_argument("Temperature cannot be below absolute zero");
        }
        celsius = temp;
    }

    // Property-like accessors with validation
    double getCelsius() const { return celsius; }

    void setCelsius(double temp) {
        if (!isValidTemperature(temp)) {
            throw std::invalid_argument("Temperature cannot be below absolute zero");
        }
        celsius = temp;
    }

    double getFahrenheit() const {
        return (celsius * 9.0 / 5.0) + 32.0;
    }

    void setFahrenheit(double temp) {
        double celsiusEquivalent = (temp - 32.0) * 5.0 / 9.0;
        setCelsius(celsiusEquivalent);
    }

    double getKelvin() const {
        return celsius + 273.15;
    }

    void setKelvin(double temp) {
        if (temp < 0) {
            throw std::invalid_argument("Kelvin temperature cannot be negative");
        }
        setCelsius(temp - 273.15);
    }

    // Comparison operators
    bool operator==(const Temperature& other) const {
        return std::abs(celsius - other.celsius) < 0.01; // Account for floating-point precision
    }

    bool operator<(const Temperature& other) const {
        return celsius < other.celsius;
    }

    bool operator>(const Temperature& other) const {
        return celsius > other.celsius;
    }

    // Output operator
    friend std::ostream& operator<<(std::ostream& os, const Temperature& temp) {
        os << temp.celsius << "°C (" << temp.getFahrenheit() << "°F, " << temp.getKelvin() << "K)";
        return os;
    }
};

// Example of a class with different access levels
class BankAccountSecure {
private:
    std::string accountNumber;
    double balance;
    std::vector<std::string> transactionHistory;

    // Private methods for internal operations
    void addTransaction(const std::string& transaction) {
        transactionHistory.push_back(transaction);
        if (transactionHistory.size() > 100) {
            transactionHistory.erase(transactionHistory.begin());
        }
    }

    bool validateAmount(double amount) const {
        return amount > 0;
    }

protected:
    // Protected members accessible by derived classes
    std::string ownerName;

    void logOperation(const std::string& operation) {
        std::cout << "[LOG] " << operation << " for account " << accountNumber << std::endl;
    }

public:
    BankAccountSecure(const std::string& accNum, const std::string& name, double initialBalance = 0.0)
        : accountNumber(accNum), balance(initialBalance), ownerName(name) {
        if (initialBalance < 0) {
            throw std::invalid_argument("Initial balance cannot be negative");
        }
        addTransaction("Account opened with balance: $" + std::to_string(initialBalance));
        logOperation("Account created");
    }

    // Public interface
    bool deposit(double amount) {
        if (!validateAmount(amount)) {
            return false;
        }

        balance += amount;
        addTransaction("Deposit: +$" + std::to_string(amount) + " | Balance: $" + std::to_string(balance));
        logOperation("Deposit of $" + std::to_string(amount));
        return true;
    }

    bool withdraw(double amount) {
        if (!validateAmount(amount) || amount > balance) {
            return false;
        }

        balance -= amount;
        addTransaction("Withdrawal: -$" + std::to_string(amount) + " | Balance: $" + std::to_string(balance));
        logOperation("Withdrawal of $" + std::to_string(amount));
        return true;
    }

    // Read-only access to private data
    double getBalance() const { return balance; }
    std::string getAccountNumber() const { return accountNumber; }
    std::string getOwnerName() const { return ownerName; }

    // Controlled access to transaction history
    std::vector<std::string> getRecentTransactions(int count = 5) const {
        std::vector<std::string> recent;
        int start = std::max(0, static_cast<int>(transactionHistory.size()) - count);
        for (int i = start; i < transactionHistory.size(); ++i) {
            recent.push_back(transactionHistory[i]);
        }
        return recent;
    }

    void displayAccountInfo() const {
        std::cout << "Account: " << accountNumber << std::endl;
        std::cout << "Owner: " << ownerName << std::endl;
        std::cout << "Balance: $" << balance << std::endl;

        auto recent = getRecentTransactions(3);
        std::cout << "Recent transactions:" << std::endl;
        for (const auto& transaction : recent) {
            std::cout << "  " << transaction << std::endl;
        }
    }
};

// Derived class showing protected access
class SavingsAccount : public BankAccountSecure {
private:
    double interestRate;

public:
    SavingsAccount(const std::string& accNum, const std::string& name,
                  double initialBalance = 0.0, double rate = 0.02)
        : BankAccountSecure(accNum, name, initialBalance), interestRate(rate) {
        logOperation("Savings account created with " + std::to_string(rate * 100) + "% interest rate");
    }

    void addInterest() {
        double interest = getBalance() * interestRate;
        if (deposit(interest)) {
            logOperation("Interest added: $" + std::to_string(interest));
        }
    }

    double getInterestRate() const { return interestRate; }

    void setInterestRate(double rate) {
        if (rate >= 0 && rate <= 0.1) { // 0-10% interest rate
            interestRate = rate;
            logOperation("Interest rate changed to " + std::to_string(rate * 100) + "%");
        }
    }
};

int main() {
    std::cout << "=== Encapsulation Demo ===" << std::endl;

    // Temperature class demonstrating encapsulation
    try {
        Temperature room(22.0);
        std::cout << "Room temperature: " << room << std::endl;

        room.setFahrenheit(86.0); // 30°C
        std::cout << "After setting to 86°F: " << room << std::endl;

        room.setKelvin(300.0); // ~26.85°C
        std::cout << "After setting to 300K: " << room << std::endl;

        // This will throw an exception
        // Temperature invalid(-300.0);

    } catch (const std::exception& e) {
        std::cout << "Temperature error: " << e.what() << std::endl;
    }

    std::cout << std::endl;

    // Bank account demonstrating access control
    try {
        BankAccountSecure account("123456", "Alice Johnson", 1000.0);
        account.displayAccountInfo();

        std::cout << std::endl;

        account.deposit(250.0);
        account.withdraw(100.0);
        account.displayAccountInfo();

        std::cout << std::endl;

        // Savings account demonstrating inheritance with encapsulation
        SavingsAccount savings("789012", "Bob Smith", 5000.0, 0.03);
        savings.displayAccountInfo();

        std::cout << "\nAdding interest..." << std::endl;
        savings.addInterest();
        savings.displayAccountInfo();

    } catch (const std::exception& e) {
        std::cout << "Bank account error: " << e.what() << std::endl;
    }

    return 0;
}
```

### 💡 Code Examples

**Example 1: Complete OOP System - Library Management**

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <memory>
#include <algorithm>
#include <chrono>
#include <iomanip>

// Abstract base class for library items
class LibraryItem {
protected:
    std::string id;
    std::string title;
    std::string author;
    bool isCheckedOut;
    std::chrono::system_clock::time_point checkedOutDate;

public:
    LibraryItem(const std::string& itemId, const std::string& itemTitle, const std::string& itemAuthor)
        : id(itemId), title(itemTitle), author(itemAuthor), isCheckedOut(false) {}

    virtual ~LibraryItem() = default;

    // Pure virtual functions
    virtual void displayInfo() const = 0;
    virtual int getMaxCheckoutDays() const = 0;
    virtual double getLateFee() const = 0;

    // Common interface
    bool checkOut() {
        if (!isCheckedOut) {
            isCheckedOut = true;
            checkedOutDate = std::chrono::system_clock::now();
            return true;
        }
        return false;
    }

    bool checkIn() {
        if (isCheckedOut) {
            isCheckedOut = false;
            return true;
        }
        return false;
    }

    bool isOverdue() const {
        if (!isCheckedOut) return false;

        auto now = std::chrono::system_clock::now();
        auto daysDiff = std::chrono::duration_cast<std::chrono::hours>(now - checkedOutDate).count() / 24;
        return daysDiff > getMaxCheckoutDays();
    }

    double calculateLateFee() const {
        if (!isOverdue()) return 0.0;

        auto now = std::chrono::system_clock::now();
        auto daysDiff = std::chrono::duration_cast<std::chrono::hours>(now - checkedOutDate).count() / 24;
        int overdueDays = daysDiff - getMaxCheckoutDays();
        return overdueDays * getLateFee();
    }

    // Getters
    std::string getId() const { return id; }
    std::string getTitle() const { return title; }
    std::string getAuthor() const { return author; }
    bool getIsCheckedOut() const { return isCheckedOut; }
};

class Book : public LibraryItem {
private:
    std::string isbn;
    int pages;
    std::string genre;

public:
    Book(const std::string& id, const std::string& title, const std::string& author,
         const std::string& bookIsbn, int pageCount, const std::string& bookGenre)
        : LibraryItem(id, title, author), isbn(bookIsbn), pages(pageCount), genre(bookGenre) {}

    void displayInfo() const override {
        std::cout << "Book: " << title << " by " << author << std::endl;
        std::cout << "  ID: " << id << " | ISBN: " << isbn << " | Pages: " << pages
                  << " | Genre: " << genre << std::endl;
        std::cout << "  Status: " << (isCheckedOut ? "Checked Out" : "Available") << std::endl;
        if (isCheckedOut && isOverdue()) {
            std::cout << "  OVERDUE - Late fee: $" << std::fixed << std::setprecision(2)
                      << calculateLateFee() << std::endl;
        }
    }

    int getMaxCheckoutDays() const override { return 21; } // 3 weeks
    double getLateFee() const override { return 0.50; } // $0.50 per day

    std::string getIsbn() const { return isbn; }
    std::string getGenre() const { return genre; }
    int getPages() const { return pages; }
};

class DVD : public LibraryItem {
private:
    int duration; // in minutes
    std::string rating;
    std::string director;

public:
    DVD(const std::string& id, const std::string& title, const std::string& author,
        int movieDuration, const std::string& movieRating, const std::string& movieDirector)
        : LibraryItem(id, title, author), duration(movieDuration), rating(movieRating), director(movieDirector) {}

    void displayInfo() const override {
        std::cout << "DVD: " << title << " directed by " << director << std::endl;
        std::cout << "  ID: " << id << " | Duration: " << duration << " min | Rating: " << rating << std::endl;
        std::cout << "  Status: " << (isCheckedOut ? "Checked Out" : "Available") << std::endl;
        if (isCheckedOut && isOverdue()) {
            std::cout << "  OVERDUE - Late fee: $" << std::fixed << std::setprecision(2)
                      << calculateLateFee() << std::endl;
        }
    }

    int getMaxCheckoutDays() const override { return 7; } // 1 week
    double getLateFee() const override { return 1.00; } // $1.00 per day

    int getDuration() const { return duration; }
    std::string getRating() const { return rating; }
    std::string getDirector() const { return director; }
};

class Magazine : public LibraryItem {
private:
    std::string issueNumber;
    std::string publicationDate;

public:
    Magazine(const std::string& id, const std::string& title, const std::string& publisher,
             const std::string& issue, const std::string& pubDate)
        : LibraryItem(id, title, publisher), issueNumber(issue), publicationDate(pubDate) {}

    void displayInfo() const override {
        std::cout << "Magazine: " << title << " (Issue " << issueNumber << ")" << std::endl;
        std::cout << "  ID: " << id << " | Publisher: " << author << " | Date: " << publicationDate << std::endl;
        std::cout << "  Status: " << (isCheckedOut ? "Checked Out" : "Available") << std::endl;
        if (isCheckedOut && isOverdue()) {
            std::cout << "  OVERDUE - Late fee: $" << std::fixed << std::setprecision(2)
                      << calculateLateFee() << std::endl;
        }
    }

    int getMaxCheckoutDays() const override { return 3; } // 3 days
    double getLateFee() const override { return 0.25; } // $0.25 per day

    std::string getIssueNumber() const { return issueNumber; }
    std::string getPublicationDate() const { return publicationDate; }
};

class Library {
private:
    std::vector<std::unique_ptr<LibraryItem>> items;

public:
    void addItem(std::unique_ptr<LibraryItem> item) {
        items.push_back(std::move(item));
    }

    LibraryItem* findItem(const std::string& id) {
        auto it = std::find_if(items.begin(), items.end(),
            [&id](const std::unique_ptr<LibraryItem>& item) {
                return item->getId() == id;
            });
        return (it != items.end()) ? it->get() : nullptr;
    }

    bool checkOutItem(const std::string& id) {
        LibraryItem* item = findItem(id);
        return item ? item->checkOut() : false;
    }

    bool checkInItem(const std::string& id) {
        LibraryItem* item = findItem(id);
        return item ? item->checkIn() : false;
    }

    void displayAllItems() const {
        std::cout << "=== Library Inventory ===" << std::endl;
        for (const auto& item : items) {
            item->displayInfo();
            std::cout << std::endl;
        }
    }

    void displayOverdueItems() const {
        std::cout << "=== Overdue Items ===" << std::endl;
        bool hasOverdue = false;

        for (const auto& item : items) {
            if (item->isOverdue()) {
                item->displayInfo();
                std::cout << std::endl;
                hasOverdue = true;
            }
        }

        if (!hasOverdue) {
            std::cout << "No overdue items." << std::endl;
        }
    }

    double getTotalLateFees() const {
        double total = 0.0;
        for (const auto& item : items) {
            total += item->calculateLateFee();
        }
        return total;
    }
};

int main() {
    std::cout << "=== Library Management System ===" << std::endl;

    Library library;

    // Add items to library
    library.addItem(std::make_unique<Book>("B001", "The Great Gatsby", "F. Scott Fitzgerald",
                                           "978-0-7432-7356-5", 180, "Classic Fiction"));
    library.addItem(std::make_unique<Book>("B002", "1984", "George Orwell",
                                           "978-0-452-28423-4", 328, "Dystopian Fiction"));
    library.addItem(std::make_unique<DVD>("D001", "Inception", "Warner Bros",
                                          148, "PG-13", "Christopher Nolan"));
    library.addItem(std::make_unique<Magazine>("M001", "National Geographic", "National Geographic Society",
                                               "Vol. 240 No. 6", "December 2024"));

    // Display all items
    library.displayAllItems();

    // Check out some items
    std::cout << "Checking out items..." << std::endl;
    library.checkOutItem("B001");
    library.checkOutItem("D001");

    // Display updated inventory
    library.displayAllItems();

    // Check for overdue items
    library.displayOverdueItems();

    std::cout << "Total late fees: $" << std::fixed << std::setprecision(2)
              << library.getTotalLateFees() << std::endl;

    return 0;
}
```

**Explanation:**
- Complete object-oriented system demonstrating all OOP principles
- Abstract base class with pure virtual functions
- Multiple inheritance levels with different behaviors
- Encapsulation with proper access control
- Polymorphism through virtual function calls
- RAII principles with smart pointers
- STL integration with modern C++ features

</details>

### ⚠️ Common Pitfalls

1. **Object Slicing**: Assigning derived objects to base class variables by value
2. **Virtual Destructor**: Always make base class destructors virtual
3. **Diamond Problem**: Multiple inheritance can create ambiguous member access
4. **Memory Leaks**: Not using RAII or smart pointers properly
5. **Constructor Order**: Base class constructors called before derived class

### ✅ Best Practices

1. **RAII Principle**: Resource Acquisition Is Initialization
2. **Rule of Three/Five**: If you define one special function, define them all
3. **Virtual Functions**: Use virtual destructors in base classes
4. **Composition over Inheritance**: Prefer composition when relationship isn't "is-a"
5. **Interface Segregation**: Keep interfaces focused and minimal

### 🏋️ Exercises

#### 🏋️ Exercise 1: Vehicle Hierarchy
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 35 minutes

Create a comprehensive vehicle hierarchy with proper inheritance, polymorphism, and encapsulation.

<details>
<summary>💡 Click to see hints</summary>

- Create abstract Vehicle base class with pure virtual functions
- Implement Car, Motorcycle, and Truck derived classes
- Add proper constructors and destructors
- Use virtual functions for polymorphic behavior
- Include operator overloading where appropriate
- Demonstrate polymorphism with container of vehicles

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <memory>

class Vehicle {
protected:
    std::string make;
    std::string model;
    int year;
    double mileage;

public:
    Vehicle(const std::string& vehicleMake, const std::string& vehicleModel, int vehicleYear)
        : make(vehicleMake), model(vehicleModel), year(vehicleYear), mileage(0.0) {}

    virtual ~Vehicle() = default;

    // Pure virtual functions
    virtual void start() const = 0;
    virtual void stop() const = 0;
    virtual double getFuelEfficiency() const = 0;
    virtual std::string getType() const = 0;

    // Virtual functions with default implementation
    virtual void displayInfo() const {
        std::cout << year << " " << make << " " << model
                  << " (Mileage: " << mileage << " miles)" << std::endl;
    }

    // Common interface
    void drive(double miles) {
        if (miles > 0) {
            mileage += miles;
            std::cout << "Drove " << miles << " miles. Total mileage: " << mileage << std::endl;
        }
    }

    // Getters
    std::string getMake() const { return make; }
    std::string getModel() const { return model; }
    int getYear() const { return year; }
    double getMileage() const { return mileage; }
};

class Car : public Vehicle {
private:
    int doors;
    bool isElectric;

public:
    Car(const std::string& make, const std::string& model, int year, int numDoors, bool electric = false)
        : Vehicle(make, model, year), doors(numDoors), isElectric(electric) {}

    void start() const override {
        std::cout << "Car started - " << (isElectric ? "Electric motor humming" : "Engine running") << std::endl;
    }

    void stop() const override {
        std::cout << "Car stopped - " << (isElectric ? "Motor off" : "Engine off") << std::endl;
    }

    double getFuelEfficiency() const override {
        return isElectric ? 120.0 : 28.5; // MPGe for electric, MPG for gas
    }

    std::string getType() const override {
        return isElectric ? "Electric Car" : "Gas Car";
    }

    void displayInfo() const override {
        std::cout << getType() << " - ";
        Vehicle::displayInfo();
        std::cout << "  Doors: " << doors << ", Fuel Efficiency: "
                  << getFuelEfficiency() << (isElectric ? " MPGe" : " MPG") << std::endl;
    }

    void openTrunk() const {
        std::cout << "Trunk opened" << std::endl;
    }
};

class Motorcycle : public Vehicle {
private:
    bool hasSidecar;
    int engineSize; // in cc

public:
    Motorcycle(const std::string& make, const std::string& model, int year, int cc, bool sidecar = false)
        : Vehicle(make, model, year), hasSidecar(sidecar), engineSize(cc) {}

    void start() const override {
        std::cout << "Motorcycle started - Engine roaring (" << engineSize << "cc)" << std::endl;
    }

    void stop() const override {
        std::cout << "Motorcycle stopped - Engine off" << std::endl;
    }

    double getFuelEfficiency() const override {
        return 45.0 - (engineSize / 100.0); // Larger engines less efficient
    }

    std::string getType() const override {
        return hasSidecar ? "Motorcycle with Sidecar" : "Motorcycle";
    }

    void displayInfo() const override {
        std::cout << getType() << " - ";
        Vehicle::displayInfo();
        std::cout << "  Engine: " << engineSize << "cc, Fuel Efficiency: "
                  << getFuelEfficiency() << " MPG" << std::endl;
    }

    void wheelie() const {
        if (!hasSidecar) {
            std::cout << "Performing wheelie!" << std::endl;
        } else {
            std::cout << "Cannot perform wheelie with sidecar" << std::endl;
        }
    }
};

class Truck : public Vehicle {
private:
    double cargoCapacity; // in tons
    bool isDiesel;

public:
    Truck(const std::string& make, const std::string& model, int year, double capacity, bool diesel = true)
        : Vehicle(make, model, year), cargoCapacity(capacity), isDiesel(diesel) {}

    void start() const override {
        std::cout << "Truck started - " << (isDiesel ? "Diesel engine rumbling" : "Gas engine running") << std::endl;
    }

    void stop() const override {
        std::cout << "Truck stopped - Engine off" << std::endl;
    }

    double getFuelEfficiency() const override {
        double baseMPG = isDiesel ? 12.0 : 10.0;
        return baseMPG - (cargoCapacity * 0.5); // Heavier trucks less efficient
    }

    std::string getType() const override {
        return isDiesel ? "Diesel Truck" : "Gas Truck";
    }

    void displayInfo() const override {
        std::cout << getType() << " - ";
        Vehicle::displayInfo();
        std::cout << "  Cargo Capacity: " << cargoCapacity << " tons, Fuel Efficiency: "
                  << getFuelEfficiency() << " MPG" << std::endl;
    }

    void loadCargo(double tons) const {
        if (tons <= cargoCapacity) {
            std::cout << "Loaded " << tons << " tons of cargo" << std::endl;
        } else {
            std::cout << "Cannot load " << tons << " tons - exceeds capacity of "
                      << cargoCapacity << " tons" << std::endl;
        }
    }
};

class VehicleFleet {
private:
    std::vector<std::unique_ptr<Vehicle>> vehicles;

public:
    void addVehicle(std::unique_ptr<Vehicle> vehicle) {
        vehicles.push_back(std::move(vehicle));
    }

    void displayFleet() const {
        std::cout << "=== Vehicle Fleet ===" << std::endl;
        for (const auto& vehicle : vehicles) {
            vehicle->displayInfo();
            std::cout << std::endl;
        }
    }

    void startAllVehicles() const {
        std::cout << "Starting all vehicles:" << std::endl;
        for (const auto& vehicle : vehicles) {
            vehicle->start();
        }
        std::cout << std::endl;
    }

    void stopAllVehicles() const {
        std::cout << "Stopping all vehicles:" << std::endl;
        for (const auto& vehicle : vehicles) {
            vehicle->stop();
        }
        std::cout << std::endl;
    }

    double getAverageFuelEfficiency() const {
        if (vehicles.empty()) return 0.0;

        double total = 0.0;
        for (const auto& vehicle : vehicles) {
            total += vehicle->getFuelEfficiency();
        }
        return total / vehicles.size();
    }

    void driveAllVehicles(double miles) {
        std::cout << "Driving all vehicles " << miles << " miles:" << std::endl;
        for (const auto& vehicle : vehicles) {
            std::cout << vehicle->getType() << ": ";
            vehicle->drive(miles);
        }
        std::cout << std::endl;
    }
};

int main() {
    VehicleFleet fleet;

    // Add different types of vehicles
    fleet.addVehicle(std::make_unique<Car>("Toyota", "Prius", 2023, 4, true));
    fleet.addVehicle(std::make_unique<Car>("Honda", "Civic", 2022, 4, false));
    fleet.addVehicle(std::make_unique<Motorcycle>("Harley-Davidson", "Street Glide", 2023, 1868, false));
    fleet.addVehicle(std::make_unique<Truck>("Ford", "F-150", 2023, 2.5, false));

    // Display fleet information
    fleet.displayFleet();

    // Polymorphic operations
    fleet.startAllVehicles();
    fleet.driveAllVehicles(100);
    fleet.stopAllVehicles();

    std::cout << "Fleet average fuel efficiency: "
              << fleet.getAverageFuelEfficiency() << " MPG" << std::endl;

    return 0;
}
```

**Explanation:**
- Abstract Vehicle base class defines common interface
- Derived classes implement specific behaviors
- Proper use of virtual functions for polymorphism
- Encapsulation with protected and private members
- Fleet management demonstrating polymorphic operations
- Real-world functionality with meaningful methods

</details>

[Back to top](#-c-documentation)

---

## 🧠 Memory Management

**📊 Chapter 7 of 14**

🎯 **Learning Objectives:**
- Understand stack vs heap memory allocation
- Master pointers and references in C++
- Learn smart pointer usage and RAII principles
- Explore memory management best practices and common pitfalls

⏱️ **Estimated Reading Time:** 30 minutes

📋 **Prerequisites:** Understanding of basic C++ syntax and object-oriented programming

### Stack vs Heap

#### Understanding Memory Layout

```cpp
#include <iostream>
#include <string>

void demonstrateStackAllocation() {
    std::cout << "=== Stack Allocation ===" << std::endl;

    // Stack variables - automatically managed
    int localInt = 42;
    double localDouble = 3.14159;
    std::string localString = "Hello, Stack!";

    // Arrays on stack
    int localArray[100];

    std::cout << "Stack variables addresses:" << std::endl;
    std::cout << "localInt address: " << &localInt << std::endl;
    std::cout << "localDouble address: " << &localDouble << std::endl;
    std::cout << "localString address: " << &localString << std::endl;
    std::cout << "localArray address: " << &localArray << std::endl;

    // Variables automatically destroyed when leaving scope
}

void demonstrateHeapAllocation() {
    std::cout << "\n=== Heap Allocation ===" << std::endl;

    // Dynamic allocation on heap
    int* heapInt = new int(42);
    double* heapDouble = new double(3.14159);
    std::string* heapString = new std::string("Hello, Heap!");

    // Dynamic arrays
    int* heapArray = new int[100];

    std::cout << "Heap variables addresses:" << std::endl;
    std::cout << "heapInt address: " << heapInt << ", value: " << *heapInt << std::endl;
    std::cout << "heapDouble address: " << heapDouble << ", value: " << *heapDouble << std::endl;
    std::cout << "heapString address: " << heapString << ", value: " << *heapString << std::endl;
    std::cout << "heapArray address: " << heapArray << std::endl;

    // Manual cleanup required
    delete heapInt;
    delete heapDouble;
    delete heapString;
    delete[] heapArray;

    std::cout << "Heap memory manually freed" << std::endl;
}

class StackVsHeapDemo {
public:
    static void comparePerformance() {
        std::cout << "\n=== Performance Comparison ===" << std::endl;

        const int iterations = 1000000;

        // Stack allocation timing
        auto start = std::chrono::high_resolution_clock::now();
        for (int i = 0; i < iterations; ++i) {
            int stackVar = i;  // Stack allocation
            (void)stackVar;    // Suppress unused variable warning
        }
        auto end = std::chrono::high_resolution_clock::now();
        auto stackTime = std::chrono::duration_cast<std::chrono::microseconds>(end - start);

        // Heap allocation timing
        start = std::chrono::high_resolution_clock::now();
        for (int i = 0; i < iterations; ++i) {
            int* heapVar = new int(i);  // Heap allocation
            delete heapVar;             // Don't forget to delete!
        }
        end = std::chrono::high_resolution_clock::now();
        auto heapTime = std::chrono::duration_cast<std::chrono::microseconds>(end - start);

        std::cout << "Stack allocation time: " << stackTime.count() << " μs" << std::endl;
        std::cout << "Heap allocation time: " << heapTime.count() << " μs" << std::endl;
        std::cout << "Heap is " << (heapTime.count() / (double)stackTime.count())
                  << "x slower than stack" << std::endl;
    }
};

int main() {
    demonstrateStackAllocation();
    demonstrateHeapAllocation();
    StackVsHeapDemo::comparePerformance();

    return 0;
}
```

### Pointers and References

#### Understanding Pointers

```cpp
#include <iostream>

int main() {
    std::cout << "=== Pointer Basics ===" << std::endl;

    int value = 42;
    int* ptr = &value;  // Pointer to int

    std::cout << "Value: " << value << std::endl;
    std::cout << "Address of value: " << &value << std::endl;
    std::cout << "Pointer ptr: " << ptr << std::endl;
    std::cout << "Value pointed to by ptr: " << *ptr << std::endl;

    // Modifying through pointer
    *ptr = 100;
    std::cout << "After *ptr = 100, value is: " << value << std::endl;

    // Pointer arithmetic
    int array[] = {10, 20, 30, 40, 50};
    int* arrayPtr = array;

    std::cout << "\nPointer arithmetic:" << std::endl;
    for (int i = 0; i < 5; ++i) {
        std::cout << "arrayPtr[" << i << "] = " << *(arrayPtr + i) << std::endl;
    }

    // Null pointers
    int* nullPtr = nullptr;  // C++11 nullptr
    if (nullPtr == nullptr) {
        std::cout << "nullPtr is null" << std::endl;
    }

    return 0;
}
```

#### References vs Pointers

```cpp
#include <iostream>

void demonstrateReferences() {
    std::cout << "=== References vs Pointers ===" << std::endl;

    int original = 50;

    // Reference - alias to original
    int& ref = original;

    // Pointer - stores address
    int* ptr = &original;

    std::cout << "Original: " << original << std::endl;
    std::cout << "Reference: " << ref << std::endl;
    std::cout << "Pointer value: " << *ptr << std::endl;

    // Modifying through reference
    ref = 75;
    std::cout << "After ref = 75, original: " << original << std::endl;

    // Modifying through pointer
    *ptr = 100;
    std::cout << "After *ptr = 100, original: " << original << std::endl;

    // References cannot be reassigned, pointers can
    int another = 200;
    // ref = another;  // This assigns value, not reference!
    ptr = &another;    // This changes what ptr points to

    std::cout << "After ptr = &another:" << std::endl;
    std::cout << "Original: " << original << std::endl;
    std::cout << "Another: " << another << std::endl;
    std::cout << "Pointer now points to: " << *ptr << std::endl;
}

// Function parameter examples
void byValue(int x) {
    x = 999;  // Only modifies local copy
}

void byReference(int& x) {
    x = 999;  // Modifies original
}

void byPointer(int* x) {
    if (x) *x = 999;  // Modifies original if pointer is valid
}

int main() {
    demonstrateReferences();

    std::cout << "\n=== Function Parameter Passing ===" << std::endl;
    int value = 42;

    std::cout << "Original value: " << value << std::endl;

    byValue(value);
    std::cout << "After byValue: " << value << std::endl;

    byReference(value);
    std::cout << "After byReference: " << value << std::endl;

    value = 42;  // Reset
    byPointer(&value);
    std::cout << "After byPointer: " << value << std::endl;

    return 0;
}
```

### Smart Pointers

#### Modern Memory Management with Smart Pointers

```cpp
#include <iostream>
#include <memory>
#include <vector>
#include <string>

class Resource {
private:
    std::string name;

public:
    Resource(const std::string& n) : name(n) {
        std::cout << "Resource '" << name << "' created" << std::endl;
    }

    ~Resource() {
        std::cout << "Resource '" << name << "' destroyed" << std::endl;
    }

    void use() const {
        std::cout << "Using resource '" << name << "'" << std::endl;
    }

    std::string getName() const { return name; }
};

void demonstrateUniquePtr() {
    std::cout << "=== unique_ptr Demo ===" << std::endl;

    // Create unique_ptr
    std::unique_ptr<Resource> resource1 = std::make_unique<Resource>("Resource1");
    resource1->use();

    // Transfer ownership
    std::unique_ptr<Resource> resource2 = std::move(resource1);

    if (!resource1) {
        std::cout << "resource1 is now null" << std::endl;
    }

    resource2->use();

    // Automatic cleanup when leaving scope
    std::cout << "Leaving unique_ptr scope..." << std::endl;
}

void demonstrateSharedPtr() {
    std::cout << "\n=== shared_ptr Demo ===" << std::endl;

    std::shared_ptr<Resource> shared1 = std::make_shared<Resource>("SharedResource");
    std::cout << "Reference count: " << shared1.use_count() << std::endl;

    {
        std::shared_ptr<Resource> shared2 = shared1;  // Copy - increases ref count
        std::cout << "Reference count after copy: " << shared1.use_count() << std::endl;

        shared2->use();
    } // shared2 goes out of scope, decreases ref count

    std::cout << "Reference count after shared2 destroyed: " << shared1.use_count() << std::endl;

    std::cout << "Leaving shared_ptr scope..." << std::endl;
}

void demonstrateWeakPtr() {
    std::cout << "\n=== weak_ptr Demo ===" << std::endl;

    std::weak_ptr<Resource> weak;

    {
        std::shared_ptr<Resource> shared = std::make_shared<Resource>("WeakResource");
        weak = shared;  // weak_ptr doesn't increase reference count

        std::cout << "shared use_count: " << shared.use_count() << std::endl;
        std::cout << "weak expired: " << weak.expired() << std::endl;

        if (auto locked = weak.lock()) {  // Convert to shared_ptr if still valid
            locked->use();
        }
    } // shared goes out of scope and destroys the resource

    std::cout << "After shared destroyed, weak expired: " << weak.expired() << std::endl;
}

// Custom deleter example
void customDeleter(Resource* ptr) {
    std::cout << "Custom deleter called for " << ptr->getName() << std::endl;
    delete ptr;
}

void demonstrateCustomDeleter() {
    std::cout << "\n=== Custom Deleter Demo ===" << std::endl;

    std::unique_ptr<Resource, void(*)(Resource*)> resource(
        new Resource("CustomDeleted"), customDeleter);

    resource->use();

    std::cout << "Leaving custom deleter scope..." << std::endl;
}

int main() {
    demonstrateUniquePtr();
    demonstrateSharedPtr();
    demonstrateWeakPtr();
    demonstrateCustomDeleter();

    return 0;
}
```

### RAII Principle

#### Resource Acquisition Is Initialization

```cpp
#include <iostream>
#include <fstream>
#include <memory>
#include <vector>
#include <mutex>

// Example 1: File RAII wrapper
class FileManager {
private:
    std::fstream file;
    std::string filename;

public:
    FileManager(const std::string& fname, std::ios::openmode mode)
        : filename(fname) {
        file.open(filename, mode);
        if (!file.is_open()) {
            throw std::runtime_error("Failed to open file: " + filename);
        }
        std::cout << "File '" << filename << "' opened successfully" << std::endl;
    }

    ~FileManager() {
        if (file.is_open()) {
            file.close();
            std::cout << "File '" << filename << "' closed automatically" << std::endl;
        }
    }

    // Delete copy constructor and assignment to prevent issues
    FileManager(const FileManager&) = delete;
    FileManager& operator=(const FileManager&) = delete;

    // Move constructor and assignment
    FileManager(FileManager&& other) noexcept
        : file(std::move(other.file)), filename(std::move(other.filename)) {}

    FileManager& operator=(FileManager&& other) noexcept {
        if (this != &other) {
            if (file.is_open()) file.close();
            file = std::move(other.file);
            filename = std::move(other.filename);
        }
        return *this;
    }

    std::fstream& getFile() { return file; }
};

// Example 2: Memory Pool RAII
class MemoryPool {
private:
    std::vector<std::unique_ptr<char[]>> pools;
    size_t poolSize;

public:
    explicit MemoryPool(size_t size) : poolSize(size) {
        std::cout << "Memory pool created with size " << size << std::endl;
    }

    ~MemoryPool() {
        std::cout << "Memory pool destroyed, " << pools.size()
                  << " pools automatically freed" << std::endl;
    }

    char* allocate() {
        auto pool = std::make_unique<char[]>(poolSize);
        char* ptr = pool.get();
        pools.push_back(std::move(pool));
        return ptr;
    }

    size_t getPoolCount() const { return pools.size(); }
};

// Example 3: Lock Guard (similar to std::lock_guard)
class CustomLockGuard {
private:
    std::mutex& mtx;

public:
    explicit CustomLockGuard(std::mutex& m) : mtx(m) {
        mtx.lock();
        std::cout << "Mutex locked" << std::endl;
    }

    ~CustomLockGuard() {
        mtx.unlock();
        std::cout << "Mutex unlocked automatically" << std::endl;
    }

    // Non-copyable, non-movable
    CustomLockGuard(const CustomLockGuard&) = delete;
    CustomLockGuard& operator=(const CustomLockGuard&) = delete;
    CustomLockGuard(CustomLockGuard&&) = delete;
    CustomLockGuard& operator=(CustomLockGuard&&) = delete;
};

void demonstrateRAII() {
    std::cout << "=== RAII Demonstration ===" << std::endl;

    try {
        // File RAII
        {
            FileManager file("test.txt", std::ios::out);
            file.getFile() << "Hello, RAII!" << std::endl;
        } // File automatically closed here

        // Memory Pool RAII
        {
            MemoryPool pool(1024);
            char* mem1 = pool.allocate();
            char* mem2 = pool.allocate();
            std::cout << "Allocated " << pool.getPoolCount() << " memory pools" << std::endl;
        } // Memory automatically freed here

        // Mutex RAII
        std::mutex mtx;
        {
            CustomLockGuard lock(mtx);
            std::cout << "Critical section - mutex is locked" << std::endl;
            // Even if exception is thrown here, mutex will be unlocked
        } // Mutex automatically unlocked here

    } catch (const std::exception& e) {
        std::cout << "Exception caught: " << e.what() << std::endl;
        std::cout << "Resources still cleaned up properly due to RAII" << std::endl;
    }
}

int main() {
    demonstrateRAII();

    std::cout << "\n=== RAII Benefits ===" << std::endl;
    std::cout << "1. Automatic resource cleanup" << std::endl;
    std::cout << "2. Exception safety" << std::endl;
    std::cout << "3. No memory leaks" << std::endl;
    std::cout << "4. Clear ownership semantics" << std::endl;

    return 0;
}
```

### 💡 Code Examples

**Example 1: Advanced Memory Management System**

```cpp
#include <iostream>
#include <memory>
#include <vector>
#include <map>
#include <string>
#include <chrono>

// Object pool for efficient memory reuse
template<typename T>
class ObjectPool {
private:
    std::vector<std::unique_ptr<T>> available;
    std::vector<std::unique_ptr<T>> inUse;

public:
    template<typename... Args>
    std::shared_ptr<T> acquire(Args&&... args) {
        std::unique_ptr<T> obj;

        if (!available.empty()) {
            obj = std::move(available.back());
            available.pop_back();
            // Reset object state if needed
        } else {
            obj = std::make_unique<T>(std::forward<Args>(args)...);
        }

        T* rawPtr = obj.get();
        inUse.push_back(std::move(obj));

        // Return shared_ptr with custom deleter that returns to pool
        return std::shared_ptr<T>(rawPtr, [this](T* ptr) {
            this->release(ptr);
        });
    }

private:
    void release(T* ptr) {
        auto it = std::find_if(inUse.begin(), inUse.end(),
            [ptr](const std::unique_ptr<T>& obj) {
                return obj.get() == ptr;
            });

        if (it != inUse.end()) {
            available.push_back(std::move(*it));
            inUse.erase(it);
        }
    }

public:
    size_t availableCount() const { return available.size(); }
    size_t inUseCount() const { return inUse.size(); }
};

// Example class for pooling
class ExpensiveObject {
private:
    std::vector<int> data;
    std::string name;

public:
    ExpensiveObject(const std::string& n) : name(n), data(1000000) {
        std::cout << "Expensive object '" << name << "' created" << std::endl;
        // Simulate expensive initialization
        std::fill(data.begin(), data.end(), 42);
    }

    ~ExpensiveObject() {
        std::cout << "Expensive object '" << name << "' destroyed" << std::endl;
    }

    void use() const {
        std::cout << "Using expensive object '" << name << "'" << std::endl;
    }

    const std::string& getName() const { return name; }
};

int main() {
    std::cout << "=== Object Pool Demo ===" << std::endl;

    ObjectPool<ExpensiveObject> pool;

    // Acquire objects
    {
        auto obj1 = pool.acquire("Object1");
        auto obj2 = pool.acquire("Object2");

        obj1->use();
        obj2->use();

        std::cout << "Pool stats - Available: " << pool.availableCount()
                  << ", In use: " << pool.inUseCount() << std::endl;
    } // Objects returned to pool here

    std::cout << "After scope - Available: " << pool.availableCount()
              << ", In use: " << pool.inUseCount() << std::endl;

    // Reuse pooled objects
    {
        auto obj3 = pool.acquire("Object3");  // Reuses pooled object
        obj3->use();
    }

    return 0;
}
```

### ⚠️ Common Pitfalls

1. **Memory Leaks**: Forgetting to delete dynamically allocated memory
2. **Double Delete**: Deleting the same memory twice
3. **Use After Free**: Accessing deleted memory
4. **Dangling Pointers**: Pointers to deallocated memory
5. **Circular References**: shared_ptr cycles preventing cleanup

### ✅ Best Practices

1. **Prefer Stack Allocation**: Use stack when possible for better performance
2. **RAII Everywhere**: Use RAII for automatic resource management
3. **Smart Pointers**: Use smart pointers instead of raw pointers
4. **unique_ptr by Default**: Use unique_ptr unless sharing is needed
5. **Make Functions**: Use make_unique and make_shared

### 🏋️ Exercise: Memory Management System

**Difficulty:** 🔴 Advanced
**Estimated Time:** 45 minutes

Create a comprehensive memory management system with object pools, smart pointers, and RAII principles.

<details>
<summary>💡 Click to see hints</summary>

- Implement custom smart pointer class
- Create object pool for memory reuse
- Use RAII for automatic cleanup
- Include memory usage statistics
- Handle circular references properly

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <memory>
#include <vector>
#include <unordered_map>
#include <atomic>
#include <chrono>

class MemoryStats {
private:
    std::atomic<size_t> allocations{0};
    std::atomic<size_t> deallocations{0};
    std::atomic<size_t> currentAllocated{0};
    std::atomic<size_t> peakAllocated{0};

public:
    void recordAllocation(size_t bytes) {
        allocations.fetch_add(1);
        size_t current = currentAllocated.fetch_add(bytes) + bytes;

        // Update peak if necessary
        size_t peak = peakAllocated.load();
        while (current > peak && !peakAllocated.compare_exchange_weak(peak, current)) {
            // Keep trying until we successfully update or peak becomes larger
        }
    }

    void recordDeallocation(size_t bytes) {
        deallocations.fetch_add(1);
        currentAllocated.fetch_sub(bytes);
    }

    void printStats() const {
        std::cout << "Memory Statistics:" << std::endl;
        std::cout << "  Allocations: " << allocations.load() << std::endl;
        std::cout << "  Deallocations: " << deallocations.load() << std::endl;
        std::cout << "  Current allocated: " << currentAllocated.load() << " bytes" << std::endl;
        std::cout << "  Peak allocated: " << peakAllocated.load() << " bytes" << std::endl;
        std::cout << "  Active allocations: " << (allocations.load() - deallocations.load()) << std::endl;
    }
};

// Global memory statistics
MemoryStats g_memStats;

// Custom allocator that tracks memory usage
template<typename T>
class TrackedAllocator {
public:
    using value_type = T;

    T* allocate(std::size_t n) {
        size_t bytes = n * sizeof(T);
        T* ptr = static_cast<T*>(std::malloc(bytes));
        if (!ptr) {
            throw std::bad_alloc();
        }
        g_memStats.recordAllocation(bytes);
        return ptr;
    }

    void deallocate(T* ptr, std::size_t n) {
        size_t bytes = n * sizeof(T);
        g_memStats.recordDeallocation(bytes);
        std::free(ptr);
    }

    template<typename U>
    bool operator==(const TrackedAllocator<U>&) const { return true; }

    template<typename U>
    bool operator!=(const TrackedAllocator<U>&) const { return false; }
};

// Managed object base class
class ManagedObject {
protected:
    static std::atomic<size_t> nextId;
    size_t id;

public:
    ManagedObject() : id(nextId.fetch_add(1)) {
        std::cout << "ManagedObject " << id << " created" << std::endl;
    }

    virtual ~ManagedObject() {
        std::cout << "ManagedObject " << id << " destroyed" << std::endl;
    }

    size_t getId() const { return id; }
};

std::atomic<size_t> ManagedObject::nextId{1};

// Resource-intensive object for demonstration
class ResourceHeavyObject : public ManagedObject {
private:
    std::vector<int, TrackedAllocator<int>> data;
    std::string name;

public:
    ResourceHeavyObject(const std::string& n, size_t dataSize = 1000)
        : name(n), data(dataSize, 42) {
        std::cout << "ResourceHeavyObject '" << name << "' with "
                  << dataSize << " elements created" << std::endl;
    }

    ~ResourceHeavyObject() {
        std::cout << "ResourceHeavyObject '" << name << "' destroyed" << std::endl;
    }

    void process() const {
        std::cout << "Processing " << name << " (ID: " << getId() << ")" << std::endl;
        // Simulate processing
        volatile int sum = 0;
        for (size_t i = 0; i < std::min(data.size(), size_t(1000)); ++i) {
            sum += data[i];
        }
    }

    const std::string& getName() const { return name; }
    size_t getDataSize() const { return data.size(); }
};

// Advanced object pool with statistics
template<typename T>
class AdvancedObjectPool {
private:
    std::vector<std::unique_ptr<T>> available;
    std::unordered_map<T*, std::unique_ptr<T>> inUse;
    std::atomic<size_t> totalCreated{0};
    std::atomic<size_t> totalReused{0};

public:
    template<typename... Args>
    std::shared_ptr<T> acquire(Args&&... args) {
        std::unique_ptr<T> obj;

        if (!available.empty()) {
            obj = std::move(available.back());
            available.pop_back();
            totalReused.fetch_add(1);
        } else {
            obj = std::make_unique<T>(std::forward<Args>(args)...);
            totalCreated.fetch_add(1);
        }

        T* rawPtr = obj.get();
        inUse[rawPtr] = std::move(obj);

        return std::shared_ptr<T>(rawPtr, [this](T* ptr) {
            this->release(ptr);
        });
    }

private:
    void release(T* ptr) {
        auto it = inUse.find(ptr);
        if (it != inUse.end()) {
            available.push_back(std::move(it->second));
            inUse.erase(it);
        }
    }

public:
    void printStats() const {
        std::cout << "Object Pool Statistics:" << std::endl;
        std::cout << "  Total created: " << totalCreated.load() << std::endl;
        std::cout << "  Total reused: " << totalReused.load() << std::endl;
        std::cout << "  Available: " << available.size() << std::endl;
        std::cout << "  In use: " << inUse.size() << std::endl;
        std::cout << "  Reuse ratio: " <<
            (totalCreated.load() > 0 ?
             (double)totalReused.load() / totalCreated.load() * 100 : 0)
            << "%" << std::endl;
    }

    void cleanup() {
        available.clear();
        // inUse objects are managed by shared_ptr, will be cleaned up when references are gone
    }
};

// RAII wrapper for timing operations
class Timer {
private:
    std::chrono::high_resolution_clock::time_point start;
    std::string operation;

public:
    Timer(const std::string& op) : operation(op), start(std::chrono::high_resolution_clock::now()) {
        std::cout << "Starting " << operation << "..." << std::endl;
    }

    ~Timer() {
        auto end = std::chrono::high_resolution_clock::now();
        auto duration = std::chrono::duration_cast<std::chrono::milliseconds>(end - start);
        std::cout << operation << " completed in " << duration.count() << "ms" << std::endl;
    }
};

int main() {
    std::cout << "=== Advanced Memory Management System ===" << std::endl;

    AdvancedObjectPool<ResourceHeavyObject> pool;

    // Demonstrate pool usage with timing
    {
        Timer timer("Object pool demonstration");

        std::vector<std::shared_ptr<ResourceHeavyObject>> objects;

        // Create and use objects
        for (int i = 0; i < 5; ++i) {
            auto obj = pool.acquire("Object" + std::to_string(i), 10000);
            obj->process();
            objects.push_back(obj);
        }

        // Objects still in scope, using memory
        std::cout << "\nObjects in scope:" << std::endl;
        pool.printStats();
        g_memStats.printStats();

        // Clear some objects
        objects.erase(objects.begin(), objects.begin() + 3);

        std::cout << "\nAfter clearing 3 objects:" << std::endl;
        pool.printStats();

        // Reuse objects from pool
        for (int i = 0; i < 3; ++i) {
            auto obj = pool.acquire("Reused" + std::to_string(i), 5000);
            obj->process();
            objects.push_back(obj);
        }

        std::cout << "\nAfter reusing objects:" << std::endl;
        pool.printStats();

    } // All objects destroyed here due to RAII

    std::cout << "\nFinal statistics:" << std::endl;
    pool.printStats();
    g_memStats.printStats();

    // Cleanup pool
    pool.cleanup();

    std::cout << "\nAfter cleanup:" << std::endl;
    g_memStats.printStats();

    return 0;
}
```

**Explanation:**
- Thread-safe memory statistics tracking
- Custom allocator that monitors memory usage
- Advanced object pool with reuse statistics
- RAII timer for performance measurement
- Comprehensive memory management demonstration
- Proper cleanup and resource management
- Real-world applicable memory optimization techniques

</details>

[Back to top](#-c-documentation)

---

## 📦 Templates & Generic Programming

**📊 Chapter 8 of 14**

🎯 **Learning Objectives:**
- Master function and class template creation
- Understand template specialization and SFINAE
- Learn modern C++20 concepts and constraints
- Explore advanced template metaprogramming techniques

⏱️ **Estimated Reading Time:** 35 minutes

📋 **Prerequisites:** Strong understanding of functions, classes, and C++ syntax

### Function Templates

#### Basic Function Templates

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <type_traits>

// Simple function template
template<typename T>
T maximum(T a, T b) {
    return (a > b) ? a : b;
}

// Function template with multiple type parameters
template<typename T, typename U>
auto add(T a, U b) -> decltype(a + b) {
    return a + b;
}

// Function template with non-type parameter
template<typename T, size_t N>
constexpr size_t arraySize(T (&)[N]) {
    return N;
}

// Variadic function template (C++11)
template<typename... Args>
void print(Args... args) {
    ((std::cout << args << " "), ...);  // C++17 fold expression
    std::cout << std::endl;
}

// Template with default parameter
template<typename T = int, typename Compare = std::less<T>>
T findExtreme(const std::vector<T>& vec, Compare comp = Compare{}) {
    if (vec.empty()) {
        throw std::invalid_argument("Empty vector");
    }

    T result = vec[0];
    for (const auto& item : vec) {
        if (comp(result, item)) {
            result = item;
        }
    }
    return result;
}

int main() {
    std::cout << "=== Function Templates Demo ===" << std::endl;

    // Basic template usage
    std::cout << "max(5, 10) = " << maximum(5, 10) << std::endl;
    std::cout << "max(3.14, 2.71) = " << maximum(3.14, 2.71) << std::endl;
    std::cout << "max('a', 'z') = " << maximum('a', 'z') << std::endl;

    // Multiple type parameters
    std::cout << "add(5, 3.14) = " << add(5, 3.14) << std::endl;
    std::cout << "add(std::string(\"Hello \"), \"World\") = "
              << add(std::string("Hello "), "World") << std::endl;

    // Non-type parameters
    int arr[] = {1, 2, 3, 4, 5};
    std::cout << "Array size: " << arraySize(arr) << std::endl;

    // Variadic templates
    std::cout << "Printing multiple values: ";
    print(1, 2.5, "hello", 'c');

    // Template with defaults
    std::vector<int> numbers = {3, 7, 1, 9, 2, 8};
    std::cout << "Maximum: " << findExtreme(numbers) << std::endl;
    std::cout << "Minimum: " << findExtreme(numbers, std::greater<int>{}) << std::endl;

    return 0;
}
```

### Class Templates

#### Basic Class Templates

```cpp
#include <iostream>
#include <vector>
#include <memory>
#include <stdexcept>

// Simple class template
template<typename T>
class Stack {
private:
    std::vector<T> elements;

public:
    void push(const T& element) {
        elements.push_back(element);
    }

    void pop() {
        if (elements.empty()) {
            throw std::runtime_error("Stack is empty");
        }
        elements.pop_back();
    }

    const T& top() const {
        if (elements.empty()) {
            throw std::runtime_error("Stack is empty");
        }
        return elements.back();
    }

    bool empty() const {
        return elements.empty();
    }

    size_t size() const {
        return elements.size();
    }
};

// Class template with multiple parameters
template<typename Key, typename Value, typename Compare = std::less<Key>>
class SimpleBST {
private:
    struct Node {
        Key key;
        Value value;
        std::unique_ptr<Node> left;
        std::unique_ptr<Node> right;

        Node(const Key& k, const Value& v) : key(k), value(v) {}
    };

    std::unique_ptr<Node> root;
    Compare comp;

public:
    void insert(const Key& key, const Value& value) {
        root = insertHelper(std::move(root), key, value);
    }

    bool find(const Key& key, Value& value) const {
        return findHelper(root.get(), key, value);
    }

    void inorderTraversal() const {
        inorderHelper(root.get());
        std::cout << std::endl;
    }

private:
    std::unique_ptr<Node> insertHelper(std::unique_ptr<Node> node, const Key& key, const Value& value) {
        if (!node) {
            return std::make_unique<Node>(key, value);
        }

        if (comp(key, node->key)) {
            node->left = insertHelper(std::move(node->left), key, value);
        } else if (comp(node->key, key)) {
            node->right = insertHelper(std::move(node->right), key, value);
        } else {
            node->value = value; // Update existing key
        }

        return node;
    }

    bool findHelper(Node* node, const Key& key, Value& value) const {
        if (!node) return false;

        if (comp(key, node->key)) {
            return findHelper(node->left.get(), key, value);
        } else if (comp(node->key, key)) {
            return findHelper(node->right.get(), key, value);
        } else {
            value = node->value;
            return true;
        }
    }

    void inorderHelper(Node* node) const {
        if (node) {
            inorderHelper(node->left.get());
            std::cout << "(" << node->key << ", " << node->value << ") ";
            inorderHelper(node->right.get());
        }
    }
};

// Template with non-type parameters
template<typename T, size_t Size>
class FixedArray {
private:
    T data[Size];

public:
    constexpr size_t size() const { return Size; }

    T& operator[](size_t index) {
        if (index >= Size) {
            throw std::out_of_range("Index out of range");
        }
        return data[index];
    }

    const T& operator[](size_t index) const {
        if (index >= Size) {
            throw std::out_of_range("Index out of range");
        }
        return data[index];
    }

    T* begin() { return data; }
    T* end() { return data + Size; }
    const T* begin() const { return data; }
    const T* end() const { return data + Size; }
};

int main() {
    std::cout << "=== Class Templates Demo ===" << std::endl;

    // Stack template
    Stack<int> intStack;
    intStack.push(1);
    intStack.push(2);
    intStack.push(3);

    std::cout << "Stack contents (top to bottom): ";
    while (!intStack.empty()) {
        std::cout << intStack.top() << " ";
        intStack.pop();
    }
    std::cout << std::endl;

    // BST template
    SimpleBST<std::string, int> nameAges;
    nameAges.insert("Alice", 25);
    nameAges.insert("Bob", 30);
    nameAges.insert("Charlie", 35);
    nameAges.insert("Diana", 28);

    std::cout << "BST inorder traversal: ";
    nameAges.inorderTraversal();

    int age;
    if (nameAges.find("Bob", age)) {
        std::cout << "Bob's age: " << age << std::endl;
    }

    // Fixed array template
    FixedArray<double, 5> fixedArr;
    for (size_t i = 0; i < fixedArr.size(); ++i) {
        fixedArr[i] = i * 1.5;
    }

    std::cout << "Fixed array contents: ";
    for (const auto& val : fixedArr) {
        std::cout << val << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

### Template Specialization

#### Explicit and Partial Specialization

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <cstring>

// Primary template
template<typename T>
class TypeInfo {
public:
    static std::string getName() {
        return "Unknown type";
    }

    static void printInfo(const T& value) {
        std::cout << "Generic type: " << value << std::endl;
    }

    static bool isNumeric() { return false; }
};

// Explicit specialization for int
template<>
class TypeInfo<int> {
public:
    static std::string getName() {
        return "Integer";
    }

    static void printInfo(const int& value) {
        std::cout << "Integer value: " << value << std::endl;
    }

    static bool isNumeric() { return true; }
};

// Explicit specialization for std::string
template<>
class TypeInfo<std::string> {
public:
    static std::string getName() {
        return "String";
    }

    static void printInfo(const std::string& value) {
        std::cout << "String value: \"" << value << "\" (length: " << value.length() << ")" << std::endl;
    }

    static bool isNumeric() { return false; }
};

// Partial specialization for pointers
template<typename T>
class TypeInfo<T*> {
public:
    static std::string getName() {
        return "Pointer to " + TypeInfo<T>::getName();
    }

    static void printInfo(T* const& value) {
        if (value) {
            std::cout << "Pointer to " << TypeInfo<T>::getName()
                      << " at address " << value << ", pointing to: ";
            TypeInfo<T>::printInfo(*value);
        } else {
            std::cout << "Null pointer to " << TypeInfo<T>::getName() << std::endl;
        }
    }

    static bool isNumeric() { return false; }
};

// Partial specialization for std::vector
template<typename T>
class TypeInfo<std::vector<T>> {
public:
    static std::string getName() {
        return "Vector of " + TypeInfo<T>::getName();
    }

    static void printInfo(const std::vector<T>& value) {
        std::cout << "Vector of " << TypeInfo<T>::getName()
                  << " with " << value.size() << " elements: [";
        for (size_t i = 0; i < value.size(); ++i) {
            if (i > 0) std::cout << ", ";
            std::cout << value[i];
        }
        std::cout << "]" << std::endl;
    }

    static bool isNumeric() { return false; }
};

// Function template specialization
template<typename T>
void processValue(const T& value) {
    std::cout << "Processing generic value: " << value << std::endl;
}

// Specialized for const char*
template<>
void processValue<const char*>(const char* const& value) {
    std::cout << "Processing C-string: \"" << value << "\" (length: " << strlen(value) << ")" << std::endl;
}

// SFINAE example (Substitution Failure Is Not An Error)
template<typename T>
typename std::enable_if<std::is_arithmetic<T>::value, void>::type
printArithmetic(const T& value) {
    std::cout << "Arithmetic value: " << value << std::endl;
}

template<typename T>
typename std::enable_if<!std::is_arithmetic<T>::value, void>::type
printArithmetic(const T& value) {
    std::cout << "Non-arithmetic value: " << value << std::endl;
}

int main() {
    std::cout << "=== Template Specialization Demo ===" << std::endl;

    // Test primary template and specializations
    int intVal = 42;
    std::string strVal = "Hello, World!";
    double doubleVal = 3.14;

    std::cout << TypeInfo<int>::getName() << std::endl;
    TypeInfo<int>::printInfo(intVal);

    std::cout << TypeInfo<std::string>::getName() << std::endl;
    TypeInfo<std::string>::printInfo(strVal);

    std::cout << TypeInfo<double>::getName() << std::endl;
    TypeInfo<double>::printInfo(doubleVal);

    // Test pointer specialization
    int* intPtr = &intVal;
    std::cout << TypeInfo<int*>::getName() << std::endl;
    TypeInfo<int*>::printInfo(intPtr);

    // Test vector specialization
    std::vector<int> intVec = {1, 2, 3, 4, 5};
    std::cout << TypeInfo<std::vector<int>>::getName() << std::endl;
    TypeInfo<std::vector<int>>::printInfo(intVec);

    // Function template specialization
    processValue(42);
    processValue("Hello");
    processValue(std::string("World"));

    // SFINAE demonstration
    printArithmetic(42);
    printArithmetic(3.14);
    printArithmetic(std::string("Not arithmetic"));

    return 0;
}
```

### Concepts (C++20)

#### Modern Template Constraints

```cpp
#include <iostream>
#include <concepts>
#include <type_traits>
#include <vector>
#include <string>

// Define custom concepts
template<typename T>
concept Numeric = std::is_arithmetic_v<T>;

template<typename T>
concept Printable = requires(T t) {
    std::cout << t;
};

template<typename T>
concept Container = requires(T t) {
    t.begin();
    t.end();
    t.size();
};

template<typename T>
concept Comparable = requires(T a, T b) {
    { a < b } -> std::convertible_to<bool>;
    { a > b } -> std::convertible_to<bool>;
    { a == b } -> std::convertible_to<bool>;
};

// Function templates using concepts
template<Numeric T>
T multiply(T a, T b) {
    return a * b;
}

template<Printable T>
void print(const T& value) {
    std::cout << "Printing: " << value << std::endl;
}

template<Container C>
void printContainer(const C& container) {
    std::cout << "Container with " << container.size() << " elements: ";
    for (const auto& item : container) {
        std::cout << item << " ";
    }
    std::cout << std::endl;
}

template<Comparable T>
T findMax(const std::vector<T>& vec) {
    if (vec.empty()) {
        throw std::invalid_argument("Empty vector");
    }

    T maxVal = vec[0];
    for (const auto& item : vec) {
        if (item > maxVal) {
            maxVal = item;
        }
    }
    return maxVal;
}

int main() {
    std::cout << "=== Concepts Demo ===" << std::endl;
    
    // Numeric concept
    std::cout << "multiply(5, 3) = " << multiply(5, 3) << std::endl;
    std::cout << "multiply(2.5, 4.0) = " << multiply(2.5, 4.0) << std::endl;
    
    // Printable concept
    print(42);
    print(std::string("Hello, Concepts!"));
    print(3.14159);
    
    // Container concept
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    printContainer(numbers);
    
    std::string text = "Hello";
    printContainer(text);  // string is a container of chars
    
    // Comparable concept
    std::cout << "Max in vector: " << findMax(numbers) << std::endl;
    
    return 0;
}
```

### ⚠️ Common Pitfalls

1. **Template Instantiation Errors**: Errors only appear when templates are instantiated
2. **Specialization Ambiguity**: Multiple specializations can match the same type
3. **SFINAE Complexity**: Substitution Failure Is Not An Error can be hard to debug
4. **Concept Requirements**: C++20 concepts must be carefully designed
5. **Compilation Time**: Heavy template usage can slow compilation

### ✅ Best Practices

1. **Prefer Concepts**: Use C++20 concepts instead of SFINAE when possible
2. **Template Constraints**: Always constrain your templates appropriately
3. **Clear Error Messages**: Design templates to give meaningful error messages
4. **Avoid Deep Nesting**: Keep template specialization hierarchies simple
5. **Document Requirements**: Clearly document what types your templates expect

### 🏋️ Exercises

#### 🏋️ Exercise 1: Advanced Template Library
**Difficulty:** 🔴 Advanced  
**Estimated Time:** 45 minutes

Create a comprehensive template library that demonstrates function templates, class templates, specialization, and C++20 concepts.

<details>
<summary>💡 Click to see hints</summary>

- Create a generic container template with specializations
- Use concepts to constrain template parameters
- Include both partial and full specializations
- Add SFINAE examples for older C++ versions
- Demonstrate template metaprogramming techniques

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <vector>
#include <type_traits>
#include <concepts>
#include <string>
#include <memory>

// C++20 Concepts
template<typename T>
concept Arithmetic = std::is_arithmetic_v<T>;

template<typename T>
concept Printable = requires(T t) {
    std::cout << t;
};

template<typename T>
concept Comparable = requires(T a, T b) {
    { a < b } -> std::convertible_to<bool>;
    { a > b } -> std::convertible_to<bool>;
};

// Primary template for a generic container
template<typename T, size_t N = 10>
class Container {
private:
    T data[N];
    size_t current_size = 0;
    
public:
    Container() = default;
    
    void push(const T& item) requires Printable<T> {
        if (current_size < N) {
            data[current_size++] = item;
            std::cout << "Added: " << item << std::endl;
        } else {
            std::cout << "Container full!" << std::endl;
        }
    }
    
    T& operator[](size_t index) {
        return data[index];
    }
    
    const T& operator[](size_t index) const {
        return data[index];
    }
    
    size_t size() const { return current_size; }
    constexpr size_t capacity() const { return N; }
    
    void display() const requires Printable<T> {
        std::cout << "Container contents: ";
        for (size_t i = 0; i < current_size; ++i) {
            std::cout << data[i] << " ";
        }
        std::cout << std::endl;
    }
    
    T findMax() const requires Comparable<T> {
        if (current_size == 0) throw std::runtime_error("Empty container");
        
        T max_val = data[0];
        for (size_t i = 1; i < current_size; ++i) {
            if (data[i] > max_val) {
                max_val = data[i];
            }
        }
        return max_val;
    }
};

// Partial specialization for pointers
template<typename T, size_t N>
class Container<T*, N> {
private:
    T* data[N];
    size_t current_size = 0;
    
public:
    Container() {
        for (size_t i = 0; i < N; ++i) {
            data[i] = nullptr;
        }
    }
    
    ~Container() {
        for (size_t i = 0; i < current_size; ++i) {
            delete data[i];
        }
    }
    
    void push(T* item) {
        if (current_size < N) {
            data[current_size++] = item;
            std::cout << "Added pointer to: " << *item << std::endl;
        } else {
            std::cout << "Container full!" << std::endl;
        }
    }
    
    T* operator[](size_t index) {
        return data[index];
    }
    
    size_t size() const { return current_size; }
    constexpr size_t capacity() const { return N; }
    
    void display() const {
        std::cout << "Pointer container contents: ";
        for (size_t i = 0; i < current_size; ++i) {
            if (data[i]) {
                std::cout << *data[i] << " ";
            }
        }
        std::cout << std::endl;
    }
};

// Full specialization for strings
template<size_t N>
class Container<std::string, N> {
private:
    std::string data[N];
    size_t current_size = 0;
    
public:
    Container() = default;
    
    void push(const std::string& item) {
        if (current_size < N) {
            data[current_size++] = item;
            std::cout << "Added string: \"" << item << "\"" << std::endl;
        } else {
            std::cout << "String container full!" << std::endl;
        }
    }
    
    std::string& operator[](size_t index) {
        return data[index];
    }
    
    const std::string& operator[](size_t index) const {
        return data[index];
    }
    
    size_t size() const { return current_size; }
    constexpr size_t capacity() const { return N; }
    
    void display() const {
        std::cout << "String container contents:" << std::endl;
        for (size_t i = 0; i < current_size; ++i) {
            std::cout << "  [" << i << "]: \"" << data[i] << "\"" << std::endl;
        }
    }
    
    std::string concatenateAll() const {
        std::string result;
        for (size_t i = 0; i < current_size; ++i) {
            if (i > 0) result += " ";
            result += data[i];
        }
        return result;
    }
};

// Template metaprogramming example
template<int N>
struct Factorial {
    static constexpr int value = N * Factorial<N-1>::value;
};

template<>
struct Factorial<0> {
    static constexpr int value = 1;
};

// SFINAE example for backward compatibility
template<typename T>
typename std::enable_if_t<std::is_arithmetic_v<T>, T>
safe_divide(T a, T b) {
    if (b == 0) {
        throw std::runtime_error("Division by zero");
    }
    return a / b;
}

template<typename T>
typename std::enable_if_t<!std::is_arithmetic_v<T>, std::string>
safe_divide(T a, T b) {
    return "Cannot divide non-arithmetic types";
}

// Variadic template example
template<typename First, typename... Rest>
auto sum(First first, Rest... rest) {
    if constexpr (sizeof...(rest) == 0) {
        return first;
    } else {
        return first + sum(rest...);
    }
}

// Template alias
template<typename T>
using SmartContainer = Container<std::unique_ptr<T>, 5>;

int main() {
    std::cout << "=== Advanced Template Library Demo ===" << std::endl;
    
    // Primary template
    Container<int, 5> intContainer;
    intContainer.push(1);
    intContainer.push(5);
    intContainer.push(3);
    intContainer.display();
    std::cout << "Max value: " << intContainer.findMax() << std::endl;
    
    std::cout << std::endl;
    
    // Pointer specialization
    Container<int*, 3> ptrContainer;
    ptrContainer.push(new int(10));
    ptrContainer.push(new int(20));
    ptrContainer.push(new int(15));
    ptrContainer.display();
    
    std::cout << std::endl;
    
    // String specialization
    Container<std::string, 4> stringContainer;
    stringContainer.push("Hello");
    stringContainer.push("World");
    stringContainer.push("Template");
    stringContainer.push("Specialization");
    stringContainer.display();
    std::cout << "Concatenated: \"" << stringContainer.concatenateAll() << "\"" << std::endl;
    
    std::cout << std::endl;
    
    // Template metaprogramming
    std::cout << "Factorial<5>::value = " << Factorial<5>::value << std::endl;
    std::cout << "Factorial<0>::value = " << Factorial<0>::value << std::endl;
    
    // SFINAE examples
    std::cout << "safe_divide(10.0, 2.0) = " << safe_divide(10.0, 2.0) << std::endl;
    std::cout << "safe_divide(string, string) = " << safe_divide(std::string("a"), std::string("b")) << std::endl;
    
    // Variadic templates
    std::cout << "sum(1, 2, 3, 4, 5) = " << sum(1, 2, 3, 4, 5) << std::endl;
    std::cout << "sum(1.1, 2.2, 3.3) = " << sum(1.1, 2.2, 3.3) << std::endl;
    
    return 0;
}
```

**Explanation:**
- Comprehensive template library with primary template and specializations
- C++20 concepts used for template constraints
- Template metaprogramming with compile-time factorial calculation
- SFINAE for backward compatibility with older C++ standards
- Variadic templates for flexible function parameters
- Proper resource management in pointer specialization
- Advanced template techniques combined in practical examples

</details>

[Back to top](#-c-documentation)

[Back to top](#-c-documentation)

---

## 🌊 STL - Standard Template Library

**📊 Chapter 9 of 14**

🎯 **Learning Objectives:**
- Master STL containers and their use cases
- Understand iterators and their categories
- Learn STL algorithms and functional programming
- Explore custom comparators and function objects

⏱️ **Estimated Reading Time:** 40 minutes

📋 **Prerequisites:** Understanding of templates and object-oriented programming

### Containers

#### Sequential Containers

```cpp
#include <iostream>
#include <vector>
#include <deque>
#include <list>
#include <array>
#include <forward_list>
#include <algorithm>
#include <chrono>

void demonstrateVector() {
    std::cout << "=== std::vector ===" << std::endl;

    std::vector<int> vec = {1, 2, 3, 4, 5};

    // Basic operations
    vec.push_back(6);
    vec.insert(vec.begin() + 2, 99);  // Insert at position 2

    std::cout << "Vector contents: ";
    for (const auto& val : vec) {
        std::cout << val << " ";
    }
    std::cout << std::endl;

    // Access methods
    std::cout << "First element: " << vec.front() << std::endl;
    std::cout << "Last element: " << vec.back() << std::endl;
    std::cout << "Element at index 3: " << vec[3] << std::endl;
    std::cout << "Element at index 3 (safe): " << vec.at(3) << std::endl;

    // Capacity information
    std::cout << "Size: " << vec.size() << ", Capacity: " << vec.capacity() << std::endl;

    // Reserve space to avoid reallocations
    vec.reserve(100);
    std::cout << "After reserve(100) - Size: " << vec.size() << ", Capacity: " << vec.capacity() << std::endl;
}

void demonstrateDeque() {
    std::cout << "\n=== std::deque ===" << std::endl;

    std::deque<int> deq = {3, 4, 5};

    // Efficient insertion at both ends
    deq.push_front(2);
    deq.push_front(1);
    deq.push_back(6);
    deq.push_back(7);

    std::cout << "Deque contents: ";
    for (const auto& val : deq) {
        std::cout << val << " ";
    }
    std::cout << std::endl;

    // Random access like vector
    std::cout << "Middle element: " << deq[deq.size()/2] << std::endl;
}

void demonstrateList() {
    std::cout << "\n=== std::list ===" << std::endl;

    std::list<std::string> lst = {"banana", "apple", "orange"};

    // Efficient insertion anywhere
    auto it = std::find(lst.begin(), lst.end(), "apple");
    if (it != lst.end()) {
        lst.insert(it, "grape");
    }

    // Sort the list
    lst.sort();

    std::cout << "Sorted list: ";
    for (const auto& val : lst) {
        std::cout << val << " ";
    }
    std::cout << std::endl;

    // Splice operation (move elements from another list)
    std::list<std::string> otherList = {"mango", "kiwi"};
    lst.splice(lst.end(), otherList);

    std::cout << "After splice: ";
    for (const auto& val : lst) {
        std::cout << val << " ";
    }
    std::cout << std::endl;
}

void demonstrateArray() {
    std::cout << "\n=== std::array ===" << std::endl;

    std::array<int, 5> arr = {1, 2, 3, 4, 5};

    std::cout << "Array contents: ";
    for (const auto& val : arr) {
        std::cout << val << " ";
    }
    std::cout << std::endl;

    // Array-specific operations
    std::cout << "Size: " << arr.size() << std::endl;
    std::cout << "Max size: " << arr.max_size() << std::endl;

    // Fill array
    std::array<int, 3> fillArr;
    fillArr.fill(42);
    std::cout << "Filled array: ";
    for (const auto& val : fillArr) {
        std::cout << val << " ";
    }
    std::cout << std::endl;
}

int main() {
    demonstrateVector();
    demonstrateDeque();
    demonstrateList();
    demonstrateArray();

    return 0;
}
```

#### Associative Containers

```cpp
#include <iostream>
#include <set>
#include <map>
#include <unordered_set>
#include <unordered_map>
#include <string>

void demonstrateSet() {
    std::cout << "=== std::set ===" << std::endl;

    std::set<int> s = {3, 1, 4, 1, 5, 9, 2, 6};  // Duplicates automatically removed

    std::cout << "Set contents (sorted): ";
    for (const auto& val : s) {
        std::cout << val << " ";
    }
    std::cout << std::endl;

    // Insert and find
    s.insert(7);
    if (s.find(5) != s.end()) {
        std::cout << "Found 5 in set" << std::endl;
    }

    // Count (always 0 or 1 for set)
    std::cout << "Count of 5: " << s.count(5) << std::endl;

    // Range-based operations
    auto lower = s.lower_bound(4);
    auto upper = s.upper_bound(6);
    std::cout << "Elements in range [4, 6]: ";
    for (auto it = lower; it != upper; ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;
}

void demonstrateMap() {
    std::cout << "\n=== std::map ===" << std::endl;

    std::map<std::string, int> ageMap = {
        {"Alice", 25},
        {"Bob", 30},
        {"Charlie", 35}
    };

    // Insert new elements
    ageMap["Diana"] = 28;
    ageMap.insert({"Eve", 32});

    std::cout << "Age map contents:" << std::endl;
    for (const auto& [name, age] : ageMap) {  // C++17 structured binding
        std::cout << name << ": " << age << " years old" << std::endl;
    }

    // Safe access with find
    if (auto it = ageMap.find("Bob"); it != ageMap.end()) {
        std::cout << "Bob's age: " << it->second << std::endl;
    }

    // Update existing element
    ageMap["Alice"] = 26;
    std::cout << "Updated Alice's age: " << ageMap["Alice"] << std::endl;
}

void demonstrateUnorderedContainers() {
    std::cout << "\n=== Unordered Containers ===" << std::endl;

    // Unordered set (hash table)
    std::unordered_set<std::string> words = {"apple", "banana", "cherry", "date"};
    words.insert("elderberry");

    std::cout << "Unordered set contents: ";
    for (const auto& word : words) {
        std::cout << word << " ";
    }
    std::cout << std::endl;

    // Unordered map (hash table)
    std::unordered_map<std::string, double> prices = {
        {"apple", 0.5},
        {"banana", 0.3},
        {"cherry", 2.0}
    };

    prices["date"] = 1.5;

    std::cout << "Price list:" << std::endl;
    for (const auto& [item, price] : prices) {
        std::cout << item << ": $" << price << std::endl;
    }

    // Hash table statistics
    std::cout << "Bucket count: " << prices.bucket_count() << std::endl;
    std::cout << "Load factor: " << prices.load_factor() << std::endl;
}

int main() {
    demonstrateSet();
    demonstrateMap();
    demonstrateUnorderedContainers();

    return 0;
}
```

### Iterators

#### Iterator Categories and Usage

```cpp
#include <iostream>
#include <vector>
#include <list>
#include <iterator>
#include <algorithm>

void demonstrateIteratorCategories() {
    std::cout << "=== Iterator Categories ===" << std::endl;

    std::vector<int> vec = {1, 2, 3, 4, 5};
    std::list<int> lst = {10, 20, 30, 40, 50};

    // Random access iterators (vector)
    auto vecIt = vec.begin();
    vecIt += 2;  // Jump to 3rd element
    std::cout << "Vector element at +2: " << *vecIt << std::endl;

    // Bidirectional iterators (list)
    auto lstIt = lst.begin();
    ++lstIt; ++lstIt;  // Move forward twice
    std::cout << "List element after ++, ++: " << *lstIt << std::endl;
    --lstIt;  // Move backward once
    std::cout << "List element after --: " << *lstIt << std::endl;

    // Iterator arithmetic with random access iterators
    auto distance = vec.end() - vec.begin();
    std::cout << "Vector size using iterator arithmetic: " << distance << std::endl;

    // std::distance works with all iterator categories
    auto lstDistance = std::distance(lst.begin(), lst.end());
    std::cout << "List size using std::distance: " << lstDistance << std::endl;
}

void demonstrateIteratorAdapters() {
    std::cout << "\n=== Iterator Adapters ===" << std::endl;

    std::vector<int> vec = {1, 2, 3, 4, 5};

    // Reverse iterators
    std::cout << "Vector in reverse: ";
    for (auto it = vec.rbegin(); it != vec.rend(); ++it) {
        std::cout << *it << " ";
    }
    std::cout << std::endl;

    // Insert iterators
    std::vector<int> dest;

    // back_insert_iterator
    std::copy(vec.begin(), vec.end(), std::back_inserter(dest));
    std::cout << "After back_inserter copy: ";
    for (const auto& val : dest) {
        std::cout << val << " ";
    }
    std::cout << std::endl;

    // front_insert_iterator (works with deque, list, etc.)
    std::list<int> destList;
    std::copy(vec.begin(), vec.end(), std::front_inserter(destList));
    std::cout << "After front_inserter copy (reversed): ";
    for (const auto& val : destList) {
        std::cout << val << " ";
    }
    std::cout << std::endl;

    // insert_iterator
    std::vector<int> destVec = {100, 200};
    auto insertPos = destVec.begin() + 1;
    std::copy(vec.begin(), vec.begin() + 3, std::inserter(destVec, insertPos));
    std::cout << "After inserter copy: ";
    for (const auto& val : destVec) {
        std::cout << val << " ";
    }
    std::cout << std::endl;
}

void demonstrateStreamIterators() {
    std::cout << "\n=== Stream Iterators ===" << std::endl;

    // ostream_iterator
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    std::cout << "Using ostream_iterator: ";
    std::copy(numbers.begin(), numbers.end(),
              std::ostream_iterator<int>(std::cout, " "));
    std::cout << std::endl;

    // istream_iterator (commented out for automated testing)
    /*
    std::cout << "Enter some integers (Ctrl+D to end): ";
    std::vector<int> input_numbers;
    std::copy(std::istream_iterator<int>(std::cin),
              std::istream_iterator<int>(),
              std::back_inserter(input_numbers));

    std::cout << "You entered: ";
    for (const auto& num : input_numbers) {
        std::cout << num << " ";
    }
    std::cout << std::endl;
    */
}

int main() {
    demonstrateIteratorCategories();
    demonstrateIteratorAdapters();
    demonstrateStreamIterators();

    return 0;
}
```

### Algorithms

#### Common STL Algorithms

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <numeric>
#include <functional>
#include <string>

void demonstrateSearchingAlgorithms() {
    std::cout << "=== Searching Algorithms ===" << std::endl;

    std::vector<int> vec = {1, 3, 5, 7, 9, 11, 13, 15};

    // find
    auto it = std::find(vec.begin(), vec.end(), 7);
    if (it != vec.end()) {
        std::cout << "Found 7 at position: " << std::distance(vec.begin(), it) << std::endl;
    }

    // find_if
    auto evenIt = std::find_if(vec.begin(), vec.end(), [](int x) { return x % 2 == 0; });
    if (evenIt == vec.end()) {
        std::cout << "No even numbers found" << std::endl;
    }

    // binary_search (requires sorted container)
    bool found = std::binary_search(vec.begin(), vec.end(), 9);
    std::cout << "Binary search for 9: " << (found ? "found" : "not found") << std::endl;

    // lower_bound and upper_bound
    auto lower = std::lower_bound(vec.begin(), vec.end(), 7);
    auto upper = std::upper_bound(vec.begin(), vec.end(), 7);
    std::cout << "Range for value 7: [" << std::distance(vec.begin(), lower)
              << ", " << std::distance(vec.begin(), upper) << ")" << std::endl;

    // count and count_if
    std::vector<int> numbers = {1, 2, 3, 2, 4, 2, 5};
    int count = std::count(numbers.begin(), numbers.end(), 2);
    std::cout << "Count of 2s: " << count << std::endl;

    int evenCount = std::count_if(numbers.begin(), numbers.end(), [](int x) { return x % 2 == 0; });
    std::cout << "Count of even numbers: " << evenCount << std::endl;
}

void demonstrateModifyingAlgorithms() {
    std::cout << "\n=== Modifying Algorithms ===" << std::endl;

    std::vector<int> source = {1, 2, 3, 4, 5};
    std::vector<int> dest(source.size());

    // copy
    std::copy(source.begin(), source.end(), dest.begin());
    std::cout << "After copy: ";
    for (const auto& val : dest) std::cout << val << " ";
    std::cout << std::endl;

    // transform
    std::vector<int> squared(source.size());
    std::transform(source.begin(), source.end(), squared.begin(),
                   [](int x) { return x * x; });
    std::cout << "After transform (square): ";
    for (const auto& val : squared) std::cout << val << " ";
    std::cout << std::endl;

    // fill and fill_n
    std::vector<int> filled(5);
    std::fill(filled.begin(), filled.end(), 42);
    std::cout << "After fill with 42: ";
    for (const auto& val : filled) std::cout << val << " ";
    std::cout << std::endl;

    // generate
    std::vector<int> generated(5);
    int counter = 0;
    std::generate(generated.begin(), generated.end(), [&counter]() { return ++counter * 10; });
    std::cout << "After generate: ";
    for (const auto& val : generated) std::cout << val << " ";
    std::cout << std::endl;

    // replace and replace_if
    std::vector<int> values = {1, 2, 3, 2, 4, 2, 5};
    std::replace(values.begin(), values.end(), 2, 99);
    std::cout << "After replace 2 with 99: ";
    for (const auto& val : values) std::cout << val << " ";
    std::cout << std::endl;
}

void demonstrateSortingAlgorithms() {
    std::cout << "\n=== Sorting Algorithms ===" << std::endl;

    std::vector<int> vec = {3, 1, 4, 1, 5, 9, 2, 6};

    // sort
    std::vector<int> sorted = vec;
    std::sort(sorted.begin(), sorted.end());
    std::cout << "After sort: ";
    for (const auto& val : sorted) std::cout << val << " ";
    std::cout << std::endl;

    // sort with custom comparator
    std::vector<int> descending = vec;
    std::sort(descending.begin(), descending.end(), std::greater<int>());
    std::cout << "After sort (descending): ";
    for (const auto& val : descending) std::cout << val << " ";
    std::cout << std::endl;

    // partial_sort
    std::vector<int> partial = vec;
    std::partial_sort(partial.begin(), partial.begin() + 3, partial.end());
    std::cout << "After partial_sort (first 3): ";
    for (const auto& val : partial) std::cout << val << " ";
    std::cout << std::endl;

    // nth_element
    std::vector<int> nthVec = vec;
    std::nth_element(nthVec.begin(), nthVec.begin() + 3, nthVec.end());
    std::cout << "4th element (0-indexed): " << nthVec[3] << std::endl;

    // is_sorted
    bool isSorted = std::is_sorted(sorted.begin(), sorted.end());
    std::cout << "Is sorted vector actually sorted? " << (isSorted ? "Yes" : "No") << std::endl;
}

void demonstrateNumericAlgorithms() {
    std::cout << "\n=== Numeric Algorithms ===" << std::endl;

    std::vector<int> numbers = {1, 2, 3, 4, 5};

    // accumulate
    int sum = std::accumulate(numbers.begin(), numbers.end(), 0);
    std::cout << "Sum: " << sum << std::endl;

    int product = std::accumulate(numbers.begin(), numbers.end(), 1, std::multiplies<int>());
    std::cout << "Product: " << product << std::endl;

    // partial_sum
    std::vector<int> partialSums(numbers.size());
    std::partial_sum(numbers.begin(), numbers.end(), partialSums.begin());
    std::cout << "Partial sums: ";
    for (const auto& val : partialSums) std::cout << val << " ";
    std::cout << std::endl;

    // adjacent_difference
    std::vector<int> differences(numbers.size());
    std::adjacent_difference(numbers.begin(), numbers.end(), differences.begin());
    std::cout << "Adjacent differences: ";
    for (const auto& val : differences) std::cout << val << " ";
    std::cout << std::endl;

    // iota (C++11)
    std::vector<int> sequence(10);
    std::iota(sequence.begin(), sequence.end(), 1);
    std::cout << "Sequence from iota: ";
    for (const auto& val : sequence) std::cout << val << " ";
    std::cout << std::endl;
}

int main() {
    demonstrateSearchingAlgorithms();
    demonstrateModifyingAlgorithms();
    demonstrateSortingAlgorithms();
    demonstrateNumericAlgorithms();
    
    return 0;
}
```

### Function Objects

#### Custom Function Objects and Predicates

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <functional>
#include <string>

// Custom function object (functor)
class MultiplyBy {
private:
    int factor;
    
public:
    MultiplyBy(int f) : factor(f) {}
    
    int operator()(int value) const {
        return value * factor;
    }
};

// Predicate function object
class IsEven {
public:
    bool operator()(int value) const {
        return value % 2 == 0;
    }
};

// Stateful function object
class Counter {
private:
    mutable int count = 0;
    
public:
    int operator()(int value) const {
        return ++count;
    }
    
    int getCount() const { return count; }
};

void demonstrateFunctionObjects() {
    std::cout << "=== Function Objects Demo ===" << std::endl;
    
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    
    // Using custom function object
    std::vector<int> doubled(numbers.size());
    std::transform(numbers.begin(), numbers.end(), doubled.begin(), MultiplyBy(2));
    
    std::cout << "Doubled: ";
    for (int n : doubled) std::cout << n << " ";
    std::cout << std::endl;
    
    // Using predicate function object
    auto evenCount = std::count_if(numbers.begin(), numbers.end(), IsEven());
    std::cout << "Even numbers count: " << evenCount << std::endl;
    
    // Using stateful function object
    Counter counter;
    std::for_each(numbers.begin(), numbers.end(), counter);
    std::cout << "Processed " << counter.getCount() << " elements" << std::endl;
    
    // Standard function objects
    std::sort(numbers.begin(), numbers.end(), std::greater<int>());
    std::cout << "Sorted descending: ";
    for (int n : numbers) std::cout << n << " ";
    std::cout << std::endl;
}

int main() {
    demonstrateFunctionObjects();
    return 0;
}
```

### ⚠️ Common Pitfalls

1. **Iterator Invalidation**: Modifying containers while iterating can invalidate iterators
2. **Algorithm Requirements**: Not all algorithms work with all iterator types
3. **Performance Considerations**: Choose appropriate containers for your use case
4. **Memory Management**: Be careful with raw pointers in containers
5. **Exception Safety**: STL operations can throw exceptions

### ✅ Best Practices

1. **Use Range-Based Loops**: Prefer range-based for loops when possible
2. **Choose Right Container**: Select containers based on performance requirements
3. **Const Correctness**: Use const iterators when not modifying data
4. **Algorithm Selection**: Use appropriate STL algorithms instead of manual loops
5. **Smart Pointers**: Use smart pointers instead of raw pointers in containers

### 🏋️ Exercises

#### 🏋️ Exercise 1: Custom Container with STL Integration
**Difficulty:** 🟡 Intermediate  
**Estimated Time:** 40 minutes

Create a custom container that integrates seamlessly with STL algorithms and follows STL conventions.

<details>
<summary>💡 Click to see hints</summary>

- Implement proper iterator types and member functions
- Follow STL naming conventions (begin(), end(), size(), etc.)
- Make your container work with range-based for loops
- Include proper type aliases (value_type, iterator, etc.)
- Test with various STL algorithms

</details>

<details>
<summary>✅ Click to see solution</summary>

```cpp
#include <iostream>
#include <algorithm>
#include <iterator>
#include <vector>
#include <numeric>

template<typename T, size_t Capacity>
class CircularBuffer {
public:
    using value_type = T;
    using size_type = size_t;
    using difference_type = std::ptrdiff_t;
    using reference = T&;
    using const_reference = const T&;
    using pointer = T*;
    using const_pointer = const T*;
    
private:
    T buffer[Capacity];
    size_type head = 0;
    size_type count = 0;
    
public:
    // Iterator class
    class iterator {
    private:
        CircularBuffer* container;
        size_type index;
        
    public:
        using iterator_category = std::random_access_iterator_tag;
        using value_type = T;
        using difference_type = std::ptrdiff_t;
        using pointer = T*;
        using reference = T&;
        
        iterator(CircularBuffer* c, size_type i) : container(c), index(i) {}
        
        reference operator*() { return (*container)[index]; }
        pointer operator->() { return &(*container)[index]; }
        
        iterator& operator++() { ++index; return *this; }
        iterator operator++(int) { iterator tmp = *this; ++index; return tmp; }
        
        iterator& operator--() { --index; return *this; }
        iterator operator--(int) { iterator tmp = *this; --index; return tmp; }
        
        iterator& operator+=(difference_type n) { index += n; return *this; }
        iterator& operator-=(difference_type n) { index -= n; return *this; }
        
        iterator operator+(difference_type n) const { return iterator(container, index + n); }
        iterator operator-(difference_type n) const { return iterator(container, index - n); }
        
        difference_type operator-(const iterator& other) const { return index - other.index; }
        
        reference operator[](difference_type n) { return (*container)[index + n]; }
        
        bool operator==(const iterator& other) const { return index == other.index; }
        bool operator!=(const iterator& other) const { return index != other.index; }
        bool operator<(const iterator& other) const { return index < other.index; }
        bool operator>(const iterator& other) const { return index > other.index; }
        bool operator<=(const iterator& other) const { return index <= other.index; }
        bool operator>=(const iterator& other) const { return index >= other.index; }
    };
    
    class const_iterator {
    private:
        const CircularBuffer* container;
        size_type index;
        
    public:
        using iterator_category = std::random_access_iterator_tag;
        using value_type = T;
        using difference_type = std::ptrdiff_t;
        using pointer = const T*;
        using reference = const T&;
        
        const_iterator(const CircularBuffer* c, size_type i) : container(c), index(i) {}
        
        reference operator*() const { return (*container)[index]; }
        pointer operator->() const { return &(*container)[index]; }
        
        const_iterator& operator++() { ++index; return *this; }
        const_iterator operator++(int) { const_iterator tmp = *this; ++index; return tmp; }
        
        const_iterator& operator--() { --index; return *this; }
        const_iterator operator--(int) { const_iterator tmp = *this; --index; return tmp; }
        
        const_iterator& operator+=(difference_type n) { index += n; return *this; }
        const_iterator& operator-=(difference_type n) { index -= n; return *this; }
        
        const_iterator operator+(difference_type n) const { return const_iterator(container, index + n); }
        const_iterator operator-(difference_type n) const { return const_iterator(container, index - n); }
        
        difference_type operator-(const const_iterator& other) const { return index - other.index; }
        
        reference operator[](difference_type n) const { return (*container)[index + n]; }
        
        bool operator==(const const_iterator& other) const { return index == other.index; }
        bool operator!=(const const_iterator& other) const { return index != other.index; }
        bool operator<(const const_iterator& other) const { return index < other.index; }
        bool operator>(const const_iterator& other) const { return index > other.index; }
        bool operator<=(const const_iterator& other) const { return index <= other.index; }
        bool operator>=(const const_iterator& other) const { return index >= other.index; }
    };
    
    CircularBuffer() = default;
    
    void push_back(const T& value) {
        if (count < Capacity) {
            buffer[(head + count) % Capacity] = value;
            ++count;
        } else {
            buffer[head] = value;
            head = (head + 1) % Capacity;
        }
    }
    
    void pop_front() {
        if (count > 0) {
            head = (head + 1) % Capacity;
            --count;
        }
    }
    
    reference operator[](size_type index) {
        return buffer[(head + index) % Capacity];
    }
    
    const_reference operator[](size_type index) const {
        return buffer[(head + index) % Capacity];
    }
    
    reference front() { return buffer[head]; }
    const_reference front() const { return buffer[head]; }
    
    reference back() { return buffer[(head + count - 1) % Capacity]; }
    const_reference back() const { return buffer[(head + count - 1) % Capacity]; }
    
    iterator begin() { return iterator(this, 0); }
    iterator end() { return iterator(this, count); }
    
    const_iterator begin() const { return const_iterator(this, 0); }
    const_iterator end() const { return const_iterator(this, count); }
    
    const_iterator cbegin() const { return const_iterator(this, 0); }
    const_iterator cend() const { return const_iterator(this, count); }
    
    size_type size() const { return count; }
    constexpr size_type max_size() const { return Capacity; }
    bool empty() const { return count == 0; }
    bool full() const { return count == Capacity; }
    
    void clear() {
        head = 0;
        count = 0;
    }
};

int main() {
    std::cout << "=== Custom Container STL Integration Demo ===" << std::endl;
    
    CircularBuffer<int, 5> buffer;
    
    // Fill the buffer
    for (int i = 1; i <= 7; ++i) {
        buffer.push_back(i * 10);
        std::cout << "Added " << (i * 10) << ", buffer size: " << buffer.size() << std::endl;
    }
    
    // Use with range-based for loop
    std::cout << "Buffer contents: ";
    for (const auto& value : buffer) {
        std::cout << value << " ";
    }
    std::cout << std::endl;
    
    // Use with STL algorithms
    auto maxElement = std::max_element(buffer.begin(), buffer.end());
    if (maxElement != buffer.end()) {
        std::cout << "Maximum element: " << *maxElement << std::endl;
    }
    
    // Transform elements
    std::transform(buffer.begin(), buffer.end(), buffer.begin(), 
                   [](int x) { return x / 10; });
    
    std::cout << "After transformation: ";
    for (const auto& value : buffer) {
        std::cout << value << " ";
    }
    std::cout << std::endl;
    
    // Use accumulate
    int sum = std::accumulate(buffer.begin(), buffer.end(), 0);
    std::cout << "Sum of elements: " << sum << std::endl;
    
    // Sort the buffer
    std::sort(buffer.begin(), buffer.end(), std::greater<int>());
    
    std::cout << "After sorting (descending): ";
    for (const auto& value : buffer) {
        std::cout << value << " ";
    }
    std::cout << std::endl;
    
    // Find element
    auto found = std::find(buffer.begin(), buffer.end(), 5);
    if (found != buffer.end()) {
        std::cout << "Found element 5 at position: " 
                  << std::distance(buffer.begin(), found) << std::endl;
    }
    
    return 0;
}
```

**Explanation:**
- Complete STL-compatible circular buffer implementation
- Proper iterator implementation with all required operations
- STL-style member functions and type aliases
- Integration with range-based for loops and STL algorithms
- Demonstrates advanced iterator concepts and STL design principles
- Shows how custom containers can seamlessly work with existing STL code

</details>

[Back to top](#-c-documentation)

[Back to top](#-c-documentation)

---

## ⚠️ Error Handling

**📊 Chapter 10 of 14**

🎯 **Learning Objectives:**
- Master exception handling with try-catch blocks
- Understand error codes and their appropriate usage
- Learn RAII principles for exception safety
- Explore modern error handling techniques

⏱️ **Estimated Reading Time:** 25 minutes

📋 **Prerequisites:** Understanding of functions and basic C++ syntax

### Exceptions

#### Basic Exception Handling

```cpp
#include <iostream>
#include <stdexcept>
#include <string>
#include <vector>

void demonstrateBasicExceptions() {
    std::cout << "=== Basic Exception Handling ===" << std::endl;

    try {
        // Throw a standard exception
        throw std::runtime_error("Something went wrong!");
    } catch (const std::runtime_error& e) {
        std::cout << "Caught runtime_error: " << e.what() << std::endl;
    }

    // Multiple catch blocks
    try {
        int choice;
        std::cout << "Enter 1 for logic_error, 2 for runtime_error, 3 for int: ";
        std::cin >> choice;

        switch (choice) {
            case 1: throw std::logic_error("Logic error occurred");
            case 2: throw std::runtime_error("Runtime error occurred");
            case 3: throw 42;
            default: std::cout << "No exception thrown" << std::endl;
        }
    } catch (const std::logic_error& e) {
        std::cout << "Caught logic_error: " << e.what() << std::endl;
    } catch (const std::runtime_error& e) {
        std::cout << "Caught runtime_error: " << e.what() << std::endl;
    } catch (int value) {
        std::cout << "Caught integer: " << value << std::endl;
    } catch (...) {
        std::cout << "Caught unknown exception" << std::endl;
    }
}

// Custom exception class
class CustomException : public std::exception {
private:
    std::string message;
    int errorCode;

public:
    CustomException(const std::string& msg, int code)
        : message(msg), errorCode(code) {}

    const char* what() const noexcept override {
        return message.c_str();
    }

    int getErrorCode() const { return errorCode; }
};

void demonstrateCustomExceptions() {
    std::cout << "\n=== Custom Exceptions ===" << std::endl;

    try {
        throw CustomException("Custom error occurred", 404);
    } catch (const CustomException& e) {
        std::cout << "Caught CustomException: " << e.what()
                  << " (Code: " << e.getErrorCode() << ")" << std::endl;
    }
}

// Function that might throw
double divide(double a, double b) {
    if (b == 0) {
        throw std::invalid_argument("Division by zero");
    }
    return a / b;
}

void demonstrateExceptionPropagation() {
    std::cout << "\n=== Exception Propagation ===" << std::endl;

    try {
        std::cout << "10 / 2 = " << divide(10, 2) << std::endl;
        std::cout << "10 / 0 = " << divide(10, 0) << std::endl;  // This will throw
        std::cout << "This line won't be reached" << std::endl;
    } catch (const std::invalid_argument& e) {
        std::cout << "Caught exception: " << e.what() << std::endl;
    }

    std::cout << "Program continues after exception handling" << std::endl;
}

int main() {
    demonstrateBasicExceptions();
    demonstrateCustomExceptions();
    demonstrateExceptionPropagation();

    return 0;
}
```

### RAII and Exception Safety

#### Exception-Safe Resource Management

```cpp
#include <iostream>
#include <memory>
#include <fstream>
#include <vector>
#include <stdexcept>

// RAII class for file handling
class FileHandler {
private:
    std::FILE* file;
    std::string filename;

public:
    FileHandler(const std::string& fname, const char* mode)
        : filename(fname) {
        file = std::fopen(fname.c_str(), mode);
        if (!file) {
            throw std::runtime_error("Failed to open file: " + filename);
        }
        std::cout << "File '" << filename << "' opened successfully" << std::endl;
    }

    ~FileHandler() {
        if (file) {
            std::fclose(file);
            std::cout << "File '" << filename << "' closed automatically" << std::endl;
        }
    }

    // Delete copy operations to prevent double-close
    FileHandler(const FileHandler&) = delete;
    FileHandler& operator=(const FileHandler&) = delete;

    // Move operations
    FileHandler(FileHandler&& other) noexcept
        : file(other.file), filename(std::move(other.filename)) {
        other.file = nullptr;
    }

    FileHandler& operator=(FileHandler&& other) noexcept {
        if (this != &other) {
            if (file) std::fclose(file);
            file = other.file;
            filename = std::move(other.filename);
            other.file = nullptr;
        }
        return *this;
    }

    std::FILE* get() const { return file; }

    void write(const std::string& data) {
        if (!file) {
            throw std::runtime_error("File not open");
        }
        if (std::fputs(data.c_str(), file) == EOF) {
            throw std::runtime_error("Write failed");
        }
    }
};

// Exception-safe transaction class
class Transaction {
private:
    std::vector<std::function<void()>> rollbackOperations;
    bool committed = false;

public:
    ~Transaction() {
        if (!committed) {
            rollback();
        }
    }

    void addRollbackOperation(std::function<void()> operation) {
        rollbackOperations.push_back(std::move(operation));
    }

    void commit() {
        committed = true;
        rollbackOperations.clear();
    }

    void rollback() {
        std::cout << "Rolling back transaction..." << std::endl;
        for (auto it = rollbackOperations.rbegin(); it != rollbackOperations.rend(); ++it) {
            try {
                (*it)();
            } catch (...) {
                // Log rollback failure but continue
                std::cout << "Rollback operation failed" << std::endl;
            }
        }
        rollbackOperations.clear();
    }
};

void demonstrateRAIIExceptionSafety() {
    std::cout << "=== RAII Exception Safety ===" << std::endl;

    try {
        FileHandler file("test.txt", "w");
        file.write("Hello, RAII!\n");

        // Simulate an exception
        throw std::runtime_error("Something went wrong!");

        file.write("This won't be written\n");
    } catch (const std::exception& e) {
        std::cout << "Exception caught: " << e.what() << std::endl;
        std::cout << "File was automatically closed due to RAII" << std::endl;
    }
}

void demonstrateTransactionRollback() {
    std::cout << "\n=== Transaction Rollback ===" << std::endl;

    std::vector<int> data = {1, 2, 3};

    try {
        Transaction txn;

        // Operation 1: Add element
        data.push_back(4);
        txn.addRollbackOperation([&data]() { data.pop_back(); });
        std::cout << "Added 4, data size: " << data.size() << std::endl;

        // Operation 2: Add another element
        data.push_back(5);
        txn.addRollbackOperation([&data]() { data.pop_back(); });
        std::cout << "Added 5, data size: " << data.size() << std::endl;

        // Simulate failure - exception will trigger rollback
        throw std::runtime_error("Transaction failed!");

        txn.commit();  // This won't be reached
    } catch (const std::exception& e) {
        std::cout << "Exception: " << e.what() << std::endl;
        std::cout << "After rollback, data size: " << data.size() << std::endl;
    }
}

int main() {
    demonstrateRAIIExceptionSafety();
    demonstrateTransactionRollback();
    
    return 0;
}
```

### Error Codes

#### Alternative Error Handling Approaches

```cpp
#include <iostream>
#include <optional>
#include <variant>
#include <string>
#include <system_error>

// Custom error codes
enum class FileError {
    SUCCESS = 0,
    FILE_NOT_FOUND,
    PERMISSION_DENIED,
    DISK_FULL,
    INVALID_FORMAT
};

// Error category for custom errors
class FileErrorCategory : public std::error_category {
public:
    const char* name() const noexcept override {
        return "file_error";
    }
    
    std::string message(int ev) const override {
        switch (static_cast<FileError>(ev)) {
            case FileError::SUCCESS: return "Success";
            case FileError::FILE_NOT_FOUND: return "File not found";
            case FileError::PERMISSION_DENIED: return "Permission denied";
            case FileError::DISK_FULL: return "Disk full";
            case FileError::INVALID_FORMAT: return "Invalid file format";
            default: return "Unknown error";
        }
    }
};

const FileErrorCategory& file_error_category() {
    static FileErrorCategory instance;
    return instance;
}

std::error_code make_error_code(FileError e) {
    return std::error_code(static_cast<int>(e), file_error_category());
}

// Make FileError compatible with std::error_code
namespace std {
    template<>
    struct is_error_code_enum<FileError> : true_type {};
}

// Result type using std::variant
template<typename T, typename E>
class Result {
private:
    std::variant<T, E> data;
    
public:
    Result(const T& value) : data(value) {}
    Result(const E& error) : data(error) {}
    
    bool hasValue() const {
        return std::holds_alternative<T>(data);
    }
    
    bool hasError() const {
        return std::holds_alternative<E>(data);
    }
    
    const T& getValue() const {
        return std::get<T>(data);
    }
    
    const E& getError() const {
        return std::get<E>(data);
    }
    
    T valueOr(const T& defaultValue) const {
        return hasValue() ? getValue() : defaultValue;
    }
};

// Example functions using different error handling approaches
std::optional<std::string> readFileOptional(const std::string& filename) {
    if (filename.empty()) {
        return std::nullopt;
    }
    if (filename == "missing.txt") {
        return std::nullopt;
    }
    return "File contents: " + filename;
}

Result<std::string, FileError> readFileResult(const std::string& filename) {
    if (filename.empty()) {
        return FileError::INVALID_FORMAT;
    }
    if (filename == "missing.txt") {
        return FileError::FILE_NOT_FOUND;
    }
    if (filename == "protected.txt") {
        return FileError::PERMISSION_DENIED;
    }
    return std::string("File contents: " + filename);
}

std::pair<std::string, std::error_code> readFileErrorCode(const std::string& filename) {
    if (filename.empty()) {
        return {"", make_error_code(FileError::INVALID_FORMAT)};
    }
    if (filename == "missing.txt") {
        return {"", make_error_code(FileError::FILE_NOT_FOUND)};
    }
    if (filename == "protected.txt") {
        return {"", make_error_code(FileError::PERMISSION_DENIED)};
    }
    return {"File contents: " + filename, make_error_code(FileError::SUCCESS)};
}

void demonstrateErrorCodes() {
    std::cout << "=== Error Code Handling Demo ===" << std::endl;
    
    // Using std::optional
    std::cout << "1. Using std::optional:" << std::endl;
    auto opt1 = readFileOptional("test.txt");
    if (opt1) {
        std::cout << "Success: " << *opt1 << std::endl;
    } else {
        std::cout << "Failed to read file" << std::endl;
    }
    
    auto opt2 = readFileOptional("missing.txt");
    if (!opt2) {
        std::cout << "File not found (optional approach)" << std::endl;
    }
    
    // Using Result type
    std::cout << "\n2. Using Result type:" << std::endl;
    auto result1 = readFileResult("test.txt");
    if (result1.hasValue()) {
        std::cout << "Success: " << result1.getValue() << std::endl;
    } else {
        std::cout << "Error: " << static_cast<int>(result1.getError()) << std::endl;
    }
    
    auto result2 = readFileResult("protected.txt");
    if (result2.hasError()) {
        std::cout << "Access denied: " << static_cast<int>(result2.getError()) << std::endl;
    }
    
    // Using std::error_code
    std::cout << "\n3. Using std::error_code:" << std::endl;
    auto [content, ec] = readFileErrorCode("test.txt");
    if (!ec) {
        std::cout << "Success: " << content << std::endl;
    } else {
        std::cout << "Error: " << ec.message() << std::endl;
    }
    
    auto [content2, ec2] = readFileErrorCode("missing.txt");
    if (ec2) {
        std::cout << "Error (" << ec

[Back to top](#-c-documentation)

---

## 🔄 Modern C++ Features

**📊 Chapter 11 of 14**

🎯 **Learning Objectives:**
- Master move semantics and perfect forwarding
- Understand range-based loops and structured bindings
- Learn about modules and coroutines in C++20
- Explore other modern C++ features and best practices

⏱️ **Estimated Reading Time:** 30 minutes

📋 **Prerequisites:** Understanding of templates and object-oriented programming

### Move Semantics

#### Understanding Move Operations

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <utility>
#include <chrono>

class Resource {
private:
    std::vector<int> data;
    std::string name;

public:
    // Constructor
    Resource(const std::string& n, size_t size) : name(n), data(size, 42) {
        std::cout << "Resource '" << name << "' created with " << size << " elements" << std::endl;
    }

    // Copy constructor
    Resource(const Resource& other) : name(other.name + "_copy"), data(other.data) {
        std::cout << "Resource copied: " << name << std::endl;
    }

    // Move constructor
    Resource(Resource&& other) noexcept : name(std::move(other.name)), data(std::move(other.data)) {
        std::cout << "Resource moved: " << name << std::endl;
        other.name = "moved_from";
    }

    // Copy assignment
    Resource& operator=(const Resource& other) {
        if (this != &other) {
            name = other.name + "_assigned";
            data = other.data;
            std::cout << "Resource copy-assigned: " << name << std::endl;
        }
        return *this;
    }

    // Move assignment
    Resource& operator=(Resource&& other) noexcept {
        if (this != &other) {
            name = std::move(other.name);
            data = std::move(other.data);
            std::cout << "Resource move-assigned: " << name << std::endl;
            other.name = "moved_from";
        }
        return *this;
    }

    // Destructor
    ~Resource() {
        std::cout << "Resource destroyed: " << name << std::endl;
    }

    const std::string& getName() const { return name; }
    size_t getSize() const { return data.size(); }
};

void demonstrateMoveSemantics() {
    std::cout << "=== Move Semantics Demo ===" << std::endl;

    // Create resource
    Resource res1("Original", 1000000);

    // Copy vs Move timing
    auto start = std::chrono::high_resolution_clock::now();
    Resource res2 = res1;  // Copy constructor
    auto end = std::chrono::high_resolution_clock::now();
    auto copyTime = std::chrono::duration_cast<std::chrono::microseconds>(end - start);

    start = std::chrono::high_resolution_clock::now();
    Resource res3 = std::move(res1);  // Move constructor
    end = std::chrono::high_resolution_clock::now();
    auto moveTime = std::chrono::duration_cast<std::chrono::microseconds>(end - start);

    std::cout << "Copy time: " << copyTime.count() << "μs" << std::endl;
    std::cout << "Move time: " << moveTime.count() << "μs" << std::endl;
    std::cout << "Original resource after move: " << res1.getName() << std::endl;
}

// Perfect forwarding example
template<typename T>
void processValue(T&& value) {
    std::cout << "Processing: " << value << std::endl;
    // Forward the value to another function
    someFunction(std::forward<T>(value));
}

void someFunction(const std::string& s) {
    std::cout << "someFunction called with lvalue: " << s << std::endl;
}

void someFunction(std::string&& s) {
    std::cout << "someFunction called with rvalue: " << s << std::endl;
}

int main() {
    demonstrateMoveSemantics();

    // Perfect forwarding
    std::string str = "Hello";
    processValue(str);                    // Forwards as lvalue
    processValue(std::string("World"));   // Forwards as rvalue
    processValue("Temporary");            // Forwards as rvalue

    return 0;
}
```

### Range-based Loops

#### Modern Iteration Techniques

```cpp
#include <iostream>
#include <vector>
#include <map>
#include <string>
#include <ranges>

void demonstrateBasicRangeLoops() {
    std::cout << "=== Basic Range-based Loops ===" << std::endl;

    std::vector<int> numbers = {1, 2, 3, 4, 5};

    // Basic range-based for loop
    std::cout << "Numbers: ";
    for (const auto& num : numbers) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    // Modifying elements
    std::cout << "Doubling numbers: ";
    for (auto& num : numbers) {
        num *= 2;
        std::cout << num << " ";
    }
    std::cout << std::endl;

    // With maps
    std::map<std::string, int> ages = {{"Alice", 25}, {"Bob", 30}, {"Charlie", 35}};

    std::cout << "Ages:" << std::endl;
    for (const auto& [name, age] : ages) {  // C++17 structured binding
        std::cout << name << ": " << age << " years old" << std::endl;
    }
}

void demonstrateRangesLibrary() {
    std::cout << "\n=== C++20 Ranges Library ===" << std::endl;

    std::vector<int> numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    // Filter and transform with ranges
    auto evenSquares = numbers
        | std::views::filter([](int n) { return n % 2 == 0; })
        | std::views::transform([](int n) { return n * n; });

    std::cout << "Even numbers squared: ";
    for (int value : evenSquares) {
        std::cout << value << " ";
    }
    std::cout << std::endl;

    // Take first N elements
    auto firstFive = numbers | std::views::take(5);
    std::cout << "First 5 elements: ";
    for (int value : firstFive) {
        std::cout << value << " ";
    }
    std::cout << std::endl;

    // Reverse view
    auto reversed = numbers | std::views::reverse;
    std::cout << "Reversed: ";
    for (int value : reversed) {
        std::cout << value << " ";
    }
    std::cout << std::endl;
}

int main() {
    demonstrateBasicRangeLoops();
    demonstrateRangesLibrary();

    return 0;
}
```

### Structured Bindings

#### C++17 Structured Bindings

```cpp
#include <iostream>
#include <tuple>
#include <map>
#include <array>
#include <utility>

struct Point {
    double x, y, z;
};

std::tuple<int, std::string, double> getPersonInfo() {
    return std::make_tuple(25, "Alice", 175.5);
}

std::pair<bool, std::string> validateInput(const std::string& input) {
    if (input.empty()) {
        return {false, "Input cannot be empty"};
    }
    return {true, "Input is valid"};
}

void demonstrateStructuredBindings() {
    std::cout << "=== Structured Bindings Demo ===" << std::endl;

    // With tuples
    auto [age, name, height] = getPersonInfo();
    std::cout << "Person: " << name << ", Age: " << age << ", Height: " << height << "cm" << std::endl;

    // With pairs
    auto [isValid, message] = validateInput("Hello World");
    std::cout << "Validation result: " << (isValid ? "Valid" : "Invalid") << " - " << message << std::endl;

    // With structs
    Point p{1.5, 2.5, 3.5};
    auto [x, y, z] = p;
    std::cout << "Point coordinates: (" << x << ", " << y << ", " << z << ")" << std::endl;

    // With arrays
    std::array<int, 3> arr = {10, 20, 30};
    auto [first, second, third] = arr;
    std::cout << "Array elements: " << first << ", " << second << ", " << third << std::endl;

    // With maps (in range-based for loop)
    std::map<std::string, int> scores = {{"Alice", 95}, {"Bob", 87}, {"Charlie", 92}};
    std::cout << "Scores:" << std::endl;
    for (const auto& [student, score] : scores) {
        std::cout << student << ": " << score << std::endl;
    }
}

int main() {
    demonstrateStructuredBindings();
    return 0;
}
```

[Back to top](#-c-documentation)

---

## ⚡ Concurrency & Parallelism

**📊 Chapter 12 of 14**

🎯 **Learning Objectives:**
- Master thread creation and management
- Understand synchronization primitives and thread safety
- Learn atomic operations and lock-free programming
- Explore parallel algorithms and execution policies

⏱️ **Estimated Reading Time:** 35 minutes

📋 **Prerequisites:** Understanding of modern C++ features and memory management

### Threads

#### Basic Threading

```cpp
#include <iostream>
#include <thread>
#include <vector>
#include <chrono>
#include <atomic>

void simpleTask(int id, int duration) {
    std::cout << "Thread " << id << " starting work..." << std::endl;
    std::this_thread::sleep_for(std::chrono::milliseconds(duration));
    std::cout << "Thread " << id << " finished work after " << duration << "ms" << std::endl;
}

void demonstrateBasicThreads() {
    std::cout << "=== Basic Threading ===" << std::endl;

    // Create and start threads
    std::thread t1(simpleTask, 1, 1000);
    std::thread t2(simpleTask, 2, 1500);
    std::thread t3(simpleTask, 3, 800);

    std::cout << "Main thread waiting for workers..." << std::endl;

    // Wait for threads to complete
    t1.join();
    t2.join();
    t3.join();

    std::cout << "All threads completed!" << std::endl;
}

// Thread-safe counter example
class ThreadSafeCounter {
private:
    std::atomic<int> count{0};

public:
    void increment() {
        count.fetch_add(1);
    }

    void decrement() {
        count.fetch_sub(1);
    }

    int getValue() const {
        return count.load();
    }
};

void counterWorker(ThreadSafeCounter& counter, int iterations) {
    for (int i = 0; i < iterations; ++i) {
        counter.increment();
        std::this_thread::sleep_for(std::chrono::microseconds(1));
    }
}

void demonstrateThreadSafety() {
    std::cout << "\n=== Thread Safety with Atomic ===" << std::endl;

    ThreadSafeCounter counter;
    const int iterations = 1000;
    const int numThreads = 4;

    std::vector<std::thread> threads;

    auto start = std::chrono::high_resolution_clock::now();

    // Launch worker threads
    for (int i = 0; i < numThreads; ++i) {
        threads.emplace_back(counterWorker, std::ref(counter), iterations);
    }

    // Wait for all threads
    for (auto& t : threads) {
        t.join();
    }

    auto end = std::chrono::high_resolution_clock::now();
    auto duration = std::chrono::duration_cast<std::chrono::milliseconds>(end - start);

    std::cout << "Expected count: " << (iterations * numThreads) << std::endl;
    std::cout << "Actual count: " << counter.getValue() << std::endl;
    std::cout << "Time taken: " << duration.count() << "ms" << std::endl;
}

int main() {
    demonstrateBasicThreads();
    demonstrateThreadSafety();

    return 0;
}
```

### Synchronization

#### Mutexes and Lock Guards

```cpp
#include <iostream>
#include <thread>
#include <mutex>
#include <condition_variable>
#include <queue>
#include <vector>
#include <chrono>

class SafePrinter {
private:
    std::mutex mtx;

public:
    void print(const std::string& message, int id) {
        std::lock_guard<std::mutex> lock(mtx);
        std::cout << "Thread " << id << ": " << message << std::endl;
        std::this_thread::sleep_for(std::chrono::milliseconds(100));
    }
};

void demonstrateMutex() {
    std::cout << "=== Mutex and Lock Guard ===" << std::endl;

    SafePrinter printer;
    std::vector<std::thread> threads;

    for (int i = 1; i <= 5; ++i) {
        threads.emplace_back([&printer, i]() {
            printer.print("Hello from thread", i);
            printer.print("Second message from thread", i);
        });
    }

    for (auto& t : threads) {
        t.join();
    }
}

// Producer-Consumer pattern with condition variables
template<typename T>
class ThreadSafeQueue {
private:
    std::queue<T> queue;
    std::mutex mtx;
    std::condition_variable condition;

public:
    void push(T item) {
        std::lock_guard<std::mutex> lock(mtx);
        queue.push(std::move(item));
        condition.notify_one();
    }

    T pop() {
        std::unique_lock<std::mutex> lock(mtx);
        condition.wait(lock, [this] { return !queue.empty(); });

        T result = std::move(queue.front());
        queue.pop();
        return result;
    }

    bool tryPop(T& item) {
        std::lock_guard<std::mutex> lock(mtx);
        if (queue.empty()) {
            return false;
        }
        item = std::move(queue.front());
        queue.pop();
        return true;
    }

    size_t size() const {
        std::lock_guard<std::mutex> lock(mtx);
        return queue.size();
    }

    bool empty() const {
        std::lock_guard<std::mutex> lock(mtx);
        return queue.empty();
    }
};

void producer(ThreadSafeQueue<int>& queue, int id, int count) {
    for (int i = 1; i <= count; ++i) {
        int value = id * 1000 + i;
        queue.push(value);
        std::cout << "Producer " << id << " produced: " << value << std::endl;
        std::this_thread::sleep_for(std::chrono::milliseconds(100));
    }
    std::cout << "Producer " << id << " finished" << std::endl;
}

void consumer(ThreadSafeQueue<int>& queue, int id, int count) {
    for (int i = 0; i < count; ++i) {
        int value = queue.pop();
        std::cout << "Consumer " << id << " consumed: " << value << std::endl;
        std::this_thread::sleep_for(std::chrono::milliseconds(150));
    }
    std::cout << "Consumer " << id << " finished" << std::endl;
}

void demonstrateProducerConsumer() {
    std::cout << "\n=== Producer-Consumer Pattern ===" << std::endl;

    ThreadSafeQueue<int> queue;
    const int itemsPerProducer = 3;
    const int numProducers = 2;
    const int numConsumers = 2;
    const int itemsPerConsumer = (itemsPerProducer * numProducers) / numConsumers;

    std::vector<std::thread> threads;

    // Start producers
    for (int i = 1; i <= numProducers; ++i) {
        threads.emplace_back(producer, std::ref(queue), i, itemsPerProducer);
    }

    // Start consumers
    for (int i = 1; i <= numConsumers; ++i) {
        threads.emplace_back(consumer, std::ref(queue), i, itemsPerConsumer);
    }

    // Wait for all threads
    for (auto& t : threads) {
        t.join();
    }

    std::cout << "Remaining items in queue: " << queue.size() << std::endl;
}

int main() {
    demonstrateMutex();
    demonstrateProducerConsumer();
    
    return 0;
}
```

### Atomic Operations

#### Lock-free Programming with Atomics

```cpp
#include <iostream>
#include <atomic>
#include <thread>
#include <vector>
#include <chrono>

class LockFreeStack {
private:
    struct Node {
        std::atomic<Node*> next;
        int data;
        
        Node(int value) : data(value), next(nullptr) {}
    };
    
    std::atomic<Node*> head{nullptr};
    
public:
    void push(int value) {
        Node* newNode = new Node(value);
        Node* prevHead = head.load();
        
        do {
            newNode->next = prevHead;
        } while (!head.compare_exchange_weak(prevHead, newNode));
    }
    
    bool pop(int& result) {
        Node* prevHead = head.load();
        
        while (prevHead && !head.compare_exchange_weak(prevHead, prevHead->next)) {
            // Keep trying
        }
        
        if (!prevHead) {
            return false;
        }
        
        result = prevHead->data;
        delete prevHead;
        return true;
    }
    
    bool empty() const {
        return head.load() == nullptr;
    }
};

void demonstrateAtomicOperations() {
    std::cout << "=== Atomic Operations Demo ===" << std::endl;
    
    // Basic atomic operations
    std::atomic<int> counter{0};
    std::atomic<bool> flag{false};
    
    const int numThreads = 4;
    const int increments = 10000;
    
    std::vector<std::thread> threads;
    
    auto start = std::chrono::high_resolution_clock::now();
    
    // Launch threads that increment counter
    for (int i = 0; i < numThreads; ++i) {
        threads.emplace_back([&counter, increments]() {
            for (int j = 0; j < increments; ++j) {
                counter.fetch_add(1, std::memory_order_relaxed);
            }
        });
    }
    
    // Wait for completion
    for (auto& t : threads) {
        t.join();
    }
    
    auto end = std::chrono::high_resolution_clock::now();
    auto duration = std::chrono::duration_cast<std::chrono::milliseconds>(end - start);
    
    std::cout << "Expected count: " << (numThreads * increments) << std::endl;
    std::cout << "Actual count: " << counter.load() << std::endl;
    std::cout << "Time taken: " << duration.count() << "ms" << std::endl;
    
    // Test lock-free stack
    std::cout << "\nTesting lock-free stack:" << std::endl;
    LockFreeStack stack;
    
    // Push some values
    for (int i = 1; i <= 5; ++i) {
        stack.push(i * 10);
        std::cout << "Pushed: " << (i * 10) << std::endl;
    }
    
    // Pop values
    int value;
    while (stack.pop(value)) {
        std::cout << "Popped: " << value << std::endl;
    }
}

// Memory ordering examples
void demonstrateMemoryOrdering() {
    std::cout << "\n=== Memory Ordering Demo ===" << std::endl;
    
    std::atomic<int> x{0}, y{0};
    std::atomic<int> r1{0}, r2{0};
    
    std::thread t1([&]() {
        x.store(1, std::memory_order_release);
        r1.store(y.load(std::memory_order_acquire));
    });
    
    std::thread t2([&]() {
        y.store(1, std::memory_order_release);
        r2.store(x.load(std::memory_order_acquire));
    });
    
    t1.join();
    t2.join();
    
    std::cout << "r1: " << r1.load() << ", r2: " << r2.load() << std::endl;
    std::cout << "Memory ordering ensures proper synchronization" << std::endl;
}

int main() {
    demonstrateAtomicOperations();
    demonstrateMemoryOrdering();
    
    return 0;
}
```

### Parallel Algorithms

#### C++17 Execution Policies

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <execution>
#include <chrono>
#include <numeric>
#include <random>

void demonstrateParallelAlgorithms() {
    std::cout << "=== Parallel Algorithms Demo ===" << std::endl;
    
    // Create large vector for testing
    const size_t size = 1000000;
    std::vector<int> data(size);
    
    // Fill with random data
    std::random_device rd;
    std::mt19937 gen(rd());
    std::uniform_int_distribution<> dis(1, 1000);
    
    std::generate(data.begin(), data.end(), [&]() { return dis(gen); });
    
    // Test sequential vs parallel sort
    std::vector<int> seqData = data;
    std::vector<int> parData = data;
    
    // Sequential sort
    auto start = std::chrono::high_resolution_clock::now();
    std::sort(seqData.begin(), seqData.end());
    auto end = std::chrono::high_resolution_clock::now();
    auto seqTime = std::chrono::duration_cast<std::chrono::milliseconds>(end - start);
    
    // Parallel sort
    start = std::chrono::high_resolution_clock::now();
    std::sort(std::execution::par, parData.begin(), parData.end());
    end = std::chrono::high_resolution_clock::now();
    auto parTime = std::chrono::duration_cast<std::chrono::milliseconds>(end - start);
    
    std::cout << "Sequential sort time: " << seqTime.count() << "ms" << std::endl;
    std::cout << "Parallel sort time: " << parTime.count() << "ms" << std::endl;
    std::cout << "Speedup: " << (double)seqTime.count() / parTime.count() << "x" << std::endl;
    
    // Verify results are identical
    bool same = std::equal(seqData.begin(), seqData.end(), parData.begin());
    std::cout << "Results identical: " << (same ? "Yes" : "No") << std::endl;
    
    // Other parallel algorithms
    std::vector<int> input(1000000, 1);
    
    // Parallel accumulate
    start = std::chrono::high_resolution_clock::now();
    long long seqSum = std::accumulate(input.begin(), input.end(), 0LL);
    end = std::chrono::high_resolution_clock::now();
    auto seqAccumTime = std::chrono::duration_cast<std::chrono::microseconds>(end - start);
    
    start = std::chrono::high_resolution_clock::now();
    long long parSum = std::reduce(std::execution::par, input.begin(), input.end(), 0LL);
    end = std::chrono::high_resolution_clock::now();
    auto parAccumTime = std::chrono::duration_cast<std::chrono::microseconds>(end - start);
    
    std::cout << "\nAccumulation results:" << std::endl;
    std::cout << "Sequential sum: " << seqSum << " (" << seqAccumTime.count() << "μs)" << std::endl;
    std::cout << "Parallel sum: " << parSum << " (" << parAccumTime.count() << "μs)" << std::endl;
    
    // Parallel transform
    std::vector<int> squares(input.size());
    start = std::chrono::high_resolution_clock::now();
    std::transform(std::execution::par, input.begin(), input.end(), squares.begin(),
                   [](int x) { return x * x; });
    end = std::chrono::high_resolution_clock::now();
    auto transformTime = std::chrono::duration_cast<std::chrono::milliseconds>(end - start);
    
    std::cout << "Parallel transform time: " << transformTime.count() << "ms" << std::endl;
}

int main() {
    demonstrateParallelAlgorithms();
    return 0;
}
```

[Back to top](#-c-documentation)

---

## 🔄 Modern C++ Features

**📊 Chapter 11 of 14**

🎯 **Learning Objectives:**
- Master move semantics and perfect forwarding
- Understand range-based loops and structured bindings
- Learn about modules and coroutines in C++20
- Explore other modern C++ features and best practices

⏱️ **Estimated Reading Time:** 30 minutes

📋 **Prerequisites:** Understanding of templates and object-oriented programming

### Move Semantics

#### Understanding Move Operations

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <utility>
#include <chrono>

class Resource {
private:
    std::vector<int> data;
    std::string name;
    
public:
    // Constructor
    Resource(const std::string& n, size_t size) : name(n), data(size, 42) {
        std::cout << "Resource '" << name << "' created with " << size << " elements" << std::endl;
    }
    
    // Copy constructor
    Resource(const Resource& other) : name(other.name + "_copy"), data(other.data) {
        std::cout << "Resource copied: " << name << std::endl;
    }
    
    // Move constructor
    Resource(Resource&& other) noexcept : name(std::move(other.name)), data(std::move(other.data)) {
        std::cout << "Resource moved: " << name << std::endl;
        other.name = "moved_from";
    }
    
    // Copy assignment
    Resource& operator=(const Resource& other) {
        if (this != &other) {
            name = other.name + "_assigned";
            data = other.data;
            std::cout << "Resource copy-assigned: " << name << std::endl;
        }
        return *this;
    }
    
    // Move assignment
    Resource& operator=(Resource&& other) noexcept {
        if (this != &other) {
            name = std::move(other.name);
            data = std::move(other.data);
            std::cout << "Resource move-assigned: " << name << std::endl;
            other.name = "moved_from";
        }
        return *this;
    }
    
    // Destructor
    ~Resource() {
        std::cout << "Resource destroyed: " << name << std::endl;
    }
    
    const std::string& getName() const { return name; }
    size_t getSize() const { return data.size(); }
};

void demonstrateMoveSemantics() {
    std::cout << "=== Move Semantics Demo ===" << std::endl;
    
    // Create resource
    Resource res1("Original", 1000000);
    
    // Copy vs Move timing
    auto start = std::chrono::high_resolution_clock::now();
    Resource res2 = res1;  // Copy constructor
    auto end = std::chrono::high_resolution_clock::now();
    auto copyTime = std::chrono::duration_cast<std::chrono::microseconds>(end - start);
    
    start = std::chrono::high_resolution_clock::now();
    Resource res3 = std::move(res1);  // Move constructor
    end = std::chrono::high_resolution_clock::now();
    auto moveTime = std::chrono::duration_cast<std::chrono::microseconds>(end - start);
    
    std::cout << "Copy time: " << copyTime.count() << "μs" << std::endl;
    std::cout << "Move time: " << moveTime.count() << "μs" << std::endl;
    std::cout << "Original resource after move: " << res1.getName() << std::endl;
}

// Perfect forwarding example
template<typename T>
void processValue(T&& value) {
    std::cout << "Processing: " << value << std::endl;
    // Forward the value to another function
    someFunction(std::forward<T>(value));
}

void someFunction(const std::string& s) {
    std::cout << "someFunction called with lvalue: " << s << std::endl;
}

void someFunction(std::string&& s) {
    std::cout << "someFunction called with rvalue: " << s << std::endl;
}

int main() {
    demonstrateMoveSemantics();
    
    // Perfect forwarding
    std::string str = "Hello";
    processValue(str);                    // Forwards as lvalue
    processValue(std::string("World"));   // Forwards as rvalue
    processValue("Temporary");            // Forwards as rvalue
    
    return 0;
}
```

### Range-based Loops

#### Modern Iteration Techniques

```cpp
#include <iostream>
#include <vector>
#include <map>
#include <string>
#include <ranges>

void demonstrateBasicRangeLoops() {
    std::cout << "=== Basic Range-based Loops ===" << std::endl;
    
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    
    // Basic range-based for loop
    std::cout << "Numbers: ";
    for (const auto& num : numbers) {
        std::cout << num << " ";
    }
    std::cout << std::endl;
    
    // Modifying elements
    std::cout << "Doubling numbers: ";
    for (auto& num : numbers) {
        num *= 2;
        std::cout << num << " ";
    }
    std::cout << std::endl;
    
    // With maps
    std::map<std::string, int> ages = {{"Alice", 25}, {"Bob", 30}, {"Charlie", 35}};
    
    std::cout << "Ages:" << std::endl;
    for (const auto& [name, age] : ages) {  // C++17 structured binding
        std::cout << name << ": " << age << " years old" << std::endl;
    }
}

void demonstrateRangesLibrary() {
    std::cout << "\n=== C++20 Ranges Library ===" << std::endl;
    
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    
    // Filter and transform with ranges
    auto evenSquares = numbers 
        | std::views::filter([](int n) { return n % 2 == 0; })
        | std::views::transform([](int n) { return n * n; });
    
    std::cout << "Even numbers squared: ";
    for (int value : evenSquares) {
        std::cout << value << " ";
    }
    std::cout << std::endl;
    
    // Take first N elements
    auto firstFive = numbers | std::views::take(5);
    std::cout << "First 5 elements: ";
    for (int value : firstFive) {
        std::cout << value << " ";
    }
    std::cout << std::endl;
    
    // Reverse view
    auto reversed = numbers | std::views::reverse;
    std::cout << "Reversed: ";
    for (int value : reversed) {
        std::cout << value << " ";
    }
    std::cout << std::endl;
}

int main() {
    demonstrateBasicRangeLoops();
    demonstrateRangesLibrary();
    
    return 0;
}
```

### Structured Bindings

#### C++17 Structured Bindings

```cpp
#include <iostream>
#include <tuple>
#include <map>
#include <array>
#include <utility>

struct Point {
    double x, y, z;
};

std::tuple<int, std::string, double> getPersonInfo() {
    return std::make_tuple(25, "Alice", 175.5);
}

std::pair<bool, std::string> validateInput(const std::string& input) {
    if (input.empty()) {
        return {false, "Input cannot be empty"};
    }
    return {true, "Input is valid"};
}

void demonstrateStructuredBindings() {
    std::cout << "=== Structured Bindings Demo ===" << std::endl;
    
    // With tuples
    auto [age, name, height] = getPersonInfo();
    std::cout << "Person: " << name << ", Age: " << age << ", Height: " << height << "cm" << std::endl;
    
    // With pairs
    auto [isValid, message] = validateInput("Hello World");
    std::cout << "Validation result: " << (isValid ? "Valid" : "Invalid") << " - " << message << std::endl;
    
    // With structs
    Point p{1.5, 2.5, 3.5};
    auto [x, y, z] = p;
    std::cout << "Point coordinates: (" << x << ", " << y << ", " << z << ")" << std::endl;
    
    // With arrays
    std::array<int, 3> arr = {10, 20, 30};
    auto [first, second, third] = arr;
    std::cout << "Array elements: " << first << ", " << second << ", " << third << std::endl;
    
    // With maps (in range-based for loop)
    std::map<std::string, int> scores = {{"Alice", 95}, {"Bob", 87}, {"Charlie", 92}};
    std::cout << "Scores:" << std::endl;
    for (const auto& [student, score] : scores) {
        std::cout << student << ": " << score << std::endl;
    }
}

int main() {
    demonstrateStructuredBindings();
    return 0;
}
```

### Modules (C++20)

#### Modern Code Organization

```cpp
// math_utils.cppm (module interface)
export module math_utils;

import <iostream>;

export namespace MathUtils {
    // Exported functions
    int add(int a, int b);
    int multiply(int a, int b);
    
    // Exported class
    class Calculator {
    private:
        double result = 0.0;
        
    public:
        void add(double value) { result += value; }
        void multiply(double value) { result *= value; }
        void clear() { result = 0.0; }
        double getResult() const { return result; }
        
        void display() const {
            std::cout << "Calculator result: " << result << std::endl;
        }
    };
    
    // Exported template
    template<typename T>
    T maximum(T a, T b) {
        return (a > b) ? a : b;
    }
}

// Implementation (can be in same file or separate .cpp file)
namespace MathUtils {
    int add(int a, int b) {
        return a + b;
    }
    
    int multiply(int a, int b) {
        return a * b;
    }
}

// main.cpp (module consumer)
import math_utils;
import <iostream>;

int main() {
    std::cout << "=== C++20 Modules Demo ===" << std::endl;
    
    // Use exported functions
    int sum = MathUtils::add(5, 3);
    int product = MathUtils::multiply(4, 7);
    
    std::cout << "5 + 3 = " << sum << std::endl;
    std::cout << "4 * 7 = " << product << std::endl;
    
    // Use exported class
    MathUtils::Calculator calc;
    calc.add(10.5);
    calc.multiply(2.0);
    calc.display();
    
    // Use exported template
    auto maxInt = MathUtils::maximum(42, 17);
    auto maxDouble = MathUtils::maximum(3.14, 2.71);
    
    std::cout << "max(42, 17) = " << maxInt << std::endl;
    std::cout << "max(3.14, 2.71) = " << maxDouble << std::endl;
    
    return 0;
}
```

### Coroutines (C++20)

#### Asynchronous Programming with Coroutines

```cpp
#include <iostream>
#include <coroutine>
#include <thread>
#include <chrono>

// Simple generator coroutine
template<typename T>
class Generator {
public:
    struct promise_type {
        T current_value;
        
        auto get_return_object() {
            return Generator{std::coroutine_handle<promise_type>::from_promise(*this)};
        }
        
        auto initial_suspend() { return std::suspend_always{}; }
        auto final_suspend() noexcept { return std::suspend_always{}; }
        void unhandled_exception() { std::terminate(); }
        
        auto yield_value(T value) {
            current_value = value;
            return std::suspend_always{};
        }
        
        void return_void() {}
    };
    
    std::coroutine_handle<promise_type> coro;
    
    explicit Generator(std::coroutine_handle<promise_type> h) : coro(h) {}
    ~Generator() { if (coro) coro.destroy(); }
    
    // Move-only
    Generator(const Generator&) = delete;
    Generator& operator=(const Generator&) = delete;
    Generator(Generator&& other) noexcept : coro(other.coro) { other.coro = {}; }
    Generator& operator=(Generator&& other) noexcept {
        if (this != &other) {
            if (coro) coro.destroy();
            coro = other.coro;
            other.coro = {};
        }
        return *this;
    }
    
    bool next() {
        coro.resume();
        return !coro.done();
    }
    
    T value() {
        return coro.promise().current_value;
    }
};

// Coroutine that generates Fibonacci numbers
Generator<int> fibonacci() {
    int a = 0, b = 1;
    
    while (true) {
        co_yield a;
        auto next = a + b;
        a = b;
        b = next;
    }
}

// Coroutine that generates even numbers
Generator<int> evenNumbers() {
    for (int i = 0; ; i += 2) {
        co_yield i;
    }
}

// Task coroutine for async operations
class Task {
public:
    struct promise_type {
        auto get_return_object() {
            return Task{std::coroutine_handle<promise_type>::from_promise(*this)};
        }
        
        auto initial_suspend() { return std::suspend_never{}; }
        auto final_suspend() noexcept { return std::suspend_never{}; }
        void unhandled_exception() { std::terminate(); }
        void return_void() {}
        
        // Awaiter for delays
        auto await_transform(std::chrono::milliseconds delay) {
            struct Awaiter {
                std::chrono::milliseconds delay;
                
                bool await_ready() { return false; }
                void await_suspend(std::coroutine_handle<> handle) {
                    std::thread([handle, delay = this->delay]() {
                        std::this_thread::sleep_for(delay);
                        handle.resume();
                    }).detach();
                }
                void await_resume() {}
            };
            
            return Awaiter{delay};
        }
    };
    
    std::coroutine_handle<promise_type> coro;
    
    explicit Task(std::coroutine_handle<promise_type> h) : coro(h) {}
    ~Task() { if (coro) coro.destroy(); }
    
    // Move-only
    Task(const Task&) = delete;
    Task& operator=(const Task&) = delete;
    Task(Task&& other) noexcept : coro(other.coro) { other.coro = {}; }
    Task& operator=(Task&& other) noexcept {
        if (this != &other) {
            if (coro) coro.destroy();
            coro = other.coro;
            other.coro = {};
        }
        return *this;
    }
};

// Async task example
Task asyncTask(int id) {
    std::cout << "Task " << id << " started" << std::endl;
    
    co_await std::chrono::milliseconds(1000);
    std::cout << "Task " << id << " after 1 second" << std::endl;
    
    co_await std::chrono::milliseconds(500);
    std::cout << "Task " << id << " completed" << std::endl;
}

void demonstrateCoroutines() {
    std::cout << "=== C++20 Coroutines Demo ===" << std::endl;
    
    // Generator example
    std::cout << "First 10 Fibonacci numbers:" << std::endl;
    auto fib = fibonacci();
    for (int i = 0; i < 10; ++i) {
        fib.next();
        std::cout << fib.value() << " ";
    }
    std::cout << std::endl;
    
    std::cout << "First 10 even numbers:" << std::endl;
    auto evens = evenNumbers();
    for (int i = 0; i < 10; ++i) {
        evens.next();
        std::cout << evens.value() << " ";
    }
    std::cout << std::endl;
    
    // Async task example
    std::cout << "Starting async tasks..." << std::endl;
    auto task1 = asyncTask(1);
    auto task2 = asyncTask(2);
    
    // Wait for tasks to complete
    std::this_thread::sleep_for(std::chrono::seconds(2));
    std::cout << "All tasks completed" << std::endl;
}

int main() {
    demonstrateCoroutines();
    return 0;
}
```

[Back to top](#-c-documentation)

---

## 🚀 Real-World Applications

**📊 Chapter 13 of 14**

🎯 **Learning Objectives:**
- Build practical projects using C++ concepts
- Understand industry use cases and applications
- Learn about popular frameworks and libraries
- Explore performance optimization techniques

⏱️ **Estimated Reading Time:** 45 minutes

### Project 1: File Manager

#### Complete File Management System

```cpp
#include <iostream>
#include <filesystem>
#include <string>
#include <vector>
#include <fstream>
#include <chrono>
#include <algorithm>
#include <iomanip>

namespace fs = std::filesystem;

class FileManager {
private:
    fs::path currentPath;

public:
    FileManager() : currentPath(fs::current_path()) {}

    void listDirectory(const fs::path& path = "") {
        fs::path targetPath = path.empty() ? currentPath : path;

        std::cout << "\n=== Directory Listing: " << targetPath << " ===" << std::endl;
        std::cout << std::left << std::setw(20) << "Name"
                  << std::setw(10) << "Type"
                  << std::setw(15) << "Size"
                  << std::setw(20) << "Last Modified" << std::endl;
        std::cout << std::string(65, '-') << std::endl;

        try {
            std::vector<fs::directory_entry> entries;
            for (const auto& entry : fs::directory_iterator(targetPath)) {
                entries.push_back(entry);
            }

            // Sort entries: directories first, then files
            std::sort(entries.begin(), entries.end(), [](const auto& a, const auto& b) {
                if (a.is_directory() && !b.is_directory()) return true;
                if (!a.is_directory() && b.is_directory()) return false;
                return a.path().filename() < b.path().filename();
            });

            for (const auto& entry : entries) {
                std::string name = entry.path().filename().string();
                std::string type = entry.is_directory() ? "DIR" : "FILE";

                std::string size = "-";
                if (entry.is_regular_file()) {
                    auto fileSize = fs::file_size(entry);
                    size = formatSize(fileSize);
                }

                auto ftime = fs::last_write_time(entry);
                auto sctp = std::chrono::time_point_cast<std::chrono::system_clock::duration>(
                    ftime - fs::file_time_type::clock::now() + std::chrono::system_clock::now());
                auto cftime = std::chrono::system_clock::to_time_t(sctp);

                std::cout << std::left << std::setw(20) << name.substr(0, 19)
                          << std::setw(10) << type
                          << std::setw(15) << size
                          << std::put_time(std::localtime(&cftime), "%Y-%m-%d %H:%M") << std::endl;
            }
        } catch (const fs::filesystem_error& e) {
            std::cout << "Error: " << e.what() << std::endl;
        }
    }

    bool changeDirectory(const std::string& path) {
        try {
            fs::path newPath = path.empty() ? fs::current_path() : fs::path(path);
            if (!fs::exists(newPath) || !fs::is_directory(newPath)) {
                std::cout << "Directory not found: " << path << std::endl;
                return false;
            }

            currentPath = fs::canonical(newPath);
            std::cout << "Changed directory to: " << currentPath << std::endl;
            return true;
        } catch (const fs::filesystem_error& e) {
            std::cout << "Error changing directory: " << e.what() << std::endl;
            return false;
        }
    }

    bool createDirectory(const std::string& name) {
        try {
            fs::path newDir = currentPath / name;
            if (fs::create_directory(newDir)) {
                std::cout << "Directory created: " << newDir << std::endl;
                return true;
            } else {
                std::cout << "Failed to create directory (may already exist): " << name << std::endl;
                return false;
            }
        } catch (const fs::filesystem_error& e) {
            std::cout << "Error creating directory: " << e.what() << std::endl;
            return false;
        }
    }

    bool deleteFile(const std::string& filename) {
        try {
            fs::path filePath = currentPath / filename;
            if (!fs::exists(filePath)) {
                std::cout << "File not found: " << filename << std::endl;
                return false;
            }

            if (fs::remove(filePath)) {
                std::cout << "Deleted: " << filename << std::endl;
                return true;
            } else {
                std::cout << "Failed to delete: " << filename << std::endl;
                return false;
            }
        } catch (const fs::filesystem_error& e) {
            std::cout << "Error deleting file: " << e.what() << std::endl;
            return false;
        }
    }

    void searchFiles(const std::string& pattern) {
        std::cout << "\n=== Search Results for: " << pattern << " ===" << std::endl;

        try {
            for (const auto& entry : fs::recursive_directory_iterator(currentPath)) {
                if (entry.is_regular_file()) {
                    std::string filename = entry.path().filename().string();
                    if (filename.find(pattern) != std::string::npos) {
                        auto relativePath = fs::relative(entry.path(), currentPath);
                        std::cout << relativePath << std::endl;
                    }
                }
            }
        } catch (const fs::filesystem_error& e) {
            std::cout << "Error during search: " << e.what() << std::endl;
        }
    }

    void copyFile(const std::string& source, const std::string& destination) {
        try {
            fs::path srcPath = currentPath / source;
            fs::path destPath = currentPath / destination;

            if (!fs::exists(srcPath)) {
                std::cout << "Source file not found: " << source << std::endl;
                return;
            }

            fs::copy_file(srcPath, destPath, fs::copy_options::overwrite_existing);
            std::cout << "File copied from " << source << " to " << destination << std::endl;

        } catch (const fs::filesystem_error& e) {
            std::cout << "Error copying file: " << e.what() << std::endl;
        }
    }

    fs::path getCurrentPath() const { return currentPath; }

private:
    std::string formatSize(std::uintmax_t size) {
        const char* units[] = {"B", "KB", "MB", "GB", "TB"};
        int unitIndex = 0;
        double dsize = static_cast<double>(size);

        while (dsize >= 1024.0 && unitIndex < 4) {
            dsize /= 1024.0;
            ++unitIndex;
        }

        std::ostringstream oss;
        oss << std::fixed << std::setprecision(1) << dsize << units[unitIndex];
        return oss.str();
    }
};

void showHelp() {
    std::cout << "\n=== File Manager Commands ===" << std::endl;
    std::cout << "ls [path]          - List directory contents" << std::endl;
    std::cout << "cd <path>          - Change directory" << std::endl;
    std::cout << "mkdir <name>       - Create directory" << std::endl;
    std::cout << "rm <filename>      - Delete file" << std::endl;
    std::cout << "search <pattern>   - Search for files" << std::endl;
    std::cout << "copy <src> <dest>  - Copy file" << std::endl;
    std::cout << "pwd                - Show current directory" << std::endl;
    std::cout << "help               - Show this help" << std::endl;
    std::cout << "exit               - Exit the program" << std::endl;
}

int main() {
    FileManager fm;
    std::string command, arg1, arg2;

    std::cout << "=== C++ File Manager ===" << std::endl;
    showHelp();

    while (true) {
        std::cout << "\n[" << fm.getCurrentPath().filename() << "]$ ";
        std::getline(std::cin, command);

        std::istringstream iss(command);
        iss >> command >> arg1 >> arg2;

        if (command == "exit") {
            break;
        } else if (command == "ls") {
            fm.listDirectory(arg1);
        } else if (command == "cd") {
            fm.changeDirectory(arg1);
        } else if (command == "mkdir") {
            fm.createDirectory(arg1);
        } else if (command == "rm") {
            fm.deleteFile(arg1);
        } else if (command == "search") {
            fm.searchFiles(arg1);
        } else if (command == "copy") {
            fm.copyFile(arg1, arg2);
        } else if (command == "pwd") {
            std::cout << fm.getCurrentPath() << std::endl;
        } else if (command == "help") {
            showHelp();
        } else if (!command.empty()) {
            std::cout << "Unknown command: " << command << std::endl;
        }
    }

    std::cout << "Goodbye!" << std::endl;
    return 0;
}
```

### Project 2: HTTP Client

#### Complete HTTP Client Implementation

```cpp
#include <iostream>
#include <string>
#include <map>
#include <vector>
#include <sstream>
#include <memory>
#include <functional>
#include <thread>
#include <chrono>

#ifdef _WIN32
#include <winsock2.h>
#include <ws2tcpip.h>
#pragma comment(lib, "ws2_32.lib")
#else
#include <sys/socket.h>
#include <netinet/in.h>
#include <arpa/inet.h>
#include <netdb.h>
#include <unistd.h>
#endif

class HTTPResponse {
public:
    int statusCode;
    std::string statusMessage;
    std::map<std::string, std::string> headers;
    std::string body;
    
    HTTPResponse() : statusCode(0) {}
    
    bool isSuccess() const {
        return statusCode >= 200 && statusCode < 300;
    }
    
    void print() const {
        std::cout << "Status: " << statusCode << " " << statusMessage << std::endl;
        std::cout << "Headers:" << std::endl;
        for (const auto& [key, value] : headers) {
            std::cout << "  " << key << ": " << value << std::endl;
        }
        std::cout << "Body (" << body.length() << " bytes):" << std::endl;
        std::cout << body << std::endl;
    }
};

class HTTPClient {
private:
    std::string userAgent = "C++HTTPClient/1.0";
    int timeout = 30;
    
#ifdef _WIN32
    bool wsaInitialized = false;
#endif

public:
    HTTPClient() {
#ifdef _WIN32
        WSADATA wsaData;
        if (WSAStartup(MAKEWORD(2, 2), &wsaData) == 0) {
            wsaInitialized = true;
        }
#endif
    }
    
    ~HTTPClient() {
#ifdef _WIN32
        if (wsaInitialized) {
            WSACleanup();
        }
#endif
    }
    
    void setUserAgent(const std::string& ua) {
        userAgent = ua;
    }
    
    void setTimeout(int seconds) {
        timeout = seconds;
    }
    
    HTTPResponse get(const std::string& url) {
        return request("GET", url, {}, "");
    }
    
    HTTPResponse post(const std::string& url, const std::string& data, 
                     const std::map<std::string, std::string>& customHeaders = {}) {
        auto headers = customHeaders;
        headers["Content-Type"] = "application/x-www-form-urlencoded";
        headers["Content-Length"] = std::to_string(data.length());
        return request("POST", url, headers, data);
    }
    
    HTTPResponse request(const std::string& method, const std::string& url,
                        const std::map<std::string, std::string>& customHeaders = {},
                        const std::string& body = "") {
        HTTPResponse response;
        
        // Parse URL
        auto urlParts = parseURL(url);
        if (urlParts.host.empty()) {
            response.statusCode = -1;
            response.statusMessage = "Invalid URL";
            return response;
        }
        
        // Create socket
        int sock = socket(AF_INET, SOCK_STREAM, 0);
        if (sock < 0) {
            response.statusCode = -1;
            response.statusMessage = "Failed to create socket";
            return response;
        }
        
        // Set timeout
        struct timeval tv;
        tv.tv_sec = timeout;
        tv.tv_usec = 0;
        setsockopt(sock, SOL_SOCKET, SO_RCVTIMEO, (const char*)&tv, sizeof(tv));
        setsockopt(sock, SOL_SOCKET, SO_SNDTIMEO, (const char*)&tv, sizeof(tv));
        
        // Resolve host
        struct hostent* host_entry = gethostbyname(urlParts.host.c_str());
        if (!host_entry) {
            response.statusCode = -1;
            response.statusMessage = "Host resolution failed";
#ifdef _WIN32
            closesocket(sock);
#else
            close(sock);
#endif
            return response;
        }
        
        // Connect
        struct sockaddr_in server_addr;
        server_addr.sin_family = AF_INET;
        server_addr.sin_port = htons(urlParts.port);
        server_addr.sin_addr = *((struct in_addr*)host_entry->h_addr);
        
        if (connect(sock, (struct sockaddr*)&server_addr, sizeof(server_addr)) < 0) {
            response.statusCode = -1;
            response.statusMessage = "Connection failed";
#ifdef _WIN32
            closesocket(sock);
#else
            close(sock);
#endif
            return response;
        }
        
        // Build HTTP request
        std::ostringstream request;
        request << method << " " << urlParts.path << " HTTP/1.1\r\n";
        request << "Host: " << urlParts.host << "\r\n";
        request << "User-Agent: " << userAgent << "\r\n";
        request << "Connection: close\r\n";
        
        // Add custom headers
        for (const auto& [key, value] : customHeaders) {
            request << key << ": " << value << "\r\n";
        }
        
        request << "\r\n";
        if (!body.empty()) {
            request << body;
        }
        
        std::string requestStr = request.str();
        
        // Send request
        if (send(sock, requestStr.c_str(), requestStr.length(), 0) < 0) {
            response.statusCode = -1;
            response.statusMessage = "Failed to send request";
#ifdef _WIN32
            closesocket(sock);
#else
            close(sock);
#endif
            return response;
        }
        
        // Receive response
        std::string responseStr;
        char buffer[4096];
        int bytesReceived;
        
        while ((bytesReceived = recv(sock, buffer, sizeof(buffer) - 1, 0)) > 0) {
            buffer[bytesReceived] = '\0';
            responseStr += buffer;
        }
        
#ifdef _WIN32
        closesocket(sock);
#else
        close(sock);
#endif
        
        // Parse response
        parseHTTPResponse(responseStr, response);
        
        return response;
    }

private:
    struct URLParts {
        std::string protocol;
        std::string host;
        int port;
        std::string path;
    };
    
    URLParts parseURL(const std::string& url) {
        URLParts parts;
        
        // Find protocol
        size_t protocolEnd = url.find("://");
        if (protocolEnd == std::string::npos) {
            return parts; // Invalid URL
        }
        
        parts.protocol = url.substr(0, protocolEnd);
        
        // Default ports
        if (parts.protocol == "http") {
            parts.port = 80;
        } else if (parts.protocol == "https") {
            parts.port = 443;
        } else {
            parts.port = 80;
        }
        
        // Find host and path
        size_t hostStart = protocolEnd + 3;
        size_t pathStart = url.find('/', hostStart);
        
        if (pathStart == std::string::npos) {
            parts.host = url.substr(hostStart);
            parts.path = "/";
        } else {
            parts.host = url.substr(hostStart, pathStart - hostStart);
            parts.path = url.substr(pathStart);
        }
        
        // Check for port in host
        size_t portPos = parts.host.find(':');
        if (portPos != std::string::npos) {
            parts.port = std::stoi(parts.host.substr(portPos + 1));
            parts.host = parts.host.substr(0, portPos);
        }
        
        return parts;
    }
    
    void parseHTTPResponse(const std::string& responseStr, HTTPResponse& response) {
        std::istringstream stream(responseStr);
        std::string line;
        
        // Parse status line
        if (std::getline(stream, line)) {
            std::istringstream statusStream(line);
            std::string httpVersion;
            statusStream >> httpVersion >> response.statusCode;
            std::getline(statusStream, response.statusMessage);
            // Remove leading space and carriage return
            if (!response.statusMessage.empty() && response.statusMessage[0] == ' ') {
                response.statusMessage = response.statusMessage.substr(1);
            }
            if (!response.statusMessage.empty() && response.statusMessage.back() == '\r') {
                response.statusMessage.pop_back();
            }
        }
        
        // Parse headers
        while (std::getline(stream, line) && line != "\r") {
            size_t colonPos = line.find(':');
            if (colonPos != std::string::npos) {
                std::string key = line.substr(0, colonPos);
                std::string value = line.substr(colonPos + 1);
                
                // Trim whitespace
                if (!value.empty() && value[0] == ' ') {
                    value = value.substr(1);
                }
                if (!value.empty() && value.back() == '\r') {
                    value.pop_back();
                }
                
                response.headers[key] = value;
            }
        }
        
        // Parse body
        std::string bodyLine;
        while (std::getline(stream, bodyLine)) {
            response.body += bodyLine + "\n";
        }
        
        // Remove trailing newline
        if (!response.body.empty() && response.body.back() == '\n') {
            response.body.pop_back();
        }
    }
};

// HTTP Client usage examples
void demonstrateHTTPClient() {
    std::cout << "=== HTTP Client Demo ===" << std::endl;
    
    HTTPClient client;
    client.setUserAgent("C++ Demo Client/1.0");
    client.setTimeout(10);
    
    // Simple GET request
    std::cout << "Making GET request to httpbin.org..." << std::endl;
    auto response = client.get("http://httpbin.org/get");
    
    if (response.isSuccess()) {
        std::cout << "✓ Request successful!" << std::endl;
        response.print();
    } else {
        std::cout << "✗ Request failed: " << response.statusMessage << std::endl;
    }
    
    std::cout << "\n" << std::string(50, '-') << std::endl;
    
    // POST request with data
    std::cout << "Making POST request..." << std::endl;
    std::string postData = "name=John&age=30&city=New York";
    auto postResponse = client.post("http://httpbin.org/post", postData);
    
    if (postResponse.isSuccess()) {
        std::cout << "✓ POST request successful!" << std::endl;
        postResponse.print();
    } else {
        std::cout << "✗ POST request failed: " << postResponse.statusMessage << std::endl;
    }
}

int main() {
    demonstrateHTTPClient();
    return 0;
}
```

### Project 3: Game Engine Basics

#### Simple 2D Game Engine Framework

```cpp
#include <iostream>
#include <vector>
#include <memory>
#include <chrono>
#include <algorithm>
#include <cmath>
#include <map>
#include <functional>

// Forward declarations
class GameObject;
class Component;
class Transform;
class Renderer;
class Physics;

// Vector2D utility class
struct Vector2D {
    float x, y;
    
    Vector2D(float x = 0, float y = 0) : x(x), y(y) {}
    
    Vector2D operator+(const Vector2D& other) const {
        return Vector2D(x + other.x, y + other.y);
    }
    
    Vector2D operator-(const Vector2D& other) const {
        return Vector2D(x - other.x, y - other.y);
    }
    
    Vector2D operator*(float scalar) const {
        return Vector2D(x * scalar, y * scalar);
    }
    
    float magnitude() const {
        return std::sqrt(x * x + y * y);
    }
    
    Vector2D normalized() const {
        float mag = magnitude();
        return mag > 0 ? Vector2D(x / mag, y / mag) : Vector2D(0, 0);
    }
    
    float dot(const Vector2D& other) const {
        return x * other.x + y * other.y;
    }
};

// Base Component class
class Component {
protected:
    GameObject* gameObject = nullptr;
    
public:
    virtual ~Component() = default;
    virtual void start() {}
    virtual void update(float deltaTime) {}
    virtual void render() {}
    
    void setGameObject(GameObject* obj) { gameObject = obj; }
    GameObject* getGameObject() const { return gameObject; }
};

// Transform component
class Transform : public Component {
public:
    Vector2D position{0, 0};
    Vector2D scale{1, 1};
    float rotation = 0.0f;
    
    Transform(Vector2D pos = Vector2D(0, 0)) : position(pos) {}
    
    void translate(const Vector2D& delta) {
        position = position + delta;
    }
    
    void rotate(float angle) {
        rotation += angle;
    }
    
    void setPosition(const Vector2D& pos) {
        position = pos;
    }
    
    Vector2D getForward() const {
        float rad = rotation * M_PI / 180.0f;
        return Vector2D(std::cos(rad), std::sin(rad));
    }
};

// Renderer component
class Renderer : public Component {
public:
    char symbol = '#';
    int width = 1;
    int height = 1;
    
    Renderer(char sym = '#', int w = 1, int h = 1) 
        : symbol(sym), width(w), height(h) {}
    
    void render() override {
        auto* transform = gameObject->getComponent<Transform>();
        if (transform) {
            int x = static_cast<int>(transform->position.x);
            int y = static_cast<int>(transform->position.y);
            
            // Simple console rendering
            std::cout << "Rendering " << symbol << " at (" << x << ", " << y << ")" << std::endl;
        }
    }
};

// Physics component
class Physics : public Component {
public:
    Vector2D velocity{0, 0};
    Vector2D acceleration{0, 0};
    float mass = 1.0f;
    float drag = 0.98f;
    bool useGravity = false;
    
    Physics(float m = 1.0f) : mass(m) {}
    
    void update(float deltaTime) override {
        auto* transform = gameObject->getComponent<Transform>();
        if (!transform) return;
        
        // Apply gravity
        if (useGravity) {
            acceleration = acceleration + Vector2D(0, 9.81f * mass);
        }
        
        // Update velocity
        velocity = velocity + acceleration * deltaTime;
        
        // Apply drag
        velocity = velocity * drag;
        
        // Update position
        transform->translate(velocity * deltaTime);
        
        // Reset acceleration
        acceleration = Vector2D(0, 0);
    }
    
    void addForce(const Vector2D& force) {
        acceleration = acceleration + force * (1.0f / mass);
    }
    
    void setVelocity(const Vector2D& vel) {
        velocity = vel;
    }
};

// GameObject class
class GameObject {
private:
    std::vector<std::unique_ptr<Component>> components;
    bool active = true;
    std::string name;
    
public:
    GameObject(const std::string& objName = "GameObject") : name(objName) {
        // Every GameObject has a Transform by default
        addComponent<Transform>();
    }
    
    virtual ~GameObject() = default;
    
    template<typename T, typename... Args>
    T* addComponent(Args&&... args) {
        auto component = std::make_unique<T>(std::forward<Args>(args)...);
        T* ptr = component.get();
        component->setGameObject(this);
        components.push_back(std::move(component));
        return ptr;
    }
    
    template<typename T>
    T* getComponent() const {
        for (const auto& component : components) {
            if (auto* ptr = dynamic_cast<T*>(component.get())) {
                return ptr;
            }
        }
        return nullptr;
    }
    
    template<typename T>
    bool removeComponent() {
        auto it = std::find_if(components.begin(), components.end(),
            [](const std::unique_ptr<Component>& comp) {
                return dynamic_cast<T*>(comp.get()) != nullptr;
            });
        
        if (it != components.end()) {
            components.erase(it);
            return true;
        }
        return false;
    }
    
    virtual void start() {
        for (auto& component : components) {
            component->start();
        }
    }
    
    virtual void update(float deltaTime) {
        if (!active) return;
        
        for (auto& component : components) {
            component->update(deltaTime);
        }
    }
    
    virtual void render() {
        if (!active) return;
        
        for (auto& component : components) {
            component->render();
        }
    }
    
    bool isActive() const { return active; }
    void setActive(bool state) { active = state; }
    const std::string& getName() const { return name; }
    void setName(const std::string& newName) { name = newName; }
};

// Input manager
class InputManager {
private:
    std::map<char, bool> keyStates;
    std::map<char, bool> prevKeyStates;
    
public:
    void updateInput() {
        prevKeyStates = keyStates;
        
        // Simulate input (in real implementation, you'd read from keyboard/mouse)
        // For demo purposes, we'll just simulate some key presses
        static int counter = 0;
        counter++;
        
        keyStates['w'] = (counter % 100 < 50);
        keyStates['a'] = (counter % 80 < 20);
        keyStates['d'] = (counter % 90 < 30);
    }
    
    bool isKeyPressed(char key) const {
        auto it = keyStates.find(key);
        return it != keyStates.end() ? it->second : false;
    }
    
    bool isKeyJustPressed(char key) const {
        bool current = isKeyPressed(key);
        auto it = prevKeyStates.find(key);
        bool previous = it != prevKeyStates.end() ? it->second : false;
        return current && !previous;
    }
};

// Game Engine class
class GameEngine {
private:
    std::vector<std::unique_ptr<GameObject>> gameObjects;
    InputManager inputManager;
    bool running = true;
    float targetFPS = 60.0f;
    
    std::chrono::high_resolution_clock::time_point lastFrameTime;
    
public:
    GameEngine() {
        lastFrameTime = std::chrono::high_resolution_clock::now();
    }
    
    void addGameObject(std::unique_ptr<GameObject> obj) {
        obj->start();
        gameObjects.push_back(std::move(obj));
    }
    
    template<typename T, typename... Args>
    T* createGameObject(Args&&... args) {
        auto obj = std::make_unique<T>(std::forward<Args>(args)...);
        T* ptr = obj.get();
        addGameObject(std::move(obj));
        return ptr;
    }
    
    void removeGameObject(GameObject* obj) {
        auto it = std::find_if(gameObjects.begin(), gameObjects.end(),
            [obj](const std::unique_ptr<GameObject>& ptr) {
                return ptr.get() == obj;
            });
        
        if (it != gameObjects.end()) {
            gameObjects.erase(it);
        }
    }
    
    float calculateDeltaTime() {
        auto currentTime = std::chrono::high_resolution_clock::now();
        float deltaTime = std::chrono::duration<float>(currentTime - lastFrameTime).count();
        lastFrameTime = currentTime;
        
        // Cap delta time to prevent large jumps
        return std::min(deltaTime, 1.0f / 30.0f);
    }
    
    void update() {
        float deltaTime = calculateDeltaTime();
        
        inputManager.updateInput();
        
        // Update all game objects
        for (auto& obj : gameObjects) {
            obj->update(deltaTime);
        }
        
        // Remove inactive objects
        gameObjects.erase(
            std::remove_if(gameObjects.begin(), gameObjects.end(),
                [](const std::unique_ptr<GameObject>& obj) {
                    return !obj->isActive();
                }),
            gameObjects.end());
    }
    
    void render() {
        // Clear screen (simplified)
        system("clear");  // On Windows, use system("cls")
        
        std::cout << "=== Game Frame ===" << std::endl;
        
        // Render all game objects
        for (auto& obj : gameObjects) {
            obj->render();
        }
        
        std::cout << "Active Objects: " << gameObjects.size() << std::endl;
    }
    
    void run() {
        std::cout << "Starting Game Engine..." << std::endl;
        
        int frameCount = 0;
        const int maxFrames = 100;  // Limit for demo
        
        while (running && frameCount < maxFrames) {
            update();
            render();
            
            frameCount++;
            
            // Simple frame rate limiting
            std::this_thread::sleep_for(std::chrono::milliseconds(16)); // ~60 FPS
        }
        
        std::cout << "Game Engine stopped." << std::endl;
    }
    
    void stop() {
        running = false;
    }
    
    InputManager& getInputManager() { return inputManager; }
};

// Example game objects
class Player : public GameObject {
public:
    Player() : GameObject("Player") {
        auto* renderer = addComponent<Renderer>('P', 1, 1);
        auto* physics = addComponent<Physics>(1.0f);
        physics->drag = 0.9f;
    }
    
    void update(float deltaTime) override {
        GameObject::update(deltaTime);
        
        // Simple player movement (this would typically be in a separate component)
        auto* transform = getComponent<Transform>();
        auto* physics = getComponent<Physics>();
        
        if (transform && physics) {
            // Simulate input-based movement
            static float time = 0;
            time += deltaTime;
            
            Vector2D moveDirection(0, 0);
            if (std::sin(time) > 0.5f) {
                moveDirection.x = 1;
            }
            if (std::cos(time) > 0.5f) {
                moveDirection.y = 1;
            }
            
            if (moveDirection.magnitude() > 0) {
                physics->addForce(moveDirection.normalized() * 50.0f);
            }
        }
    }
};

class Enemy : public GameObject {
private:
    Vector2D targetPosition;
    float speed = 20.0f;
    
public:
    Enemy(Vector2D startPos) : GameObject("Enemy"), targetPosition(startPos) {
        getComponent<Transform>()->setPosition(startPos);
        addComponent<Renderer>('E', 1, 1);
        addComponent<Physics>(0.8f);
    }
    
    void update(float deltaTime) override {
        GameObject::update(deltaTime);
        
        auto* transform = getComponent<Transform>();
        auto* physics = getComponent<Physics>();
        
        if (transform && physics) {
            // Simple AI: move in a circle
            static float angle = 0;
            angle += deltaTime;
            
            Vector2D center(10, 10);
            float radius = 5.0f;
            targetPosition = center + Vector2D(
                std::cos(angle) * radius,
                std::sin(angle) * radius
            );
            
            Vector2D direction = targetPosition - transform->position;
            if (direction.magnitude() > 0.1f) {
                physics->addForce(direction.normalized() * speed);
            }
        }
    }
};

// Demo function
void demonstrateGameEngine() {
    std::cout << "=== 2D Game Engine Demo ===" << std::endl;
    
    GameEngine engine;
    
    // Create game objects
    auto* player = engine.createGameObject<Player>();
    auto* enemy1 = engine.createGameObject<Enemy>(Vector2D(5, 5));
    auto* enemy2 = engine.createGameObject<Enemy>(Vector2D(15, 8));
    
    // Create a static object
    auto* staticObj = engine.createGameObject<GameObject>("StaticBlock");
    staticObj->getComponent<Transform>()->setPosition(Vector2D(20, 20));
    staticObj->addComponent<Renderer>('B', 2, 2);
    
    std::cout << "Created " << 4 << " game objects" << std::endl;
    std::cout << "Running game simulation..." << std::endl;
    
    // Run the game
    engine.run();
}

int main() {
    demonstrateGameEngine();
    return 0;
}
```

### Industry Use Cases

#### Performance-Critical Applications

C++ is widely used in industries where performance is paramount:

1. **Game Development**
   - Real-time graphics rendering
   - Physics simulations
   - Memory-constrained environments
   - Popular engines: Unreal Engine, CryEngine

2. **Financial Systems**
   - High-frequency trading
   - Risk management systems
   - Real-time market data processing
   - Low-latency requirements

3. **System Software**
   - Operating systems (Windows, Linux kernel components)
   - Device drivers
   - Embedded systems
   - Real-time systems

4. **Scientific Computing**
   - Numerical simulations
   - Scientific modeling
   - Data analysis frameworks
   - High-performance computing

[Back to top](#-c-documentation)

---

## 📖 Appendices

**📊 Chapter 14 of 14**

### Glossary

**Abstract Class**: A class that contains one or more pure virtual functions and cannot be instantiated directly.

**RAII**: Resource Acquisition Is Initialization - a programming idiom where resource management is tied to object lifetime.

**Template**: A feature that allows functions and classes to operate with generic types.

**STL**: Standard Template Library - a collection of template classes and functions.

**Lambda**: Anonymous function objects that can capture variables from their surrounding scope.

**Move Semantics**: C++11 feature that allows efficient transfer of resources from temporary objects.

**Smart Pointer**: Objects that manage the lifetime of dynamically allocated memory automatically.

### Quick Reference Card

#### Common Containers
```cpp
std::vector<T>        // Dynamic array
std::list<T>          // Doubly-linked list
std::deque<T>         // Double-ended queue
std::set<T>           // Sorted unique elements
std::map<K,V>         // Sorted key-value pairs
std::unordered_set<T> // Hash set
std::unordered_map<K,V> // Hash map
```

#### Smart Pointers
```cpp
std::unique_ptr<T>    // Exclusive ownership
std::shared_ptr<T>    // Shared ownership
std::weak_ptr<T>      // Non-owning observer
```

#### Common Algorithms
```cpp
std::sort()           // Sort elements
std::find()           // Find element
std::transform()      // Transform elements
std::accumulate()     // Reduce to single value
std::for_each()       // Apply function to each
```

### Further Reading

**Books:**
- "Effective C++" by Scott Meyers
- "The C++ Programming Language" by Bjarne Stroustrup
- "Modern C++ Design" by Andrei Alexandrescu
- "C++ Concurrency in Action" by Anthony Williams

**Online Resources:**
- [cppreference.com](https://cppreference.com) - Comprehensive reference
- [isocpp.org](https://isocpp.org) - ISO C++ Standard Committee
- [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines) - Best practices
- [Compiler Explorer](https://godbolt.org) - Online compiler and assembly viewer
- [C++ Weekly](https://www.youtube.com/user/lefticus1) - Weekly C++ tips

### Community Resources

**Forums and Communities:**
- [Stack Overflow](https://stackoverflow.com/questions/tagged/c++) - Q&A community
- [Reddit r/cpp](https://www.reddit.com/r/cpp/) - C++ discussions
- [C++ Slack](https://cpplang.slack.com) - Real-time chat community
- [Discord C++ Community](https://discord.gg/cpp) - Discord server for C++ developers

**Conferences:**
- CppCon - Annual C++ conference
- Meeting C++ - European C++ conference
- C++ Now - Advanced C++ conference
- ACCU Conference - Programming conference with strong C++ track

**Podcasts:**
- CppCast - Weekly C++ podcast
- cpp.chat - Conversations about C++

### Contributing Guidelines

#### Code Style Guidelines

```cpp
// Use consistent naming conventions
class MyClass {        // PascalCase for classes
private:
    int memberVar_;    // camelCase with trailing underscore for members

public:
    void doSomething(int param) const;  // camelCase for functions
};

// Use const whenever possible
void processData(const std::vector<int>& data) {
    // Function body
}

// Prefer auto for type deduction
auto result = computeValue();

// Use range-based for loops
for (const auto& item : container) {
    // Process item
}
```

#### Documentation Standards

```cpp
/**
 * @brief Brief description of the function
 * @param input Description of input parameter
 * @param output Description of output parameter
 * @return Description of return value
 * @throws std::exception Description of when exceptions are thrown
 *
 * Detailed description of the function's behavior,
 * including any side effects or special considerations.
 *
 * @code
 * // Example usage
 * auto result = myFunction(42, "test");
 * @endcode
 */
int myFunction(int input, const std::string& output);
```

#### Testing Guidelines

```cpp
#include <cassert>
#include <iostream>

// Simple assertion-based testing
void testMyFunction() {
    // Test normal cases
    assert(add(2, 3) == 5);
    assert(add(-1, 1) == 0);
    assert(add(0, 0) == 0);

    // Test edge cases
    assert(add(INT_MAX, 0) == INT_MAX);

    std::cout << "All tests passed!" << std::endl;
}

// Using a testing framework like Google Test
#include <gtest/gtest.h>

TEST(MathTest, AdditionTest) {
    EXPECT_EQ(add(2, 3), 5);
    EXPECT_EQ(add(-1, 1), 0);
    EXPECT_EQ(add(0, 0), 0);
}
```

#### Performance Guidelines

```cpp
// 1. Prefer stack allocation over heap allocation
void goodExample() {
    std::array<int, 1000> arr;  // Stack allocated
    // Process arr
}

void poorExample() {
    int* arr = new int[1000];   // Heap allocated
    // Process arr
    delete[] arr;               // Manual memory management
}

// 2. Use move semantics for expensive objects
std::vector<std::string> createLargeVector() {
    std::vector<std::string> result;
    // Fill vector
    return result;  // Move semantics automatically applied
}

// 3. Prefer const references for large objects
void processLargeObject(const LargeClass& obj) {  // No copy
    // Process obj
}

// 4. Use reserve() for vectors when size is known
void fillVector() {
    std::vector<int> vec;
    vec.reserve(1000);  // Avoid multiple reallocations
    for (int i = 0; i < 1000; ++i) {
        vec.push_back(i);
    }
}
```

#### Error Handling Guidelines

```cpp
// Prefer exceptions for exceptional conditions
class FileProcessor {
public:
    void processFile(const std::string& filename) {
        std::ifstream file(filename);
        if (!file.is_open()) {
            throw std::runtime_error("Cannot open file: " + filename);
        }

        // Process file
        if (file.bad()) {
            throw std::runtime_error("Error reading file: " + filename);
        }
    }
};

// Use error codes for expected failure modes
enum class ErrorCode {
    SUCCESS,
    FILE_NOT_FOUND,
    PERMISSION_DENIED,
    INVALID_FORMAT
};

std::pair<ErrorCode, std::string> readConfiguration(const std::string& filename) {
    // Implementation that returns error code and result
    return {ErrorCode::SUCCESS, "configuration data"};
}
```

#### Modern C++ Best Practices Summary

1. **Use Modern Features**: Prefer C++11/14/17/20 features over legacy approaches
2. **RAII Everywhere**: Use RAII for all resource management
3. **Smart Pointers**: Prefer smart pointers over raw pointers
4. **Const Correctness**: Use const wherever possible
5. **Type Safety**: Prefer strong types over primitive types
6. **Standard Library**: Use STL algorithms and containers
7. **Exception Safety**: Write exception-safe code
8. **Move Semantics**: Understand and use move semantics
9. **Template Programming**: Use templates for generic code
10. **Testing**: Write comprehensive tests for your code

---

## 🎯 Final Thoughts

Congratulations! You've completed this comprehensive C++ documentation covering everything from basic syntax to advanced concepts like concurrency and modern C++ features.

C++ is a powerful language that continues to evolve with new standards every few years. The key to mastering C++ is:

1. **Practice Regularly**: Build projects and solve problems
2. **Stay Updated**: Follow C++ standards evolution (C++23, C++26)
3. **Join the Community**: Participate in forums, conferences, and open source
4. **Read Quality Code**: Study well-written C++ projects
5. **Understand the Fundamentals**: Master memory management and object lifetimes

Remember that C++ is not just about syntax—it's about understanding system-level programming, performance optimization, and writing maintainable code. The concepts you've learned here will serve as a foundation for building high-performance, robust applications.

Keep coding, keep learning, and welcome to the C++ community!

---

> **"C makes it easy to shoot yourself in the foot; C++ makes it harder, but when you do it blows your whole leg off."** - Bjarne Stroustrup (Creator of C++)

*This documentation is a living document. As C++ evolves, so should your understanding and application of these concepts.*
