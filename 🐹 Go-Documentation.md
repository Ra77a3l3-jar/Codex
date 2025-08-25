# 🐹 Go Documentation
*Version: 1.25.0 | Last Updated: December 2024*

Go is a statically typed, compiled programming language designed at Google for building simple, reliable, and efficient software. Known for its simplicity, powerful concurrency model, and excellent performance, Go is widely used for system programming, web services, and cloud infrastructure.

## 📑 Table of Contents

### 🚀 [Getting Started](#getting-started)
- [What is Go?](#what-is-go)
- [Why Use Go?](#why-use-go)
- [Installation and Setup](#installation-and-setup)
- [Development Environment](#development-environment)
- [Hello World Example](#hello-world-example)

### 🔤 [Chapter 1: Basic Syntax and Structure](#chapter-1-basic-syntax-and-structure)
- [Go Program Structure](#go-program-structure)
- [Comments](#comments)
- [Identifiers and Keywords](#identifiers-and-keywords)
- [Operators](#operators)
- [Code Organization](#code-organization)

### 📊 [Chapter 2: Data Types and Variables](#chapter-2-data-types-and-variables)
- [Basic Data Types](#basic-data-types)
- [Variable Declarations](#variable-declarations)
- [Constants](#constants)
- [Type Conversions](#type-conversions)
- [Zero Values](#zero-values)

### 🔄 [Chapter 3: Control Structures](#chapter-3-control-structures)
- [Conditional Statements](#conditional-statements)
- [Loops](#loops)
- [Switch Statements](#switch-statements)
- [Control Flow Keywords](#control-flow-keywords)

### 🏗️ [Chapter 4: Functions](#chapter-4-functions)
- [Function Declaration](#function-declaration)
- [Parameters and Return Values](#parameters-and-return-values)
- [Variadic Functions](#variadic-functions)
- [Anonymous Functions and Closures](#anonymous-functions-and-closures)
- [Defer Statement](#defer-statement)

### 📦 [Chapter 5: Data Structures](#chapter-5-data-structures)
- [Arrays](#arrays)
- [Slices](#slices)
- [Maps](#maps)
- [Structs](#structs)
- [Pointers](#pointers)

### 🎭 [Chapter 6: Methods and Interfaces](#chapter-6-methods-and-interfaces)
- [Methods](#methods)
- [Interfaces](#interfaces)
- [Type Assertions](#type-assertions)
- [Empty Interface](#empty-interface)

### 🚨 [Chapter 7: Error Handling](#chapter-7-error-handling)
- [Error Interface](#error-interface)
- [Creating Custom Errors](#creating-custom-errors)
- [Error Wrapping](#error-wrapping)
- [Panic and Recover](#panic-and-recover)

### 📚 [Chapter 8: Packages and Modules](#chapter-8-packages-and-modules)
- [Package System](#package-system)
- [Go Modules](#go-modules)
- [Import Statements](#import-statements)
- [Creating and Publishing Packages](#creating-and-publishing-packages)

### 🚄 [Chapter 9: Concurrency](#chapter-9-concurrency)
- [Goroutines](#goroutines)
- [Channels](#channels)
- [Select Statement](#select-statement)
- [Synchronization Primitives](#synchronization-primitives)
- [Context Package](#context-package)

### 🔧 [Chapter 10: Advanced Topics](#chapter-10-advanced-topics)
- [Reflection](#reflection)
- [Generics](#generics)
- [Embedding](#embedding)
- [Build Tags and Conditional Compilation](#build-tags-and-conditional-compilation)
- [CGO and Interfacing with C](#cgo-and-interfacing-with-c)

### 🌐 [Chapter 11: Standard Library Deep Dive](#chapter-11-standard-library-deep-dive)
- [I/O Operations](#io-operations)
- [File System Operations](#file-system-operations)
- [Network Programming](#network-programming)
- [JSON and XML Processing](#json-and-xml-processing)
- [Time and Date](#time-and-date)

### 🏗️ [Chapter 12: Real-World Applications](#chapter-12-real-world-applications)
- [Web Development with Go](#web-development-with-go)
- [Building REST APIs](#building-rest-apis)
- [Command-Line Applications](#command-line-applications)
- [Testing in Go](#testing-in-go)

### 📋 [Appendices](#appendices)
- [📖 Glossary](#glossary)
- [🔗 Quick Reference Card](#quick-reference-card)
- [📚 Further Reading](#further-reading)
- [🤝 Community Resources](#community-resources)
- [💝 Contributing Guidelines](#contributing-guidelines)

---

## 🚀 Getting Started

### What is Go?

Go, often referred to as Golang, is an open-source programming language developed by Google in 2007 and officially released in 2009. Created by Robert Griesemer, Rob Pike, and Ken Thompson, Go was designed to address the challenges of modern software development at scale.

Go combines the efficiency of a compiled language with the ease of use typically found in interpreted languages. It features a clean syntax similar to C, but with modern features like garbage collection, memory safety, and built-in support for concurrent programming.

### Why Use Go?

Go offers several compelling advantages:

**🎯 Simplicity and Readability**
- Clean, minimalist syntax that's easy to learn and maintain
- Fewer language constructs compared to other modern languages
- Explicit error handling promotes robust code

**⚡ Performance**
- Compiles to native machine code
- Fast compilation times
- Efficient memory usage and garbage collection

**🔄 Concurrency Built-in**
- Goroutines provide lightweight threading
- Channels enable safe communication between concurrent processes
- No need for complex threading libraries

**📦 Excellent Standard Library**
- Comprehensive standard library covering most common tasks
- Network programming, cryptography, and web development support
- No need for many external dependencies

**🏢 Enterprise Ready**
- Static typing catches errors at compile time
- Excellent tooling including formatting, testing, and profiling
- Strong backward compatibility guarantees

### Installation and Setup

#### Installing Go 1.25.0

**🐧 Linux/macOS:**
```bash
# Download and install using the official installer
wget https://golang.org/dl/go1.25.0.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.25.0.linux-amd64.tar.gz

# Add Go to your PATH
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
source ~/.bashrc
```

**🪟 Windows:**
1. Download the MSI installer from https://golang.org/dl/
2. Run the installer and follow the prompts
3. The installer will automatically add Go to your PATH

**🍎 macOS (using Homebrew):**
```bash
brew install go@1.25
```

#### Verifying Installation
```bash
go version
# Should output: go version go1.25.0 darwin/amd64 (or your platform)
```

#### Setting Up GOPATH and GOROOT
```bash
# Check your Go environment
go env GOROOT  # Where Go is installed
go env GOPATH  # Your workspace directory
go env GOMODCACHE  # Module cache location
```

### Development Environment

#### Recommended IDEs and Editors

**🆚 Visual Studio Code**
- Install the official Go extension
- Excellent debugging support
- Integrated terminal and git support

**⚙️ GoLand (JetBrains)**
- Full-featured IDE specifically for Go
- Advanced refactoring and debugging tools
- Built-in support for Go modules

**⚡ Vim/Neovim**
- vim-go plugin provides comprehensive Go support
- Lightweight and highly customizable
- Great for remote development

#### Essential Go Tools
```bash
# Install commonly used tools
go install golang.org/x/tools/cmd/goimports@latest
go install golang.org/x/tools/cmd/godoc@latest
go install golang.org/x/lint/golint@latest
go install honnef.co/go/tools/cmd/staticcheck@latest
```

### Hello World Example

Let's create your first Go program:

```go
// main.go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
    fmt.Println("Welcome to Go 1.25.0!")
}
```

**Running the program:**
```bash
# Method 1: Run directly
go run main.go

# Method 2: Build then execute
go build main.go
./main  # Linux/macOS
main.exe  # Windows
```

**Expected Output:**
```
Hello, World!
Welcome to Go 1.25.0!
```

> 💡 **Tip:** The `package main` declaration and `main()` function are required for executable programs in Go.

---

## Chapter 1: Basic Syntax and Structure
📊 **Progress:** Chapter 1 of 12 | ⏱️ **Estimated reading time:** 15 minutes

🎯 **Learning Objectives:**
- Understand Go program structure and organization
- Learn about comments, identifiers, and keywords
- Master Go's operator system
- Understand code formatting conventions

📋 **Prerequisites:** Basic programming concepts

### Go Program Structure

Every Go program consists of packages, and every package is made up of one or more Go source files. Here's the anatomy of a Go program:

```go
// Package declaration - every Go file starts with this
package main

// Import declarations - bring in external packages
import (
    "fmt"      // Standard library package
    "strings"  // Another standard library package
)

// Global variable declarations (optional)
var globalVar string = "I'm global!"

// Function declarations
func main() {
    // Local variables and program logic
    localVar := "I'm local!"
    fmt.Println(globalVar)
    fmt.Println(localVar)

    // Call other functions
    greetUser("Alice")
}

// Additional function declarations
func greetUser(name string) {
    greeting := fmt.Sprintf("Hello, %s!", name)
    fmt.Println(strings.ToUpper(greeting))
}
```

#### Package Declaration Rules

1. **Package Name:** Must match the directory name (with some exceptions)
2. **Main Package:** Executable programs must have `package main`
3. **Library Packages:** Use descriptive names in lowercase

```go
// Good package names
package user
package httputil
package jsonparser

// Avoid these patterns
package User      // Capital letters
package http_util // Underscores
package utils     // Too generic
```

### Comments

Go supports two types of comments:

#### Single-line Comments
```go
// This is a single-line comment
var x int // Comment at the end of a line

// Multiple single-line comments
// can be used for longer explanations
// that span several lines
```

#### Multi-line Comments
```go
/*
This is a multi-line comment.
It can span multiple lines and is useful
for longer documentation or temporarily
disabling code blocks.
*/

/*
func temporarilyDisabled() {
    // This function is commented out
    fmt.Println("This won't run")
}
*/
```

#### Documentation Comments
```go
// Package math provides basic mathematical functions.
//
// This package implements common mathematical operations
// and utilities for numeric computations.
package math

// Add returns the sum of two integers.
//
// Example usage:
//   result := Add(5, 3)
//   fmt.Println(result) // Outputs: 8
func Add(a, b int) int {
    return a + b
}
```

> 📝 **Note:** Documentation comments should start with the name of the item being documented and should be complete sentences.

### Identifiers and Keywords

#### Valid Identifiers
```go
// Valid identifiers
var name string
var userName string
var user_name string  // Valid but not idiomatic
var _private string
var πr2 float64      // Unicode letters are allowed
var здравствуй string // Unicode support

// Function names
func calculateArea() float64 { return 0 }
func HandleHTTPRequest() {}  // Exported (public) function
func handleHTTPRequest() {}  // Unexported (private) function
```

#### Go Keywords
Go has 25 reserved keywords that cannot be used as identifiers:

```go
// Control flow keywords
break       continue    fallthrough  for         goto
if          return      switch       case        default
defer       go          select

// Declaration keywords
chan        const       func         import      interface
map         package     range        struct      type        var

// Other keywords
else        goto
```

#### Naming Conventions

**📏 Visibility Rules:**
```go
// Exported (public) - starts with capital letter
func PublicFunction() {}
var PublicVariable int
type PublicStruct struct{}

// Unexported (private) - starts with lowercase letter
func privateFunction() {}
var privateVariable int
type privateStruct struct{}
```

**🏷️ Naming Best Practices:**
```go
// Good naming
var userCount int
var maxRetries int
func getUserById(id int) User {}

// Avoid abbreviations unless they're common
var httpClient *http.Client  // OK - HTTP is well-known
var usrCnt int              // Avoid - unclear abbreviation

// Use single-letter names for short-lived variables
for i := 0; i < len(items); i++ {
    // 'i' is fine here
}

// But use descriptive names for longer-lived variables
var totalUserCount int // Better than 'tuc'
```

### Operators

Go provides a comprehensive set of operators for various operations:

#### Arithmetic Operators
```go
package main

import "fmt"

func main() {
    a, b := 10, 3

    fmt.Println("a + b =", a + b)  // Addition: 13
    fmt.Println("a - b =", a - b)  // Subtraction: 7
    fmt.Println("a * b =", a * b)  // Multiplication: 30
    fmt.Println("a / b =", a / b)  // Division: 3 (integer division)
    fmt.Println("a % b =", a % b)  // Modulus: 1

    // Unary operators
    fmt.Println("-a =", -a)        // Negation: -10
    fmt.Println("+a =", +a)        // Unary plus: 10
}
```

#### Comparison Operators
```go
func demonstrateComparisons() {
    x, y := 5, 10

    fmt.Println("x == y:", x == y)  // Equal: false
    fmt.Println("x != y:", x != y)  // Not equal: true
    fmt.Println("x < y:",  x < y)   // Less than: true
    fmt.Println("x <= y:", x <= y)  // Less than or equal: true
    fmt.Println("x > y:",  x > y)   // Greater than: false
    fmt.Println("x >= y:", x >= y)  // Greater than or equal: false
}
```

#### Logical Operators
```go
func demonstrateLogical() {
    a, b := true, false

    fmt.Println("a && b:", a && b)  // Logical AND: false
    fmt.Println("a || b:", a || b)  // Logical OR: true
    fmt.Println("!a:",     !a)      // Logical NOT: false
    fmt.Println("!b:",     !b)      // Logical NOT: true

    // Short-circuit evaluation
    if a || expensiveOperation() {
        // expensiveOperation() won't be called since a is true
        fmt.Println("Short-circuit worked!")
    }
}

func expensiveOperation() bool {
    fmt.Println("This is expensive!")
    return true
}
```

#### Bitwise Operators
```go
func demonstrateBitwise() {
    a, b := 12, 7  // 12 = 1100, 7 = 0111 in binary

    fmt.Printf("a & b = %d (binary: %b)\n", a & b, a & b)   // AND: 4 (0100)
    fmt.Printf("a | b = %d (binary: %b)\n", a | b, a | b)   // OR: 15 (1111)
    fmt.Printf("a ^ b = %d (binary: %b)\n", a ^ b, a ^ b)   // XOR: 11 (1011)
    fmt.Printf("^a = %d\n", ^a)                              // NOT: -13
    fmt.Printf("a << 2 = %d (binary: %b)\n", a << 2, a << 2) // Left shift: 48 (110000)
    fmt.Printf("a >> 1 = %d (binary: %b)\n", a >> 1, a >> 1) // Right shift: 6 (110)
}
```

#### Assignment Operators
```go
func demonstrateAssignment() {
    var x int = 10

    x += 5   // x = x + 5, now x = 15
    x -= 3   // x = x - 3, now x = 12
    x *= 2   // x = x * 2, now x = 24
    x /= 4   // x = x / 4, now x = 6
    x %= 4   // x = x % 4, now x = 2

    // Bitwise assignment operators
    x &= 3   // x = x & 3
    x |= 4   // x = x | 4
    x ^= 1   // x = x ^ 1
    x <<= 1  // x = x << 1
    x >>= 1  // x = x >> 1

    fmt.Println("Final x:", x)
}
```

#### Address and Pointer Operators
```go
func demonstratePointers() {
    var x int = 42
    var p *int = &x  // Get address of x

    fmt.Println("Value of x:", x)      // 42
    fmt.Println("Address of x:", &x)   // Memory address
    fmt.Println("Value of p:", p)      // Same memory address
    fmt.Println("Value at p:", *p)     // 42 (dereference)

    *p = 100  // Change value through pointer
    fmt.Println("New value of x:", x)  // 100
}
```

### Code Organization

#### File Organization
```
myproject/
├── go.mod              // Module definition
├── go.sum              // Dependency checksums
├── main.go             // Main entry point
├── config/             // Configuration package
│   ├── config.go
│   └── defaults.go
├── handlers/           // HTTP handlers
│   ├── user.go
│   ├── product.go
│   └── auth.go
└── internal/           // Private packages
    ├── database/
    │   └── db.go
    └── models/
        ├── user.go
        └── product.go
```

#### Import Organization
```go
package main

import (
    // Standard library imports first
    "context"
    "fmt"
    "net/http"
    "time"

    // Third-party imports
    "github.com/gorilla/mux"
    "github.com/sirupsen/logrus"

    // Local imports last
    "myproject/config"
    "myproject/handlers"
)
```

### ⚠️ Common Pitfalls

1. **Unused Variables and Imports**
```go
// This will cause a compilation error
func badExample() {
    var unused int  // Error: unused variable
    // import "unused" // Error: unused import
}

// Use blank identifier for intentionally unused variables
func goodExample() {
    result, _ := someFunction()  // OK: explicitly ignoring second return value
    fmt.Println(result)
}
```

2. **Case Sensitivity in Identifiers**
```go
package main

var userName string = "Alice"  // This is different from...
var username string = "Bob"    // ...this variable

// These are completely different functions
func GetUser() {}  // Exported
func getUser() {}  // Unexported
```

3. **Incorrect Package Structure**
```go
// Wrong: mixing main package with library code
package main

func UtilityFunction() {} // This should be in a separate package

// Right: separate packages for different concerns
// Put UtilityFunction in a utils package
```

### ✅ Best Practices

1. **Use Go's Formatting Tools**
```bash
# Format your code automatically
go fmt ./...

# Or use goimports for better import management
goimports -w .
```

2. **Follow Naming Conventions**
```go
// Good: Clear, concise names
func CalculateInterest(principal, rate float64) float64 {
    return principal * rate / 100
}

// Avoid: Unclear abbreviations
func CalcInt(p, r float64) float64 {
    return p * r / 100
}
```

3. **Group Related Functionality**
```go
// Group related constants
const (
    StatusActive   = "active"
    StatusInactive = "inactive"
    StatusPending  = "pending"
)

// Group related variables
var (
    defaultTimeout = 30 * time.Second
    maxRetries     = 3
    logLevel       = "info"
)
```

### 🏋️ Exercise 1: Basic Syntax Practice
**Difficulty:** 🟢 Beginner
**Estimated Time:** 15 minutes

Create a Go program that demonstrates all the operators learned in this chapter. The program should:

1. Declare variables of different types
2. Perform arithmetic operations
3. Use comparison operators
4. Demonstrate logical operations
5. Show bitwise operations
6. Use assignment operators

<details>
<summary>💡 Click to see hints</summary>

- Use multiple variables with different data types
- Print the results of each operation with descriptive messages
- Try combining different operators in expressions
- Remember to format your output clearly

</details>

<details>
<summary>✅ Click to see solution</summary>

```go
package main

import "fmt"

func main() {
    // Variable declarations
    var a int = 15
    var b int = 4
    var flag1 bool = true
    var flag2 bool = false

    fmt.Println("=== Basic Syntax and Operators Demo ===")
    fmt.Printf("Initial values: a = %d, b = %d\n", a, b)
    fmt.Printf("Boolean flags: flag1 = %t, flag2 = %t\n\n", flag1, flag2)

    // Arithmetic Operations
    fmt.Println("--- Arithmetic Operations ---")
    fmt.Printf("a + b = %d + %d = %d\n", a, b, a+b)
    fmt.Printf("a - b = %d - %d = %d\n", a, b, a-b)
    fmt.Printf("a * b = %d * %d = %d\n", a, b, a*b)
    fmt.Printf("a / b = %d / %d = %d\n", a, b, a/b)
    fmt.Printf("a %% b = %d %% %d = %d\n", a, b, a%b)
    fmt.Printf("Negation: -a = -%d = %d\n\n", a, -a)

    // Comparison Operations
    fmt.Println("--- Comparison Operations ---")
    fmt.Printf("a == b: %d == %d is %t\n", a, b, a == b)
    fmt.Printf("a != b: %d != %d is %t\n", a, b, a != b)
    fmt.Printf("a > b: %d > %d is %t\n", a, b, a > b)
    fmt.Printf("a < b: %d < %d is %t\n", a, b, a < b)
    fmt.Printf("a >= b: %d >= %d is %t\n", a, b, a >= b)
    fmt.Printf("a <= b: %d <= %d is %t\n\n", a, b, a <= b)

    // Logical Operations
    fmt.Println("--- Logical Operations ---")
    fmt.Printf("flag1 && flag2: %t && %t = %t\n", flag1, flag2, flag1 && flag2)
    fmt.Printf("flag1 || flag2: %t || %t = %t\n", flag1, flag2, flag1 || flag2)
    fmt.Printf("!flag1: !%t = %t\n", flag1, !flag1)
    fmt.Printf("!flag2: !%t = %t\n\n", flag2, !flag2)

    // Bitwise Operations
    fmt.Println("--- Bitwise Operations ---")
    fmt.Printf("a in binary: %b, b in binary: %b\n", a, b)
    fmt.Printf("a & b = %b & %b = %b (%d)\n", a, b, a&b, a&b)
    fmt.Printf("a | b = %b | %b = %b (%d)\n", a, b, a|b, a|b)
    fmt.Printf("a ^ b = %b ^ %b = %b (%d)\n", a, b, a^b, a^b)
    fmt.Printf("^a = ^%b = %d\n", a, ^a)
    fmt.Printf("a << 2 = %b << 2 = %b (%d)\n", a, a<<2, a<<2)
    fmt.Printf("a >> 1 = %b >> 1 = %b (%d)\n\n", a, a>>1, a>>1)

    // Assignment Operations
    fmt.Println("--- Assignment Operations ---")
    c := 10
    fmt.Printf("Starting with c = %d\n", c)

    c += 5
    fmt.Printf("c += 5: c is now %d\n", c)

    c -= 3
    fmt.Printf("c -= 3: c is now %d\n", c)

    c *= 2
    fmt.Printf("c *= 2: c is now %d\n", c)

    c /= 4
    fmt.Printf("c /= 4: c is now %d\n", c)

    c %= 5
    fmt.Printf("c %%= 5: c is now %d\n", c)

    // Demonstrate operator precedence
    fmt.Println("\n--- Operator Precedence ---")
    result := 2 + 3 * 4
    fmt.Printf("2 + 3 * 4 = %d (multiplication first)\n", result)

    result = (2 + 3) * 4
    fmt.Printf("(2 + 3) * 4 = %d (parentheses first)\n", result)
}
```

**Explanation:**

This solution demonstrates all the major operators in Go:

- **Arithmetic operators**: Shows basic math operations including modulus and unary negation
- **Comparison operators**: Demonstrates all comparison operations with boolean results
- **Logical operators**: Shows boolean logic with AND, OR, and NOT operations
- **Bitwise operations**: Displays binary representations and bitwise manipulations
- **Assignment operators**: Shows how compound assignment operators modify variables
- **Operator precedence**: Illustrates how Go evaluates expressions with multiple operators

**Key concepts demonstrated:**
1. Variable declaration and initialization
2. Printf formatting with different format specifiers (%d, %t, %b)
3. Operator precedence and the use of parentheses
4. How different types of operations work together in Go

**Performance considerations:**
- All operations shown are O(1) constant time operations
- Bitwise operations are typically the fastest, followed by arithmetic operations
- The example avoids expensive operations in the demonstration

</details>

---

## Chapter 2: Data Types and Variables
📊 **Progress:** Chapter 2 of 12 | ⏱️ **Estimated reading time:** 20 minutes

🎯 **Learning Objectives:**
- Master Go's type system and basic data types
- Understand variable declaration patterns
- Learn about constants and their use cases
- Explore type conversions and zero values

📋 **Prerequisites:** Basic understanding of programming concepts and Chapter 1

### Basic Data Types

Go has a rich type system that includes both basic types and composite types. Let's explore the fundamental data types:

#### Integer Types

Go provides several integer types with different sizes and signedness:

```go
package main

import (
    "fmt"
    "unsafe"
)

func demonstrateIntegerTypes() {
    // Signed integers
    var int8Var int8 = 127                    // -128 to 127
    var int16Var int16 = 32767                // -32,768 to 32,767
    var int32Var int32 = 2147483647           // -2^31 to 2^31-1
    var int64Var int64 = 9223372036854775807  // -2^63 to 2^63-1

    // Unsigned integers
    var uint8Var uint8 = 255                   // 0 to 255
    var uint16Var uint16 = 65535               // 0 to 65,535
    var uint32Var uint32 = 4294967295          // 0 to 2^32-1
    var uint64Var uint64 = 18446744073709551615 // 0 to 2^64-1

    // Platform-dependent integers
    var intVar int = 42       // 32 or 64 bits depending on platform
    var uintVar uint = 42     // 32 or 64 bits depending on platform
    var uintptrVar uintptr    // Large enough to store pointer value

    // Special integer types
    var byteVar byte = 255    // Alias for uint8
    var runeVar rune = '🐹'   // Alias for int32, represents Unicode code point

    fmt.Println("=== Integer Types ===")
    fmt.Printf("int8: %d (size: %d bytes)\n", int8Var, unsafe.Sizeof(int8Var))
    fmt.Printf("int16: %d (size: %d bytes)\n", int16Var, unsafe.Sizeof(int16Var))
    fmt.Printf("int32: %d (size: %d bytes)\n", int32Var, unsafe.Sizeof(int32Var))
    fmt.Printf("int64: %d (size: %d bytes)\n", int64Var, unsafe.Sizeof(int64Var))
    fmt.Printf("int: %d (size: %d bytes)\n", intVar, unsafe.Sizeof(intVar))
    fmt.Printf("byte: %d (character: %c)\n", byteVar, byteVar)
    fmt.Printf("rune: %d (character: %c)\n", runeVar, runeVar)
}
```

#### Floating-Point Types

Go supports two floating-point types following IEEE 754 standard:

```go
func demonstrateFloatTypes() {
    var float32Var float32 = 3.14159
    var float64Var float64 = 3.141592653589793

    // Scientific notation
    var scientific float64 = 1.23e-4  // 0.000123
    var large float64 = 6.022e23      // Avogadro's number

    fmt.Println("\n=== Floating-Point Types ===")
    fmt.Printf("float32: %.5f (size: %d bytes)\n", float32Var, unsafe.Sizeof(float32Var))
    fmt.Printf("float64: %.15f (size: %d bytes)\n", float64Var, unsafe.Sizeof(float64Var))
    fmt.Printf("Scientific: %.6e\n", scientific)
    fmt.Printf("Large number: %.3e\n", large)

    // Demonstrate precision differences
    var f32 float32 = 1.0000001
    var f64 float64 = 1.0000001
    fmt.Printf("float32 precision: %.8f\n", f32)
    fmt.Printf("float64 precision: %.8f\n", f64)
}
```

#### Complex Types

Go has built-in support for complex numbers:

```go
func demonstrateComplexTypes() {
    // Complex64 and Complex128
    var c64 complex64 = 1 + 2i
    var c128 complex128 = 3.14 + 2.71i

    // Creating complex numbers
    c1 := complex(5, 6)      // 5 + 6i
    c2 := 2 + 3i            // Direct notation

    fmt.Println("\n=== Complex Types ===")
    fmt.Printf("complex64: %v\n", c64)
    fmt.Printf("complex128: %v\n", c128)
    fmt.Printf("c1: %v\n", c1)
    fmt.Printf("c2: %v\n", c2)

    // Complex operations
    fmt.Printf("c1 + c2: %v\n", c1 + c2)
    fmt.Printf("c1 * c2: %v\n", c1 * c2)

    // Extract real and imaginary parts
    fmt.Printf("Real part of c1: %.2f\n", real(c1))
    fmt.Printf("Imaginary part of c1: %.2f\n", imag(c1))
}
```

#### Boolean Type

Go has a simple boolean type with only two possible values:

```go
func demonstrateBooleanType() {
    var flag bool = true
    var defaultBool bool  // Zero value is false

    fmt.Println("\n=== Boolean Type ===")
    fmt.Printf("flag: %t\n", flag)
    fmt.Printf("defaultBool: %t\n", defaultBool)

    // Boolean operations
    result := true && false
    fmt.Printf("true && false: %t\n", result)

    // Common boolean patterns
    isValid := len("hello") > 0
    hasPermission := true
    canProceed := isValid && hasPermission

    fmt.Printf("Can proceed: %t\n", canProceed)
}
```

#### String Type

Strings in Go are immutable sequences of bytes:

```go
func demonstrateStringType() {
    var str1 string = "Hello, World!"
    var str2 string = "Go programming"
    var emptyStr string  // Zero value is ""

    fmt.Println("\n=== String Type ===")
    fmt.Printf("str1: %s (length: %d)\n", str1, len(str1))
    fmt.Printf("str2: %s\n", str2)
    fmt.Printf("emptyStr: '%s' (length: %d)\n", emptyStr, len(emptyStr))

    // String concatenation
    combined := str1 + " " + str2
    fmt.Printf("Combined: %s\n", combined)

    // String literals
    multiline := `This is a
multi-line
string using backticks`
    fmt.Printf("Multiline:\n%s\n", multiline)

    // Unicode support
    unicode := "Hello, 世界! 🌍"
    fmt.Printf("Unicode string: %s\n", unicode)
    fmt.Printf("Byte length: %d, Rune count: %d\n", len(unicode), len([]rune(unicode)))

    // String indexing (returns bytes, not runes)
    fmt.Printf("First byte: %c (%d)\n", str1[0], str1[0])
    fmt.Printf("Substring: %s\n", str1[0:5])
}
```

### Variable Declarations

Go provides several ways to declare and initialize variables:

#### Explicit Declaration with var

```go
func demonstrateVarDeclarations() {
    // Basic var declarations
    var name string
    var age int
    var isActive bool

    fmt.Println("\n=== Variable Declarations ===")
    fmt.Printf("Uninitialized - name: '%s', age: %d, isActive: %t\n", name, age, isActive)

    // Declaration with initialization
    var fullName string = "John Doe"
    var currentYear int = 2024
    var hasLicense bool = true

    fmt.Printf("Initialized - fullName: %s, currentYear: %d, hasLicense: %t\n",
               fullName, currentYear, hasLicense)

    // Type inference
    var country = "USA"        // string inferred
    var population = 331000000 // int inferred
    var density = 36.2         // float64 inferred

    fmt.Printf("Type inferred - country: %s, population: %d, density: %.1f\n",
               country, population, density)

    // Multiple variable declarations
    var (
        firstName = "Alice"
        lastName  = "Smith"
        userAge   = 30
    )

    fmt.Printf("Multiple vars - %s %s, age: %d\n", firstName, lastName, userAge)
}
```

#### Short Declaration with :=

The short declaration operator `:=` is a concise way to declare and initialize variables:

```go
func demonstrateShortDeclarations() {
    // Short variable declarations
    name := "Bob"
    age := 25
    height := 5.9
    isStudent := true

    fmt.Println("\n=== Short Declarations ===")
    fmt.Printf("name: %s, age: %d, height: %.1f, isStudent: %t\n",
               name, age, height, isStudent)

    // Multiple short declarations
    x, y := 10, 20
    fmt.Printf("x: %d, y: %d\n", x, y)

    // Mixed assignment (at least one new variable)
    z := 30
    x, w := 40, 50  // x is reassigned, w is new
    fmt.Printf("x: %d, z: %d, w: %d\n", x, z, w)

    // Short declaration in different scopes
    if condition := true; condition {
        message := "Inside if block"
        fmt.Printf("Scoped variable: %s\n", message)
    }
    // message is not accessible here

    // Common pattern with function returns
    result, err := someFunction()
    if err != nil {
        fmt.Printf("Error: %v\n", err)
    } else {
        fmt.Printf("Result: %s\n", result)
    }
}

func someFunction() (string, error) {
    return "Success!", nil
}
```

#### Blank Identifier

The blank identifier `_` is used to ignore values:

```go
func demonstrateBlankIdentifier() {
    // Ignoring return values
    result, _ := someFunction() // Ignore error
    fmt.Printf("Only result: %s\n", result)

    // Ignoring values in assignments
    values := []int{1, 2, 3, 4, 5}
    for i, _ := range values {  // Ignore value, only use index
        if i >= 3 {
            break
        }
        fmt.Printf("Index: %d\n", i)
    }

    // Importing packages for side effects only
    // import _ "net/http/pprof"  // Would enable profiling endpoints
}
```

### Constants

Constants are immutable values known at compile time:

#### Basic Constants

```go
func demonstrateConstants() {
    // Typed constants
    const pi float64 = 3.14159265359
    const greeting string = "Hello"
    const maxUsers int = 100

    // Untyped constants (more flexible)
    const e = 2.71828
    const welcome = "Welcome"
    const limit = 1000

    fmt.Println("\n=== Constants ===")
    fmt.Printf("pi: %.5f\n", pi)
    fmt.Printf("greeting: %s\n", greeting)
    fmt.Printf("maxUsers: %d\n", maxUsers)

    // Untyped constants can be used with different types
    var radius float32 = 10.0
    area := pi * radius * radius  // pi (float64) works with radius (float32)
    fmt.Printf("Area: %.2f\n", area)
}
```

#### Constant Blocks and iota

```go
func demonstrateConstantBlocks() {
    // Constant blocks
    const (
        StatusPending = "pending"
        StatusActive  = "active"
        StatusInactive = "inactive"
    )

    // Using iota for enumerated constants
    const (
        Sunday = iota    // 0
        Monday           // 1
        Tuesday          // 2
        Wednesday        // 3
        Thursday         // 4
        Friday           // 5
        Saturday         // 6
    )

    // iota with expressions
    const (
        _  = iota                    // Skip 0
        KB = 1 << (10 * iota)       // 1024
        MB                          // 1048576
        GB                          // 1073741824
        TB                          // 1099511627776
    )

    // iota with custom types
    type Priority int
    const (
        Low Priority = iota
        Medium
        High
        Critical
    )

    fmt.Println("\n=== Constant Blocks and iota ===")
    fmt.Printf("Days: Sunday=%d, Wednesday=%d, Saturday=%d\n", Sunday, Wednesday, Saturday)
    fmt.Printf("Storage: KB=%d, MB=%d, GB=%d\n", KB, MB, GB)
    fmt.Printf("Priorities: Low=%d, High=%d, Critical=%d\n", Low, High, Critical)
}
```

### Type Conversions

Go requires explicit type conversions between different types:

```go
func demonstrateTypeConversions() {
    // Numeric conversions
    var i int = 42
    var f float64 = float64(i)
    var u uint = uint(f)

    fmt.Println("\n=== Type Conversions ===")
    fmt.Printf("int to float64: %d -> %.1f\n", i, f)
    fmt.Printf("float64 to uint: %.1f -> %d\n", f, u)

    // Be careful with precision loss
    var large float64 = 1.99999999
    var truncated int = int(large)
    fmt.Printf("Precision loss: %.8f -> %d\n", large, truncated)

    // String conversions
    var num int = 65
    var char string = string(num)  // Converts to Unicode character
    fmt.Printf("int to string (Unicode): %d -> %s\n", num, char)

    // For numeric string conversion, use strconv package
    import "strconv"

    var str string = strconv.Itoa(42)
    var parsed, err = strconv.Atoi("123")

    fmt.Printf("Number to string: %s\n", str)
    if err == nil {
        fmt.Printf("String to number: %d\n", parsed)
    }

    // Slice conversions
    var bytes []byte = []byte("Hello")
    var backToString string = string(bytes)

    fmt.Printf("String to []byte: %v\n", bytes)
    fmt.Printf("[]byte to string: %s\n", backToString)
}
```

### Zero Values

Every type in Go has a zero value - the default value for uninitialized variables:

```go
func demonstrateZeroValues() {
    // Declare variables without initialization
    var (
        zeroInt     int
        zeroFloat   float64
        zeroString  string
        zeroBool    bool
        zeroPointer *int
        zeroSlice   []int
        zeroMap     map[string]int
        zeroChannel chan int
        zeroFunc    func()
    )

    fmt.Println("\n=== Zero Values ===")
    fmt.Printf("int: %d\n", zeroInt)
    fmt.Printf("float64: %f\n", zeroFloat)
    fmt.Printf("string: '%s' (length: %d)\n", zeroString, len(zeroString))
    fmt.Printf("bool: %t\n", zeroBool)
    fmt.Printf("pointer: %v\n", zeroPointer)
    fmt.Printf("slice: %v (nil: %t)\n", zeroSlice, zeroSlice == nil)
    fmt.Printf("map: %v (nil: %t)\n", zeroMap, zeroMap == nil)
    fmt.Printf("channel: %v (nil: %t)\n", zeroChannel, zeroChannel == nil)
    fmt.Printf("function: %v (nil: %t)\n", zeroFunc, zeroFunc == nil)

    // Zero values are useful for initialization
    type Config struct {
        Host    string
        Port    int
        Enabled bool
    }

    var config Config  // All fields have zero values
    fmt.Printf("Config: %+v\n", config)
}
```

### ⚠️ Common Pitfalls

1. **Integer Overflow**
```go
// This will cause overflow without warning
var smallInt int8 = 127
smallInt += 1  // Wraps to -128
fmt.Printf("Overflow result: %d\n", smallInt)

// Better: Use appropriate type sizes or check bounds
var safeInt int32 = 127
if safeInt < math.MaxInt32 {
    safeInt += 1
}
```

2. **Float Precision Issues**
```go
// Floating point precision can be tricky
var a float64 = 0.1
var b float64 = 0.2
var sum float64 = a + b

fmt.Printf("0.1 + 0.2 = %.17f\n", sum) // Not exactly 0.3!

// For precise decimal calculations, use decimal libraries
// or work with integers when possible
```

3. **String vs Rune Confusion**
```go
str := "Hello, 世界"
fmt.Printf("String length (bytes): %d\n", len(str))           // 13
fmt.Printf("Rune count: %d\n", len([]rune(str)))             // 9

// Iterating over bytes vs runes
fmt.Print("Bytes: ")
for i := 0; i < len(str); i++ {
    fmt.Printf("%c ", str[i])  // May print invalid characters
}

fmt.Print("\nRunes: ")
for _, r := range str {
    fmt.Printf("%c ", r)  // Correctly handles Unicode
}
fmt.Println()
```

### ✅ Best Practices

1. **Choose Appropriate Types**
```go
// Good: Use specific types for clarity
type UserID int64
type Temperature float64
type EmailAddress string

var id UserID = 12345
var temp Temperature = 23.5
var email EmailAddress = "user@example.com"
```

2. **Initialize Variables Properly**
```go
// Good: Initialize with meaningful values
var (
    defaultTimeout = 30 * time.Second
    maxRetries     = 3
    bufferSize     = 1024
)

// Avoid: Relying on zero values when explicit initialization is clearer
```

3. **Use Constants for Fixed Values**
```go
// Good: Use constants for values that don't change
const (
    APIVersion = "v1"
    MaxFileSize = 10 << 20  // 10 MB
    RetryDelay = 100 * time.Millisecond
)

// Avoid: Magic numbers scattered throughout code
if fileSize > 10485760 {  // What does this number mean?
    return errors.New("file too large")
}
```

### 🏋️ Exercise 2: Type System Mastery
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 25 minutes

Create a program that demonstrates Go's type system by building a simple calculator that:

1. Uses different numeric types for operations
2. Handles type conversions safely
3. Uses constants for mathematical constants
4. Demonstrates zero values and variable declarations
5. Includes proper error handling for invalid operations

<details>
<summary>💡 Click to see hints</summary>

- Create a Calculator struct with methods for different operations
- Use constants for mathematical values like Pi, E
- Handle division by zero cases
- Show type conversions between int, float64, and complex types
- Use proper variable declaration patterns

</details>

<details>
<summary>✅ Click to see solution</summary>

```go
package main

import (
    "fmt"
    "math"
    "strconv"
)

// Mathematical constants
const (
    Pi = 3.14159265358979323846
    E  = 2.71828182845904523536
    GoldenRatio = 1.61803398874989484820
)

// Calculator represents a mathematical calculator
type Calculator struct {
    precision int
    lastResult float64
}

// Operation type for different calculator operations
type Operation int

const (
    Add Operation = iota
    Subtract
    Multiply
    Divide
    Power
    SquareRoot
)

// NewCalculator creates a new calculator with specified precision
func NewCalculator(precision int) *Calculator {
    return &Calculator{
        precision: precision,
        lastResult: 0.0, // Explicit zero value
    }
}

// BasicOperation performs basic arithmetic operations
func (c *Calculator) BasicOperation(op Operation, a, b float64) (float64, error) {
    var result float64
    var err error

    switch op {
    case Add:
        result = a + b
    case Subtract:
        result = a - b
    case Multiply:
        result = a * b
    case Divide:
        if b == 0 {
            return 0, fmt.Errorf("division by zero")
        }
        result = a / b
    case Power:
        result = math.Pow(a, b)
    case SquareRoot:
        if a < 0 {
            return 0, fmt.Errorf("square root of negative number")
        }
        result = math.Sqrt(a)
    default:
        return 0, fmt.Errorf("unknown operation")
    }

    c.lastResult = result
    return result, err
}

// ConvertAndCalculate demonstrates type conversions
func (c *Calculator) ConvertAndCalculate(intVal int, floatVal float32) {
    fmt.Println("\n=== Type Conversion Demo ===")

    // Convert int to float64 for calculation
    intAsFloat := float64(intVal)
    floatAsFloat64 := float64(floatVal)

    fmt.Printf("Original int: %d, converted to float64: %.2f\n", intVal, intAsFloat)
    fmt.Printf("Original float32: %.2f, converted to float64: %.6f\n", floatVal, floatAsFloat64)

    // Perform calculation
    result, _ := c.BasicOperation(Add, intAsFloat, floatAsFloat64)
    fmt.Printf("Sum: %.6f\n", result)

    // Convert result back to int (with precision loss warning)
    resultAsInt := int(result)
    fmt.Printf("Result as int (precision loss): %d\n", resultAsInt)

    // Safe conversion with bounds checking
    if result <= math.MaxInt32 && result >= math.MinInt32 {
        safeInt := int32(result)
        fmt.Printf("Safe conversion to int32: %d\n", safeInt)
    } else {
        fmt.Println("Result too large for int32 conversion")
    }
}

// ComplexCalculations demonstrates complex number operations
func (c *Calculator) ComplexCalculations(real1, imag1, real2, imag2 float64) {
    fmt.Println("\n=== Complex Number Operations ===")

    // Create complex numbers
    c1 := complex(real1, imag1)
    c2 := complex(real2, imag2)

    fmt.Printf("Complex number 1: %.2f%+.2fi\n", real(c1), imag(c1))
    fmt.Printf("Complex number 2: %.2f%+.2fi\n", real(c2), imag(c2))

    // Complex operations
    sum := c1 + c2
    product := c1 * c2

    fmt.Printf("Sum: %.2f%+.2fi\n", real(sum), imag(sum))
    fmt.Printf("Product: %.2f%+.2fi\n", real(product), imag(product))

    // Convert back to float64 components
    sumReal := real(sum)
    sumImag := imag(sum)

    fmt.Printf("Sum real part as float64: %.6f\n", sumReal)
    fmt.Printf("Sum imaginary part as float64: %.6f\n", sumImag)
}

// DemonstrateZeroValues shows zero values of different types
func (c *Calculator) DemonstrateZeroValues() {
    fmt.Println("\n=== Zero Values Demo ===")

    // Declare variables without initialization
    var (
        zeroInt    int
        zeroFloat  float64
        zeroString string
        zeroBool   bool
        zeroSlice  []float64
        zeroMap    map[string]int
    )

    fmt.Printf("Zero int: %d\n", zeroInt)
    fmt.Printf("Zero float64: %.1f\n", zeroFloat)
    fmt.Printf("Zero string: '%s' (empty: %t)\n", zeroString, zeroString == "")
    fmt.Printf("Zero bool: %t\n", zeroBool)
    fmt.Printf("Zero slice: %v (nil: %t)\n", zeroSlice, zeroSlice == nil)
    fmt.Printf("Zero map: %v (nil: %t)\n", zeroMap, zeroMap == nil)

    // Show that zero values are usable
    calculation, err := c.BasicOperation(Add, float64(zeroInt), zeroFloat)
    if err == nil {
        fmt.Printf("Calculation with zero values: %.1f\n", calculation)
    }
}

// StringConversions demonstrates string-number conversions
func (c *Calculator) StringConversions() {
    fmt.Println("\n=== String Conversion Demo ===")

    // Convert numbers to strings
    intVal := 42
    floatVal := 3.14159

    intStr := strconv.Itoa(intVal)
    floatStr := strconv.FormatFloat(floatVal, 'f', c.precision, 64)

    fmt.Printf("int %d to string: '%s'\n", intVal, intStr)
    fmt.Printf("float %.5f to string: '%s'\n", floatVal, floatStr)

    // Convert strings to numbers
    numStr1 := "123"
    numStr2 := "45.67"

    if parsed1, err := strconv.Atoi(numStr1); err == nil {
        fmt.Printf("string '%s' to int: %d\n", numStr1, parsed1)
    }

    if parsed2, err := strconv.ParseFloat(numStr2, 64); err == nil {
        fmt.Printf("string '%s' to float64: %.2f\n", numStr2, parsed2)

        // Use parsed values in calculation
        result, _ := c.BasicOperation(Multiply, float64(parsed1), parsed2)
        fmt.Printf("Calculation result: %.2f\n", result)
    }

    // Handle conversion errors
    invalidStr := "not-a-number"
    if _, err := strconv.ParseFloat(invalidStr, 64); err != nil {
        fmt.Printf("Error converting '%s': %v\n", invalidStr, err)
    }
}

// DisplayConstants shows the use of constants
func DisplayConstants() {
    fmt.Println("\n=== Mathematical Constants ===")
    fmt.Printf("Pi: %.10f\n", Pi)
    fmt.Printf("E (Euler's number): %.10f\n", E)
    fmt.Printf("Golden Ratio: %.10f\n", GoldenRatio)

    // Use constants in calculations
    circleRadius := 5.0
    circleArea := Pi * circleRadius * circleRadius
    circleCircumference := 2 * Pi * circleRadius

    fmt.Printf("\nCircle calculations (radius: %.1f):\n", circleRadius)
    fmt.Printf("Area: %.2f\n", circleArea)
    fmt.Printf("Circumference: %.2f\n", circleCircumference)
}

func main() {
    fmt.Println("🧮 Advanced Go Type System Calculator")
    fmt.Println("=====================================")

    // Create calculator with 4 decimal places precision
    calc := NewCalculator(4)

    // Display constants
    DisplayConstants()

    // Demonstrate basic operations
    fmt.Println("\n=== Basic Operations ===")
    operations := []struct {
        op   Operation
        a, b float64
        name string
    }{
        {Add, 10.5, 5.3, "Addition"},
        {Subtract, 20.0, 8.7, "Subtraction"},
        {Multiply, 4.2, 3.0, "Multiplication"},
        {Divide, 15.6, 3.0, "Division"},
        {Power, 2.0, 8.0, "Power"},
        {SquareRoot, 16.0, 0.0, "Square Root"},
    }

    for _, op := range operations {
        if result, err := calc.BasicOperation(op.op, op.a, op.b); err == nil {
            if op.op == SquareRoot {
                fmt.Printf("%s of %.1f = %.4f\n", op.name, op.a, result)
            } else {
                fmt.Printf("%s: %.1f and %.1f = %.4f\n", op.name, op.a, op.b, result)
            }
        } else {
            fmt.Printf("%s error: %v\n", op.name, err)
        }
    }

    // Show last result
    fmt.Printf("Last calculation result: %.4f\n", calc.lastResult)

    // Demonstrate type conversions
    calc.ConvertAndCalculate(42, 3.14159)

    // Demonstrate complex number operations
    calc.ComplexCalculations(3.0, 4.0, 1.0, 2.0)

    // Show zero values
    calc.DemonstrateZeroValues()

    // Demonstrate string conversions
    calc.StringConversions()

    // Test error handling
    fmt.Println("\n=== Error Handling Demo ===")
    if _, err := calc.BasicOperation(Divide, 10.0, 0.0); err != nil {
        fmt.Printf("Division by zero caught: %v\n", err)
    }

    if _, err := calc.BasicOperation(SquareRoot, -25.0, 0.0); err != nil {
        fmt.Printf("Square root of negative number caught: %v\n", err)
    }
}
```

**Explanation:**

This comprehensive solution demonstrates all major aspects of Go's type system:

**Key concepts demonstrated:**
1. **Custom types and constants**: Defines Operation type and mathematical constants
2. **Struct with methods**: Calculator struct with various calculation methods
3. **Type conversions**: Safe conversions between int, float32, float64, and complex types
4. **Zero values**: Shows default values for different types and their usability
5. **String conversions**: Using strconv package for string-number conversions
6. **Error handling**: Proper error handling for invalid operations
7. **Complex numbers**: Demonstrates complex number arithmetic and component extraction

**Performance considerations:**
- Uses appropriate numeric types (int for counts, float64 for calculations)
- Avoids unnecessary type conversions in hot paths
- Implements bounds checking for safe conversions
- Uses constants for mathematical values to avoid repeated calculations

**Best practices shown:**
- Clear naming conventions with exported/unexported identifiers
- Comprehensive error handling with descriptive error messages
- Proper use of zero values where appropriate
- Documentation through clear variable and function names
- Separation of concerns with different methods for different operations

</details>

---

## Chapter 3: Control Structures
📊 **Progress:** Chapter 3 of 12 | ⏱️ **Estimated reading time:** 18 minutes

🎯 **Learning Objectives:**
- Master Go's conditional statements (if, switch)
- Understand Go's loop constructs and iteration patterns
- Learn control flow keywords (break, continue, goto, fallthrough)
- Explore Go's unique features like short-circuit evaluation

📋 **Prerequisites:** Understanding of basic syntax and data types from previous chapters

### Conditional Statements

Go provides powerful and flexible conditional statements that allow your programs to make decisions based on different conditions.

#### Basic if Statements

```go
package main

import "fmt"

func demonstrateBasicIf() {
    score := 85

    fmt.Println("=== Basic if Statements ===")

    // Simple if statement
    if score >= 90 {
        fmt.Println("Grade: A")
    }

    // if-else statement
    if score >= 70 {
        fmt.Println("You passed!")
    } else {
        fmt.Println("You need to retake the exam.")
    }

    // if-else if-else chain
    if score >= 90 {
        fmt.Println("Excellent!")
    } else if score >= 80 {
        fmt.Println("Good job!")
    } else if score >= 70 {
        fmt.Println("Satisfactory")
    } else {
        fmt.Println("Needs improvement")
    }
}
```

#### if with Short Statement

Go allows you to execute a short statement before the condition:

```go
func demonstrateIfWithShortStatement() {
    fmt.Println("\n=== if with Short Statement ===")

    // Short statement before condition
    if temperature := getCurrentTemperature(); temperature > 30 {
        fmt.Printf("It's hot! Temperature: %.1f°C\n", temperature)
    } else if temperature > 20 {
        fmt.Printf("Perfect weather! Temperature: %.1f°C\n", temperature)
    } else {
        fmt.Printf("It's cold! Temperature: %.1f°C\n", temperature)
    }

    // Variable scope: temperature is only accessible within the if block
    // fmt.Println(temperature) // This would cause a compilation error

    // Common pattern with error handling
    if user, err := getUserById(123); err != nil {
        fmt.Printf("Error getting user: %v\n", err)
    } else {
        fmt.Printf("User found: %s\n", user.Name)
    }

    // Multiple short statements (less common, but possible)
    if x, y := 10, 20; x < y {
        fmt.Printf("x (%d) is less than y (%d)\n", x, y)
    }
}

func getCurrentTemperature() float64 {
    return 25.5 // Simulated temperature
}

type User struct {
    ID   int
    Name string
}

func getUserById(id int) (User, error) {
    // Simulated database lookup
    if id == 123 {
        return User{ID: id, Name: "Alice"}, nil
    }
    return User{}, fmt.Errorf("user with ID %d not found", id)
}
```

#### Complex Conditions and Logic

```go
func demonstrateComplexConditions() {
    fmt.Println("\n=== Complex Conditions ===")

    age := 25
    hasLicense := true
    hasInsurance := true
    yearsExperience := 3

    // Complex boolean expressions
    if age >= 18 && hasLicense && hasInsurance {
        fmt.Println("Eligible to drive")
    }

    // Parentheses for clarity and precedence
    if (age >= 21 && yearsExperience >= 2) || (age >= 25 && hasLicense) {
        fmt.Println("Eligible for car rental")
    }

    // Short-circuit evaluation demonstration
    if hasLicense || checkLicenseDatabase() {
        fmt.Println("License validation passed")
        // checkLicenseDatabase() won't be called if hasLicense is true
    }

    // Negation and De Morgan's laws
    if !(age < 18 || !hasLicense) {
        fmt.Println("Both conditions met: age >= 18 AND hasLicense")
    }
}

func checkLicenseDatabase() bool {
    fmt.Println("Checking license database...")
    return true
}
```

### Loops

Go has only one looping construct: the `for` loop. However, it's flexible enough to handle all common loop patterns.

#### Basic for Loop

```go
func demonstrateBasicForLoop() {
    fmt.Println("\n=== Basic for Loops ===")

    // Classic for loop with initialization, condition, and post statement
    fmt.Print("Counting up: ")
    for i := 1; i <= 5; i++ {
        fmt.Printf("%d ", i)
    }
    fmt.Println()

    // Counting down
    fmt.Print("Counting down: ")
    for i := 5; i >= 1; i-- {
        fmt.Printf("%d ", i)
    }
    fmt.Println()

    // Step by 2
    fmt.Print("Even numbers: ")
    for i := 2; i <= 10; i += 2 {
        fmt.Printf("%d ", i)
    }
    fmt.Println()

    // Multiple variables in for loop
    fmt.Print("Fibonacci sequence: ")
    for a, b := 0, 1; a < 100; a, b = b, a+b {
        fmt.Printf("%d ", a)
    }
    fmt.Println()
}
```

#### for as while Loop

```go
func demonstrateForAsWhile() {
    fmt.Println("\n=== for as while Loop ===")

    // Traditional while loop behavior
    count := 0
    for count < 5 {
        fmt.Printf("Count: %d\n", count)
        count++
    }

    // Reading input until condition is met
    attempts := 0
    maxAttempts := 3

    for attempts < maxAttempts {
        fmt.Printf("Attempt %d of %d\n", attempts+1, maxAttempts)
        // Simulate some operation
        if simulateOperation() {
            fmt.Println("Operation successful!")
            break
        }
        attempts++
    }

    if attempts == maxAttempts {
        fmt.Println("Max attempts reached")
    }
}

func simulateOperation() bool {
    // Simulate a 50% success rate
    return len(fmt.Sprintf("%d", time.Now().Nanosecond())) % 2 == 0
}
```

#### Infinite Loops and Break Conditions

```go
func demonstrateInfiniteLoops() {
    fmt.Println("\n=== Infinite Loops with Break ===")

    counter := 0
    for {  // Infinite loop
        counter++
        fmt.Printf("Iteration: %d\n", counter)

        if counter == 3 {
            fmt.Println("Breaking out of infinite loop")
            break
        }

        // Safety check to prevent actual infinite loop in demo
        if counter > 10 {
            break
        }
    }

    // Infinite loop with multiple exit conditions
    fmt.Println("\nMultiple exit conditions:")
    value := 1
    for {
        fmt.Printf("Value: %d\n", value)

        if value > 20 {
            fmt.Println("Value exceeded 20")
            break
        }

        if value == 13 {
            fmt.Println("Unlucky number encountered!")
            break
        }

        value *= 2
    }
}
```

#### Range-based Loops

```go
func demonstrateRangeLoops() {
    fmt.Println("\n=== Range-based Loops ===")

    // Range over slice
    fruits := []string{"apple", "banana", "cherry", "date"}

    fmt.Println("Fruits with indices:")
    for index, fruit := range fruits {
        fmt.Printf("%d: %s\n", index, fruit)
    }

    fmt.Println("\nJust the fruits:")
    for _, fruit := range fruits {
        fmt.Printf("- %s\n", fruit)
    }

    fmt.Println("\nJust the indices:")
    for index := range fruits {
        fmt.Printf("Index: %d\n", index)
    }

    // Range over map
    scores := map[string]int{
        "Alice": 95,
        "Bob":   87,
        "Carol": 92,
    }

    fmt.Println("\nStudent scores:")
    for name, score := range scores {
        fmt.Printf("%s: %d\n", name, score)
    }

    // Range over string (iterates over runes)
    text := "Hello, 世界!"
    fmt.Println("\nCharacter analysis:")
    for index, runeValue := range text {
        fmt.Printf("Index %d: %c (Unicode: %d)\n", index, runeValue, runeValue)
    }

    // Range over channel (will be covered in concurrency chapter)
    ch := make(chan int, 3)
    ch <- 1
    ch <- 2
    ch <- 3
    close(ch)

    fmt.Println("\nChannel values:")
    for value := range ch {
        fmt.Printf("Received: %d\n", value)
    }
}
```

### Switch Statements

Go's switch statement is more powerful and flexible than in many other languages.

#### Basic Switch

```go
func demonstrateBasicSwitch() {
    fmt.Println("\n=== Basic Switch Statements ===")

    day := "Wednesday"

    switch day {
    case "Monday":
        fmt.Println("Start of work week")
    case "Tuesday", "Wednesday", "Thursday":
        fmt.Println("Midweek")
    case "Friday":
        fmt.Println("TGIF!")
    case "Saturday", "Sunday":
        fmt.Println("Weekend!")
    default:
        fmt.Println("Invalid day")
    }

    // Switch with expressions
    score := 85

    switch {
    case score >= 90:
        fmt.Println("Grade: A")
    case score >= 80:
        fmt.Println("Grade: B")
    case score >= 70:
        fmt.Println("Grade: C")
    case score >= 60:
        fmt.Println("Grade: D")
    default:
        fmt.Println("Grade: F")
    }
}
```

#### Switch with Short Statement

```go
func demonstrateSwitchWithShortStatement() {
    fmt.Println("\n=== Switch with Short Statement ===")

    // Switch with initialization
    switch hour := time.Now().Hour(); {
    case hour < 6:
        fmt.Println("Very early morning")
    case hour < 12:
        fmt.Println("Morning")
    case hour < 18:
        fmt.Println("Afternoon")
    default:
        fmt.Println("Evening")
    }

    // Switch on function result
    switch result := calculateGrade(78); result {
    case "A", "B":
        fmt.Printf("Excellent work! Grade: %s\n", result)
    case "C":
        fmt.Printf("Good job! Grade: %s\n", result)
    default:
        fmt.Printf("Keep trying! Grade: %s\n", result)
    }
}

func calculateGrade(score int) string {
    switch {
    case score >= 90:
        return "A"
    case score >= 80:
        return "B"
    case score >= 70:
        return "C"
    case score >= 60:
        return "D"
    default:
        return "F"
    }
}
```

#### Type Switch

```go
func demonstrateTypeSwitch() {
    fmt.Println("\n=== Type Switch ===")

    var items []interface{} = []interface{}{
        42,
        "hello",
        3.14,
        true,
        []int{1, 2, 3},
        map[string]int{"key": 100},
    }

    for i, item := range items {
        fmt.Printf("Item %d: ", i+1)

        switch v := item.(type) {
        case int:
            fmt.Printf("Integer: %d\n", v)
        case string:
            fmt.Printf("String: %s (length: %d)\n", v, len(v))
        case float64:
            fmt.Printf("Float: %.2f\n", v)
        case bool:
            fmt.Printf("Boolean: %t\n", v)
        case []int:
            fmt.Printf("Int slice: %v (length: %d)\n", v, len(v))
        case map[string]int:
            fmt.Printf("String-int map: %v\n", v)
        default:
            fmt.Printf("Unknown type: %T\n", v)
        }
    }
}
```

#### Fallthrough

```go
func demonstrateFallthrough() {
    fmt.Println("\n=== Fallthrough Demonstration ===")

    grade := "B"

    fmt.Printf("Grade %s qualifies for:\n", grade)

    switch grade {
    case "A":
        fmt.Println("- Honor roll")
        fallthrough
    case "B":
        fmt.Println("- Dean's list")
        fallthrough
    case "C":
        fmt.Println("- Graduation eligible")
        fallthrough
    case "D":
        fmt.Println("- Course credit")
    case "F":
        fmt.Println("- Must retake")
    default:
        fmt.Println("- Invalid grade")
    }

    // Note: fallthrough must be the last statement in a case
    // and cannot be used in the last case or default
}
```

### Control Flow Keywords

#### Break and Continue

```go
func demonstrateBreakContinue() {
    fmt.Println("\n=== Break and Continue ===")

    // Continue skips current iteration
    fmt.Println("Even numbers from 1 to 10:")
    for i := 1; i <= 10; i++ {
        if i%2 != 0 {
            continue  // Skip odd numbers
        }
        fmt.Printf("%d ", i)
    }
    fmt.Println()

    // Break exits loop early
    fmt.Println("Finding first number divisible by 7:")
    for i := 1; i <= 100; i++ {
        if i%7 == 0 {
            fmt.Printf("Found: %d\n", i)
            break
        }
    }

    // Break and continue with labeled loops
    fmt.Println("\nNested loop with labels:")

outer:
    for i := 1; i <= 3; i++ {
        fmt.Printf("Outer loop: %d\n", i)

        for j := 1; j <= 3; j++ {
            if i == 2 && j == 2 {
                fmt.Println("  Breaking outer loop!")
                break outer
            }

            if j == 2 {
                fmt.Println("  Skipping inner iteration 2")
                continue
            }

            fmt.Printf("  Inner loop: %d\n", j)
        }
    }

    fmt.Println("After nested loops")
}
```

#### Goto Statement

```go
func demonstrateGoto() {
    fmt.Println("\n=== Goto Statement ===")

    // Note: goto is rarely used in Go and generally discouraged
    // This example shows syntax, not recommended practice

    counter := 0

loop:
    counter++
    fmt.Printf("Counter: %d\n", counter)

    if counter < 3 {
        goto loop
    }

    fmt.Println("Goto loop finished")

    // Goto for error handling (also not recommended)
    if err := riskyOperation(); err != nil {
        goto errorHandler
    }

    fmt.Println("Operation succeeded")
    goto end

errorHandler:
    fmt.Println("Error occurred, cleaning up...")
    // cleanup code here

end:
    fmt.Println("Program ending")
}

func riskyOperation() error {
    // Simulate 50% failure rate
    if time.Now().Nanosecond()%2 == 0 {
        return fmt.Errorf("operation failed")
    }
    return nil
}
```

### Advanced Control Flow Patterns

#### Error Handling Patterns

```go
func demonstrateErrorHandlingPatterns() {
    fmt.Println("\n=== Error Handling Control Flow ===")

    // Early return pattern
    if err := validateInput(""); err != nil {
        fmt.Printf("Validation error: %v\n", err)
        return
    }

    // Guard clauses
    data := []int{1, 2, 3, 4, 5}

    if len(data) == 0 {
        fmt.Println("No data to process")
        return
    }

    if data[0] < 0 {
        fmt.Println("Invalid first element")
        return
    }

    // Main processing logic
    fmt.Println("Processing data:", data)

    // Multiple error checks in loop
    for i, value := range data {
        if value < 0 {
            fmt.Printf("Skipping negative value at index %d\n", i)
            continue
        }

        if value > 10 {
            fmt.Printf("Value %d too large, stopping processing\n", value)
            break
        }

        fmt.Printf("Processing value: %d\n", value)
    }
}

func validateInput(input string) error {
    if len(input) == 0 {
        return fmt.Errorf("input cannot be empty")
    }
    return nil
}
```

#### State Machine Pattern

```go
type State int

const (
    StateIdle State = iota
    StateRunning
    StatePaused
    StateStopped
)

func (s State) String() string {
    switch s {
    case StateIdle:
        return "Idle"
    case StateRunning:
        return "Running"
    case StatePaused:
        return "Paused"
    case StateStopped:
        return "Stopped"
    default:
        return "Unknown"
    }
}

func demonstrateStateMachine() {
    fmt.Println("\n=== State Machine Example ===")

    currentState := StateIdle
    commands := []string{"start", "pause", "resume", "stop", "invalid"}

    for _, command := range commands {
        fmt.Printf("Current state: %s, Command: %s\n", currentState, command)

        switch currentState {
        case StateIdle:
            switch command {
            case "start":
                currentState = StateRunning
                fmt.Println("→ Started running")
            default:
                fmt.Printf("→ Cannot %s from idle state\n", command)
            }

        case StateRunning:
            switch command {
            case "pause":
                currentState = StatePaused
                fmt.Println("→ Paused")
            case "stop":
                currentState = StateStopped
                fmt.Println("→ Stopped")
            default:
                fmt.Printf("→ Cannot %s while running\n", command)
            }

        case StatePaused:
            switch command {
            case "resume":
                currentState = StateRunning
                fmt.Println("→ Resumed")
            case "stop":
                currentState = StateStopped
                fmt.Println("→ Stopped")
            default:
                fmt.Printf("→ Cannot %s while paused\n", command)
            }

        case StateStopped:
            switch command {
            case "start":
                currentState = StateRunning
                fmt.Println("→ Restarted")
            default:
                fmt.Printf("→ Cannot %s when stopped\n", command)
            }
        }

        fmt.Printf("New state: %s\n\n", currentState)
    }
}
```

### ⚠️ Common Pitfalls

1. **Infinite Loops Without Exit Condition**
```go
// Dangerous: truly infinite loop
func badInfiniteLoop() {
    for {
        // No break condition - this will run forever
        fmt.Println("This runs forever")
    }
}

// Better: Always have exit conditions
func goodInfiniteLoop() {
    count := 0
    for {
        if count >= 10 {
            break
        }
        fmt.Printf("Count: %d\n", count)
        count++
    }
}
```

2. **Forgetting Break in Switch (when fallthrough is not intended)**
```go
// In Go, cases don't fall through by default (unlike C/Java)
// This is actually correct Go code:
func correctSwitch(value int) {
    switch value {
    case 1:
        fmt.Println("One")
        // No break needed - Go doesn't fall through
    case 2:
        fmt.Println("Two")
    default:
        fmt.Println("Other")
    }
}
```

3. **Range Variable Reuse in Goroutines**
```go
// Common mistake (will be detailed in concurrency chapter)
func rangeVariablePitfall() {
    items := []int{1, 2, 3, 4, 5}

    // Wrong: all goroutines will likely print the same value
    for _, item := range items {
        go func() {
            fmt.Println(item) // item is reused!
        }()
    }

    // Correct: pass value as parameter
    for _, item := range items {
        go func(value int) {
            fmt.Println(value)
        }(item)
    }
}
```

### ✅ Best Practices

1. **Use Early Returns for Error Handling**
```go
func processData(data []int) error {
    if len(data) == 0 {
        return fmt.Errorf("empty data")
    }

    if data[0] < 0 {
        return fmt.Errorf("invalid first element")
    }

    // Main logic here
    return nil
}
```

2. **Prefer Range Loops for Collections**
```go
// Good: Use range for cleaner code
for index, value := range items {
    process(index, value)
}

// Less preferred: manual indexing
for i := 0; i < len(items); i++ {
    process(i, items[i])
}
```

3. **Use Switch for Multiple Conditions**
```go
// Good: switch is cleaner than multiple if-else
switch {
case score >= 90:
    return "A"
case score >= 80:
    return "B"
case score >= 70:
    return "C"
default:
    return "F"
}

// Less clean: multiple if-else statements
if score >= 90 {
    return "A"
} else if score >= 80 {
    return "B"
} else if score >= 70 {
    return "C"
} else {
    return "F"
}
```

### 🏋️ Exercise 3: Control Flow Mastery
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 30 minutes

Create a program that implements a simple text-based game using all control structures learned in this chapter. The game should:

1. Use a menu-driven interface with switch statements
2. Implement a game loop with various exit conditions
3. Use if statements for game logic and validation
4. Include range loops for processing collections
5. Demonstrate break, continue, and proper error handling
6. Use both basic and type switches where appropriate

<details>
<summary>💡 Click to see hints</summary>

- Create a simple adventure game or number guessing game
- Use an enum-like pattern with iota for game states
- Implement input validation with error handling
- Use labeled loops for complex control flow
- Include a scoring system with grade calculation
- Add a replay functionality

</details>

<details>
<summary>✅ Click to see solution</summary>

```go
package main

import (
    "bufio"
    "fmt"
    "math/rand"
    "os"
    "strconv"
    "strings"
    "time"
)

// Game states using iota
type GameState int

const (
    StateMenu GameState = iota
    StatePlaying
    StateGameOver
    StateQuit
)

func (gs GameState) String() string {
    switch gs {
    case StateMenu:
        return "Menu"
    case StatePlaying:
        return "Playing"
    case StateGameOver:
        return "Game Over"
    case StateQuit:
        return "Quit"
    default:
        return "Unknown"
    }
}

// Game difficulty levels
type Difficulty int

const (
    Easy Difficulty = iota
    Medium
    Hard
)

// Player represents a game player
type Player struct {
    Name     string
    Score    int
    Lives    int
    Level    int
}

// Game represents the main game state
type Game struct {
    Player      Player
    State       GameState
    Difficulty  Difficulty
    Target      int
    Attempts    int
    MaxAttempts int
    Reader      *bufio.Reader
}

// NewGame creates a new game instance
func NewGame() *Game {
    rand.Seed(time.Now().UnixNano())
    return &Game{
        State:  StateMenu,
        Reader: bufio.NewReader(os.Stdin),
    }
}

// Run starts the main game loop
func (g *Game) Run() {
    fmt.Println("🎮 Welcome to the Number Guessing Adventure!")
    fmt.Println("==========================================")

    // Main game loop with multiple exit conditions
gameLoop:
    for {
        switch g.State {
        case StateMenu:
            g.showMenu()
            g.handleMenuInput()

        case StatePlaying:
            g.playGame()

        case StateGameOver:
            g.showGameOver()
            if !g.askPlayAgain() {
                g.State = StateQuit
            } else {
                g.resetGame()
                g.State = StateMenu
            }

        case StateQuit:
            fmt.Println("👋 Thanks for playing!")
            break gameLoop

        default:
            fmt.Printf("Unknown game state: %s\n", g.State)
            g.State = StateQuit
        }
    }
}

// showMenu displays the main menu
func (g *Game) showMenu() {
    fmt.Println("\n=== MAIN MENU ===")
    fmt.Println("1. Start New Game")
    fmt.Println("2. View High Scores")
    fmt.Println("3. How to Play")
    fmt.Println("4. Quit")
    fmt.Print("Choose an option (1-4): ")
}

// handleMenuInput processes menu selections
func (g *Game) handleMenuInput() {
    input := g.getInput()

    switch input {
    case "1":
        if g.setupNewGame() {
            g.State = StatePlaying
        }
    case "2":
        g.showHighScores()
    case "3":
        g.showInstructions()
    case "4":
        g.State = StateQuit
    default:
        fmt.Println("❌ Invalid option. Please choose 1-4.")
    }
}

// setupNewGame initializes a new game session
func (g *Game) setupNewGame() bool {
    // Get player name with validation
    for {
        fmt.Print("Enter your name: ")
        name := g.getInput()

        // Input validation with continue
        if len(strings.TrimSpace(name)) == 0 {
            fmt.Println("❌ Name cannot be empty. Please try again.")
            continue
        }

        if len(name) > 20 {
            fmt.Println("❌ Name too long. Please use 20 characters or less.")
            continue
        }

        g.Player.Name = strings.TrimSpace(name)
        break
    }

    // Choose difficulty
    for {
        fmt.Println("\nChoose difficulty:")
        fmt.Println("1. Easy (1-10, 5 attempts)")
        fmt.Println("2. Medium (1-50, 7 attempts)")
        fmt.Println("3. Hard (1-100, 10 attempts)")
        fmt.Print("Select difficulty (1-3): ")

        choice := g.getInput()

        switch choice {
        case "1":
            g.Difficulty = Easy
            g.MaxAttempts = 5
            g.Target = rand.Intn(10) + 1
        case "2":
            g.Difficulty = Medium
            g.MaxAttempts = 7
            g.Target = rand.Intn(50) + 1
        case "3":
            g.Difficulty = Hard
            g.MaxAttempts = 10
            g.Target = rand.Intn(100) + 1
        default:
            fmt.Println("❌ Invalid choice. Please select 1-3.")
            continue
        }

        break
    }

    // Initialize player stats
    g.Player.Score = 0
    g.Player.Lives = 3
    g.Player.Level = 1
    g.Attempts = 0

    fmt.Printf("\n🎯 Game started! Good luck, %s!\n", g.Player.Name)
    g.showGameInfo()
    return true
}

// playGame handles the main game logic
func (g *Game) playGame() {
    fmt.Printf("\n=== LEVEL %d ===\n", g.Player.Level)
    fmt.Print("Enter your guess: ")

    input := g.getInput()

    // Validate numeric input
    guess, err := strconv.Atoi(input)
    if err != nil {
        fmt.Println("❌ Please enter a valid number.")
        return
    }

    g.Attempts++

    // Game logic with multiple conditions
    if guess == g.Target {
        g.handleCorrectGuess()
    } else {
        g.handleIncorrectGuess(guess)
    }

    // Check game ending conditions
    if g.Attempts >= g.MaxAttempts || g.Player.Lives <= 0 {
        g.State = StateGameOver
        return
    }
}

// handleCorreectGuess processes correct guesses
func (g *Game) handleCorrectGuess() {
    fmt.Println("🎉 Correct! You got it!")

    // Calculate score based on difficulty and attempts
    var baseScore int
    switch g.Difficulty {
    case Easy:
        baseScore = 100
    case Medium:
        baseScore = 250
    case Hard:
        baseScore = 500
    }

    // Bonus for fewer attempts
    bonus := (g.MaxAttempts - g.Attempts) * 50
    roundScore := baseScore + bonus
    g.Player.Score += roundScore

    fmt.Printf("💯 Round score: %d (Base: %d, Bonus: %d)\n",
               roundScore, baseScore, bonus)
    fmt.Printf("📊 Total score: %d\n", g.Player.Score)

    // Advance to next level or end game
    if g.Player.Level >= 3 {
        fmt.Println("🏆 Congratulations! You've completed all levels!")
        g.State = StateGameOver
    } else {
        g.advanceLevel()
    }
}

// handleIncorrectGuess processes wrong guesses
func (g *Game) handleIncorrectGuess(guess int) {
    remainingAttempts := g.MaxAttempts - g.Attempts

    if guess < g.Target {
        fmt.Printf("📈 Too low! ")
    } else {
        fmt.Printf("📉 Too high! ")
    }

    // Different messages based on attempts remaining
    switch {
    case remainingAttempts == 0:
        fmt.Printf("💀 No more attempts! The number was %d.\n", g.Target)
        g.Player.Lives--
    case remainingAttempts == 1:
        fmt.Printf("⚠️  Last chance! 1 attempt remaining.\n")
    default:
        fmt.Printf("You have %d attempts left.\n", remainingAttempts)
    }

    // Provide hints based on how close the guess is
    difference := abs(guess - g.Target)
    switch {
    case difference <= 2:
        fmt.Println("🔥 Very close!")
    case difference <= 5:
        fmt.Println("🌡️  Getting warmer!")
    case difference <= 10:
        fmt.Println("❄️  Getting colder...")
    }

    fmt.Printf("💖 Lives: %d, 📊 Score: %d\n", g.Player.Lives, g.Player.Score)
}

// advanceLevel progresses to the next level
func (g *Game) advanceLevel() {
    g.Player.Level++
    g.Attempts = 0

    // Increase difficulty progressively
    switch g.Difficulty {
    case Easy:
        g.Target = rand.Intn(15) + 1
        g.MaxAttempts = 4
    case Medium:
        g.Target = rand.Intn(75) + 1
        g.MaxAttempts = 6
    case Hard:
        g.Target = rand.Intn(150) + 1
        g.MaxAttempts = 8
    }

    fmt.Printf("🆙 Level up! Welcome to level %d!\n", g.Player.Level)
    g.showGameInfo()
}

// showGameOver displays the game over screen
func (g *Game) showGameOver() {
    fmt.Println("\n" + strings.Repeat("=", 30))
    fmt.Println("           GAME OVER")
    fmt.Println(strings.Repeat("=", 30))

    fmt.Printf("Player: %s\n", g.Player.Name)
    fmt.Printf("Final Score: %d\n", g.Player.Score)
    fmt.Printf("Levels Completed: %d\n", g.Player.Level-1)

    // Grade the performance
    grade := g.calculateGrade()
    fmt.Printf("Performance Grade: %s\n", grade)

    // Show grade-specific message
    switch grade {
    case "A+", "A":
        fmt.Println("🏆 Outstanding performance!")
    case "B":
        fmt.Println("👍 Good job!")
    case "C":
        fmt.Println("👌 Not bad!")
    default:
        fmt.Println("💪 Keep practicing!")
    }
}

// calculateGrade determines player performance grade
func (g *Game) calculateGrade() string {
    // Grade based on score ranges
    switch {
    case g.Player.Score >= 2000:
        return "A+"
    case g.Player.Score >= 1500:
        return "A"
    case g.Player.Score >= 1000:
        return "B"
    case g.Player.Score >= 500:
        return "C"
    case g.Player.Score >= 100:
        return "D"
    default:
        return "F"
    }
}

// showHighScores displays mock high scores
func (g *Game) showHighScores() {
    fmt.Println("\n=== HIGH SCORES ===")

    // Mock data for demonstration
    scores := []struct {
        name  string
        score int
        grade string
    }{
        {"Alice", 2500, "A+"},
        {"Bob", 1800, "A"},
        {"Carol", 1200, "B"},
        {"Dave", 800, "C"},
        {"Eve", 400, "D"},
    }

    for i, entry := range scores {
        fmt.Printf("%d. %s - %d points (%s)\n", i+1, entry.name, entry.score, entry.grade)
    }
}

// showInstructions displays game rules
func (g *Game) showInstructions() {
    fmt.Println("\n=== HOW TO PLAY ===")
    instructions := []string{
        "🎯 Guess the secret number within the given range",
        "📊 Earn points based on difficulty and efficiency",
        "💖 You have 3 lives - lose one when you run out of attempts",
        "🆙 Complete 3 levels to win the game",
        "🔥 Get hints based on how close your guesses are",
        "🏆 Try to achieve the highest score possible!",
    }

    for _, instruction := range instructions {
        fmt.Printf("   %s\n", instruction)
    }
}

// resetGame resets game state for replay
func (g *Game) resetGame() {
    g.Player = Player{}
    g.State = StateMenu
    g.Target = 0
    g.Attempts = 0
    g.MaxAttempts = 0
}

// showGameInfo displays current game information
func (g *Game) showGameInfo() {
    var rangeStr string
    switch g.Difficulty {
    case Easy:
        rangeStr = "1-10"
    case Medium:
        rangeStr = "1-50"
    case Hard:
        rangeStr = "1-100"
    }

    fmt.Printf("🎲 Range: %s | 🎯 Max attempts: %d | 💖 Lives: %d\n",
               rangeStr, g.MaxAttempts, g.Player.Lives)
}

// askPlayAgain prompts user to play again
func (g *Game) askPlayAgain() bool {
    for {
        fmt.Print("\nWould you like to play again? (y/n): ")
        response := strings.ToLower(strings.TrimSpace(g.getInput()))

        switch response {
        case "y", "yes":
            return true
        case "n", "no":
            return false
        default:
            fmt.Println("❌ Please enter 'y' for yes or 'n' for no.")
        }
    }
}

// getInput reads user input safely
func (g *Game) getInput() string {
    input, err := g.Reader.ReadString('\n')
    if err != nil {
        fmt.Printf("Error reading input: %v\n", err)
        return ""
    }
    return strings.TrimSpace(input)
}

// abs returns absolute value of integer
func abs(x int) int {
    if x < 0 {
        return -x
    }
    return x
}

// Type switch demonstration within the game context
func (g *Game) demonstrateTypeSwitch() {
    fmt.Println("\n=== Type Switch Demo (Advanced Feature) ===")

    var values []interface{} = []interface{}{
        42,
        "hello world",
        3.14159,
        true,
        []int{1, 2, 3},
        Player{Name: "Demo", Score: 100},
    }

    for i, val := range values {
        fmt.Printf("Value %d: ", i+1)

        switch v := val.(type) {
        case int:
            if v > 10 {
                fmt.Printf("Large integer: %d\n", v)
            } else {
                fmt.Printf("Small integer: %d\n", v)
            }
        case string:
            if len(v) > 5 {
                fmt.Printf("Long string: %s\n", v)
            } else {
                fmt.Printf("Short string: %s\n", v)
            }
        case float64:
            fmt.Printf("Float: %.2f\n", v)
        case bool:
            if v {
                fmt.Println("Boolean: true")
            } else {
                fmt.Println("Boolean: false")
            }
        case []int:
            fmt.Printf("Integer slice with %d elements: %v\n", len(v), v)
        case Player:
            fmt.Printf("Player: %s (Score: %d)\n", v.Name, v.Score)
        default:
            fmt.Printf("Unknown type: %T with value %v\n", v, v)
        }
    }
}

```

**Explanation:**

This comprehensive solution demonstrates all control structures covered in this chapter:

**Key concepts demonstrated:**
1. **Switch statements**: Menu handling, difficulty selection, game state management
2. **if-else chains**: Input validation, game logic, scoring conditions
3. **for loops**: Main game loop, input validation loops, data processing
4. **Range loops**: Processing slices of instructions, scores, and game values
5. **Break and continue**: Loop control in input validation and game flow
6. **Labeled loops**: Main game loop with clean exit
7. **Type switch**: Advanced feature demonstration with different data types

**Control flow patterns shown:**
- **State machine**: Game states transition cleanly between menu, playing, game over
- **Input validation**: Robust error handling with retry loops
- **Early returns**: Clean error handling in game setup
- **Guard clauses**: Input validation and boundary checking
- **Multiple exit conditions**: Game can end via completion, lives lost, or user quit

**Performance considerations:**
- Uses efficient switch statements instead of multiple if-else chains
- Minimizes unnecessary condition checking with early returns
- Proper resource management with bufio.Reader
- State transitions are O(1) operations

**Best practices demonstrated:**
- Clear separation of concerns with different methods
- Comprehensive input validation
- User-friendly error messages
- Consistent code formatting and naming
- Proper use of Go idioms and conventions

</details>

---

## Chapter 4: Functions
📊 **Progress:** Chapter 4 of 12 | ⏱️ **Estimated reading time:** 22 minutes

🎯 **Learning Objectives:**
- Master function declaration and parameter handling
- Understand return values and multiple returns
- Learn about variadic functions and closures
- Explore the defer statement and its applications

📋 **Prerequisites:** Understanding of basic syntax, data types, and control structures

### Function Declaration

Functions are the building blocks of Go programs. They encapsulate reusable code and provide a way to organize your program's logic.

#### Basic Function Syntax

```go
package main

import "fmt"

// Basic function with no parameters or return value
func greet() {
    fmt.Println("Hello, World!")
}

// Function with parameters
func greetPerson(name string) {
    fmt.Printf("Hello, %s!\n", name)
}

// Function with return value
func add(a, b int) int {
    return a + b
}

// Function with multiple parameters of same type
func calculateRectangleArea(length, width float64) float64 {
    return length * width
}

// Function with mixed parameter types
func formatUserInfo(name string, age int, isActive bool) string {
    status := "inactive"
    if isActive {
        status = "active"
    }
    return fmt.Sprintf("User: %s, Age: %d, Status: %s", name, age, status)
}

func demonstrateBasicFunctions() {
    fmt.Println("=== Basic Functions ===")

    // Call function with no parameters
    greet()

    // Call function with parameters
    greetPerson("Alice")

    // Call function with return value
    sum := add(5, 3)
    fmt.Printf("5 + 3 = %d\n", sum)

    // Use return value directly
    fmt.Printf("Rectangle area: %.2f\n", calculateRectangleArea(10.5, 8.2))

    // Function with multiple parameter types
    info := formatUserInfo("Bob", 30, true)
    fmt.Println(info)
}
```

#### Function Naming Conventions

```go
// Exported functions (public) - start with capital letter
func PublicFunction() {
    fmt.Println("This function is exported")
}

// Unexported functions (private) - start with lowercase letter
func privateFunction() {
    fmt.Println("This function is private to the package")
}

// Good naming examples
func calculateTax(income float64) float64 { return income * 0.15 }
func isValidEmail(email string) bool { return len(email) > 0 } // Simplified
func getUserById(id int) (User, error) { return User{}, nil } // Will implement later

// Avoid unclear abbreviations
func calcTx(inc float64) float64 { return inc * 0.15 } // Unclear

// Use descriptive names for complex operations
func generatePasswordResetToken(userID int) string {
    // Complex logic here
    return fmt.Sprintf("token_%d_%d", userID, time.Now().Unix())
}
```

### Parameters and Return Values

#### Multiple Return Values

One of Go's distinctive features is support for multiple return values:

```go
func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, fmt.Errorf("division by zero")
    }
    return a / b, nil
}

func getMinMax(numbers []int) (int, int, error) {
    if len(numbers) == 0 {
        return 0, 0, fmt.Errorf("empty slice")
    }

    min := numbers[0]
    max := numbers[0]

    for _, num := range numbers[1:] {
        if num < min {
            min = num
        }
        if num > max {
            max = num
        }
    }

    return min, max, nil
}

func demonstrateMultipleReturns() {
    fmt.Println("\n=== Multiple Return Values ===")

    // Handle multiple returns
    result, err := divide(10, 3)
    if err != nil {
        fmt.Printf("Error: %v\n", err)
    } else {
        fmt.Printf("10 / 3 = %.2f\n", result)
    }

    // Error case
    _, err = divide(10, 0)
    if err != nil {
        fmt.Printf("Error: %v\n", err)
    }

    // Multiple values
    numbers := []int{5, 2, 8, 1, 9, 3}
    min, max, err := getMinMax(numbers)
    if err != nil {
        fmt.Printf("Error: %v\n", err)
    } else {
        fmt.Printf("Numbers: %v\n", numbers)
        fmt.Printf("Min: %d, Max: %d\n", min, max)
    }

    // Ignoring return values with blank identifier
    _, maxOnly, _ := getMinMax(numbers)
    fmt.Printf("Only max value: %d\n", maxOnly)
}
```

#### Named Return Values

Go supports named return values, which can make code more readable and enable naked returns:

```go
func calculateStats(numbers []float64) (mean, median float64, err error) {
    if len(numbers) == 0 {
        err = fmt.Errorf("empty slice")
        return // naked return - returns named values
    }

    // Calculate mean
    sum := 0.0
    for _, num := range numbers {
        sum += num
    }
    mean = sum / float64(len(numbers))

    // Calculate median (simplified)
    // Note: This modifies the original slice - in production, make a copy
    sort.Float64s(numbers)
    n := len(numbers)
    if n%2 == 0 {
        median = (numbers[n/2-1] + numbers[n/2]) / 2
    } else {
        median = numbers[n/2]
    }

    return // naked return
}

func processOrder(customerID int, items []string) (orderID string, totalAmount float64, err error) {
    // Validation
    if customerID <= 0 {
        err = fmt.Errorf("invalid customer ID")
        return
    }

    if len(items) == 0 {
        err = fmt.Errorf("no items in order")
        return
    }

    // Generate order ID
    orderID = fmt.Sprintf("ORD-%d-%d", customerID, time.Now().Unix())

    // Calculate total (simplified)
    totalAmount = float64(len(items)) * 29.99

    return // Returns orderID, totalAmount, err (which is nil)
}

func demonstrateNamedReturns() {
    fmt.Println("\n=== Named Return Values ===")

    data := []float64{1.5, 2.3, 3.7, 2.1, 4.8, 3.2, 1.9}
    mean, median, err := calculateStats(data)

    if err != nil {
        fmt.Printf("Error: %v\n", err)
    } else {
        fmt.Printf("Data: %v\n", data)
        fmt.Printf("Mean: %.2f, Median: %.2f\n", mean, median)
    }

    // Process order example
    orderID, total, err := processOrder(12345, []string{"item1", "item2", "item3"})
    if err != nil {
        fmt.Printf("Order error: %v\n", err)
    } else {
        fmt.Printf("Order processed: %s, Total: $%.2f\n", orderID, total)
    }
}

### Variadic Functions

Variadic functions accept a variable number of arguments of the same type:

```go
// Basic variadic function
func sum(numbers ...int) int {
    total := 0
    for _, num := range numbers {
        total += num
    }
    return total
}

// Variadic with other parameters (must be last)
func logMessage(level string, messages ...string) {
    fmt.Printf("[%s] ", level)
    for i, message := range messages {
        fmt.Print(message)
        if i < len(messages)-1 {
            fmt.Print(" - ")
        }
    }
    fmt.Println()
}

// Printf-style function with interface{}
func printf(format string, args ...interface{}) {
    fmt.Printf(format, args...)
}

func demonstrateVariadicFunctions() {
    fmt.Println("\n=== Variadic Functions ===")

    // Call with different numbers of arguments
    fmt.Printf("sum(): %d\n", sum())
    fmt.Printf("sum(5): %d\n", sum(5))
    fmt.Printf("sum(1, 2, 3): %d\n", sum(1, 2, 3))
    fmt.Printf("sum(1, 2, 3, 4, 5): %d\n", sum(1, 2, 3, 4, 5))

    // Expanding slice to variadic
    numbers := []int{10, 20, 30, 40}
    fmt.Printf("sum(slice...): %d\n", sum(numbers...))

    // Logging examples
    logMessage("INFO", "Application started")
    logMessage("ERROR", "Database connection failed", "Retrying in 5 seconds")
    logMessage("DEBUG", "User ID:", "12345", "Action:", "login")

    // Printf-style usage
    printf("Hello, %s! You have %d messages.\n", "Alice", 5)
}
```

### Anonymous Functions and Closures

Go supports anonymous functions and closures, which can capture variables from their surrounding scope:

```go
func demonstrateAnonymousFunctions() {
    fmt.Println("\n=== Anonymous Functions ===")

    // Basic anonymous function
    func() {
        fmt.Println("Anonymous function executed")
    }()

    // Anonymous function with parameters and return
    result := func(a, b int) int {
        return a * b
    }(5, 7)
    fmt.Printf("Anonymous function result: %d\n", result)

    // Assigning anonymous function to variable
    multiply := func(x, y int) int {
        return x * y
    }
    fmt.Printf("multiply(3, 4) = %d\n", multiply(3, 4))

    // Function returning a function
    makeAdder := func(base int) func(int) int {
        return func(x int) int {
            return base + x
        }
    }

    add10 := makeAdder(10)
    add100 := makeAdder(100)

    fmt.Printf("add10(5) = %d\n", add10(5))
    fmt.Printf("add100(5) = %d\n", add100(5))
}

func demonstrateClosures() {
    fmt.Println("\n=== Closures ===")

    // Closure capturing local variable
    counter := 0
    increment := func() int {
        counter++
        return counter
    }

    fmt.Printf("Counter: %d\n", increment())
    fmt.Printf("Counter: %d\n", increment())
    fmt.Printf("Counter: %d\n", increment())

    // Multiple closures sharing state
    decrement := func() int {
        counter--
        return counter
    }

    fmt.Printf("After decrement: %d\n", decrement())

    // Closure factory
    makeCounter := func(start int) func() int {
        current := start
        return func() int {
            current++
            return current
        }
    }

    counter1 := makeCounter(0)
    counter2 := makeCounter(100)

    fmt.Printf("Counter1: %d, %d, %d\n", counter1(), counter1(), counter1())
    fmt.Printf("Counter2: %d, %d, %d\n", counter2(), counter2(), counter2())

    // Closure for event handling
    buttons := []string{"Save", "Cancel", "Delete"}
    for _, name := range buttons {
        // Capture loop variable properly
        buttonName := name
        onClick := func() {
            fmt.Printf("Button '%s' clicked!\n", buttonName)
        }
        onClick()
    }
}
```

### Defer Statement

The defer statement postpones the execution of a function until the surrounding function returns:

```go
func demonstrateBasicDefer() {
    fmt.Println("\n=== Basic Defer ===")

    fmt.Println("Function start")

    defer fmt.Println("Deferred: This executes last")

    fmt.Println("Function middle")
    fmt.Println("Function end")
}

func demonstrateMultipleDefers() {
    fmt.Println("\n=== Multiple Defers (LIFO) ===")

    defer fmt.Println("Deferred: First")
    defer fmt.Println("Deferred: Second")
    defer fmt.Println("Deferred: Third")

    fmt.Println("Regular execution")
}

func demonstrateDeferWithParameters() {
    fmt.Println("\n=== Defer with Parameters ===")

    x := 10
    defer fmt.Printf("Deferred: x = %d\n", x) // x is evaluated now (10)

    x = 20
    defer func() {
        fmt.Printf("Deferred closure: x = %d\n", x) // x evaluated when defer executes (20)
    }()

    x = 30
    fmt.Printf("Current: x = %d\n", x)
}

func demonstrateFileHandlingWithDefer() {
    fmt.Println("\n=== File Handling with Defer ===")

    // Simulate file operations
    filename := "example.txt"

    file, err := openFile(filename)
    if err != nil {
        fmt.Printf("Error opening file: %v\n", err)
        return
    }
    defer closeFile(file) // Ensures file is closed even if function returns early

    // Multiple operations that might return early
    if err := processFile(file); err != nil {
        fmt.Printf("Error processing file: %v\n", err)
        return // file still gets closed due to defer
    }

    if err := validateFile(file); err != nil {
        fmt.Printf("File validation failed: %v\n", err)
        return // file still gets closed due to defer
    }

    fmt.Println("File processing completed successfully")
}

// Helper functions for file demo
type File struct {
    name string
}

func openFile(name string) (*File, error) {
    fmt.Printf("Opening file: %s\n", name)
    return &File{name: name}, nil
}

func closeFile(file *File) {
    fmt.Printf("Closing file: %s\n", file.name)
}

func processFile(file *File) error {
    fmt.Printf("Processing file: %s\n", file.name)
    return nil
}

func validateFile(file *File) error {
    fmt.Printf("Validating file: %s\n", file.name)
    return nil
}

func demonstrateDeferErrorHandling() {
    fmt.Println("\n=== Defer for Error Handling ===")

    defer func() {
        if r := recover(); r != nil {
            fmt.Printf("Recovered from panic: %v\n", r)
        }
    }()

    defer fmt.Println("This defer executes even after panic")

    fmt.Println("About to panic...")
    panic("Something went wrong!")

    fmt.Println("This line won't execute")
}

### ⚠️ Common Pitfalls

1. **Defer in Loops**
```go
// Wrong: defers accumulate in loop
func badDeferInLoop() {
    for i := 0; i < 100; i++ {
        file, _ := openFile(fmt.Sprintf("file%d.txt", i))
        defer closeFile(file) // All defers execute at function end!
    }
    // 100 files remain open until function ends
}

// Better: use a closure or separate function
func goodDeferInLoop() {
    for i := 0; i < 100; i++ {
        func() {
            file, _ := openFile(fmt.Sprintf("file%d.txt", i))
            defer closeFile(file) // Executes at end of anonymous function
            // Process file...
        }()
    }
}
```

2. **Defer Parameter Evaluation**
```go
func deferParameterPitfall() {
    x := 1
    defer fmt.Printf("x = %d\n", x) // x evaluated now (1), not when defer executes
    x = 2
    // Prints: x = 1
}

// Correct way to capture current value
func deferParameterCorrect() {
    x := 1
    defer func() {
        fmt.Printf("x = %d\n", x) // x evaluated when defer executes
    }()
    x = 2
    // Prints: x = 2
}
```

### ✅ Best Practices

1. **Use Defer for Cleanup**
```go
func processWithCleanup() error {
    resource := acquireResource()
    defer releaseResource(resource)

    // Complex processing logic
    // Even if this returns early, resource is cleaned up

    return nil
}
```

2. **Early Return Pattern**
```go
func validateAndProcess(data []byte) error {
    if len(data) == 0 {
        return fmt.Errorf("empty data")
    }

    if !isValid(data) {
        return fmt.Errorf("invalid data")
    }

    // Main processing logic
    return processData(data)
}
```

3. **Function Factory Pattern**
```go
func makeValidator(rules []string) func(string) bool {
    return func(input string) bool {
        for _, rule := range rules {
            if !checkRule(input, rule) {
                return false
            }
        }
        return true
    }
}
```

### 🏋️ Exercise 4: Advanced Functions
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 35 minutes

Create a comprehensive function library that demonstrates:

1. Multiple return values with error handling
2. Variadic functions for flexible input processing
3. Closures for state management and callbacks
4. Defer for resource management and cleanup
5. Function composition and higher-order functions
6. Named returns for improved readability

Build a "Mathematical Expression Evaluator" that can parse and evaluate mathematical expressions with proper error handling and resource management.

<details>
<summary>💡 Click to see hints</summary>

- Create a Calculator struct that manages state
- Use variadic functions for operations with multiple operands
- Implement closures for operation callbacks and history tracking
- Use defer for cleanup and error recovery
- Include comprehensive error handling with multiple return values
- Add logging and debugging capabilities

</details>

<details>
<summary>✅ Click to see solution</summary>

```go
package main

import (
    "fmt"
    "log"
    "math"
    "strconv"
    "strings"
    "time"
)

// Operation represents a mathematical operation
type Operation struct {
    Name      string
    Symbol    string
    Execute   func(...float64) (float64, error)
    MinArgs   int
    MaxArgs   int
}

// Calculator manages mathematical operations and history
type Calculator struct {
    operations map[string]Operation
    history    []CalculationRecord
    precision  int
    debug      bool
    logger     *log.Logger
}

// CalculationRecord stores calculation history
type CalculationRecord struct {
    Expression string
    Result     float64
    Error      string
    Timestamp  time.Time
}

// NewCalculator creates a new calculator instance
func NewCalculator(precision int, debug bool) *Calculator {
    calc := &Calculator{
        operations: make(map[string]Operation),
        history:    make([]CalculationRecord, 0),
        precision:  precision,
        debug:      debug,
    }

    // Initialize logger with defer for cleanup
    if debug {
        calc.logger = log.New(os.Stdout, "[CALC] ", log.LstdFlags)
        defer calc.logger.Println("Calculator initialized with debug mode")
    }

    calc.registerOperations()
    return calc
}

// registerOperations sets up all available mathematical operations
func (c *Calculator) registerOperations() {
    defer func() {
        if c.debug {
            c.logger.Printf("Registered %d operations", len(c.operations))
        }
    }()

    // Addition (variadic)
    c.operations["add"] = Operation{
        Name:    "Addition",
        Symbol:  "+",
        MinArgs: 2,
        MaxArgs: -1, // unlimited
        Execute: func(args ...float64) (result float64, err error) {
            defer func() {
                if c.debug {
                    c.logger.Printf("Addition: %v = %f", args, result)
                }
            }()

            if len(args) < 2 {
                return 0, fmt.Errorf("addition requires at least 2 arguments")
            }

            for _, arg := range args {
                result += arg
            }
            return result, nil
        },
    }

    // Subtraction
    c.operations["subtract"] = Operation{
        Name:    "Subtraction",
        Symbol:  "-",
        MinArgs: 2,
        MaxArgs: 2,
        Execute: func(args ...float64) (float64, error) {
            if len(args) != 2 {
                return 0, fmt.Errorf("subtraction requires exactly 2 arguments")
            }
            return args[0] - args[1], nil
        },
    }

    // Multiplication (variadic)
    c.operations["multiply"] = Operation{
        Name:    "Multiplication",
        Symbol:  "*",
        MinArgs: 2,
        MaxArgs: -1,
        Execute: func(args ...float64) (result float64, err error) {
            defer c.logOperation("multiply", args, &result, &err)

            if len(args) < 2 {
                err = fmt.Errorf("multiplication requires at least 2 arguments")
                return
            }

            result = 1.0
            for _, arg := range args {
                result *= arg
            }
            return
        },
    }

    // Division
    c.operations["divide"] = Operation{
        Name:    "Division",
        Symbol:  "/",
        MinArgs: 2,
        MaxArgs: 2,
        Execute: func(args ...float64) (result float64, err error) {
            defer c.logOperation("divide", args, &result, &err)

            if len(args) != 2 {
                err = fmt.Errorf("division requires exactly 2 arguments")
                return
            }

            if args[1] == 0 {
                err = fmt.Errorf("division by zero")
                return
            }

            result = args[0] / args[1]
            return
        },
    }

    // Power function
    c.operations["power"] = Operation{
        Name:    "Power",
        Symbol:  "^",
        MinArgs: 2,
        MaxArgs: 2,
        Execute: func(args ...float64) (float64, error) {
            if len(args) != 2 {
                return 0, fmt.Errorf("power requires exactly 2 arguments")
            }

            result := math.Pow(args[0], args[1])
            if math.IsNaN(result) || math.IsInf(result, 0) {
                return 0, fmt.Errorf("invalid power operation result")
            }

            return result, nil
        },
    }

    // Square root
    c.operations["sqrt"] = Operation{
        Name:    "Square Root",
        Symbol:  "√",
        MinArgs: 1,
        MaxArgs: 1,
        Execute: func(args ...float64) (float64, error) {
            if len(args) != 1 {
                return 0, fmt.Errorf("square root requires exactly 1 argument")
            }

            if args[0] < 0 {
                return 0, fmt.Errorf("square root of negative number")
            }

            return math.Sqrt(args[0]), nil
        },
    }
}

// logOperation creates a closure for logging operations (demonstrates closure usage)
func (c *Calculator) logOperation(opName string, args []float64, result *float64, err *error) {
    if c.debug && c.logger != nil {
        if *err != nil {
            c.logger.Printf("%s(%v) failed: %v", opName, args, *err)
        } else {
            c.logger.Printf("%s(%v) = %f", opName, args, *result)
        }
    }
}

// Execute performs a mathematical operation with comprehensive error handling
func (c *Calculator) Execute(operationName string, args ...float64) (result float64, err error) {
    // Named return values for cleaner error handling
    defer func() {
        // Record in history regardless of outcome
        record := CalculationRecord{
            Expression: c.formatExpression(operationName, args),
            Result:     result,
            Timestamp:  time.Now(),
        }

        if err != nil {
            record.Error = err.Error()
        }

        c.history = append(c.history, record)

        if c.debug {
            c.logger.Printf("Recorded calculation: %+v", record)
        }
    }()

    // Validate operation exists
    op, exists := c.operations[operationName]
    if !exists {
        err = fmt.Errorf("unknown operation: %s", operationName)
        return
    }

    // Validate argument count
    if len(args) < op.MinArgs {
        err = fmt.Errorf("%s requires at least %d arguments, got %d",
                        op.Name, op.MinArgs, len(args))
        return
    }

    if op.MaxArgs > 0 && len(args) > op.MaxArgs {
        err = fmt.Errorf("%s accepts at most %d arguments, got %d",
                        op.Name, op.MaxArgs, len(args))
        return
    }

    // Validate arguments are not NaN or Inf
    for i, arg := range args {
        if math.IsNaN(arg) || math.IsInf(arg, 0) {
            err = fmt.Errorf("invalid argument at position %d: %f", i, arg)
            return
        }
    }

    // Execute operation
    result, err = op.Execute(args...)
    if err != nil {
        return
    }

    // Round result to specified precision
    multiplier := math.Pow(10, float64(c.precision))
    result = math.Round(result*multiplier) / multiplier

    return
}

// Chain creates a function that can chain multiple operations
func (c *Calculator) Chain(operations ...func(float64) (float64, error)) func(float64) (float64, error) {
    return func(input float64) (float64, error) {
        result := input

        for i, op := range operations {
            var err error
            result, err = op(result)
            if err != nil {
                return 0, fmt.Errorf("chain operation %d failed: %w", i, err)
            }
        }

        return result, nil
    }
}

// CreateOperationClosure returns a closure for a specific operation
func (c *Calculator) CreateOperationClosure(opName string, fixedArgs ...float64) func(...float64) (float64, error) {
    return func(args ...float64) (float64, error) {
        // Combine fixed args with provided args
        allArgs := append(fixedArgs, args...)
        return c.Execute(opName, allArgs...)
    }
}

// BatchProcess processes multiple calculations using variadic functions
func (c *Calculator) BatchProcess(calculations ...CalculationInput) (results []BatchResult) {
    defer func() {
        if c.debug {
            c.logger.Printf("Batch processed %d calculations", len(calculations))
        }
    }()

    results = make([]BatchResult, len(calculations))

    for i, calc := range calculations {
        result, err := c.Execute(calc.Operation, calc.Args...)
        results[i] = BatchResult{
            Index:     i,
            Input:     calc,
            Result:    result,
            Error:     err,
            Timestamp: time.Now(),
        }
    }

    return
}

// CalculationInput represents input for batch processing
type CalculationInput struct {
    Operation string
    Args      []float64
}

// BatchResult represents the result of a batch calculation
type BatchResult struct {
    Index     int
    Input     CalculationInput
    Result    float64
    Error     error
    Timestamp time.Time
}

// GetHistory returns calculation history with optional filtering
func (c *Calculator) GetHistory(filter ...func(CalculationRecord) bool) []CalculationRecord {
    if len(filter) == 0 {
        return c.history
    }

    var filtered []CalculationRecord
    for _, record := range c.history {
        include := true
        for _, f := range filter {
            if !f(record) {
                include = false
                break
            }
        }
        if include {
            filtered = append(filtered, record)
        }
    }

    return filtered
}

// CreateHistoryFilter returns closures for filtering history
func (c *Calculator) CreateHistoryFilters() map[string]func(CalculationRecord) bool {
    return map[string]func(CalculationRecord) bool{
        "successful": func(r CalculationRecord) bool {
            return r.Error == ""
        },
        "errors": func(r CalculationRecord) bool {
            return r.Error != ""
        },
        "recent": func(r CalculationRecord) bool {
            return time.Since(r.Timestamp) < 5*time.Minute
        },
        "high_results": func(r CalculationRecord) bool {
            return r.Result > 100
        },
    }
}

// Statistics calculates statistics about the calculator usage
func (c *Calculator) Statistics() (totalOps, successfulOps, failedOps int, avgResult float64) {
    defer func() {
        if c.debug {
            c.logger.Printf("Statistics: Total=%d, Success=%d, Failed=%d, Avg=%.2f",
                           totalOps, successfulOps, failedOps, avgResult)
        }
    }()

    totalOps = len(c.history)
    if totalOps == 0 {
        return
    }

    var resultSum float64
    for _, record := range c.history {
        if record.Error == "" {
            successfulOps++
            resultSum += record.Result
        } else {
            failedOps++
        }
    }

    if successfulOps > 0 {
        avgResult = resultSum / float64(successfulOps)
    }

    return
}

// formatExpression creates a readable expression string
func (c *Calculator) formatExpression(opName string, args []float64) string {
    var strArgs []string
    for _, arg := range args {
        strArgs = append(strArgs, fmt.Sprintf("%.2f", arg))
    }

    return fmt.Sprintf("%s(%s)", opName, strings.Join(strArgs, ", "))
}

// Cleanup performs cleanup operations using defer
func (c *Calculator) Cleanup() {
    defer func() {
        if c.debug && c.logger != nil {
            c.logger.Println("Calculator cleanup completed")
        }
    }()

    defer func() {
        if r := recover(); r != nil {
            fmt.Printf("Recovered during cleanup: %v\n", r)
        }
    }()

    // Clear sensitive data
    c.history = nil
    c.operations = nil

    if c.debug {
        fmt.Println("Calculator resources cleaned up")
    }
}

// Demo function showcasing all features
func demonstrateAdvancedFunctions() {
    fmt.Println("🔢 Advanced Functions: Mathematical Expression Evaluator")
    fmt.Println("======================================================")

    // Create calculator with defer-managed cleanup
    calc := NewCalculator(2, true)
    defer calc.Cleanup()

    // Basic operations
    fmt.Println("\n=== Basic Operations ===")
    if result, err := calc.Execute("add", 10, 20, 30); err != nil {
        fmt.Printf("Error: %v\n", err)
    } else {
        fmt.Printf("10 + 20 + 30 = %.2f\n", result)
    }

    if result, err := calc.Execute("multiply", 2, 3, 4); err != nil {
        fmt.Printf("Error: %v\n", err)
    } else {
        fmt.Printf("2 × 3 × 4 = %.2f\n", result)
    }

    // Error handling demonstration
    fmt.Println("\n=== Error Handling ===")
    if _, err := calc.Execute("divide", 10, 0); err != nil {
        fmt.Printf("Division by zero caught: %v\n", err)
    }

    if _, err := calc.Execute("sqrt", -25); err != nil {
        fmt.Printf("Invalid sqrt caught: %v\n", err)
    }

    // Closures and operation factories
    fmt.Println("\n=== Closures and Operation Factories ===")

    // Create specialized operations using closures
    add10 := calc.CreateOperationClosure("add", 10)
    multiply5 := calc.CreateOperationClosure("multiply", 5)

    if result, err := add10(15); err == nil {
        fmt.Printf("add10(15) = %.2f\n", result)
    }

    if result, err := multiply5(7); err == nil {
        fmt.Printf("multiply5(7) = %.2f\n", result)
    }

    // Function chaining
    fmt.Println("\n=== Function Chaining ===")

    // Create a chain: add 10, then multiply by 2, then subtract 5
    chain := calc.Chain(
        func(x float64) (float64, error) { return calc.Execute("add", x, 10) },
        func(x float64) (float64, error) { return calc.Execute("multiply", x, 2) },
        func(x float64) (float64, error) { return calc.Execute("subtract", x, 5) },
    )

    if result, err := chain(5); err == nil {
        fmt.Printf("chain(5): (5+10)*2-5 = %.2f\n", result)
    }

    // Batch processing with variadic functions
    fmt.Println("\n=== Batch Processing ===")

    calculations := []CalculationInput{
        {"add", []float64{1, 2, 3, 4, 5}},
        {"multiply", []float64{2, 3, 4}},
        {"power", []float64{2, 8}},
        {"sqrt", []float64{144}},
        {"divide", []float64{100, 4}},
    }

    results := calc.BatchProcess(calculations...)

    for _, result := range results {
        if result.Error != nil {
            fmt.Printf("Batch[%d]: Error - %v\n", result.Index, result.Error)
        } else {
            fmt.Printf("Batch[%d]: %s = %.2f\n",
                      result.Index,
                      calc.formatExpression(result.Input.Operation, result.Input.Args),
                      result.Result)
        }
    }

    // History and filtering with closures
    fmt.Println("\n=== History and Filtering ===")

    filters := calc.CreateHistoryFilters()

    successfulCalcs := calc.GetHistory(filters["successful"])
    fmt.Printf("Successful calculations: %d\n", len(successfulCalcs))

    errorCalcs := calc.GetHistory(filters["errors"])
    fmt.Printf("Failed calculations: %d\n", len(errorCalcs))

    // Statistics
    total, successful, failed, avg := calc.Statistics()
    fmt.Printf("Statistics - Total: %d, Success: %d, Failed: %d, Average: %.2f\n",
              total, successful, failed, avg)

    // Show recent history
    fmt.Println("\n=== Recent History ===")
    recentHistory := calc.GetHistory(filters["recent"])
    for i, record := range recentHistory {
        status := "✓"
        if record.Error != "" {
            status = "✗"
        }
        fmt.Printf("%d. %s %s = %.2f %s\n",
                  i+1, status, record.Expression, record.Result,
                  func() string {
                      if record.Error != "" {
                          return fmt.Sprintf("(Error: %s)", record.Error)
                      }
                      return ""
                  }())
    }
}

func main() {
    demonstrateAdvancedFunctions()
}
```

**Explanation:**

This comprehensive solution demonstrates all advanced function concepts covered in this chapter:

**Key concepts demonstrated:**
1. **Multiple return values**: Extensive error handling with named returns throughout
2. **Variadic functions**: Operations that accept variable numbers of arguments (add, multiply)
3. **Closures**: Operation factories, history filters, and function chaining
4. **Defer statements**: Resource cleanup, logging, and error recovery
5. **Anonymous functions**: Used in closures and function composition
6. **Higher-order functions**: Functions that accept and return other functions

**Advanced patterns shown:**
- **Function factories**: CreateOperationClosure creates specialized operations
- **Function composition**: Chain method combines multiple operations
- **Callback patterns**: History filtering with closure-based filters
- **Resource management**: Proper cleanup with defer statements
- **Error handling**: Comprehensive error checking with multiple return values

**Performance considerations:**
- Named return values reduce memory allocations
- Defer statements have minimal overhead for cleanup operations
- Closures capture only necessary variables to avoid memory leaks
- Batch processing reduces function call overhead
- History filtering uses efficient slice operations

**Best practices demonstrated:**
- Clear separation of concerns with different methods
- Comprehensive error handling at all levels
- Resource cleanup with defer statements
- Consistent naming conventions and code organization
- Proper logging and debugging support

</details>

---

## Chapter 5: Data Structures
📊 **Progress:** Chapter 5 of 12 | ⏱️ **Estimated reading time:** 25 minutes

🎯 **Learning Objectives:**
- Master Go's fundamental data structures (arrays, slices, maps)
- Understand structs and their composition patterns
- Learn pointer usage and memory management concepts
- Explore advanced data structure techniques

📋 **Prerequisites:** Understanding of basic syntax, data types, and functions

### Arrays

Arrays in Go are fixed-size sequences of elements of the same type. The size is part of the array's type.

#### Array Declaration and Initialization

```go
package main

import "fmt"

func demonstrateArrayBasics() {
    fmt.Println("=== Array Basics ===")

    // Declaration with explicit size and type
    var numbers [5]int
    fmt.Printf("Uninitialized array: %v\n", numbers) // Zero values: [0 0 0 0 0]

    // Declaration with initialization
    var fruits [3]string = [3]string{"apple", "banana", "cherry"}
    fmt.Printf("Initialized array: %v\n", fruits)

    // Short declaration with size inference
    colors := [...]string{"red", "green", "blue", "yellow"}
    fmt.Printf("Inferred size array: %v (length: %d)\n", colors, len(colors))

    // Array with specific indices
    var sparse [10]int
    sparse[0] = 100
    sparse[5] = 500
    sparse[9] = 900
    fmt.Printf("Sparse array: %v\n", sparse)

    // Array literal with index specification
    indexed := [5]int{0: 10, 2: 30, 4: 50}
    fmt.Printf("Indexed initialization: %v\n", indexed)
}

func demonstrateArrayOperations() {
    fmt.Println("\n=== Array Operations ===")

    // Array assignment (copies entire array)
    original := [3]int{1, 2, 3}
    copy := original
    copy[0] = 100

    fmt.Printf("Original: %v\n", original)
    fmt.Printf("Copy: %v\n", copy) // Original is unchanged

    // Array comparison
    array1 := [3]int{1, 2, 3}
    array2 := [3]int{1, 2, 3}
    array3 := [3]int{1, 2, 4}

    fmt.Printf("array1 == array2: %t\n", array1 == array2)
    fmt.Printf("array1 == array3: %t\n", array1 == array3)

    // Iterating over arrays
    scores := [5]int{85, 92, 78, 96, 88}

    fmt.Println("Scores with indices:")
    for i, score := range scores {
        fmt.Printf("  Student %d: %d\n", i+1, score)
    }

    fmt.Println("Just scores:")
    for _, score := range scores {
        fmt.Printf("%d ", score)
    }
    fmt.Println()
}

func demonstrateArrayLimitations() {
    fmt.Println("\n=== Array Limitations ===")

    // Arrays of different sizes are different types
    var small [3]int = [3]int{1, 2, 3}
    var large [5]int = [5]int{1, 2, 3, 4, 5}

    // This would cause a compilation error:
    // small = large // Cannot assign [5]int to [3]int

    fmt.Printf("Small array: %v (type: %T)\n", small, small)
    fmt.Printf("Large array: %v (type: %T)\n", large, large)

    // Arrays are passed by value to functions
    modifyArray(small)
    fmt.Printf("After function call: %v (unchanged)\n", small)

    // To modify, pass by reference
    modifyArrayByReference(&small)
    fmt.Printf("After reference modification: %v (changed)\n", small)
}

func modifyArray(arr [3]int) {
    arr[0] = 999 // This modifies the copy, not the original
}

func modifyArrayByReference(arr *[3]int) {
    arr[0] = 999 // This modifies the original array
}
```

### Slices

Slices are more flexible than arrays and are used more commonly in Go. They provide a dynamic view into arrays.

#### Slice Creation and Operations

```go
func demonstrateSliceBasics() {
    fmt.Println("\n=== Slice Basics ===")

    // Creating slices
    var emptySlice []int
    fmt.Printf("Empty slice: %v (nil: %t, len: %d, cap: %d)\n",
               emptySlice, emptySlice == nil, len(emptySlice), cap(emptySlice))

    // Slice literal
    numbers := []int{10, 20, 30, 40, 50}
    fmt.Printf("Numbers slice: %v (len: %d, cap: %d)\n",
               numbers, len(numbers), cap(numbers))

    // Using make function
    madeSlice := make([]int, 5)        // length 5, capacity 5
    madeWithCap := make([]int, 3, 10)  // length 3, capacity 10

    fmt.Printf("Made slice: %v (len: %d, cap: %d)\n",
               madeSlice, len(madeSlice), cap(madeSlice))
    fmt.Printf("Made with capacity: %v (len: %d, cap: %d)\n",
               madeWithCap, len(madeWithCap), cap(madeWithCap))

    // Slicing arrays and slices
    array := [10]int{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
    slice1 := array[2:7]   // Elements 2, 3, 4, 5, 6
    slice2 := array[:5]    // Elements 0, 1, 2, 3, 4
    slice3 := array[5:]    // Elements 5, 6, 7, 8, 9
    slice4 := array[:]     // All elements

    fmt.Printf("Original array: %v\n", array)
    fmt.Printf("array[2:7]: %v\n", slice1)
    fmt.Printf("array[:5]: %v\n", slice2)
    fmt.Printf("array[5:]: %v\n", slice3)
    fmt.Printf("array[:]: %v\n", slice4)
}

func demonstrateSliceOperations() {
    fmt.Println("\n=== Slice Operations ===")

    // Append operations
    var slice []int
    fmt.Printf("Initial: %v (len: %d, cap: %d)\n", slice, len(slice), cap(slice))

    slice = append(slice, 1)
    fmt.Printf("After append(1): %v (len: %d, cap: %d)\n", slice, len(slice), cap(slice))

    slice = append(slice, 2, 3, 4)
    fmt.Printf("After append(2,3,4): %v (len: %d, cap: %d)\n", slice, len(slice), cap(slice))

    // Append another slice
    more := []int{5, 6, 7}
    slice = append(slice, more...)
    fmt.Printf("After append slice: %v (len: %d, cap: %d)\n", slice, len(slice), cap(slice))

    // Copy operation
    source := []int{10, 20, 30, 40, 50}
    destination := make([]int, len(source))

    copied := copy(destination, source)
    fmt.Printf("Copied %d elements: %v\n", copied, destination)

    // Partial copy
    partial := make([]int, 3)
    copied = copy(partial, source)
    fmt.Printf("Partial copy (%d elements): %v\n", copied, partial)

    // Delete operations (removing elements)
    data := []string{"a", "b", "c", "d", "e"}
    fmt.Printf("Original: %v\n", data)

    // Remove element at index 2 ("c")
    index := 2
    data = append(data[:index], data[index+1:]...)
    fmt.Printf("After removing index 2: %v\n", data)
}

func demonstrateSliceInternals() {
    fmt.Println("\n=== Slice Internals ===")

    // Slices share underlying array
    array := [10]int{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
    slice1 := array[2:7]
    slice2 := array[4:9]

    fmt.Printf("Original array: %v\n", array)
    fmt.Printf("slice1 [2:7]: %v\n", slice1)
    fmt.Printf("slice2 [4:9]: %v\n", slice2)

    // Modify through slice1
    slice1[2] = 999 // This is array[4]

    fmt.Printf("After slice1[2] = 999:\n")
    fmt.Printf("Array: %v\n", array)
    fmt.Printf("slice1: %v\n", slice1)
    fmt.Printf("slice2: %v (notice slice2[0] changed)\n", slice2)

    // Capacity and reslicing
    original := []int{1, 2, 3, 4, 5}
    fmt.Printf("Original: %v (len: %d, cap: %d)\n",
               original, len(original), cap(original))

    sub := original[1:3]
    fmt.Printf("sub[1:3]: %v (len: %d, cap: %d)\n",
               sub, len(sub), cap(sub))

    // Extend sub using its capacity
    extended := sub[:4] // Can extend beyond len but within cap
    fmt.Printf("Extended: %v (len: %d, cap: %d)\n",
               extended, len(extended), cap(extended))
}

func demonstrateSlicePatterns() {
    fmt.Println("\n=== Common Slice Patterns ===")

    // Filter slice
    numbers := []int{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
    var evens []int

    for _, num := range numbers {
        if num%2 == 0 {
            evens = append(evens, num)
        }
    }
    fmt.Printf("Even numbers: %v\n", evens)

    // Map operation
    doubled := make([]int, len(numbers))
    for i, num := range numbers {
        doubled[i] = num * 2
    }
    fmt.Printf("Doubled: %v\n", doubled)

    // Reverse slice
    data := []string{"apple", "banana", "cherry", "date"}
    fmt.Printf("Original: %v\n", data)

    // In-place reverse
    for i, j := 0, len(data)-1; i < j; i, j = i+1, j-1 {
        data[i], data[j] = data[j], data[i]
    }
    fmt.Printf("Reversed: %v\n", data)

    // Insert element at specific position
    slice := []int{1, 2, 4, 5}
    insertPos := 2
    valueToInsert := 3

    fmt.Printf("Before insert: %v\n", slice)

    // Insert by expanding and shifting
    slice = append(slice, 0)                                    // Expand
    copy(slice[insertPos+1:], slice[insertPos:])               // Shift
    slice[insertPos] = valueToInsert                           // Insert

    fmt.Printf("After inserting %d at position %d: %v\n",
               valueToInsert, insertPos, slice)
}
```

### Maps

Maps are Go's built-in hash table implementation, providing key-value pair storage.

#### Map Creation and Operations

```go
func demonstrateMapBasics() {
    fmt.Println("\n=== Map Basics ===")

    // Map declaration and initialization
    var emptyMap map[string]int
    fmt.Printf("Empty map: %v (nil: %t)\n", emptyMap, emptyMap == nil)

    // Initialize with make
    scores := make(map[string]int)
    scores["Alice"] = 95
    scores["Bob"] = 87
    scores["Carol"] = 92

    fmt.Printf("Scores map: %v\n", scores)

    // Map literal
    capitals := map[string]string{
        "France":  "Paris",
        "Germany": "Berlin",
        "Italy":   "Rome",
        "Spain":   "Madrid",
    }
    fmt.Printf("Capitals: %v\n", capitals)

    // Nested maps
    inventory := map[string]map[string]int{
        "fruits": {
            "apples":  50,
            "bananas": 30,
            "oranges": 25,
        },
        "vegetables": {
            "carrots":  40,
            "broccoli": 15,
            "spinach":  20,
        },
    }

    fmt.Printf("Fruit apples: %d\n", inventory["fruits"]["apples"])
}

func demonstrateMapOperations() {
    fmt.Println("\n=== Map Operations ===")

    users := make(map[int]string)

    // Adding elements
    users[1001] = "Alice Johnson"
    users[1002] = "Bob Smith"
    users[1003] = "Carol Davis"

    fmt.Printf("Users: %v\n", users)

    // Accessing elements
    name := users[1001]
    fmt.Printf("User 1001: %s\n", name)

    // Check if key exists
    name, exists := users[1001]
    if exists {
        fmt.Printf("Found user 1001: %s\n", name)
    }

    // Non-existent key
    name, exists = users[9999]
    if !exists {
        fmt.Printf("User 9999 not found (got zero value: '%s')\n", name)
    }

    // Delete element
    delete(users, 1002)
    fmt.Printf("After deleting 1002: %v\n", users)

    // Check length
    fmt.Printf("Number of users: %d\n", len(users))

    // Iterate over map
    fmt.Println("All users:")
    for id, name := range users {
        fmt.Printf("  ID: %d, Name: %s\n", id, name)
    }

    // Iterate over keys only
    fmt.Print("User IDs: ")
    for id := range users {
        fmt.Printf("%d ", id)
    }
    fmt.Println()

    // Iterate over values only
    fmt.Print("User names: ")
    for _, name := range users {
        fmt.Printf("%s ", name)
    }
    fmt.Println()
}

func demonstrateMapPatterns() {
    fmt.Println("\n=== Common Map Patterns ===")

    // Counting occurrences
    text := "hello world hello"
    wordCount := make(map[string]int)

    words := strings.Fields(text)
    for _, word := range words {
        wordCount[word]++
    }

    fmt.Printf("Word counts: %v\n", wordCount)

    // Grouping data
    people := []struct {
        name string
        city string
    }{
        {"Alice", "New York"},
        {"Bob", "London"},
        {"Carol", "New York"},
        {"Dave", "London"},
        {"Eve", "Paris"},
    }

    cityGroups := make(map[string][]string)
    for _, person := range people {
        cityGroups[person.city] = append(cityGroups[person.city], person.name)
    }

    fmt.Println("People by city:")
    for city, residents := range cityGroups {
        fmt.Printf("  %s: %v\n", city, residents)
    }

    // Set operations using map[type]bool
    set1 := map[int]bool{1: true, 2: true, 3: true, 4: true}
    set2 := map[int]bool{3: true, 4: true, 5: true, 6: true}

    // Union
    union := make(map[int]bool)
    for k := range set1 {
        union[k] = true
    }
    for k := range set2 {
        union[k] = true
    }
    fmt.Printf("Union: %v\n", getKeys(union))

    // Intersection
    intersection := make(map[int]bool)
    for k := range set1 {
        if set2[k] {
            intersection[k] = true
        }
    }
    fmt.Printf("Intersection: %v\n", getKeys(intersection))
}

func getKeys(m map[int]bool) []int {
    keys := make([]int, 0, len(m))
    for k := range m {
        keys = append(keys, k)
    }
    return keys
}
```

### Structs

Structs are composite types that group together related data and can have methods attached to them.

#### Struct Definition and Usage

```go
// Basic struct definition
type Person struct {
    FirstName string
    LastName  string
    Age       int
    Email     string
}

// Struct with embedded types
type Address struct {
    Street   string
    City     string
    State    string
    ZipCode  string
    Country  string
}

type Employee struct {
    Person            // Embedded struct
    ID       int
    Position string
    Salary   float64
    Address  Address  // Nested struct
}

func demonstrateStructBasics() {
    fmt.Println("\n=== Struct Basics ===")

    // Struct literal with field names
    person1 := Person{
        FirstName: "Alice",
        LastName:  "Johnson",
        Age:       30,
        Email:     "alice@example.com",
    }

    fmt.Printf("Person1: %+v\n", person1)

    // Struct literal without field names (order matters)
    person2 := Person{"Bob", "Smith", 25, "bob@example.com"}
    fmt.Printf("Person2: %+v\n", person2)

    // Partial initialization (other fields get zero values)
    person3 := Person{
        FirstName: "Carol",
        Age:       35,
    }
    fmt.Printf("Person3: %+v\n", person3)

    // Zero value struct
    var person4 Person
    fmt.Printf("Zero value person: %+v\n", person4)

    // Accessing and modifying fields
    person1.Age = 31
    fmt.Printf("Updated age: %d\n", person1.Age)

    // Nested and embedded structs
    employee := Employee{
        Person: Person{
            FirstName: "Dave",
            LastName:  "Wilson",
            Age:       28,
            Email:     "dave@company.com",
        },
        ID:       12345,
        Position: "Software Engineer",
        Salary:   75000.0,
        Address: Address{
            Street:  "123 Tech St",
            City:    "San Francisco",
            State:   "CA",
            ZipCode: "94105",
            Country: "USA",
        },
    }

    fmt.Printf("Employee: %+v\n", employee)

    // Accessing embedded fields directly
    fmt.Printf("Employee name: %s %s\n", employee.FirstName, employee.LastName)
    fmt.Printf("Employee email: %s\n", employee.Email) // Direct access to embedded field
}

func demonstrateStructMethods() {
    fmt.Println("\n=== Struct Methods ===")

    // Methods will be detailed in the Methods chapter
    // Here's a preview of the syntax

    alice := Person{
        FirstName: "Alice",
        LastName:  "Johnson",
        Age:       30,
        Email:     "alice@example.com",
    }

    fmt.Printf("Full name: %s\n", alice.FullName())
    fmt.Printf("Is adult: %t\n", alice.IsAdult())

    // Pointer receiver method
    alice.HaveBirthday()
    fmt.Printf("After birthday: %d years old\n", alice.Age)
}

// Method definitions (preview - will be covered in detail later)
func (p Person) FullName() string {
    return p.FirstName + " " + p.LastName
}

func (p Person) IsAdult() bool {
    return p.Age >= 18
}

func (p *Person) HaveBirthday() {
    p.Age++
}

func demonstrateStructPatterns() {
    fmt.Println("\n=== Struct Patterns ===")

    // Constructor pattern
    employee := NewEmployee("John", "Doe", "Engineer", 80000)
    fmt.Printf("New employee: %+v\n", employee)

    // Builder pattern
    config := NewConfigBuilder().
        SetHost("localhost").
        SetPort(8080).
        SetTimeout(30).
        EnableSSL(true).
        Build()

    fmt.Printf("Config: %+v\n", config)

    // Anonymous structs for temporary data
    result := struct {
        Success bool
        Message string
        Data    interface{}
    }{
        Success: true,
        Message: "Operation completed",
        Data:    map[string]int{"count": 42},
    }

    fmt.Printf("Result: %+v\n", result)
}

// Constructor pattern
func NewEmployee(firstName, lastName, position string, salary float64) Employee {
    return Employee{
        Person: Person{
            FirstName: firstName,
            LastName:  lastName,
            Age:       0, // Will be set later
        },
        ID:       generateEmployeeID(),
        Position: position,
        Salary:   salary,
    }
}

func generateEmployeeID() int {
    // Simplified ID generation
    return int(time.Now().Unix() % 100000)
}

// Builder pattern
type Config struct {
    Host    string
    Port    int
    Timeout int
    SSL     bool
}

type ConfigBuilder struct {
    config Config
}

func NewConfigBuilder() *ConfigBuilder {
    return &ConfigBuilder{
        config: Config{
            Host:    "127.0.0.1",
            Port:    80,
            Timeout: 10,
            SSL:     false,
        },
    }
}

func (cb *ConfigBuilder) SetHost(host string) *ConfigBuilder {
    cb.config.Host = host
    return cb
}

func (cb *ConfigBuilder) SetPort(port int) *ConfigBuilder {
    cb.config.Port = port
    return cb
}

func (cb *ConfigBuilder) SetTimeout(timeout int) *ConfigBuilder {
    cb.config.Timeout = timeout
    return cb
}

func (cb *ConfigBuilder) EnableSSL(enable bool) *ConfigBuilder {
    cb.config.SSL = enable
    return cb
}

func (cb *ConfigBuilder) Build() Config {
    return cb.config
}
```

### Pointers

Pointers store memory addresses and enable indirect access to values, allowing for efficient passing of large data structures and modification of variables.

#### Pointer Basics

```go
func demonstratePointerBasics() {
    fmt.Println("\n=== Pointer Basics ===")

    // Basic pointer operations
    x := 42
    fmt.Printf("x = %d, address = %p\n", x, &x)

    // Declare pointer and assign address
    var p *int = &x
    fmt.Printf("p = %p, *p = %d\n", p, *p)

    // Modify value through pointer
    *p = 100
    fmt.Printf("After *p = 100: x = %d\n", x)

    // Nil pointer
    var nilPointer *int
    fmt.Printf("Nil pointer: %v (nil: %t)\n", nilPointer, nilPointer == nil)

    // if nilPointer != nil { // Always check before dereferencing
    //     fmt.Println(*nilPointer)
    // }

    // Pointer to pointer
    var pp **int = &p
    fmt.Printf("pp = %p, *pp = %p, **pp = %d\n", pp, *pp, **pp)

    // New function allocates memory and returns pointer
    newInt := new(int)
    *newInt = 200
    fmt.Printf("new(int): %p, value: %d\n", newInt, *newInt)
}

func demonstratePointerWithFunctions() {
    fmt.Println("\n=== Pointers with Functions ===")

    // Pass by value (copy)
    a := 10
    fmt.Printf("Before passByValue: a = %d\n", a)
    passByValue(a)
    fmt.Printf("After passByValue: a = %d (unchanged)\n", a)

    // Pass by pointer (reference)
    fmt.Printf("Before passByPointer: a = %d\n", a)
    passByPointer(&a)
    fmt.Printf("After passByPointer: a = %d (changed)\n", a)

    // Function returning pointer
    ptr := createInt(42)
    fmt.Printf("Created int: %p, value: %d\n", ptr, *ptr)
}

func passByValue(x int) {
    x = 999 // Modifies copy, not original
}

func passByPointer(x *int) {
    *x = 999 // Modifies original value
}

func createInt(value int) *int {
    x := value
    return &x // Safe to return address of local variable
}

func demonstratePointerWithStructs() {
    fmt.Println("\n=== Pointers with Structs ===")

    // Create struct and pointer
    person := Person{FirstName: "Alice", LastName: "Johnson", Age: 30}
    personPtr := &person

    fmt.Printf("person: %+v\n", person)
    fmt.Printf("personPtr: %p\n", personPtr)

    // Access fields through pointer (automatic dereferencing)
    fmt.Printf("Name via pointer: %s %s\n", personPtr.FirstName, personPtr.LastName)

    // Modify through pointer
    personPtr.Age = 31
    fmt.Printf("After modification: %+v\n", person)

    // Explicit dereferencing (equivalent to above)
    (*personPtr).Email = "alice@newdomain.com"
    fmt.Printf("After email change: %+v\n", person)

    // Pointer to struct field
    agePtr := &person.Age
    *agePtr = 32
    fmt.Printf("After age pointer modification: age = %d\n", person.Age)
}

func demonstratePointerPatterns() {
    fmt.Println("\n=== Common Pointer Patterns ===")

    // Optional values (using pointers for nullable fields)
    type User struct {
        Name  string
        Email *string // Optional field
        Phone *string // Optional field
    }

    // Helper function to get pointer to string
    stringPtr := func(s string) *string { return &s }

    user1 := User{
        Name:  "John",
        Email: stringPtr("john@example.com"),
        // Phone is nil (not provided)
    }

    user2 := User{
        Name:  "Jane",
        Email: stringPtr("jane@example.com"),
        Phone: stringPtr("+1-555-0123"),
    }

    users := []User{user1, user2}

    for i, user := range users {
        fmt.Printf("User %d: %s\n", i+1, user.Name)

        if user.Email != nil {
            fmt.Printf("  Email: %s\n", *user.Email)
        } else {
            fmt.Println("  Email: not provided")
        }

        if user.Phone != nil {
            fmt.Printf("  Phone: %s\n", *user.Phone)
        } else {
            fmt.Println("  Phone: not provided")
        }
    }

    // Linked list implementation using pointers
    type ListNode struct {
        Value int
        Next  *ListNode
    }

    // Create a simple linked list: 1 -> 2 -> 3 -> nil
    node3 := &ListNode{Value: 3, Next: nil}
    node2 := &ListNode{Value: 2, Next: node3}
    node1 := &ListNode{Value: 1, Next: node2}

    fmt.Print("Linked list: ")
    current := node1
    for current != nil {
        fmt.Printf("%d ", current.Value)
        current = current.Next
    }
    fmt.Println()
}
```

### ⚠️ Common Pitfalls

1. **Nil Pointer Dereferencing**
```go
func nilPointerPitfall() {
    var ptr *int
    // fmt.Println(*ptr) // This will cause a runtime panic

    // Always check for nil before dereferencing
    if ptr != nil {
        fmt.Println(*ptr)
    } else {
        fmt.Println("Pointer is nil")
    }
}
```

2. **Range Variable Address**
```go
func rangePointerPitfall() {
    items := []int{1, 2, 3}
    var pointers []*int

    // Wrong: all pointers point to the same variable
    for _, item := range items {
        pointers = append(pointers, &item) // item is reused!
    }

    // All pointers point to the last value
    for _, ptr := range pointers {
        fmt.Printf("%d ", *ptr) // Prints: 3 3 3
    }

    // Correct: create a new variable in each iteration
    pointers = nil // Clear the wrong pointers
    for _, item := range items {
        value := item // Create new variable
        pointers = append(pointers, &value)
    }

    fmt.Print("Correct pointers: ")
    for _, ptr := range pointers {
        fmt.Printf("%d ", *ptr) // Prints: 1 2 3
    }
    fmt.Println()
}
```

3. **Slice Append Gotcha**
```go
func sliceAppendPitfall() {
    // Slices sharing underlying array
    original := []int{1, 2, 3}
    slice1 := original[:2] // [1, 2]
    slice2 := original[1:] // [2, 3]

    // Appending to slice1 might affect slice2 if capacity allows
    slice1 = append(slice1, 99)

    fmt.Printf("original: %v\n", original) // [1, 2, 99]
    fmt.Printf("slice2: %v\n", slice2)     // [2, 99] - affected!
}
```

### ✅ Best Practices

1. **Use Slices Over Arrays**
```go
// Preferred: Use slices for flexibility
func processNumbers(numbers []int) {
    // Process slice
}

// Less preferred: Fixed-size arrays
func processFixedNumbers(numbers [10]int) {
    // Process array
}
```

2. **Initialize Maps and Slices**
```go
// Good: Initialize before use
users := make(map[string]User)
items := make([]Item, 0, expectedCapacity)

// Avoid: Using nil maps
var users map[string]User
// users["key"] = value // Runtime panic!
```

3. **Use Struct Embedding Wisely**
```go
// Good: Logical embedding for "is-a" relationships
type Manager struct {
    Employee // A manager is an employee
    TeamSize int
}

// Consider composition for "has-a" relationships
type Team struct {
    Manager Manager // A team has a manager
    Members []Employee
}
```

### 🏋️ Exercise 5: Data Structures Mastery
**Difficulty:** 🔴 Advanced
**Estimated Time:** 45 minutes

Create a comprehensive data management system that demonstrates:

1. Complex data structures (nested structs, slices, maps)
2. Pointer usage for efficient memory management
3. Custom collection types with methods
4. Data transformation and querying operations
5. Memory-efficient patterns and best practices

Build a "Library Management System" that handles books, authors, members, and borrowing records.

<details>
<summary>💡 Click to see hints</summary>

- Use struct embedding for different types of library items
- Implement custom collections with slice-based storage
- Use maps for efficient lookups by different keys
- Include pointer-based relationships between entities
- Implement search and filter functionality
- Add data validation and error handling

</details>

<details>
<summary>✅ Click to see solution</summary>

```go
package main

import (
    "fmt"
    "sort"
    "strings"
    "time"
)

// Core data structures

// Author represents a book author
type Author struct {
    ID        int
    Name      string
    Biography string
    BirthYear int
}

// Book represents a library book
type Book struct {
    ID          int
    Title       string
    Authors     []*Author // Pointers to authors
    ISBN        string
    PublishYear int
    Genre       string
    TotalCopies int
    Available   int
}

// Member represents a library member
type Member struct {
    ID           int
    Name         string
    Email        string
    Phone        string
    MembershipID string
    JoinDate     time.Time
    IsActive     bool
}

// BorrowRecord represents a borrowing transaction
type BorrowRecord struct {
    ID         int
    BookID     int
    MemberID   int
    BorrowDate time.Time
    DueDate    time.Time
    ReturnDate *time.Time // Pointer for optional value
    IsReturned bool
    Fine       float64
}

// LibraryItem interface for different types of items
type LibraryItem interface {
    GetID() int
    GetTitle() string
    IsAvailable() bool
}

// Implement LibraryItem for Book
func (b Book) GetID() int {
    return b.ID
}

func (b Book) GetTitle() string {
    return b.Title
}

func (b Book) IsAvailable() bool {
    return b.Available > 0
}

// Custom collection types

// AuthorCollection manages authors with efficient lookups
type AuthorCollection struct {
    authors   []Author
    idIndex   map[int]*Author
    nameIndex map[string][]*Author
}

// NewAuthorCollection creates a new author collection
func NewAuthorCollection() *AuthorCollection {
    return &AuthorCollection{
        authors:   make([]Author, 0),
        idIndex:   make(map[int]*Author),
        nameIndex: make(map[string][]*Author),
    }
}

// Add adds a new author to the collection
func (ac *AuthorCollection) Add(author Author) {
    ac.authors = append(ac.authors, author)
    authorPtr := &ac.authors[len(ac.authors)-1]

    // Update indices
    ac.idIndex[author.ID] = authorPtr

    nameLower := strings.ToLower(author.Name)
    ac.nameIndex[nameLower] = append(ac.nameIndex[nameLower], authorPtr)
}

// FindByID finds author by ID (O(1) lookup)
func (ac *AuthorCollection) FindByID(id int) (*Author, bool) {
    author, exists := ac.idIndex[id]
    return author, exists
}

// FindByName finds authors by name (case-insensitive)
func (ac *AuthorCollection) FindByName(name string) []*Author {
    return ac.nameIndex[strings.ToLower(name)]
}

// GetAll returns all authors
func (ac *AuthorCollection) GetAll() []Author {
    return ac.authors
}

// BookCollection manages books with complex indexing
type BookCollection struct {
    books       []Book
    idIndex     map[int]*Book
    titleIndex  map[string][]*Book
    genreIndex  map[string][]*Book
    authorIndex map[int][]*Book // Books by author ID
}

// NewBookCollection creates a new book collection
func NewBookCollection() *BookCollection {
    return &BookCollection{
        books:       make([]Book, 0),
        idIndex:     make(map[int]*Book),
        titleIndex:  make(map[string][]*Book),
        genreIndex:  make(map[string][]*Book),
        authorIndex: make(map[int][]*Book),
    }
}

// Add adds a new book to the collection
func (bc *BookCollection) Add(book Book) {
    bc.books = append(bc.books, book)
    bookPtr := &bc.books[len(bc.books)-1]

    // Update indices
    bc.idIndex[book.ID] = bookPtr

    titleLower := strings.ToLower(book.Title)
    bc.titleIndex[titleLower] = append(bc.titleIndex[titleLower], bookPtr)

    genreLower := strings.ToLower(book.Genre)
    bc.genreIndex[genreLower] = append(bc.genreIndex[genreLower], bookPtr)

    // Index by authors
    for _, author := range book.Authors {
        bc.authorIndex[author.ID] = append(bc.authorIndex[author.ID], bookPtr)
    }
}

// FindByID finds book by ID
func (bc *BookCollection) FindByID(id int) (*Book, bool) {
    book, exists := bc.idIndex[id]
    return book, exists
}

// FindByTitle finds books by title (case-insensitive, partial match)
func (bc *BookCollection) FindByTitle(title string) []*Book {
    titleLower := strings.ToLower(title)
    var matches []*Book

    for _, book := range bc.books {
        if strings.Contains(strings.ToLower(book.Title), titleLower) {
            matches = append(matches, &book)
        }
    }

    return matches
}

// FindByGenre finds books by genre
func (bc *BookCollection) FindByGenre(genre string) []*Book {
    return bc.genreIndex[strings.ToLower(genre)]
}

// FindByAuthor finds books by author ID
func (bc *BookCollection) FindByAuthor(authorID int) []*Book {
    return bc.authorIndex[authorID]
}

// GetAvailable returns all available books
func (bc *BookCollection) GetAvailable() []Book {
    var available []Book
    for _, book := range bc.books {
        if book.IsAvailable() {
            available = append(available, book)
        }
    }
    return available
}

// UpdateAvailability updates book availability
func (bc *BookCollection) UpdateAvailability(bookID int, change int) error {
    book, exists := bc.FindByID(bookID)
    if !exists {
        return fmt.Errorf("book with ID %d not found", bookID)
    }

    newAvailable := book.Available + change
    if newAvailable < 0 {
        return fmt.Errorf("not enough copies available")
    }

    if newAvailable > book.TotalCopies {
        return fmt.Errorf("available copies cannot exceed total copies")
    }

    book.Available = newAvailable
    return nil
}

// Library represents the main library system
type Library struct {
    Name            string
    Authors         *AuthorCollection
    Books           *BookCollection
    Members         map[int]*Member
    BorrowRecords   []BorrowRecord
    NextAuthorID    int
    NextBookID      int
    NextMemberID    int
    NextRecordID    int
}

// NewLibrary creates a new library system
func NewLibrary(name string) *Library {
    return &Library{
        Name:            name,
        Authors:         NewAuthorCollection(),
        Books:           NewBookCollection(),
        Members:         make(map[int]*Member),
        BorrowRecords:   make([]BorrowRecord, 0),
        NextAuthorID:    1,
        NextBookID:      1,
        NextMemberID:    1,
        NextRecordID:    1,
    }
}

// AddAuthor adds a new author to the library
func (l *Library) AddAuthor(name, biography string, birthYear int) *Author {
    author := Author{
        ID:        l.NextAuthorID,
        Name:      name,
        Biography: biography,
        BirthYear: birthYear,
    }

    l.Authors.Add(author)
    l.NextAuthorID++

    return &author
}

// AddBook adds a new book to the library
func (l *Library) AddBook(title, isbn string, authorIDs []int, publishYear int, genre string, totalCopies int) (*Book, error) {
    // Validate authors exist
    var authors []*Author
    for _, authorID := range authorIDs {
        author, exists := l.Authors.FindByID(authorID)
        if !exists {
            return nil, fmt.Errorf("author with ID %d not found", authorID)
        }
        authors = append(authors, author)
    }

    book := Book{
        ID:          l.NextBookID,
        Title:       title,
        Authors:     authors,
        ISBN:        isbn,
        PublishYear: publishYear,
        Genre:       genre,
        TotalCopies: totalCopies,
        Available:   totalCopies,
    }

    l.Books.Add(book)
    l.NextBookID++

    return &book, nil
}

// AddMember adds a new library member
func (l *Library) AddMember(name, email, phone string) *Member {
    member := Member{
        ID:           l.NextMemberID,
        Name:         name,
        Email:        email,
        Phone:        phone,
        MembershipID: fmt.Sprintf("LIB%06d", l.NextMemberID),
        JoinDate:     time.Now(),
        IsActive:     true,
    }

    l.Members[member.ID] = &member
    l.NextMemberID++

    return &member
}

// BorrowBook creates a borrowing record
func (l *Library) BorrowBook(bookID, memberID int, borrowDays int) error {
    // Validate book exists and is available
    book, exists := l.Books.FindByID(bookID)
    if !exists {
        return fmt.Errorf("book with ID %d not found", bookID)
    }

    if !book.IsAvailable() {
        return fmt.Errorf("book '%s' is not available", book.Title)
    }

    // Validate member exists and is active
    member, exists := l.Members[memberID]
    if !exists {
        return fmt.Errorf("member with ID %d not found", memberID)
    }

    if !member.IsActive {
        return fmt.Errorf("member '%s' is not active", member.Name)
    }

    // Check if member has overdue books
    if l.HasOverdueBooks(memberID) {
        return fmt.Errorf("member has overdue books")
    }

    // Create borrow record
    record := BorrowRecord{
        ID:         l.NextRecordID,
        BookID:     bookID,
        MemberID:   memberID,
        BorrowDate: time.Now(),
        DueDate:    time.Now().AddDate(0, 0, borrowDays),
        IsReturned: false,
        Fine:       0.0,
    }

    l.BorrowRecords = append(l.BorrowRecords, record)
    l.NextRecordID++

    // Update book availability
    l.Books.UpdateAvailability(bookID, -1)

    fmt.Printf("Book '%s' borrowed by %s (Due: %s)\n",
               book.Title, member.Name, record.DueDate.Format("2006-01-02"))

    return nil
}

// ReturnBook processes a book return
func (l *Library) ReturnBook(bookID, memberID int) error {
    // Find the active borrow record
    recordIndex := -1
    for i, record := range l.BorrowRecords {
        if record.BookID == bookID && record.MemberID == memberID && !record.IsReturned {
            recordIndex = i
            break
        }
    }

    if recordIndex == -1 {
        return fmt.Errorf("no active borrow record found")
    }

    record := &l.BorrowRecords[recordIndex]
    now := time.Now()
    record.ReturnDate = &now
    record.IsReturned = true

    // Calculate fine for overdue books
    if now.After(record.DueDate) {
        overdueDays := int(now.Sub(record.DueDate).Hours() / 24)
        record.Fine = float64(overdueDays) * 0.50 // $0.50 per day
    }

    // Update book availability
    l.Books.UpdateAvailability(bookID, 1)

    book, _ := l.Books.FindByID(bookID)
    member := l.Members[memberID]

    fmt.Printf("Book '%s' returned by %s", book.Title, member.Name)
    if record.Fine > 0 {
        fmt.Printf(" (Fine: $%.2f)", record.Fine)
    }
    fmt.Println()

    return nil
}

// HasOverdueBooks checks if member has overdue books
func (l *Library) HasOverdueBooks(memberID int) bool {
    now := time.Now()
    for _, record := range l.BorrowRecords {
        if record.MemberID == memberID && !record.IsReturned && now.After(record.DueDate) {
            return true
        }
    }
    return false
}

// GetMemberBorrowHistory returns member's borrowing history
func (l *Library) GetMemberBorrowHistory(memberID int) []BorrowRecord {
    var history []BorrowRecord
    for _, record := range l.BorrowRecords {
        if record.MemberID == memberID {
            history = append(history, record)
        }
    }

    // Sort by borrow date (most recent first)
    sort.Slice(history, func(i, j int) bool {
        return history[i].BorrowDate.After(history[j].BorrowDate)
    })

    return history
}

// GetPopularBooks returns most borrowed books
func (l *Library) GetPopularBooks(limit int) []struct {
    Book       *Book
    BorrowCount int
} {
    borrowCounts := make(map[int]int)

    // Count borrows per book
    for _, record := range l.BorrowRecords {
        borrowCounts[record.BookID]++
    }

    // Create sorted list
    type BookPopularity struct {
        Book       *Book
        BorrowCount int
    }

    var popular []BookPopularity
    for bookID, count := range borrowCounts {
        if book, exists := l.Books.FindByID(bookID); exists {
            popular = append(popular, BookPopularity{
                Book:        book,
                BorrowCount: count,
            })
        }
    }

    // Sort by borrow count (descending)
    sort.Slice(popular, func(i, j int) bool {
        return popular[i].BorrowCount > popular[j].BorrowCount
    })

    // Limit results
    if limit > 0 && limit < len(popular) {
        popular = popular[:limit]
    }

    // Convert to return format
    result := make([]struct {
        Book       *Book
        BorrowCount int
    }, len(popular))

    for i, item := range popular {
        result[i] = struct {
            Book       *Book
            BorrowCount int
        }{
            Book:        item.Book,
            BorrowCount: item.BorrowCount,
        }
    }

    return result
}

// SearchBooks performs comprehensive book search
func (l *Library) SearchBooks(query string) []*Book {
    query = strings.ToLower(query)
    bookSet := make(map[int]*Book) // Use map to avoid duplicates

    // Search by title
    for _, book := range l.Books.FindByTitle(query) {
        bookSet[book.ID] = book
    }

    // Search by genre
    for _, book := range l.Books.FindByGenre(query) {
        bookSet[book.ID] = book
    }

    // Search by author name
    for _, author := range l.Authors.FindByName(query) {
        for _, book := range l.Books.FindByAuthor(author.ID) {
            bookSet[book.ID] = book
        }
    }

    // Convert map to slice
    var results []*Book
    for _, book := range bookSet {
        results = append(results, book)
    }

    // Sort by title
    sort.Slice(results, func(i, j int) bool {
        return results[i].Title < results[j].Title
    })

    return results
}

// GenerateReport generates various library reports
func (l *Library) GenerateReport() {
    fmt.Println("\n" + strings.Repeat("=", 50))
    fmt.Printf("📚 %s - Library Report\n", l.Name)
    fmt.Println(strings.Repeat("=", 50))

    // Collection statistics
    fmt.Printf("📖 Total Books: %d\n", len(l.Books.books))
    fmt.Printf("✍️  Total Authors: %d\n", len(l.Authors.authors))
    fmt.Printf("👥 Total Members: %d\n", len(l.Members))
    fmt.Printf("📋 Total Borrow Records: %d\n", len(l.BorrowRecords))

    // Available vs borrowed
    available := len(l.Books.GetAvailable())
    total := len(l.Books.books)
    borrowed := total - available
    fmt.Printf("📚 Available: %d, Borrowed: %d\n", available, borrowed)

    // Active vs returned records
    activeLoans := 0
    totalFines := 0.0
    for _, record := range l.BorrowRecords {
        if !record.IsReturned {
            activeLoans++
        }
        totalFines += record.Fine
    }
    fmt.Printf("🔄 Active Loans: %d\n", activeLoans)
    fmt.Printf("💰 Total Fines Collected: $%.2f\n", totalFines)

    // Popular books
    fmt.Println("\n📈 Top 5 Most Popular Books:")
    popular := l.GetPopularBooks(5)
    for i, item := range popular {
        fmt.Printf("%d. '%s' - %d borrows\n",
                   i+1, item.Book.Title, item.BorrowCount)
    }

    // Overdue books
    fmt.Println("\n⚠️  Overdue Books:")
    now := time.Now()
    overdueCount := 0
    for _, record := range l.BorrowRecords {
        if !record.IsReturned && now.After(record.DueDate) {
            member := l.Members[record.MemberID]
            book, _ := l.Books.FindByID(record.BookID)
            overdueDays := int(now.Sub(record.DueDate).Hours() / 24)
            fmt.Printf("  - '%s' borrowed by %s (%d days overdue)\n",
                       book.Title, member.Name, overdueDays)
            overdueCount++
        }
    }
    if overdueCount == 0 {
        fmt.Println("  No overdue books! 🎉")
    }
}

// Demo function showcasing the library system
func demonstrateLibrarySystem() {
    fmt.Println("📚 Advanced Data Structures: Library Management System")
    fmt.Println("=====================================================")

    // Create library
    lib := NewLibrary("City Central Library")

    // Add authors
    fmt.Println("\n➕ Adding Authors...")
    tolkien := lib.AddAuthor("J.R.R. Tolkien", "British author and professor", 1892)
    christie := lib.AddAuthor("Agatha Christie", "British crime novelist", 1890)
    orwell := lib.AddAuthor("George Orwell", "British author and journalist", 1903)

    fmt.Printf("Added: %s, %s, %s\n", tolkien.Name, christie.Name, orwell.Name)

    // Add books
    fmt.Println("\n📖 Adding Books...")
    book1, _ := lib.AddBook("The Lord of the Rings", "978-0547928227",
                           []int{tolkien.ID}, 1954, "Fantasy", 3)
    book2, _ := lib.AddBook("Murder on the Orient Express", "978-0062693662",
                           []int{christie.ID}, 1934, "Mystery", 2)
    book3, _ := lib.AddBook("1984", "978-0451524935",
                           []int{orwell.ID}, 1949, "Dystopian Fiction", 4)
    book4, _ := lib.AddBook("Animal Farm", "978-0451526342",
                           []int{orwell.ID}, 1945, "Political Satire", 2)

    fmt.Printf("Added 4 books to the collection\n")

    // Add members
    fmt.Println("\n👥 Adding Members...")
    alice := lib.AddMember("Alice Johnson", "alice@email.com", "555-0101")
    bob := lib.AddMember("Bob Smith", "bob@email.com", "555-0102")
    carol := lib.AddMember("Carol Davis", "carol@email.com", "555-0103")

    fmt.Printf("Added: %s, %s, %s\n", alice.Name, bob.Name, carol.Name)

    // Demonstrate borrowing
    fmt.Println("\n📤 Borrowing Books...")
    lib.BorrowBook(book1.ID, alice.ID, 14) // 14 days
    lib.BorrowBook(book2.ID, bob.ID, 7)    // 7 days
    lib.BorrowBook(book3.ID, carol.ID, 21) // 21 days
    lib.BorrowBook(book4.ID, alice.ID, 14) // Alice borrows second book

    // Try to borrow unavailable book
    fmt.Println("\n❌ Trying to borrow unavailable book...")
    err := lib.BorrowBook(book1.ID, bob.ID, 14) // Should fail - already borrowed
    if err != nil {
        fmt.Printf("Error: %v\n", err)
    }

    // Simulate some returns
    fmt.Println("\n📥 Returning Books...")
    time.Sleep(10 * time.Millisecond) // Small delay to simulate time passing
    lib.ReturnBook(book2.ID, bob.ID)

    // Search functionality
    fmt.Println("\n🔍 Search Results:")

    // Search by title
    results := lib.SearchBooks("1984")
    fmt.Printf("Search '1984': %d results\n", len(results))
    for _, book := range results {
        fmt.Printf("  - %s by %s\n", book.Title, book.Authors[0].Name)
    }

    // Search by author
    results = lib.SearchBooks("orwell")
    fmt.Printf("Search 'orwell': %d results\n", len(results))
    for _, book := range results {
        fmt.Printf("  - %s (%s)\n", book.Title, book.Genre)
    }

    // Member history
    fmt.Println("\n📋 Alice's Borrowing History:")
    history := lib.GetMemberBorrowHistory(alice.ID)
    for _, record := range history {
        book, _ := lib.Books.FindByID(record.BookID)
        status := "Active"
        if record.IsReturned {
            status = "Returned"
        }
        fmt.Printf("  - '%s' borrowed on %s (%s)\n",
                   book.Title, record.BorrowDate.Format("2006-01-02"), status)
    }

    // Generate comprehensive report
    lib.GenerateReport()

    // Demonstrate data structure efficiency
    fmt.Println("\n⚡ Performance Demonstration:")
    start := time.Now()

    // Fast ID lookups (O(1))
    book, exists := lib.Books.FindByID(1)
    if exists {
        fmt.Printf("Fast ID lookup: Found '%s' in %v\n", book.Title, time.Since(start))
    }

    // Author lookup by name (indexed)
    start = time.Now()
    authors := lib.Authors.FindByName("tolkien")
    fmt.Printf("Author name lookup: Found %d authors in %v\n", len(authors), time.Since(start))

    // Genre filtering
    start = time.Now()
    fantasyBooks := lib.Books.FindByGenre("fantasy")
    fmt.Printf("Genre filtering: Found %d fantasy books in %v\n", len(fantasyBooks), time.Since(start))
}

func main() {
    demonstrateLibrarySystem()
}
```

**Explanation:**

This comprehensive solution demonstrates all major data structure concepts:

**Key concepts demonstrated:**
1. **Arrays and Slices**: Used throughout for collections, with proper capacity management
2. **Maps**: Multiple indexing strategies for O(1) lookups by different keys
3. **Structs**: Complex nested structures with embedding and composition
4. **Pointers**: Efficient references between related data, optional fields
5. **Custom Collections**: Specialized data structures with built-in indexing
6. **Interfaces**: LibraryItem interface for polymorphic behavior

**Advanced patterns shown:**
- **Multiple indexing**: Books indexed by ID, title, genre, and author
- **Pointer relationships**: Books contain pointers to authors for memory efficiency
- **Optional fields**: ReturnDate uses pointer for nullable timestamp
- **Collection composition**: Library aggregates multiple specialized collections
- **Memory-efficient search**: Set-based search results to avoid duplicates

**Performance optimizations:**
- O(1) lookups for ID-based queries using maps
- Indexed searches for common query patterns
- Minimal memory allocation in search operations
- Efficient sorting using Go's built-in sort package
- Proper capacity hints for slice allocations

**Best practices demonstrated:**
- Clear separation of concerns with specialized collection types
- Comprehensive error handling with meaningful messages
- Consistent data validation throughout the system
- Memory-efficient pointer usage for relationships
- Well-structured reporting and analysis functionality

</details>

---

## Appendices

### 📖 Glossary

**Buffer**: A temporary storage area for data, commonly used in I/O operations.

**Channel**: A Go communication primitive that allows goroutines to send and receive values.

**Closure**: A function that captures variables from its surrounding scope.

**Composite Literal**: A syntax for creating instances of structs, arrays, slices, and maps.

**Concurrency**: The ability to execute multiple tasks simultaneously or in overlapping time periods.

**Defer**: A Go statement that postpones function execution until the surrounding function returns.

**Embedding**: Including one type inside another, providing a form of inheritance in Go.

**Goroutine**: A lightweight thread managed by the Go runtime.

**Interface**: A type that specifies a set of method signatures.

**Method**: A function associated with a particular type.

**Nil**: The zero value for pointers, slices, maps, channels, functions, and interfaces.

**Package**: A collection of Go source files that are compiled together.

**Panic**: A built-in function that stops normal execution and begins panicking.

**Pointer**: A variable that stores the memory address of another variable.

**Receiver**: The value or pointer that a method is called on.

**Rune**: An alias for int32, representing a Unicode code point.

**Slice**: A dynamically-sized array that provides a view into an underlying array.

**Type Assertion**: An operation that extracts the underlying value from an interface.

**Variadic Function**: A function that accepts a variable number of arguments.

**Zero Value**: The default value assigned to variables that are declared but not initialized.

### 🔗 Quick Reference Card

#### Basic Syntax
```go
// Variables
var name string = "value"
name := "value"                    // Short declaration
var x, y int = 1, 2               // Multiple variables

// Constants
const Pi = 3.14159
const (
    Red = iota                     // 0
    Green                          // 1
    Blue                           // 2
)

// Functions
func add(a, b int) int {
    return a + b
}

// Multiple returns
func divmod(a, b int) (int, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}
```

#### Control Structures
```go
// If statement
if condition {
    // code
} else if other {
    // code
} else {
    // code
}

// For loop
for i := 0; i < 10; i++ {
    // code
}

// While loop
for condition {
    // code
}

// Range loop
for index, value := range slice {
    // code
}

// Switch statement
switch value {
case 1:
    // code
case 2, 3:
    // code
default:
    // code
}
```

#### Data Structures
```go
// Arrays
var arr [5]int = [5]int{1, 2, 3, 4, 5}
arr := [...]int{1, 2, 3, 4, 5}

// Slices
var slice []int
slice = append(slice, 1, 2, 3)
slice = make([]int, 5, 10)        // length 5, capacity 10

// Maps
var m map[string]int
m = make(map[string]int)
m["key"] = value
value, exists := m["key"]
delete(m, "key")

// Structs
type Person struct {
    Name string
    Age  int
}
p := Person{Name: "Alice", Age: 30}
p := Person{"Alice", 30}           // Positional

// Pointers
var p *int
x := 42
p = &x                             // Get address
fmt.Println(*p)                    // Dereference
```

#### Error Handling
```go
// Basic error handling
result, err := someFunction()
if err != nil {
    log.Fatal(err)
}

// Custom errors
import "errors"
err := errors.New("something went wrong")
err := fmt.Errorf("error: %v", someValue)

// Panic and recover
defer func() {
    if r := recover(); r != nil {
        fmt.Println("Recovered:", r)
    }
}()
panic("something went wrong")
```

#### Concurrency
```go
// Goroutines
go func() {
    // concurrent code
}()

// Channels
ch := make(chan int)
ch := make(chan int, 10)           // Buffered channel
ch <- value                        // Send
value := <-ch                      // Receive
close(ch)

// Select
select {
case v := <-ch1:
    // handle v
case ch2 <- value:
    // sent value
default:
    // no communication ready
}
```

### 📚 Further Reading

#### Official Resources
- **Go Official Website**: https://golang.org/
- **Go Documentation**: https://golang.org/doc/
- **Go Blog**: https://blog.golang.org/
- **Go Playground**: https://play.golang.org/
- **Go Tour**: https://tour.golang.org/

#### Essential Books
- **"The Go Programming Language"** by Alan Donovan and Brian Kernighan
- **"Go in Action"** by William Kennedy, Brian Ketelsen, and Erik St. Martin
- **"Concurrency in Go"** by Katherine Cox-Buday
- **"Go Web Programming"** by Sau Sheong Chang
- **"Building Microservices with Go"** by Nic Jackson

#### Advanced Topics
- **Go Memory Model**: https://golang.org/ref/mem
- **Effective Go**: https://golang.org/doc/effective_go.html
- **Go Code Review Comments**: https://github.com/golang/go/wiki/CodeReviewComments
- **Go Proverbs**: https://go-proverbs.github.io/

#### Tools and Libraries
- **Popular Frameworks**: Gin, Echo, Fiber (web), GORM (ORM)
- **Testing**: Testify, GoConvey, Ginkgo
- **CLI Tools**: Cobra, Viper, urfave/cli
- **Monitoring**: Prometheus client, OpenTelemetry

### 🤝 Community Resources

#### Online Communities
- **Go Forum**: https://forum.golangbridge.org/
- **Reddit**: r/golang
- **Stack Overflow**: golang tag
- **Discord**: Gophers Discord Server
- **Slack**: Gophers Slack Workspace

#### Conferences and Events
- **GopherCon**: The largest Go conference
- **GoLab**: European Go conference
- **Go meetups**: Local user groups worldwide
- **Go Time Podcast**: Weekly Go podcast

#### Learning Platforms
- **Go by Example**: https://gobyexample.com/
- **Learn Go with Tests**: https://quii.gitbook.io/learn-go-with-tests/
- **Gopher Guides**: https://www.gopherguides.com/
- **Go Web Examples**: https://gowebexamples.com/

#### Open Source Projects
- **Kubernetes**: Container orchestration
- **Docker**: Container platform
- **Prometheus**: Monitoring system
- **InfluxDB**: Time series database
- **CockroachDB**: Distributed SQL database

### 💝 Contributing Guidelines

#### Getting Started with Go Development

**Environment Setup:**
1. Install Go 1.25.0 from https://golang.org/dl/
2. Set up your workspace with proper GOPATH/GOROOT
3. Configure your editor with Go language support
4. Install essential tools: `gofmt`, `goimports`, `golint`, `staticcheck`

**Code Style Guidelines:**
- Use `gofmt` to format your code automatically
- Follow the naming conventions (exported vs unexported)
- Write clear, descriptive variable and function names
- Keep functions small and focused on a single responsibility
- Use interfaces to define behavior contracts

**Testing Best Practices:**
- Write table-driven tests when appropriate
- Use `t.Helper()` in test helper functions
- Test both happy path and error conditions
- Aim for high test coverage but focus on meaningful tests
- Use benchmarks for performance-critical code

**Documentation Standards:**
- Write package documentation that explains the package's purpose
- Document all exported functions, types, and constants
- Use examples in documentation comments
- Keep comments up-to-date with code changes
- Use meaningful commit messages

**Performance Considerations:**
- Profile your code using `go tool pprof`
- Avoid premature optimization
- Use appropriate data structures for your use case
- Be mindful of memory allocations in hot paths
- Leverage Go's built-in concurrency primitives effectively

#### Contributing to Open Source Go Projects

**Finding Projects:**
- Look for "good first issue" labels on GitHub
- Start with projects you use regularly
- Contribute to documentation and examples
- Fix bugs before adding new features

**Submission Process:**
1. Fork the repository
2. Create a feature branch
3. Write tests for your changes
4. Ensure all tests pass
5. Submit a pull request with clear description
6. Respond to code review feedback

**Community Participation:**
- Join Go community discussions
- Attend local Go meetups
- Share your Go projects and experiences
- Help answer questions on forums and chat rooms
- Write blog posts about Go techniques and lessons learned

---



## Chapter 6: Methods and Interfaces
📊 **Progress:** Chapter 6 of 12 | ⏱️ **Estimated reading time:** 30 minutes

🎯 **Learning Objectives:**
- Understand method definition and receiver types
- Master Go's interface system and type assertions
- Learn interface composition and polymorphism
- Explore the empty interface and type switches

📋 **Prerequisites:** Understanding of structs, functions, and basic Go syntax

### Methods

Methods in Go are functions with a special receiver argument. They allow you to define behavior for types.

#### Method Declaration and Receiver Types

```go
package main

import (
    "fmt"
    "math"
    "strings"
)

// Rectangle struct for demonstrating methods
type Rectangle struct {
    Width  float64
    Height float64
}

// Value receiver method - doesn't modify the receiver
func (r Rectangle) Area() float64 {
    return r.Width * r.Height
}

func (r Rectangle) Perimeter() float64 {
    return 2 * (r.Width + r.Height)
}

// String method makes Rectangle implement fmt.Stringer interface
func (r Rectangle) String() string {
    return fmt.Sprintf("Rectangle{Width: %.2f, Height: %.2f}", r.Width, r.Height)
}

// Pointer receiver method - can modify the receiver
func (r *Rectangle) Scale(factor float64) {
    r.Width *= factor
    r.Height *= factor
}

func (r *Rectangle) SetDimensions(width, height float64) {
    r.Width = width
    r.Height = height
}

func demonstrateBasicMethods() {
    fmt.Println("=== Basic Methods ===")

    rect := Rectangle{Width: 10.0, Height: 5.0}

    // Call value receiver methods
    fmt.Printf("Rectangle: %s\n", rect)
    fmt.Printf("Area: %.2f\n", rect.Area())
    fmt.Printf("Perimeter: %.2f\n", rect.Perimeter())

    // Call pointer receiver method
    fmt.Printf("Before scaling: %s\n", rect)
    rect.Scale(2.0)
    fmt.Printf("After scaling by 2: %s\n", rect)

    // Go automatically handles pointer/value conversion
    rectPtr := &Rectangle{Width: 3.0, Height: 4.0}
    fmt.Printf("Area via pointer: %.2f\n", rectPtr.Area()) // Automatic dereferencing

    // Modify through pointer
    rectPtr.SetDimensions(6.0, 8.0)
    fmt.Printf("After setting dimensions: %s\n", rectPtr)
}
```

#### Methods on Different Types

```go
// Methods on custom types
type Temperature float64

const (
    FreezingC Temperature = 0
    BoilingC  Temperature = 100
)

// Methods on basic type
func (t Temperature) Celsius() float64 {
    return float64(t)
}

func (t Temperature) Fahrenheit() float64 {
    return float64(t)*9/5 + 32
}

func (t Temperature) Kelvin() float64 {
    return float64(t) + 273.15
}

func (t Temperature) String() string {
    return fmt.Sprintf("%.1f°C", float64(t))
}

// Methods on slice types
type IntSlice []int

func (is IntSlice) Sum() int {
    total := 0
    for _, v := range is {
        total += v
    }
    return total
}

func (is IntSlice) Average() float64 {
    if len(is) == 0 {
        return 0
    }
    return float64(is.Sum()) / float64(len(is))
}

func (is *IntSlice) Append(values ...int) {
    *is = append(*is, values...)
}

func (is IntSlice) Contains(value int) bool {
    for _, v := range is {
        if v == value {
            return true
        }
    }
    return false
}

func demonstrateMethodsOnTypes() {
    fmt.Println("\n=== Methods on Different Types ===")

    // Methods on custom basic type
    temp := Temperature(25.0)
    fmt.Printf("Temperature: %s\n", temp)
    fmt.Printf("Fahrenheit: %.1f°F\n", temp.Fahrenheit())
    fmt.Printf("Kelvin: %.1f K\n", temp.Kelvin())

    // Methods on slice type
    numbers := IntSlice{1, 2, 3, 4, 5}
    fmt.Printf("Numbers: %v\n", numbers)
    fmt.Printf("Sum: %d\n", numbers.Sum())
    fmt.Printf("Average: %.2f\n", numbers.Average())
    fmt.Printf("Contains 3: %t\n", numbers.Contains(3))

    numbers.Append(6, 7, 8)
    fmt.Printf("After append: %v\n", numbers)
}
```

#### Method Sets and Receiver Rules

```go
// Demonstrate method sets and when to use value vs pointer receivers

type Counter struct {
    value int
    name  string
}

// Value receiver - good for methods that don't modify state
func (c Counter) Value() int {
    return c.value
}

func (c Counter) Name() string {
    return c.name
}

// Pointer receiver - required for methods that modify state
func (c *Counter) Increment() {
    c.value++
}

func (c *Counter) Add(n int) {
    c.value += n
}

func (c *Counter) Reset() {
    c.value = 0
}

// Mixed receivers example
type BankAccount struct {
    accountNumber string
    balance       float64
    owner         string
}

// Value receivers for read-only operations
func (ba BankAccount) Balance() float64 {
    return ba.balance
}

func (ba BankAccount) Owner() string {
    return ba.owner
}

func (ba BankAccount) AccountNumber() string {
    return ba.accountNumber
}

// Pointer receivers for state-modifying operations
func (ba *BankAccount) Deposit(amount float64) error {
    if amount <= 0 {
        return fmt.Errorf("deposit amount must be positive")
    }
    ba.balance += amount
    return nil
}

func (ba *BankAccount) Withdraw(amount float64) error {
    if amount <= 0 {
        return fmt.Errorf("withdrawal amount must be positive")
    }
    if amount > ba.balance {
        return fmt.Errorf("insufficient funds")
    }
    ba.balance -= amount
    return nil
}

func demonstrateMethodSets() {
    fmt.Println("\n=== Method Sets and Receivers ===")

    // Counter example
    counter := Counter{value: 0, name: "Page Views"}
    fmt.Printf("Counter: %s = %d\n", counter.Name(), counter.Value())

    counter.Increment()
    counter.Add(5)
    fmt.Printf("After increment and add 5: %d\n", counter.Value())

    counter.Reset()
    fmt.Printf("After reset: %d\n", counter.Value())

    // Bank account example
    account := BankAccount{
        accountNumber: "12345",
        balance:       1000.0,
        owner:         "Alice Johnson",
    }

    fmt.Printf("Account: %s, Owner: %s, Balance: $%.2f\n",
               account.AccountNumber(), account.Owner(), account.Balance())

    // Successful operations
    if err := account.Deposit(250.0); err != nil {
        fmt.Printf("Deposit error: %v\n", err)
    } else {
        fmt.Printf("After deposit: $%.2f\n", account.Balance())
    }

    if err := account.Withdraw(100.0); err != nil {
        fmt.Printf("Withdrawal error: %v\n", err)
    } else {
        fmt.Printf("After withdrawal: $%.2f\n", account.Balance())
    }

    // Error case
    if err := account.Withdraw(2000.0); err != nil {
        fmt.Printf("Withdrawal error: %v\n", err)
    }
}
```

### Interfaces

Interfaces in Go define a set of method signatures. Types implement interfaces implicitly by having the required methods.

#### Basic Interface Definition and Implementation

```go
// Shape interface defines behavior for geometric shapes
type Shape interface {
    Area() float64
    Perimeter() float64
}

// Drawable interface for things that can be drawn
type Drawable interface {
    Draw()
}

// Combined interface
type DrawableShape interface {
    Shape    // Embedded interface
    Drawable // Embedded interface
}

// Circle implements Shape interface
type Circle struct {
    Radius float64
}

func (c Circle) Area() float64 {
    return math.Pi * c.Radius * c.Radius
}

func (c Circle) Perimeter() float64 {
    return 2 * math.Pi * c.Radius
}

func (c Circle) Draw() {
    fmt.Printf("Drawing circle with radius %.2f\n", c.Radius)
}

func (c Circle) String() string {
    return fmt.Sprintf("Circle{Radius: %.2f}", c.Radius)
}

// Triangle implements Shape interface
type Triangle struct {
    Base   float64
    Height float64
    SideA  float64
    SideB  float64
    SideC  float64
}

func (t Triangle) Area() float64 {
    return 0.5 * t.Base * t.Height
}

func (t Triangle) Perimeter() float64 {
    return t.SideA + t.SideB + t.SideC
}

func (t Triangle) Draw() {
    fmt.Printf("Drawing triangle with base %.2f and height %.2f\n", t.Base, t.Height)
}

func (t Triangle) String() string {
    return fmt.Sprintf("Triangle{Base: %.2f, Height: %.2f}", t.Base, t.Height)
}

// Rectangle already implements Shape from earlier
func (r Rectangle) Draw() {
    fmt.Printf("Drawing rectangle %.2f x %.2f\n", r.Width, r.Height)
}

func demonstrateBasicInterfaces() {
    fmt.Println("\n=== Basic Interfaces ===")

    // Create shapes
    shapes := []Shape{
        Rectangle{Width: 10, Height: 5},
        Circle{Radius: 3},
        Triangle{Base: 4, Height: 6, SideA: 3, SideB: 4, SideC: 5},
    }

    fmt.Println("Shape calculations:")
    totalArea := 0.0
    for _, shape := range shapes {
        area := shape.Area()
        perimeter := shape.Perimeter()
        totalArea += area

        fmt.Printf("  %s: Area=%.2f, Perimeter=%.2f\n",
                   shape, area, perimeter)
    }
    fmt.Printf("Total area: %.2f\n", totalArea)

    // Interface composition
    fmt.Println("\nDrawable shapes:")
    drawableShapes := []DrawableShape{
        Rectangle{Width: 8, Height: 6},
        Circle{Radius: 2.5},
        Triangle{Base: 3, Height: 4, SideA: 3, SideB: 4, SideC: 5},
    }

    for _, ds := range drawableShapes {
        ds.Draw()
        fmt.Printf("  Area: %.2f\n", ds.Area())
    }
}
```

#### Interface Best Practices and Patterns

```go
// Small, focused interfaces (Interface Segregation Principle)
type Reader interface {
    Read([]byte) (int, error)
}

type Writer interface {
    Write([]byte) (int, error)
}

type ReadWriter interface {
    Reader
    Writer
}

// Common interface patterns
type Stringer interface {
    String() string
}

type Error interface {
    Error() string
}

// Custom error type implementing Error interface
type ValidationError struct {
    Field   string
    Message string
}

func (ve ValidationError) Error() string {
    return fmt.Sprintf("validation error in field '%s': %s", ve.Field, ve.Message)
}

// Service interfaces for dependency injection
type Logger interface {
    Log(message string)
    Logf(format string, args ...interface{})
}

type Database interface {
    Save(data interface{}) error
    Find(id string) (interface{}, error)
    Delete(id string) error
}

// Console logger implementation
type ConsoleLogger struct {
    prefix string
}

func NewConsoleLogger(prefix string) *ConsoleLogger {
    return &ConsoleLogger{prefix: prefix}
}

func (cl *ConsoleLogger) Log(message string) {
    fmt.Printf("[%s] %s\n", cl.prefix, message)
}

func (cl *ConsoleLogger) Logf(format string, args ...interface{}) {
    message := fmt.Sprintf(format, args...)
    cl.Log(message)
}

// Mock database for testing
type MockDatabase struct {
    data map[string]interface{}
}

func NewMockDatabase() *MockDatabase {
    return &MockDatabase{
        data: make(map[string]interface{}),
    }
}

func (mdb *MockDatabase) Save(data interface{}) error {
    // In real implementation, would generate ID
    id := fmt.Sprintf("item_%d", len(mdb.data)+1)
    mdb.data[id] = data
    return nil
}

func (mdb *MockDatabase) Find(id string) (interface{}, error) {
    if data, exists := mdb.data[id]; exists {
        return data, nil
    }
    return nil, fmt.Errorf("item with ID %s not found", id)
}

func (mdb *MockDatabase) Delete(id string) error {
    if _, exists := mdb.data[id]; exists {
        delete(mdb.data, id)
        return nil
    }
    return fmt.Errorf("item with ID %s not found", id)
}

// Service using interfaces for dependencies
type UserService struct {
    db     Database
    logger Logger
}

func NewUserService(db Database, logger Logger) *UserService {
    return &UserService{
        db:     db,
        logger: logger,
    }
}

func (us *UserService) CreateUser(name, email string) error {
    us.logger.Logf("Creating user: %s (%s)", name, email)

    // Validation
    if name == "" {
        return ValidationError{Field: "name", Message: "cannot be empty"}
    }
    if email == "" {
        return ValidationError{Field: "email", Message: "cannot be empty"}
    }

    user := map[string]string{
        "name":  name,
        "email": email,
    }

    if err := us.db.Save(user); err != nil {
        us.logger.Logf("Failed to save user: %v", err)
        return err
    }

    us.logger.Log("User created successfully")
    return nil
}

func demonstrateInterfacePatterns() {
    fmt.Println("\n=== Interface Patterns ===")

    // Dependency injection with interfaces
    logger := NewConsoleLogger("USER_SERVICE")
    db := NewMockDatabase()
    userService := NewUserService(db, logger)

    // Create users
    if err := userService.CreateUser("Alice", "alice@example.com"); err != nil {
        fmt.Printf("Error: %v\n", err)
    }

    if err := userService.CreateUser("Bob", "bob@example.com"); err != nil {
        fmt.Printf("Error: %v\n", err)
    }

    // Test validation error
    if err := userService.CreateUser("", "invalid@example.com"); err != nil {
        fmt.Printf("Validation error: %v\n", err)
    }
}
```

### Type Assertions

Type assertions provide access to an interface value's underlying concrete value.

#### Basic Type Assertions

```go
func demonstrateTypeAssertions() {
    fmt.Println("\n=== Type Assertions ===")

    var i interface{} = "hello world"

    // Type assertion with panic risk
    s := i.(string)
    fmt.Printf("String value: %s\n", s)

    // Safe type assertion
    s2, ok := i.(string)
    if ok {
        fmt.Printf("Safe string assertion: %s\n", s2)
    }

    // Failed assertion
    num, ok := i.(int)
    if ok {
        fmt.Printf("Integer: %d\n", num)
    } else {
        fmt.Printf("Not an integer, got zero value: %d\n", num)
    }

    // Type assertion with different types
    values := []interface{}{
        42,
        "hello",
        3.14,
        true,
        []int{1, 2, 3},
        map[string]int{"key": 100},
        Rectangle{Width: 5, Height: 3},
    }

    fmt.Println("\nType assertion examples:")
    for i, val := range values {
        fmt.Printf("Value %d (%T): ", i+1, val)

        switch v := val.(type) {
        case int:
            fmt.Printf("Integer: %d\n", v)
        case string:
            fmt.Printf("String: %q (length: %d)\n", v, len(v))
        case float64:
            fmt.Printf("Float: %.2f\n", v)
        case bool:
            fmt.Printf("Boolean: %t\n", v)
        case []int:
            fmt.Printf("Int slice: %v (sum: %d)\n", v, sumSlice(v))
        case map[string]int:
            fmt.Printf("String-int map: %v\n", v)
        case Rectangle:
            fmt.Printf("Rectangle: %.2f x %.2f (area: %.2f)\n",
                       v.Width, v.Height, v.Area())
        default:
            fmt.Printf("Unknown type: %v\n", v)
        }
    }
}

func sumSlice(slice []int) int {
    sum := 0
    for _, v := range slice {
        sum += v
    }
    return sum
}
```

#### Advanced Type Assertion Patterns

```go
// Interface for different message types
type Message interface {
    Type() string
    Content() string
}

// Text message
type TextMessage struct {
    Text string
    From string
}

func (tm TextMessage) Type() string {
    return "text"
}

func (tm TextMessage) Content() string {
    return tm.Text
}

// Image message
type ImageMessage struct {
    URL    string
    Width  int
    Height int
    From   string
}

func (im ImageMessage) Type() string {
    return "image"
}

func (im ImageMessage) Content() string {
    return fmt.Sprintf("Image: %s (%dx%d)", im.URL, im.Width, im.Height)
}

// Audio message
type AudioMessage struct {
    URL      string
    Duration int // seconds
    From     string
}

func (am AudioMessage) Type() string {
    return "audio"
}

func (am AudioMessage) Content() string {
    return fmt.Sprintf("Audio: %s (%d seconds)", am.URL, am.Duration)
}

// Message processor using type assertions
func processMessage(msg Message) {
    fmt.Printf("Processing %s message: %s\n", msg.Type(), msg.Content())

    // Type-specific processing
    switch m := msg.(type) {
    case TextMessage:
        if len(m.Text) > 100 {
            fmt.Println("  -> Long text message detected")
        }
        fmt.Printf("  -> From: %s\n", m.From)

    case ImageMessage:
        if m.Width > 1920 || m.Height > 1080 {
            fmt.Println("  -> High resolution image")
        }
        fmt.Printf("  -> From: %s\n", m.From)

    case AudioMessage:
        if m.Duration > 300 { // 5 minutes
            fmt.Println("  -> Long audio message")
        }
        fmt.Printf("  -> From: %s\n", m.From)

    default:
        fmt.Println("  -> Unknown message type")
    }
}

func demonstrateAdvancedTypeAssertions() {
    fmt.Println("\n=== Advanced Type Assertions ===")

    messages := []Message{
        TextMessage{
            Text: "Hello, how are you today?",
            From: "Alice",
        },
        ImageMessage{
            URL:    "https://example.com/photo.jpg",
            Width:  1920,
            Height: 1080,
            From:   "Bob",
        },
        AudioMessage{
            URL:      "https://example.com/voice.mp3",
            Duration: 45,
            From:     "Carol",
        },
        TextMessage{
            Text: strings.Repeat("This is a very long message. ", 10),
            From: "Dave",
        },
    }

    for _, msg := range messages {
        processMessage(msg)
        fmt.Println()
    }
}
```

### Empty Interface

The empty interface `interface{}` can hold any type and is commonly used for generic programming.

```go
func demonstrateEmptyInterface() {
    fmt.Println("\n=== Empty Interface ===")

    // Empty interface can hold any value
    var any interface{}

    any = 42
    fmt.Printf("any = %v (type: %T)\n", any, any)

    any = "hello"
    fmt.Printf("any = %v (type: %T)\n", any, any)

    any = []int{1, 2, 3}
    fmt.Printf("any = %v (type: %T)\n", any, any)

    // Generic container using empty interface
    container := []interface{}{
        "text",
        123,
        3.14,
        true,
        Rectangle{Width: 5, Height: 3},
        map[string]int{"count": 42},
    }

    fmt.Println("\nGeneric container:")
    for i, item := range container {
        fmt.Printf("  [%d] %v (%T)\n", i, item, item)
    }

    // Generic functions
    fmt.Println("\nGeneric function results:")
    fmt.Printf("Max of (10, 20): %v\n", max(10, 20))
    fmt.Printf("Max of (3.14, 2.71): %v\n", max(3.14, 2.71))
    fmt.Printf("Max of strings: %v\n", max("apple", "banana"))
}

// Generic max function using empty interface
func max(a, b interface{}) interface{} {
    switch a := a.(type) {
    case int:
        if b, ok := b.(int); ok {
            if a > b {
                return a
            }
            return b
        }
    case float64:
        if b, ok := b.(float64); ok {
            if a > b {
                return a
            }
            return b
        }
    case string:
        if b, ok := b.(string); ok {
            if a > b {
                return a
            }
            return b
        }
    }
    return nil // Unable to compare
}
```

### ⚠️ Common Pitfalls

1. **Interface Pollution**
```go
// Wrong: Too many methods in interface
type UserManager interface {
    Create(user User) error
    Update(user User) error
    Delete(id string) error
    Find(id string) (User, error)
    List() ([]User, error)
    SendEmail(id, subject, body string) error
    ValidateUser(user User) error
    HashPassword(password string) string
}

// Better: Focused interfaces
type UserRepository interface {
    Save(user User) error
    Find(id string) (User, error)
    Delete(id string) error
}

type EmailSender interface {
    SendEmail(to, subject, body string) error
}

type UserValidator interface {
    Validate(user User) error
}
```

2. **Nil Interface Confusion**
```go
func nilInterfacePitfall() {
    var ptr *string = nil
    var iface interface{} = ptr

    // This is false! Interface contains type information
    fmt.Printf("iface == nil: %t\n", iface == nil) // false
    fmt.Printf("iface is nil: %t\n", iface == (*string)(nil)) // true

    // Check for nil interface properly
    if iface == nil {
        fmt.Println("Interface is nil")
    } else {
        fmt.Printf("Interface is not nil, type: %T, value: %v\n", iface, iface)
    }
}
```

### ✅ Best Practices

1. **Accept Interfaces, Return Concrete Types**
```go
// Good: Accept interface parameter
func ProcessData(r io.Reader) ([]byte, error) {
    return io.ReadAll(r)
}

// Good: Return concrete type
func NewFileProcessor(filename string) *FileProcessor {
    return &FileProcessor{filename: filename}
}
```

2. **Keep Interfaces Small**
```go
// Good: Single responsibility
type Writer interface {
    Write([]byte) (int, error)
}

// Good: Composed from small interfaces
type ReadWriteCloser interface {
    io.Reader
    io.Writer
    io.Closer
}
```

3. **Define Interfaces Where They're Used**
```go
// Good: Interface defined near usage
package main

type DataProcessor interface {
    Process(data []byte) error
}

func HandleRequest(processor DataProcessor, data []byte) error {
    return processor.Process(data)
}
```

### 🏋️ Exercise 6: Methods and Interfaces Mastery
**Difficulty:** 🔴 Advanced
**Estimated Time:** 50 minutes

Create a comprehensive media player system that demonstrates:

1. Method definition with appropriate receiver types
2. Interface design and composition
3. Type assertions and type switches
4. Polymorphic behavior through interfaces
5. Interface-based dependency injection
6. Error handling with custom error types

Build a "Media Player" that can handle different media types with plugins and event handling.

<details>
<summary>💡 Click to see hints</summary>

- Design interfaces for media players, audio/video codecs, and event handlers
- Use method sets appropriately for state management
- Implement plugin architecture with interfaces
- Create custom error types with helpful information
- Use type assertions for codec-specific optimizations
- Implement observer pattern with interfaces

</details>

<details>
<summary>✅ Click to see solution</summary>

```go
package main

import (
    "fmt"
    "strings"
    "time"
)

// Core interfaces

// MediaFile represents any media file
type MediaFile interface {
    Filename() string
    Duration() time.Duration
    FileSize() int64
    MediaType() string
}

// Player interface for different player implementations
type Player interface {
    Play(media MediaFile) error
    Pause() error
    Stop() error
    Seek(position time.Duration) error
    GetPosition() time.Duration
    GetState() PlaybackState
    SetVolume(volume float64) error
    GetVolume() float64
}

// Codec interface for encoding/decoding media
type Codec interface {
    Name() string
    SupportedFormats() []string
    CanDecode(filename string) bool
    Decode(media MediaFile) (DecodedMedia, error)
}

// EventListener for player events
type EventListener interface {
    OnPlaybackStarted(media MediaFile)
    OnPlaybackPaused()
    OnPlaybackStopped()
    OnPlaybackFinished(media MediaFile)
    OnError(err error)
}

// DecodedMedia represents decoded media data
type DecodedMedia interface {
    GetData() []byte
    GetMetadata() map[string]interface{}
}

// Playback states
type PlaybackState int

const (
    StateStopped PlaybackState = iota
    StatePlaying
    StatePaused
    StateBuffering
)

func (ps PlaybackState) String() string {
    switch ps {
    case StateStopped:
        return "Stopped"
    case StatePlaying:
        return "Playing"
    case StatePaused:
        return "Paused"
    case StateBuffering:
        return "Buffering"
    default:
        return "Unknown"
    }
}

// Media file implementations

// AudioFile represents an audio file
type AudioFile struct {
    filename   string
    duration   time.Duration
    fileSize   int64
    sampleRate int
    bitRate    int
    channels   int
}

// Implement MediaFile interface
func (af AudioFile) Filename() string          { return af.filename }
func (af AudioFile) Duration() time.Duration   { return af.duration }
func (af AudioFile) FileSize() int64           { return af.fileSize }
func (af AudioFile) MediaType() string         { return "audio" }

// Audio-specific methods
func (af AudioFile) SampleRate() int { return af.sampleRate }
func (af AudioFile) BitRate() int    { return af.bitRate }
func (af AudioFile) Channels() int   { return af.channels }

func (af AudioFile) String() string {
    return fmt.Sprintf("AudioFile{%s, %v, %d Hz, %d kbps, %d ch}",
                       af.filename, af.duration, af.sampleRate, af.bitRate/1000, af.channels)
}

// VideoFile represents a video file
type VideoFile struct {
    filename   string
    duration   time.Duration
    fileSize   int64
    width      int
    height     int
    frameRate  float64
    bitRate    int
}

func (vf VideoFile) Filename() string          { return vf.filename }
func (vf VideoFile) Duration() time.Duration   { return vf.duration }
func (vf VideoFile) FileSize() int64           { return vf.fileSize }
func (vf VideoFile) MediaType() string         { return "video" }

// Video-specific methods
func (vf VideoFile) Resolution() (int, int) { return vf.width, vf.height }
func (vf VideoFile) FrameRate() float64     { return vf.frameRate }
func (vf VideoFile) BitRate() int           { return vf.bitRate }

func (vf VideoFile) String() string {
    return fmt.Sprintf("VideoFile{%s, %v, %dx%d, %.1f fps}",
                       vf.filename, vf.duration, vf.width, vf.height, vf.frameRate)
}

// Custom error types

// MediaError represents media-related errors
type MediaError struct {
    Operation string
    MediaFile string
    Cause     error
}

func (me MediaError) Error() string {
    if me.Cause != nil {
        return fmt.Sprintf("media error during %s of '%s': %v", me.Operation, me.MediaFile, me.Cause)
    }
    return fmt.Sprintf("media error during %s of '%s'", me.Operation, me.MediaFile)
}

// CodecError represents codec-related errors
type CodecError struct {
    CodecName string
    Format    string
    Message   string
}

func (ce CodecError) Error() string {
    return fmt.Sprintf("codec error [%s]: %s format - %s", ce.CodecName, ce.Format, ce.Message)
}

// Codec implementations

// MP3Codec for MP3 audio files
type MP3Codec struct {
    name string
}

func NewMP3Codec() *MP3Codec {
    return &MP3Codec{name: "MP3 Codec"}
}

func (mp3 *MP3Codec) Name() string {
    return mp3.name
}

func (mp3 *MP3Codec) SupportedFormats() []string {
    return []string{"mp3", "mpeg"}
}

func (mp3 *MP3Codec) CanDecode(filename string) bool {
    lower := strings.ToLower(filename)
    return strings.HasSuffix(lower, ".mp3") || strings.HasSuffix(lower, ".mpeg")
}

func (mp3 *MP3Codec) Decode(media MediaFile) (DecodedMedia, error) {
    if !mp3.CanDecode(media.Filename()) {
        return nil, CodecError{
            CodecName: mp3.name,
            Format:    "MP3",
            Message:   "unsupported file format",
        }
    }

    // Simulate decoding
    return &SimpleDecodedMedia{
        data: make([]byte, media.FileSize()),
        metadata: map[string]interface{}{
            "codec": "mp3",
            "duration": media.Duration(),
            "type": "audio",
        },
    }, nil
}

// MP4Codec for MP4 video files
type MP4Codec struct {
    name string
}

func NewMP4Codec() *MP4Codec {
    return &MP4Codec{name: "MP4 Codec"}
}

func (mp4 *MP4Codec) Name() string {
    return mp4.name
}

func (mp4 *MP4Codec) SupportedFormats() []string {
    return []string{"mp4", "m4v", "m4a"}
}

func (mp4 *MP4Codec) CanDecode(filename string) bool {
    lower := strings.ToLower(filename)
    for _, format := range mp4.SupportedFormats() {
        if strings.HasSuffix(lower, "."+format) {
            return true
        }
    }
    return false
}

func (mp4 *MP4Codec) Decode(media MediaFile) (DecodedMedia, error) {
    if !mp4.CanDecode(media.Filename()) {
        return nil, CodecError{
            CodecName: mp4.name,
            Format:    "MP4",
            Message:   "unsupported file format",
        }
    }

    return &SimpleDecodedMedia{
        data: make([]byte, media.FileSize()),
        metadata: map[string]interface{}{
            "codec": "mp4",
            "duration": media.Duration(),
            "type": media.MediaType(),
        },
    }, nil
}

// SimpleDecodedMedia implementation
type SimpleDecodedMedia struct {
    data     []byte
    metadata map[string]interface{}
}

func (sdm *SimpleDecodedMedia) GetData() []byte {
    return sdm.data
}

func (sdm *SimpleDecodedMedia) GetMetadata() map[string]interface{} {
    return sdm.metadata
}

// Universal media player implementation
type UniversalPlayer struct {
    currentMedia  MediaFile
    position      time.Duration
    state         PlaybackState
    volume        float64
    codecs        []Codec
    listeners     []EventListener
}

func NewUniversalPlayer() *UniversalPlayer {
    return &UniversalPlayer{
        state:     StateStopped,
        volume:    1.0,
        codecs:    make([]Codec, 0),
        listeners: make([]EventListener, 0),
    }
}

// Player interface implementation
func (up *UniversalPlayer) Play(media MediaFile) error {
    // Find appropriate codec
    codec := up.findCodec(media.Filename())
    if codec == nil {
        err := MediaError{
            Operation: "play",
            MediaFile: media.Filename(),
            Cause:     fmt.Errorf("no suitable codec found"),
        }
        up.notifyError(err)
        return err
    }

    // Decode media
    decoded, err := codec.Decode(media)
    if err != nil {
        mediaErr := MediaError{
            Operation: "play",
            MediaFile: media.Filename(),
            Cause:     err,
        }
        up.notifyError(mediaErr)
        return mediaErr
    }

    up.currentMedia = media
    up.position = 0
    up.state = StatePlaying

    // Notify listeners
    up.notifyPlaybackStarted(media)

    fmt.Printf("🎵 Playing %s with %s\n", media.Filename(), codec.Name())
    fmt.Printf("📊 Metadata: %v\n", decoded.GetMetadata())

    return nil
}

func (up *UniversalPlayer) Pause() error {
    if up.state != StatePlaying {
        return fmt.Errorf("cannot pause: not currently playing")
    }

    up.state = StatePaused
    up.notifyPlaybackPaused()
    fmt.Printf("⏸️  Paused at %v\n", up.position)
    return nil
}

func (up *UniversalPlayer) Stop() error {
    if up.state == StateStopped {
        return fmt.Errorf("already stopped")
    }

    up.state = StateStopped
    up.position = 0
    up.notifyPlaybackStopped()
    fmt.Println("⏹️  Stopped")
    return nil
}

func (up *UniversalPlayer) Seek(position time.Duration) error {
    if up.currentMedia == nil {
        return fmt.Errorf("no media loaded")
    }

    if position < 0 || position > up.currentMedia.Duration() {
        return fmt.Errorf("seek position out of range")
    }

    up.position = position
    fmt.Printf("⏭️  Seeked to %v\n", position)
    return nil
}

func (up *UniversalPlayer) GetPosition() time.Duration {
    return up.position
}

func (up *UniversalPlayer) GetState() PlaybackState {
    return up.state
}

func (up *UniversalPlayer) SetVolume(volume float64) error {
    if volume < 0.0 || volume > 1.0 {
        return fmt.Errorf("volume must be between 0.0 and 1.0")
    }

    up.volume = volume
    fmt.Printf("🔊 Volume set to %.0f%%\n", volume*100)
    return nil
}

func (up *UniversalPlayer) GetVolume() float64 {
    return up.volume
}

// Plugin management methods
func (up *UniversalPlayer) RegisterCodec(codec Codec) {
    up.codecs = append(up.codecs, codec)
    fmt.Printf("🔌 Registered codec: %s (formats: %v)\n",
               codec.Name(), codec.SupportedFormats())
}

func (up *UniversalPlayer) AddEventListener(listener EventListener) {
    up.listeners = append(up.listeners, listener)
}

func (up *UniversalPlayer) RemoveEventListener(listener EventListener) {
    for i, l := range up.listeners {
        if l == listener {
            up.listeners = append(up.listeners[:i], up.listeners[i+1:]...)
            break
        }
    }
}

// Private helper methods
func (up *UniversalPlayer) findCodec(filename string) Codec {
    for _, codec := range up.codecs {
        if codec.CanDecode(filename) {
            return codec
        }
    }
    return nil
}

func (up *UniversalPlayer) notifyPlaybackStarted(media MediaFile) {
    for _, listener := range up.listeners {
        listener.OnPlaybackStarted(media)
    }
}

func (up *UniversalPlayer) notifyPlaybackPaused() {
    for _, listener := range up.listeners {
        listener.OnPlaybackPaused()
    }
}

func (up *UniversalPlayer) notifyPlaybackStopped() {
    for _, listener := range up.listeners {
        listener.OnPlaybackStopped()
    }
}

func (up *UniversalPlayer) notifyPlaybackFinished(media MediaFile) {
    for _, listener := range up.listeners {
        listener.OnPlaybackFinished(media)
    }
}

func (up *UniversalPlayer) notifyError(err error) {
    for _, listener := range up.listeners {
        listener.OnError(err)
    }
}

// Event listener implementations

// ConsoleEventListener logs events to console
type ConsoleEventListener struct {
    name string
}

func NewConsoleEventListener(name string) *ConsoleEventListener {
    return &ConsoleEventListener{name: name}
}

func (cel *ConsoleEventListener) OnPlaybackStarted(media MediaFile) {
    fmt.Printf("[%s] 🎬 Playback started: %s\n", cel.name, media.Filename())
}

func (cel *ConsoleEventListener) OnPlaybackPaused() {
    fmt.Printf("[%s] ⏸️  Playback paused\n", cel.name)
}

func (cel *ConsoleEventListener) OnPlaybackStopped() {
    fmt.Printf("[%s] ⏹️  Playback stopped\n", cel.name)
}

func (cel *ConsoleEventListener) OnPlaybackFinished(media MediaFile) {
    fmt.Printf("[%s] ✅ Playback finished: %s\n", cel.name, media.Filename())
}

func (cel *ConsoleEventListener) OnError(err error) {
    fmt.Printf("[%s] ❌ Error: %v\n", cel.name, err)
}

// StatisticsListener tracks playback statistics
type StatisticsListener struct {
    totalPlayed    int
    totalErrors    int
    playbackTime   time.Duration
    startTime      time.Time
}

func NewStatisticsListener() *StatisticsListener {
    return &StatisticsListener{}
}

func (sl *StatisticsListener) OnPlaybackStarted(media MediaFile) {
    sl.totalPlayed++
    sl.startTime = time.Now()
}

func (sl *StatisticsListener) OnPlaybackPaused() {
    if !sl.startTime.IsZero() {
        sl.playbackTime += time.Since(sl.startTime)
    }
}

func (sl *StatisticsListener) OnPlaybackStopped() {
    if !sl.startTime.IsZero() {
        sl.playbackTime += time.Since(sl.startTime)
        sl.startTime = time.Time{}
    }
}

func (sl *StatisticsListener) OnPlaybackFinished(media MediaFile) {
    if !sl.startTime.IsZero() {
        sl.playbackTime += time.Since(sl.startTime)
        sl.startTime = time.Time{}
    }
}

func (sl *StatisticsListener) OnError(err error) {
    sl.totalErrors++
}

func (sl *StatisticsListener) GetStatistics() map[string]interface{} {
    return map[string]interface{}{
        "totalPlayed":    sl.totalPlayed,
        "totalErrors":    sl.totalErrors,
        "playbackTime":   sl.playbackTime,
    }
}

// Advanced type assertion example
func analyzeMedia(media MediaFile) {
    fmt.Printf("📋 Analyzing media: %s\n", media.Filename())
    fmt.Printf("   Type: %s, Duration: %v, Size: %d bytes\n",
               media.MediaType(), media.Duration(), media.FileSize())

    // Type-specific analysis using type assertions
    switch m := media.(type) {
    case AudioFile:
        fmt.Printf("   Audio details: %d Hz, %d kbps, %d channels\n",
                   m.SampleRate(), m.BitRate()/1000, m.Channels())

        // Audio quality assessment
        if m.BitRate() >= 320000 {
            fmt.Println("   🎵 High quality audio")
        } else if m.BitRate() >= 128000 {
            fmt.Println("   🎵 Standard quality audio")
        } else {
            fmt.Println("   🎵 Low quality audio")
        }

    case VideoFile:
        width, height := m.Resolution()
        fmt.Printf("   Video details: %dx%d, %.1f fps, %d kbps\n",
                   width, height, m.FrameRate(), m.BitRate()/1000)

        // Video quality assessment
        if width >= 1920 && height >= 1080 {
            fmt.Println("   🎬 HD video")
        } else if width >= 1280 && height >= 720 {
            fmt.Println("   🎬 Standard definition video")
        } else {
            fmt.Println("   🎬 Low definition video")
        }

    default:
        fmt.Println("   ❓ Unknown media type for detailed analysis")
    }
    fmt.Println()
}

// Demonstrate the media player system
func demonstrateMediaPlayerSystem() {
    fmt.Println("🎬 Advanced Methods and Interfaces: Media Player System")
    fmt.Println("=====================================================")

    // Create player and register codecs
    player := NewUniversalPlayer()
    player.RegisterCodec(NewMP3Codec())
    player.RegisterCodec(NewMP4Codec())

    // Add event listeners
    consoleListener := NewConsoleEventListener("CONSOLE")
    statsListener := NewStatisticsListener()

    player.AddEventListener(consoleListener)
    player.AddEventListener(statsListener)

    // Create sample media files
    audioFile := AudioFile{
        filename:   "song.mp3",
        duration:   3*time.Minute + 45*time.Second,
        fileSize:   5242880, // ~5MB
        sampleRate: 44100,
        bitRate:    320000,
        channels:   2,
    }

    videoFile := VideoFile{
        filename:  "movie.mp4",
        duration:  120 * time.Minute,
        fileSize:  1073741824, // 1GB
        width:     1920,
        height:    1080,
        frameRate: 23.976,
        bitRate:   8000000,
    }

    // Analyze media files
    fmt.Println("📊 Media Analysis:")
    analyzeMedia(audioFile)
    analyzeMedia(videoFile)

    // Demonstrate playback
    fmt.Println("🎵 Audio Playback Demo:")
    if err := player.Play(audioFile); err != nil {
        fmt.Printf("Error playing audio: %v\n", err)
    }

    time.Sleep(100 * time.Millisecond) // Simulate playback
    player.SetVolume(0.8)
    player.Seek(1 * time.Minute)
    player.Pause()
    player.Stop()

    fmt.Println("\n🎬 Video Playback Demo:")
    if err := player.Play(videoFile); err != nil {
        fmt.Printf("Error playing video: %v\n", err)
    }

    time.Sleep(100 * time.Millisecond)
    player.Seek(30 * time.Minute)
    player.SetVolume(0.6)
    player.Stop()

    // Test unsupported format
    fmt.Println("\n❌ Unsupported Format Test:")
    unsupportedFile := AudioFile{
        filename: "song.flac",
        duration: 4 * time.Minute,
        fileSize: 30000000,
        sampleRate: 96000,
        bitRate: 1411200,
        channels: 2,
    }

    if err := player.Play(unsupportedFile); err != nil {
        fmt.Printf("Expected error: %v\n", err)
    }

    // Display statistics
    fmt.Println("\n📈 Playback Statistics:")
    stats := statsListener.GetStatistics()
    for key, value := range stats {
        fmt.Printf("   %s: %v\n", key, value)
    }

    // Demonstrate interface composition
    fmt.Println("\n🔧 Interface Composition Demo:")
    demonstrateInterfaceComposition(player)
}

func demonstrateInterfaceComposition(p Player) {
    // Player interface allows us to work with any player implementation
    fmt.Printf("Player state: %s\n", p.GetState())
    fmt.Printf("Volume: %.0f%%\n", p.GetVolume()*100)

    // Type assertion to access extended functionality
    if up, ok := p.(*UniversalPlayer); ok {
        fmt.Printf("Codec count: %d\n", len(up.codecs))
        fmt.Printf("Listener count: %d\n", len(up.listeners))
    }
}

func main() {
    demonstrateBasicMethods()
    demonstrateMethodsOnTypes()
    demonstrateMethodSets()
    demonstrateBasicInterfaces()
    demonstrateInterfacePatterns()
    demonstrateTypeAssertions()
    demonstrateAdvancedTypeAssertions()
    demonstrateEmptyInterface()
    demonstrateMediaPlayerSystem()
}
```

**Explanation:**

This comprehensive solution demonstrates all advanced methods and interfaces concepts:

**Key concepts demonstrated:**
1. **Method definition**: Value and pointer receivers with appropriate usage
2. **Interface design**: Small, focused interfaces with clear responsibilities
3. **Interface composition**: Building complex interfaces from simple ones
4. **Type assertions**: Safe type checking and conversion with error handling
5. **Polymorphism**: Different media types implementing common interfaces
6. **Plugin architecture**: Codec registration and dynamic loading

**Advanced patterns shown:**
- **Observer pattern**: Event listeners for player events
- **Strategy pattern**: Different codecs for different file formats
- **Dependency injection**: Player accepts interfaces, not concrete types
- **Custom error types**: Detailed error information with context
- **Interface segregation**: Focused interfaces for specific responsibilities

**Performance considerations:**
- Pointer receivers for state-modifying operations
- Value receivers for read-only operations
- Efficient type assertions with ok pattern
- Minimal interface overhead
- Plugin system allows for extensibility without modification

</details>

---

## Chapter 7: Error Handling
📊 **Progress:** Chapter 7 of 12 | ⏱️ **Estimated reading time:** 25 minutes

🎯 **Learning Objectives:**
- Master Go's explicit error handling philosophy
- Understand the error interface and custom error types
- Learn error wrapping and unwrapping techniques
- Explore panic and recover mechanisms

📋 **Prerequisites:** Understanding of interfaces, functions, and basic Go syntax

### Error Interface

Go's approach to error handling is explicit and straightforward, using the built-in `error` interface.

#### Basic Error Handling

```go
package main

import (
    "errors"
    "fmt"
    "strconv"
)

func demonstrateBasicErrors() {
    fmt.Println("=== Basic Error Handling ===")

    // Function that returns an error
    result, err := divide(10, 2)
    if err != nil {
        fmt.Printf("Error: %v\n", err)
    } else {
        fmt.Printf("10 / 2 = %.2f\n", result)
    }

    // Error case
    result, err = divide(10, 0)
    if err != nil {
        fmt.Printf("Error: %v\n", err)
    } else {
        fmt.Printf("Result: %.2f\n", result)
    }

    // String conversion with error
    num, err := strconv.Atoi("123")
    if err != nil {
        fmt.Printf("Conversion error: %v\n", err)
    } else {
        fmt.Printf("Converted number: %d\n", num)
    }

    // Invalid conversion
    num, err = strconv.Atoi("invalid")
    if err != nil {
        fmt.Printf("Expected error: %v\n", err)
    }
}

func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}
```

### Creating Custom Errors

Custom error types provide more context and structured error information.

#### Custom Error Types

```go
// ValidationError represents validation failures
type ValidationError struct {
    Field   string
    Value   interface{}
    Message string
}

func (ve ValidationError) Error() string {
    return fmt.Sprintf("validation failed for field '%s' (value: %v): %s",
                       ve.Field, ve.Value, ve.Message)
}

// NetworkError represents network-related errors
type NetworkError struct {
    Operation string
    URL       string
    StatusCode int
    Cause     error
}

func (ne NetworkError) Error() string {
    if ne.Cause != nil {
        return fmt.Sprintf("network error during %s to %s (status %d): %v",
                          ne.Operation, ne.URL, ne.StatusCode, ne.Cause)
    }
    return fmt.Sprintf("network error during %s to %s (status %d)",
                      ne.Operation, ne.URL, ne.StatusCode)
}

// DatabaseError with error categories
type DatabaseError struct {
    Query     string
    Table     string
    Operation string
    Category  ErrorCategory
    Cause     error
}

type ErrorCategory int

const (
    ErrorCategoryConnection ErrorCategory = iota
    ErrorCategoryQuery
    ErrorCategoryConstraint
    ErrorCategoryTimeout
)

func (ec ErrorCategory) String() string {
    switch ec {
    case ErrorCategoryConnection:
        return "Connection"
    case ErrorCategoryQuery:
        return "Query"
    case ErrorCategoryConstraint:
        return "Constraint"
    case ErrorCategoryTimeout:
        return "Timeout"
    default:
        return "Unknown"
    }
}

func (de DatabaseError) Error() string {
    return fmt.Sprintf("database error [%s] during %s on table '%s': %v",
                       de.Category, de.Operation, de.Table, de.Cause)
}

func demonstrateCustomErrors() {
    fmt.Println("\n=== Custom Error Types ===")

    // Validation error
    err := validateUser("", "invalid-email", -5)
    if err != nil {
        fmt.Printf("Validation error: %v\n", err)

        // Type assertion to access specific error details
        if ve, ok := err.(ValidationError); ok {
            fmt.Printf("Failed field: %s\n", ve.Field)
            fmt.Printf("Invalid value: %v\n", ve.Value)
        }
    }

    // Network error
    netErr := NetworkError{
        Operation:  "GET",
        URL:        "https://api.example.com/users",
        StatusCode: 404,
        Cause:      errors.New("resource not found"),
    }
    fmt.Printf("Network error: %v\n", netErr)

    // Database error
    dbErr := DatabaseError{
        Query:     "INSERT INTO users (id, name) VALUES (?, ?)",
        Table:     "users",
        Operation: "INSERT",
        Category:  ErrorCategoryConstraint,
        Cause:     errors.New("duplicate key violation"),
    }
    fmt.Printf("Database error: %v\n", dbErr)
}

func validateUser(name, email string, age int) error {
    if name == "" {
        return ValidationError{
            Field:   "name",
            Value:   name,
            Message: "cannot be empty",
        }
    }

    if !isValidEmail(email) {
        return ValidationError{
            Field:   "email",
            Value:   email,
            Message: "invalid format",
        }
    }

    if age < 0 {
        return ValidationError{
            Field:   "age",
            Value:   age,
            Message: "cannot be negative",
        }
    }

    return nil
}

func isValidEmail(email string) bool {
    return len(email) > 0 && strings.Contains(email, "@")
}
```

### Error Wrapping

Go 1.13 introduced error wrapping, allowing you to add context while preserving the original error.

#### Error Wrapping and Unwrapping

```go
import (
    "errors"
    "fmt"
)

func demonstrateErrorWrapping() {
    fmt.Println("\n=== Error Wrapping ===")

    // Create a chain of wrapped errors
    err := processData("invalid-data")
    if err != nil {
        fmt.Printf("Final error: %v\n", err)

        // Unwrap errors to find root cause
        fmt.Println("\nError chain:")
        current := err
        level := 0
        for current != nil {
            fmt.Printf("Level %d: %v\n", level, current)
            current = errors.Unwrap(current)
            level++
        }

        // Check for specific error types in the chain
        var validationErr ValidationError
        if errors.As(err, &validationErr) {
            fmt.Printf("\nFound validation error: %s = %v\n",
                      validationErr.Field, validationErr.Value)
        }

        // Check if error chain contains specific error
        if errors.Is(err, ErrInvalidFormat) {
            fmt.Println("Error chain contains ErrInvalidFormat")
        }
    }
}

var (
    ErrInvalidFormat = errors.New("invalid format")
    ErrDataTooLarge  = errors.New("data too large")
    ErrProcessingFailed = errors.New("processing failed")
)

func processData(data string) error {
    // Step 1: Validate format
    if err := validateFormat(data); err != nil {
        return fmt.Errorf("data processing failed: %w", err)
    }

    // Step 2: Check size
    if err := checkSize(data); err != nil {
        return fmt.Errorf("data processing failed: %w", err)
    }

    // Step 3: Process
    if err := performProcessing(data); err != nil {
        return fmt.Errorf("data processing failed: %w", err)
    }

    return nil
}

func validateFormat(data string) error {
    if data == "invalid-data" {
        return fmt.Errorf("format validation failed: %w", ErrInvalidFormat)
    }
    return nil
}

func checkSize(data string) error {
    if len(data) > 1000 {
        return fmt.Errorf("size check failed: %w", ErrDataTooLarge)
    }
    return nil
}

func performProcessing(data string) error {
    if data == "fail-processing" {
        return ValidationError{
            Field:   "data",
            Value:   data,
            Message: "processing requirements not met",
        }
    }
    return nil
}

// Custom wrapper error type
type ProcessingError struct {
    Stage string
    Data  string
    Err   error
}

func (pe ProcessingError) Error() string {
    return fmt.Sprintf("processing error at stage '%s' with data '%s': %v",
                       pe.Stage, pe.Data, pe.Err)
}

func (pe ProcessingError) Unwrap() error {
    return pe.Err
}

func demonstrateCustomWrapper() {
    fmt.Println("\n=== Custom Error Wrapper ===")

    originalErr := ValidationError{
        Field:   "input",
        Value:   "bad-value",
        Message: "contains invalid characters",
    }

    wrappedErr := ProcessingError{
        Stage: "validation",
        Data:  "user-input",
        Err:   originalErr,
    }

    fmt.Printf("Wrapped error: %v\n", wrappedErr)

    // Unwrap to get original error
    unwrapped := errors.Unwrap(wrappedErr)
    fmt.Printf("Unwrapped error: %v\n", unwrapped)

    // Check for specific error type
    var validationErr ValidationError
    if errors.As(wrappedErr, &validationErr) {
        fmt.Printf("Found validation error in chain: field='%s', value='%v'\n",
                  validationErr.Field, validationErr.Value)
    }
}
```

### Panic and Recover

Panic and recover provide a mechanism for handling exceptional conditions.

#### Understanding Panic and Recover

```go
func demonstratePanicRecover() {
    fmt.Println("\n=== Panic and Recover ===")

    // Example 1: Basic panic and recover
    fmt.Println("1. Basic panic and recover:")
    func() {
        defer func() {
            if r := recover(); r != nil {
                fmt.Printf("Recovered from panic: %v\n", r)
            }
        }()

        fmt.Println("About to panic...")
        panic("something went wrong!")
        fmt.Println("This line won't execute")
    }()

    fmt.Println("Execution continues after recovery\n")

    // Example 2: Panic with custom type
    fmt.Println("2. Panic with custom error:")
    func() {
        defer func() {
            if r := recover(); r != nil {
                fmt.Printf("Recovered from custom panic: %v\n", r)

                // Type assertion on panic value
                if err, ok := r.(error); ok {
                    fmt.Printf("Panic was an error: %v\n", err)
                }
            }
        }()

        customErr := DatabaseError{
            Query:     "SELECT * FROM nonexistent",
            Table:     "nonexistent",
            Operation: "SELECT",
            Category:  ErrorCategoryQuery,
            Cause:     errors.New("table does not exist"),
        }

        panic(customErr)
    }()

    // Example 3: Conditional recovery
    fmt.Println("3. Conditional recovery:")
    recoverFromPanic(true)  // Will recover
    recoverFromPanic(false) // Will not recover (but we catch it)
}

func recoverFromPanic(shouldRecover bool) {
    defer func() {
        if r := recover(); r != nil {
            fmt.Printf("Caught panic: %v\n", r)
        }
    }()

    func() {
        defer func() {
            if r := recover(); r != nil && shouldRecover {
                fmt.Printf("Conditionally recovered: %v\n", r)
                return
            }
            // Re-panic if we're not supposed to recover
            if r := recover(); r != nil {
                panic(r)
            }
        }()

        fmt.Printf("Should recover: %t, panicking...\n", shouldRecover)
        panic("conditional panic")
    }()

    fmt.Printf("Function completed normally (recovered: %t)\n", shouldRecover)
}

// Practical example: Safe array access
func safeArrayAccess() {
    fmt.Println("\n=== Safe Array Access ===")

    arr := []int{1, 2, 3, 4, 5}

    // Safe access function that recovers from index panics
    getValue := func(index int) (value int, ok bool) {
        defer func() {
            if r := recover(); r != nil {
                fmt.Printf("Recovered from index panic: %v\n", r)
                value = 0
                ok = false
            }
        }()

        value = arr[index]
        ok = true
        return
    }

    // Test safe access
    indices := []int{0, 2, 4, 10, -1}
    for _, idx := range indices {
        if val, ok := getValue(idx); ok {
            fmt.Printf("arr[%d] = %d\n", idx, val)
        } else {
            fmt.Printf("arr[%d] = invalid index\n", idx)
        }
    }
}

func main() {
    demonstrateBasicErrors()
    demonstrateCustomErrors()
    demonstrateErrorWrapping()
    demonstrateCustomWrapper()
    demonstratePanicRecover()
    safeArrayAccess()
}
```

---

## Chapter 8: Packages and Modules
📊 **Progress:** Chapter 8 of 12 | ⏱️ **Estimated reading time:** 20 minutes

🎯 **Learning Objectives:**
- Understand Go's package system and organization
- Master Go modules for dependency management
- Learn import statements and package visibility
- Explore creating and publishing packages

📋 **Prerequisites:** Understanding of basic Go syntax and project structure

### Package System

Go organizes code into packages, which are collections of source files in the same directory.

#### Package Declaration and Organization

```go
// Example package structure:
// myproject/
// ├── go.mod
// ├── main.go
// ├── utils/
// │   ├── math.go
// │   └── string.go
// ├── models/
// │   ├── user.go
// │   └── product.go
// └── handlers/
//     ├── user_handler.go
//     └── product_handler.go

// File: utils/math.go
package utils

import "math"

// Exported function (public)
func Add(a, b float64) float64 {
    return a + b
}

// Exported function
func Max(a, b float64) float64 {
    if a > b {
        return a
    }
    return b
}

// unexported function (private)
func sqrt(x float64) float64 {
    return math.Sqrt(x)
}

// Exported function using private function
func Distance(x1, y1, x2, y2 float64) float64 {
    dx := x2 - x1
    dy := y2 - y1
    return sqrt(dx*dx + dy*dy)
}

// File: utils/string.go
package utils

import (
    "strings"
    "unicode"
)

// Exported function
func Capitalize(s string) string {
    if s == "" {
        return s
    }
    runes := []rune(s)
    runes[0] = unicode.ToUpper(runes[0])
    return string(runes)
}

// Exported function
func IsEmpty(s string) bool {
    return strings.TrimSpace(s) == ""
}

// File: models/user.go
package models

import (
    "fmt"
    "time"
)

// Exported type
type User struct {
    ID       int       `json:"id"`
    Username string    `json:"username"`
    Email    string    `json:"email"`
    Created  time.Time `json:"created"`
}

// Exported method
func (u User) String() string {
    return fmt.Sprintf("User{ID: %d, Username: %s, Email: %s}",
                       u.ID, u.Username, u.Email)
}

// Exported function
func NewUser(username, email string) User {
    return User{
        Username: username,
        Email:    email,
        Created:  time.Now(),
    }
}

// File: main.go
package main

import (
    "fmt"
    "myproject/models"
    "myproject/utils"
)

func main() {
    // Using functions from utils package
    result := utils.Add(10, 20)
    fmt.Printf("10 + 20 = %.2f\n", result)

    distance := utils.Distance(0, 0, 3, 4)
    fmt.Printf("Distance: %.2f\n", distance)

    // Using string utilities
    name := utils.Capitalize("alice")
    fmt.Printf("Capitalized: %s\n", name)

    // Using models package
    user := models.NewUser("alice", "alice@example.com")
    fmt.Printf("User: %s\n", user)
}
```

### Go Modules

Go modules are the dependency management system introduced in Go 1.11.

#### Creating and Managing Modules

```go
// Initialize a new module
// $ go mod init github.com/username/myproject

// go.mod file content:
module github.com/username/myproject

go 1.25

require (
    github.com/gorilla/mux v1.8.0
    golang.org/x/time v0.3.0
)

require (
    github.com/gorilla/handlers v1.5.1 // indirect
)

// Working with dependencies
// Add dependency: go get github.com/gorilla/mux
// Update all: go get -u ./...
// Tidy modules: go mod tidy
// Vendor dependencies: go mod vendor

// Example using external dependencies
package main

import (
    "encoding/json"
    "log"
    "net/http"

    "github.com/gorilla/mux"
    "golang.org/x/time/rate"
)

type Server struct {
    router  *mux.Router
    limiter *rate.Limiter
}

func NewServer() *Server {
    s := &Server{
        router:  mux.NewRouter(),
        limiter: rate.NewLimiter(rate.Limit(10), 1), // 10 requests per second
    }
    s.setupRoutes()
    return s
}

func (s *Server) setupRoutes() {
    s.router.HandleFunc("/api/health", s.healthHandler).Methods("GET")
    s.router.HandleFunc("/api/users", s.usersHandler).Methods("GET")
}

func (s *Server) healthHandler(w http.ResponseWriter, r *http.Request) {
    if !s.limiter.Allow() {
        http.Error(w, "Rate limit exceeded", http.StatusTooManyRequests)
        return
    }

    response := map[string]string{
        "status": "healthy",
        "timestamp": time.Now().Format(time.RFC3339),
    }

    w.Header().Set("Content-Type", "application/json")
    json.NewEncoder(w).Encode(response)
}

func (s *Server) usersHandler(w http.ResponseWriter, r *http.Request) {
    users := []map[string]interface{}{
        {"id": 1, "name": "Alice", "email": "alice@example.com"},
        {"id": 2, "name": "Bob", "email": "bob@example.com"},
    }

    w.Header().Set("Content-Type", "application/json")
    json.NewEncoder(w).Encode(users)
}
```

### Import Statements

Go provides several ways to import packages with different behaviors.

#### Import Patterns and Aliases

```go
package main

import (
    // Standard import
    "fmt"
    "net/http"

    // Import with alias
    j "encoding/json"

    // Import for side effects only
    _ "net/http/pprof"

    // Dot import (import into current namespace)
    . "math"

    // Local package imports
    "myproject/models"
    "myproject/utils"

    // Remote package imports
    "github.com/gorilla/mux"
    "golang.org/x/sync/errgroup"
)

func demonstrateImports() {
    // Standard import usage
    fmt.Println("Standard import")

    // Aliased import usage
    data := map[string]string{"message": "hello"}
    jsonData, _ := j.Marshal(data) // Using 'j' alias for json
    fmt.Printf("JSON: %s\n", jsonData)

    // Dot import usage (math functions available directly)
    result := Sqrt(16) // No need for math.Sqrt
    fmt.Printf("Square root of 16: %.2f\n", result)

    // Local package usage
    user := models.NewUser("testuser", "test@example.com")
    fmt.Printf("Created user: %s\n", user)

    sum := utils.Add(10, 20)
    fmt.Printf("Sum: %.2f\n", sum)
}

// Package-level variables and initialization
var (
    // Package-level variables are initialized before main()
    ServerPort = getEnvOrDefault("PORT", "8080")
    Debug      = getEnvOrDefault("DEBUG", "false") == "true"
)

func init() {
    // init() functions run before main()
    // Multiple init() functions can exist and run in order
    fmt.Println("Package initialization")

    if Debug {
        fmt.Println("Debug mode enabled")
    }
}

func getEnvOrDefault(key, defaultValue string) string {
    // Simplified environment variable getter
    // In real code, use os.Getenv()
    return defaultValue
}
```

### Creating and Publishing Packages

#### Package Design Best Practices

```go
// File: calculator/calculator.go
// Package calculator provides mathematical calculation utilities
package calculator

import (
    "errors"
    "math"
)

// Common errors
var (
    ErrDivisionByZero = errors.New("division by zero")
    ErrNegativeSquareRoot = errors.New("square root of negative number")
    ErrInvalidInput = errors.New("invalid input")
)

// Calculator represents a mathematical calculator
type Calculator struct {
    precision int
    memory    float64
}

// New creates a new Calculator with specified precision
func New(precision int) *Calculator {
    if precision < 0 {
        precision = 2 // default precision
    }
    return &Calculator{
        precision: precision,
    }
}

// Add performs addition
func (c *Calculator) Add(a, b float64) float64 {
    result := a + b
    c.memory = result
    return c.roundToPrecision(result)
}

// Divide performs division with error handling
func (c *Calculator) Divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, ErrDivisionByZero
    }
    result := a / b
    c.memory = result
    return c.roundToPrecision(result), nil
}

// SquareRoot calculates square root
func (c *Calculator) SquareRoot(x float64) (float64, error) {
    if x < 0 {
        return 0, ErrNegativeSquareRoot
    }
    result := math.Sqrt(x)
    c.memory = result
    return c.roundToPrecision(result), nil
}

// Memory returns the last calculated result
func (c *Calculator) Memory() float64 {
    return c.memory
}

// ClearMemory resets the memory
func (c *Calculator) ClearMemory() {
    c.memory = 0
}

// SetPrecision updates the precision
func (c *Calculator) SetPrecision(precision int) {
    if precision >= 0 {
        c.precision = precision
    }
}

// roundToPrecision rounds to the specified precision
func (c *Calculator) roundToPrecision(value float64) float64 {
    multiplier := math.Pow(10, float64(c.precision))
    return math.Round(value*multiplier) / multiplier
}

// Package-level convenience functions

// QuickAdd provides a simple addition function
func QuickAdd(values ...float64) float64 {
    var sum float64
    for _, v := range values {
        sum += v
    }
    return sum
}

// QuickDivide provides simple division with error handling
func QuickDivide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, ErrDivisionByZero
    }
    return a / b, nil
}

// File: calculator/examples_test.go
package calculator_test

import (
    "fmt"
    "log"

    "myproject/calculator"
)

func ExampleCalculator_Add() {
    calc := calculator.New(2)
    result := calc.Add(10.5, 20.3)
    fmt.Printf("%.2f", result)
    // Output: 30.80
}

func ExampleCalculator_Divide() {
    calc := calculator.New(2)
    result, err := calc.Divide(10, 3)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Printf("%.2f", result)
    // Output: 3.33
}

func ExampleQuickAdd() {
    result := calculator.QuickAdd(1, 2, 3, 4, 5)
    fmt.Printf("%.0f", result)
    // Output: 15
}

// File: main.go demonstrating package usage
package main

import (
    "fmt"
    "log"

    "myproject/calculator"
)

func demonstratePackageUsage() {
    fmt.Println("=== Calculator Package Demo ===")

    // Create calculator instance
    calc := calculator.New(3)

    // Basic operations
    sum := calc.Add(10.5, 20.75)
    fmt.Printf("Addition: %.3f\n", sum)

    // Error handling
    result, err := calc.Divide(100, 3)
    if err != nil {
        log.Printf("Division error: %v", err)
    } else {
        fmt.Printf("Division: %.3f\n", result)
    }

    // Error case
    _, err = calc.Divide(10, 0)
    if err == calculator.ErrDivisionByZero {
        fmt.Println("Caught division by zero error")
    }

    // Using memory
    fmt.Printf("Last result in memory: %.3f\n", calc.Memory())

    // Package-level functions
    quickSum := calculator.QuickAdd(1, 2, 3, 4, 5)
    fmt.Printf("Quick sum: %.0f\n", quickSum)
}
```

---

## Chapter 9: Concurrency
📊 **Progress:** Chapter 9 of 12 | ⏱️ **Estimated reading time:** 35 minutes

🎯 **Learning Objectives:**
- Master goroutines for concurrent programming
- Understand channels for communication between goroutines
- Learn the select statement for channel operations
- Explore synchronization primitives and the context package

📋 **Prerequisites:** Understanding of functions, interfaces, and error handling

### Goroutines

Goroutines are lightweight threads managed by the Go runtime.

#### Basic Goroutines

```go
package main

import (
    "fmt"
    "runtime"
    "sync"
    "time"
)

func demonstrateBasicGoroutines() {
    fmt.Println("=== Basic Goroutines ===")

    // Anonymous goroutine
    go func() {
        for i := 0; i < 5; i++ {
            fmt.Printf("Goroutine 1: %d\n", i)
            time.Sleep(100 * time.Millisecond)
        }
    }()

    // Named function as goroutine
    go worker("Worker-A")
    go worker("Worker-B")

    // Main goroutine continues
    for i := 0; i < 3; i++ {
        fmt.Printf("Main: %d\n", i)
        time.Sleep(150 * time.Millisecond)
    }

    // Wait a bit for goroutines to finish
    time.Sleep(1 * time.Second)
    fmt.Printf("Active goroutines: %d\n", runtime.NumGoroutine())
}

func worker(name string) {
    for i := 0; i < 3; i++ {
        fmt.Printf("%s: working on task %d\n", name, i+1)
        time.Sleep(200 * time.Millisecond)
    }
    fmt.Printf("%s: finished\n", name)
}

// WaitGroup for synchronization
func demonstrateWaitGroup() {
    fmt.Println("\n=== WaitGroup Synchronization ===")

    var wg sync.WaitGroup

    // Start multiple goroutines
    for i := 1; i <= 3; i++ {
        wg.Add(1) // Increment counter
        go func(id int) {
            defer wg.Done() // Decrement counter when done

            fmt.Printf("Worker %d starting\n", id)
            time.Sleep(time.Duration(id) * 200 * time.Millisecond)
            fmt.Printf("Worker %d completed\n", id)
        }(i)
    }

    fmt.Println("Waiting for all workers to complete...")
    wg.Wait() // Block until counter becomes 0
    fmt.Println("All workers completed!")
}
```

### Channels

Channels provide a way for goroutines to communicate and synchronize.

#### Channel Basics

```go
func demonstrateBasicChannels() {
    fmt.Println("\n=== Basic Channels ===")

    // Unbuffered channel
    ch := make(chan string)

    // Send data in a goroutine
    go func() {
        time.Sleep(500 * time.Millisecond)
        ch <- "Hello from goroutine!"
    }()

    // Receive data (blocks until data is available)
    message := <-ch
    fmt.Printf("Received: %s\n", message)

    // Buffered channel
    buffered := make(chan int, 3)
    buffered <- 1
    buffered <- 2
    buffered <- 3

    fmt.Printf("Buffered channel length: %d, capacity: %d\n",
               len(buffered), cap(buffered))

    // Receive all values
    for i := 0; i < 3; i++ {
        value := <-buffered
        fmt.Printf("Received from buffered: %d\n", value)
    }
}

func demonstrateChannelDirection() {
    fmt.Println("\n=== Channel Direction ===")

    ch := make(chan int)

    // Send-only channel function
    go sender(ch)

    // Receive-only channel function
    receiver(ch)
}

// Send-only channel parameter
func sender(ch chan<- int) {
    for i := 1; i <= 5; i++ {
        fmt.Printf("Sending: %d\n", i)
        ch <- i
        time.Sleep(200 * time.Millisecond)
    }
    close(ch)
}

// Receive-only channel parameter
func receiver(ch <-chan int) {
    for {
        value, ok := <-ch
        if !ok {
            fmt.Println("Channel closed, receiver stopping")
            break
        }
        fmt.Printf("Received: %d\n", value)
    }
}

// Channel range and closing
func demonstrateChannelRange() {
    fmt.Println("\n=== Channel Range and Closing ===")

    numbers := make(chan int)

    // Producer goroutine
    go func() {
        for i := 1; i <= 5; i++ {
            numbers <- i
        }
        close(numbers) // Important: close channel when done
    }()

    // Consumer using range (automatically stops when channel is closed)
    fmt.Println("Reading with range:")
    for num := range numbers {
        fmt.Printf("Got: %d\n", num)
    }

    fmt.Println("Range loop completed")
}
```

### Select Statement

The select statement lets a goroutine wait on multiple channel operations.

#### Basic Select Usage

```go
func demonstrateSelect() {
    fmt.Println("\n=== Select Statement ===")

    ch1 := make(chan string)
    ch2 := make(chan string)

    // Two goroutines sending at different times
    go func() {
        time.Sleep(1 * time.Second)
        ch1 <- "Message from channel 1"
    }()

    go func() {
        time.Sleep(500 * time.Millisecond)
        ch2 <- "Message from channel 2"
    }()

    // Select waits for the first available channel
    for i := 0; i < 2; i++ {
        select {
        case msg1 := <-ch1:
            fmt.Printf("Received from ch1: %s\n", msg1)
        case msg2 := <-ch2:
            fmt.Printf("Received from ch2: %s\n", msg2)
        }
    }
}

func demonstrateSelectWithDefault() {
    fmt.Println("\n=== Select with Default ===")

    ch := make(chan int, 1)

    // Non-blocking send
    select {
    case ch <- 42:
        fmt.Println("Sent 42 to channel")
    default:
        fmt.Println("Channel full, couldn't send")
    }

    // Non-blocking receive
    select {
    case value := <-ch:
        fmt.Printf("Received: %d\n", value)
    default:
        fmt.Println("No data available")
    }

    // Second receive attempt
    select {
    case value := <-ch:
        fmt.Printf("Received: %d\n", value)
    default:
        fmt.Println("No data available on second attempt")
    }
}

// Timeout pattern with select
func demonstrateTimeout() {
    fmt.Println("\n=== Timeout Pattern ===")

    ch := make(chan string)

    // Simulate slow operation
    go func() {
        time.Sleep(2 * time.Second)
        ch <- "Slow operation completed"
    }()

    // Wait with timeout
    select {
    case result := <-ch:
        fmt.Printf("Operation result: %s\n", result)
    case <-time.After(1 * time.Second):
        fmt.Println("Operation timed out")
    }
}

// Fan-in pattern: multiple sources, one destination
func demonstrateFanIn() {
    fmt.Println("\n=== Fan-in Pattern ===")

    // Create input channels
    input1 := make(chan string)
    input2 := make(chan string)

    // Start producers
    go func() {
        for i := 0; i < 3; i++ {
            input1 <- fmt.Sprintf("Producer 1 - Message %d", i+1)
            time.Sleep(500 * time.Millisecond)
        }
        close(input1)
    }()

    go func() {
        for i := 0; i < 3; i++ {
            input2 <- fmt.Sprintf("Producer 2 - Message %d", i+1)
            time.Sleep(700 * time.Millisecond)
        }
        close(input2)
    }()

    // Fan-in: merge both channels
    output := fanIn(input1, input2)

    // Consume merged output
    for message := range output {
        fmt.Printf("Merged: %s\n", message)
    }
}

func fanIn(ch1, ch2 <-chan string) <-chan string {
    output := make(chan string)

    go func() {
        defer close(output)

        for {
            select {
            case msg, ok := <-ch1:
                if !ok {
                    ch1 = nil // Disable this case
                } else {
                    output <- msg
                }
            case msg, ok := <-ch2:
                if !ok {
                    ch2 = nil // Disable this case
                } else {
                    output <- msg
                }
            }

            // Both channels closed
            if ch1 == nil && ch2 == nil {
                break
            }
        }
    }()

    return output
}
```

### Synchronization Primitives

Go provides several synchronization primitives beyond channels.

#### Mutex and RWMutex

```go
import (
    "fmt"
    "sync"
    "time"
)

// Thread-safe counter using mutex
type SafeCounter struct {
    mu    sync.Mutex
    value int
}

func (c *SafeCounter) Increment() {
    c.mu.Lock()
    defer c.mu.Unlock()
    c.value++
}

func (c *SafeCounter) Value() int {
    c.mu.Lock()
    defer c.mu.Unlock()
    return c.value
}

// Thread-safe cache using RWMutex
type SafeCache struct {
    mu   sync.RWMutex
    data map[string]string
}

func NewSafeCache() *SafeCache {
    return &SafeCache{
        data: make(map[string]string),
    }
}

func (c *SafeCache) Set(key, value string) {
    c.mu.Lock()
    defer c.mu.Unlock()
    c.data[key] = value
}

func (c *SafeCache) Get(key string) (string, bool) {
    c.mu.RLock() // Read lock allows multiple readers
    defer c.mu.RUnlock()
    value, ok := c.data[key]
    return value, ok
}

func demonstrateMutex() {
    fmt.Println("\n=== Mutex Synchronization ===")

    counter := &SafeCounter{}
    var wg sync.WaitGroup

    // Start multiple goroutines incrementing counter
    for i := 0; i < 10; i++ {
        wg.Add(1)
        go func(id int) {
            defer wg.Done()
            for j := 0; j < 100; j++ {
                counter.Increment()
            }
            fmt.Printf("Goroutine %d completed\n", id)
        }(i)
    }

    wg.Wait()
    fmt.Printf("Final counter value: %d\n", counter.Value())

    // Demonstrate cache
    cache := NewSafeCache()

    // Concurrent writes
    go func() {
        for i := 0; i < 5; i++ {
            key := fmt.Sprintf("key%d", i)
            value := fmt.Sprintf("value%d", i)
            cache.Set(key, value)
            time.Sleep(100 * time.Millisecond)
        }
    }()

    // Concurrent reads
    time.Sleep(50 * time.Millisecond) // Let some writes happen
    for i := 0; i < 10; i++ {
        go func(id int) {
            key := fmt.Sprintf("key%d", id%5)
            if value, ok := cache.Get(key); ok {
                fmt.Printf("Read %s: %s\n", key, value)
            } else {
                fmt.Printf("Key %s not found\n", key)
            }
        }(i)
    }

    time.Sleep(1 * time.Second)
}
```

### Context Package

The context package provides a way to carry deadlines, cancellation signals, and other request-scoped values.

#### Context Usage

```go
import (
    "context"
    "fmt"
    "time"
)

func demonstrateContext() {
    fmt.Println("\n=== Context Package ===")

    // Basic context with timeout
    ctx, cancel := context.WithTimeout(context.Background(), 2*time.Second)
    defer cancel()

    // Simulate work that respects context
    err := doWork(ctx, "Task 1", 1*time.Second)
    if err != nil {
        fmt.Printf("Task 1 error: %v\n", err)
    }

    // This will timeout
    err = doWork(ctx, "Task 2", 3*time.Second)
    if err != nil {
        fmt.Printf("Task 2 error: %v\n", err)
    }

    // Context with cancellation
    fmt.Println("\nContext cancellation:")
    ctx2, cancel2 := context.WithCancel(context.Background())

    go func() {
        time.Sleep(1 * time.Second)
        fmt.Println("Cancelling context...")
        cancel2()
    }()

    err = doWork(ctx2, "Cancellable Task", 2*time.Second)
    if err != nil {
        fmt.Printf("Cancellable task error: %v\n", err)
    }
}

func doWork(ctx context.Context, name string, duration time.Duration) error {
    fmt.Printf("Starting %s (duration: %v)\n", name, duration)

    select {
    case <-time.After(duration):
        fmt.Printf("%s completed successfully\n", name)
        return nil
    case <-ctx.Done():
        fmt.Printf("%s cancelled: %v\n", name, ctx.Err())
        return ctx.Err()
    }
}

// Context with values
func demonstrateContextValues() {
    fmt.Println("\n=== Context Values ===")

    // Create context with values
    ctx := context.Background()
    ctx = context.WithValue(ctx, "userID", "12345")
    ctx = context.WithValue(ctx, "requestID", "req-abcdef")

    // Pass context through function calls
    processRequest(ctx)
}

func processRequest(ctx context.Context) {
    userID, ok := ctx.Value("userID").(string)
    if !ok {
        fmt.Println("No user ID in context")
        return
    }

    requestID, ok := ctx.Value("requestID").(string)
    if !ok {
        fmt.Println("No request ID in context")
        return
    }

    fmt.Printf("Processing request %s for user %s\n", requestID, userID)

    // Simulate database operation
    fetchUserData(ctx, userID)
}

func fetchUserData(ctx context.Context, userID string) {
    fmt.Printf("Fetching data for user: %s\n", userID)

    // Context can be passed to other operations
    select {
    case <-time.After(500 * time.Millisecond):
        fmt.Println("User data fetched successfully")
    case <-ctx.Done():
        fmt.Printf("Fetch cancelled: %v\n", ctx.Err())
    }
}

func main() {
    demonstrateBasicGoroutines()
    demonstrateWaitGroup()
    demonstrateBasicChannels()
    demonstrateChannelDirection()
    demonstrateChannelRange()
    demonstrateSelect()
    demonstrateSelectWithDefault()
    demonstrateTimeout()
    demonstrateFanIn()
    demonstrateMutex()
    demonstrateContext()
    demonstrateContextValues()
}
```

---

## Chapter 10: Advanced Topics
📊 **Progress:** Chapter 10 of 12 | ⏱️ **Estimated reading time:** 40 minutes

🎯 **Learning Objectives:**
- Master reflection for runtime type inspection and manipulation
- Understand Go generics and type parameters
- Learn embedding and composition patterns
- Explore build tags and conditional compilation
- Understand CGO and interfacing with C code

📋 **Prerequisites:** Understanding of interfaces, methods, packages, and concurrency

### Reflection

Reflection allows a program to examine its own structure at runtime. Go's `reflect` package provides this capability.

#### Basic Reflection Operations

```go
package main

import (
    "fmt"
    "reflect"
    "time"
)

func demonstrateBasicReflection() {
    fmt.Println("=== Basic Reflection ===")

    // Reflect on basic types
    values := []interface{}{
        42,
        "hello world",
        3.14159,
        true,
        time.Now(),
        []int{1, 2, 3},
        map[string]int{"key": 100},
    }

    for i, value := range values {
        t := reflect.TypeOf(value)
        v := reflect.ValueOf(value)

        fmt.Printf("Value %d:\n", i+1)
        fmt.Printf("  Type: %v\n", t)
        fmt.Printf("  Kind: %v\n", t.Kind())
        fmt.Printf("  Value: %v\n", v.Interface())
        fmt.Printf("  String representation: %s\n", v.String())

        // Type-specific information
        switch t.Kind() {
        case reflect.Slice:
            fmt.Printf("  Slice length: %d\n", v.Len())
            if v.Len() > 0 {
                fmt.Printf("  Element type: %v\n", t.Elem())
            }
        case reflect.Map:
            fmt.Printf("  Map length: %d\n", v.Len())
            fmt.Printf("  Key type: %v\n", t.Key())
            fmt.Printf("  Value type: %v\n", t.Elem())
        case reflect.String:
            fmt.Printf("  String length: %d\n", v.Len())
        }
        fmt.Println()
    }
}

// Struct for reflection examples
type Person struct {
    Name     string    `json:"name" validate:"required"`
    Age      int       `json:"age" validate:"min=0,max=150"`
    Email    string    `json:"email" validate:"email"`
    IsActive bool      `json:"is_active"`
    Tags     []string  `json:"tags,omitempty"`
    metadata map[string]interface{} // unexported field
}

func (p Person) GetFullInfo() string {
    return fmt.Sprintf("%s (%d years old) - %s", p.Name, p.Age, p.Email)
}

func (p *Person) SetEmail(email string) {
    p.Email = email
}

func (p Person) IsAdult() bool {
    return p.Age >= 18
}

func demonstrateStructReflection() {
    fmt.Println("\n=== Struct Reflection ===")

    person := Person{
        Name:     "Alice Johnson",
        Age:      30,
        Email:    "alice@example.com",
        IsActive: true,
        Tags:     []string{"developer", "golang"},
    }

    t := reflect.TypeOf(person)
    v := reflect.ValueOf(person)

    fmt.Printf("Struct: %s\n", t.Name())
    fmt.Printf("Package: %s\n", t.PkgPath())
    fmt.Printf("Number of fields: %d\n", t.NumField())

    // Iterate through struct fields
    fmt.Println("\nFields:")
    for i := 0; i < t.NumField(); i++ {
        field := t.Field(i)
        value := v.Field(i)

        fmt.Printf("  Field %d: %s\n", i, field.Name)
        fmt.Printf("    Type: %v\n", field.Type)
        fmt.Printf("    Tag: %s\n", field.Tag)

        // Parse specific tags
        if jsonTag := field.Tag.Get("json"); jsonTag != "" {
            fmt.Printf("    JSON tag: %s\n", jsonTag)
        }
        if validateTag := field.Tag.Get("validate"); validateTag != "" {
            fmt.Printf("    Validation: %s\n", validateTag)
        }

        // Check if field is exported
        if field.IsExported() {
            fmt.Printf("    Value: %v\n", value.Interface())
        } else {
            fmt.Printf("    Value: <unexported>\n")
        }
        fmt.Println()
    }

    // Method reflection
    fmt.Printf("Number of methods: %d\n", t.NumMethod())
    fmt.Println("Methods:")
    for i := 0; i < t.NumMethod(); i++ {
        method := t.Method(i)
        fmt.Printf("  Method %d: %s\n", i, method.Name)
        fmt.Printf("    Type: %v\n", method.Type)
        fmt.Printf("    Input types: %d\n", method.Type.NumIn())
        fmt.Printf("    Output types: %d\n", method.Type.NumOut())

        // Call method if it has no parameters (besides receiver)
        if method.Type.NumIn() == 1 && method.Type.NumOut() > 0 {
            results := v.Method(i).Call([]reflect.Value{})
            fmt.Printf("    Result: %v\n", results[0].Interface())
        }
        fmt.Println()
    }
}

func demonstrateReflectionModification() {
    fmt.Println("\n=== Reflection Modification ===")

    person := Person{
        Name:  "Bob Smith",
        Age:   25,
        Email: "bob@example.com",
    }

    fmt.Printf("Original: %+v\n", person)

    // Get addressable reflect value
    v := reflect.ValueOf(&person).Elem()

    // Modify fields by name
    nameField := v.FieldByName("Name")
    if nameField.IsValid() && nameField.CanSet() {
        nameField.SetString("Robert Smith")
    }

    ageField := v.FieldByName("Age")
    if ageField.IsValid() && ageField.CanSet() {
        ageField.SetInt(26)
    }

    // Modify using field index
    emailField := v.Field(2) // Email is the 3rd field (index 2)
    if emailField.IsValid() && emailField.CanSet() {
        emailField.SetString("robert@example.com")
    }

    fmt.Printf("Modified: %+v\n", person)

    // Call method with parameters using reflection
    ptrValue := reflect.ValueOf(&person)
    setEmailMethod := ptrValue.MethodByName("SetEmail")
    if setEmailMethod.IsValid() {
        args := []reflect.Value{reflect.ValueOf("robert.smith@newdomain.com")}
        setEmailMethod.Call(args)
    }

    fmt.Printf("After method call: %+v\n", person)
}

// Generic function using reflection
func deepCopy(src interface{}) interface{} {
    srcValue := reflect.ValueOf(src)

    // Handle pointers
    if srcValue.Kind() == reflect.Ptr {
        srcValue = srcValue.Elem()
    }

    // Create new instance of the same type
    dstValue := reflect.New(srcValue.Type()).Elem()

    copyValue(dstValue, srcValue)

    return dstValue.Interface()
}

func copyValue(dst, src reflect.Value) {
    switch src.Kind() {
    case reflect.Struct:
        for i := 0; i < src.NumField(); i++ {
            srcField := src.Field(i)
            dstField := dst.Field(i)

            if dstField.CanSet() {
                copyValue(dstField, srcField)
            }
        }
    case reflect.Slice:
        if !src.IsNil() {
            dst.Set(reflect.MakeSlice(src.Type(), src.Len(), src.Cap()))
            for i := 0; i < src.Len(); i++ {
                copyValue(dst.Index(i), src.Index(i))
            }
        }
    case reflect.Map:
        if !src.IsNil() {
            dst.Set(reflect.MakeMap(src.Type()))
            for _, key := range src.MapKeys() {
                srcVal := src.MapIndex(key)
                dstVal := reflect.New(srcVal.Type()).Elem()
                copyValue(dstVal, srcVal)
                dst.SetMapIndex(key, dstVal)
            }
        }
    default:
        dst.Set(src)
    }
}

func demonstrateDeepCopy() {
    fmt.Println("\n=== Deep Copy with Reflection ===")

    original := Person{
        Name:     "Original Person",
        Age:      30,
        Email:    "original@example.com",
        IsActive: true,
        Tags:     []string{"tag1", "tag2"},
    }

    // Create deep copy
    copied := deepCopy(original).(Person)

    fmt.Printf("Original: %+v\n", original)
    fmt.Printf("Copied: %+v\n", copied)

    // Modify original to show they're independent
    original.Name = "Modified Original"
    original.Tags[0] = "modified-tag"

    fmt.Printf("After modification:\n")
    fmt.Printf("Original: %+v\n", original)
    fmt.Printf("Copied: %+v\n", copied)
}
```

### Generics

Go 1.18 introduced generics, allowing you to write functions and types that work with multiple types.

#### Basic Generic Functions and Types

```go
import (
    "fmt"
    "constraints"
)

// Generic function with type parameter
func Max[T constraints.Ordered](a, b T) T {
    if a > b {
        return a
    }
    return b
}

// Generic function with multiple type parameters
func Map[T any, R any](slice []T, fn func(T) R) []R {
    result := make([]R, len(slice))
    for i, v := range slice {
        result[i] = fn(v)
    }
    return result
}

// Generic function with type constraint
func Sum[T constraints.Signed | constraints.Unsigned | constraints.Float](values []T) T {
    var sum T
    for _, v := range values {
        sum += v
    }
    return sum
}

// Generic stack type
type Stack[T any] struct {
    items []T
}

func NewStack[T any]() *Stack[T] {
    return &Stack[T]{
        items: make([]T, 0),
    }
}

func (s *Stack[T]) Push(item T) {
    s.items = append(s.items, item)
}

func (s *Stack[T]) Pop() (T, bool) {
    if len(s.items) == 0 {
        var zero T
        return zero, false
    }

    index := len(s.items) - 1
    item := s.items[index]
    s.items = s.items[:index]
    return item, true
}

func (s *Stack[T]) Peek() (T, bool) {
    if len(s.items) == 0 {
        var zero T
        return zero, false
    }
    return s.items[len(s.items)-1], true
}

func (s *Stack[T]) Size() int {
    return len(s.items)
}

func (s *Stack[T]) IsEmpty() bool {
    return len(s.items) == 0
}

// Generic map with custom key constraint
type Hashable interface {
    comparable
}

type SafeMap[K Hashable, V any] struct {
    mu   sync.RWMutex
    data map[K]V
}

func NewSafeMap[K Hashable, V any]() *SafeMap[K, V] {
    return &SafeMap[K, V]{
        data: make(map[K]V),
    }
}

func (sm *SafeMap[K, V]) Set(key K, value V) {
    sm.mu.Lock()
    defer sm.mu.Unlock()
    sm.data[key] = value
}

func (sm *SafeMap[K, V]) Get(key K) (V, bool) {
    sm.mu.RLock()
    defer sm.mu.RUnlock()
    value, ok := sm.data[key]
    return value, ok
}

func (sm *SafeMap[K, V]) Delete(key K) {
    sm.mu.Lock()
    defer sm.mu.Unlock()
    delete(sm.data, key)
}

func (sm *SafeMap[K, V]) Keys() []K {
    sm.mu.RLock()
    defer sm.mu.RUnlock()

    keys := make([]K, 0, len(sm.data))
    for k := range sm.data {
        keys = append(keys, k)
    }
    return keys
}

func demonstrateGenerics() {
    fmt.Println("\n=== Generics ===")

    // Generic functions
    fmt.Printf("Max of ints: %d\n", Max(10, 20))
    fmt.Printf("Max of floats: %.2f\n", Max(3.14, 2.71))
    fmt.Printf("Max of strings: %s\n", Max("apple", "banana"))

    // Generic Map function
    numbers := []int{1, 2, 3, 4, 5}
    doubled := Map(numbers, func(x int) int { return x * 2 })
    fmt.Printf("Original: %v, Doubled: %v\n", numbers, doubled)

    strings := []string{"hello", "world", "golang"}
    lengths := Map(strings, func(s string) int { return len(s) })
    fmt.Printf("Strings: %v, Lengths: %v\n", strings, lengths)

    // Generic Sum function
    intSum := Sum([]int{1, 2, 3, 4, 5})
    floatSum := Sum([]float64{1.1, 2.2, 3.3})
    fmt.Printf("Int sum: %d, Float sum: %.1f\n", intSum, floatSum)

    // Generic Stack
    intStack := NewStack[int]()
    intStack.Push(10)
    intStack.Push(20)
    intStack.Push(30)

    fmt.Printf("Stack size: %d\n", intStack.Size())

    for !intStack.IsEmpty() {
        if value, ok := intStack.Pop(); ok {
            fmt.Printf("Popped: %d\n", value)
        }
    }

    // String stack
    stringStack := NewStack[string]()
    stringStack.Push("first")
    stringStack.Push("second")

    if value, ok := stringStack.Peek(); ok {
        fmt.Printf("Top of string stack: %s\n", value)
    }

    // Generic map
    userMap := NewSafeMap[string, Person]()
    userMap.Set("alice", Person{Name: "Alice", Age: 30})
    userMap.Set("bob", Person{Name: "Bob", Age: 25})

    if user, ok := userMap.Get("alice"); ok {
        fmt.Printf("Found user: %s\n", user.Name)
    }

    keys := userMap.Keys()
    fmt.Printf("User keys: %v\n", keys)
}

// Custom constraint interface
type Numeric interface {
    constraints.Integer | constraints.Float
}

// Generic function with custom constraint
func Average[T Numeric](values []T) float64 {
    if len(values) == 0 {
        return 0
    }

    sum := Sum(values)
    return float64(sum) / float64(len(values))
}

// Type inference example
func demonstrateTypeInference() {
    fmt.Println("\n=== Type Inference ===")

    // Type inference in function calls
    result1 := Max(10, 20)        // T inferred as int
    result2 := Max(3.14, 2.71)    // T inferred as float64

    fmt.Printf("Inferred int max: %d\n", result1)
    fmt.Printf("Inferred float max: %.2f\n", result2)

    // Type inference with slices
    numbers := []int{1, 2, 3, 4, 5}
    avg := Average(numbers) // T inferred as int
    fmt.Printf("Average: %.2f\n", avg)

    floats := []float64{1.1, 2.2, 3.3, 4.4}
    avgFloat := Average(floats) // T inferred as float64
    fmt.Printf("Float average: %.2f\n", avgFloat)
}
```

### Embedding

Go supports embedding types within other types, providing a form of composition.

#### Struct Embedding

```go
// Base types for embedding
type Person struct {
    Name  string
    Age   int
    Email string
}

func (p Person) Introduce() string {
    return fmt.Sprintf("Hi, I'm %s, %d years old", p.Name, p.Age)
}

func (p *Person) SetEmail(email string) {
    p.Email = email
}

// Employee embeds Person
type Employee struct {
    Person          // Embedded field
    EmployeeID      string
    Department      string
    Salary          float64
    Manager         *Employee
}

func (e Employee) Work() string {
    return fmt.Sprintf("%s is working in %s department", e.Name, e.Department)
}

func (e Employee) GetSalaryInfo() string {
    return fmt.Sprintf("Employee %s earns $%.2f", e.Name, e.Salary)
}

// Manager embeds Employee
type Manager struct {
    Employee        // Embedded field
    TeamSize        int
    Budget          float64
    DirectReports   []Employee
}

func (m Manager) ManageTeam() string {
    return fmt.Sprintf("Manager %s manages %d people with budget $%.2f",
                       m.Name, m.TeamSize, m.Budget)
}

func (m *Manager) AddDirectReport(emp Employee) {
    emp.Manager = &m.Employee
    m.DirectReports = append(m.DirectReports, emp)
    m.TeamSize = len(m.DirectReports)
}

func demonstrateStructEmbedding() {
    fmt.Println("\n=== Struct Embedding ===")

    // Create manager
    manager := Manager{
        Employee: Employee{
            Person: Person{
                Name:  "Alice Johnson",
                Age:   35,
                Email: "alice@company.com",
            },
            EmployeeID: "MGR001",
            Department: "Engineering",
            Salary:     120000,
        },
        TeamSize: 0,
        Budget:   500000,
    }

    // Access embedded methods directly
    fmt.Println(manager.Introduce())          // From Person
    fmt.Println(manager.Work())               // From Employee
    fmt.Println(manager.ManageTeam())         // From Manager
    fmt.Println(manager.GetSalaryInfo())      // From Employee

    // Access embedded fields directly
    fmt.Printf("Manager name: %s\n", manager.Name)           // From Person
    fmt.Printf("Manager ID: %s\n", manager.EmployeeID)       // From Employee
    fmt.Printf("Team size: %d\n", manager.TeamSize)          // From Manager

    // Modify through embedded field
    manager.SetEmail("alice.johnson@company.com")            // From Person
    fmt.Printf("Updated email: %s\n", manager.Email)

    // Add team members
    dev1 := Employee{
        Person: Person{Name: "Bob Smith", Age: 28, Email: "bob@company.com"},
        EmployeeID: "DEV001",
        Department: "Engineering",
        Salary: 90000,
    }

    dev2 := Employee{
        Person: Person{Name: "Carol Davis", Age: 26, Email: "carol@company.com"},
        EmployeeID: "DEV002",
        Department: "Engineering",
        Salary: 85000,
    }

    manager.AddDirectReport(dev1)
    manager.AddDirectReport(dev2)

    fmt.Printf("Team after adding members: %d people\n", manager.TeamSize)
    for i, report := range manager.DirectReports {
        fmt.Printf("  %d. %s (%s)\n", i+1, report.Name, report.EmployeeID)
    }
}

// Interface embedding
type Reader interface {
    Read([]byte) (int, error)
}

type Writer interface {
    Write([]byte) (int, error)
}

type Closer interface {
    Close() error
}

// ReadWriteCloser embeds multiple interfaces
type ReadWriteCloser interface {
    Reader
    Writer
    Closer
}

// Implementation of embedded interfaces
type FileHandler struct {
    filename string
    data     []byte
    position int
    closed   bool
}

func NewFileHandler(filename string, data []byte) *FileHandler {
    return &FileHandler{
        filename: filename,
        data:     make([]byte, len(data)),
        position: 0,
        closed:   false,
    }
}

func (fh *FileHandler) Read(p []byte) (int, error) {
    if fh.closed {
        return 0, fmt.Errorf("file is closed")
    }

    if fh.position >= len(fh.data) {
        return 0, fmt.Errorf("EOF")
    }

    n := copy(p, fh.data[fh.position:])
    fh.position += n
    return n, nil
}

func (fh *FileHandler) Write(p []byte) (int, error) {
    if fh.closed {
        return 0, fmt.Errorf("file is closed")
    }

    fh.data = append(fh.data, p...)
    return len(p), nil
}

func (fh *FileHandler) Close() error {
    if fh.closed {
        return fmt.Errorf("already closed")
    }
    fh.closed = true
    return nil
}

func demonstrateInterfaceEmbedding() {
    fmt.Println("\n=== Interface Embedding ===")

    // FileHandler implements ReadWriteCloser through embedded interfaces
    var rwc ReadWriteCloser = NewFileHandler("test.txt", []byte("initial data"))

    // Use as Writer
    data := []byte("additional data")
    n, err := rwc.Write(data)
    if err != nil {
        fmt.Printf("Write error: %v\n", err)
    } else {
        fmt.Printf("Written %d bytes\n", n)
    }

    // Use as Reader
    buffer := make([]byte, 20)
    n, err = rwc.Read(buffer)
    if err != nil {
        fmt.Printf("Read error: %v\n", err)
    } else {
        fmt.Printf("Read %d bytes: %s\n", n, string(buffer[:n]))
    }

    // Use as Closer
    err = rwc.Close()
    if err != nil {
        fmt.Printf("Close error: %v\n", err)
    } else {
        fmt.Println("File closed successfully")
    }
}
```

### Build Tags and Conditional Compilation

Build tags allow you to include or exclude files from compilation based on conditions.

#### Using Build Tags

```go
// File: config_development.go
//go:build development
// +build development

package config

import "time"

const (
    DatabaseURL     = "localhost:5432/myapp_dev"
    LogLevel        = "debug"
    CacheTimeout    = 5 * time.Minute
    EnableProfiling = true
)

// File: config_production.go
//go:build production
// +build production

package config

import "time"

const (
    DatabaseURL     = "prod-db.company.com:5432/myapp"
    LogLevel        = "error"
    CacheTimeout    = 1 * time.Hour
    EnableProfiling = false
)

// File: config_test.go
//go:build test
// +build test

package config

import "time"

const (
    DatabaseURL     = "localhost:5432/myapp_test"
    LogLevel        = "debug"
    CacheTimeout    = 1 * time.Minute
    EnableProfiling = true
)

// File: logger_unix.go
//go:build unix
// +build unix

package logger

import (
    "log/syslog"
    "os"
)

func NewSystemLogger() (*syslog.Writer, error) {
    return syslog.New(syslog.LOG_INFO|syslog.LOG_LOCAL0, "myapp")
}

func GetLogPath() string {
    return "/var/log/myapp.log"
}

// File: logger_windows.go
//go:build windows
// +build windows

package logger

import (
    "os"
    "path/filepath"
)

func NewSystemLogger() (*os.File, error) {
    logDir := filepath.Join(os.Getenv("PROGRAMDATA"), "MyApp", "logs")
    os.MkdirAll(logDir, 0755)
    return os.OpenFile(filepath.Join(logDir, "myapp.log"),
                       os.O_CREATE|os.O_WRONLY|os.O_APPEND, 0644)
}

func GetLogPath() string {
    return filepath.Join(os.Getenv("PROGRAMDATA"), "MyApp", "logs", "myapp.log")
}

// Build commands:
// go build -tags development
// go build -tags production
// go build -tags test
// GOOS=linux go build -tags unix
// GOOS=windows go build -tags windows
```

### CGO and Interfacing with C

CGO allows Go programs to call C code and vice versa.

#### Basic CGO Usage

```go
// File: mathutil.go
package main

/*
#include <math.h>
#include <stdlib.h>

// C function that we'll call from Go
double calculate_distance(double x1, double y1, double x2, double y2) {
    double dx = x2 - x1;
    double dy = y2 - y1;
    return sqrt(dx * dx + dy * dy);
}

// C function with memory allocation
char* create_message(char* name) {
    char* message = malloc(256);
    sprintf(message, "Hello from C, %s!", name);
    return message;
}

// C function to free memory
void free_message(char* message) {
    free(message);
}
*/
import "C"
import (
    "fmt"
    "unsafe"
)

func demonstrateCGO() {
    fmt.Println("\n=== CGO Interface ===")

    // Call C function with numeric parameters
    distance := C.calculate_distance(0.0, 0.0, 3.0, 4.0)
    fmt.Printf("Distance calculated in C: %.2f\n", float64(distance))

    // Call C function with string parameter
    name := C.CString("Go Developer")
    defer C.free(unsafe.Pointer(name)) // Important: free C memory

    cMessage := C.create_message(name)
    defer C.free_message(cMessage) // Important: free C memory

    goMessage := C.GoString(cMessage)
    fmt.Printf("Message from C: %s\n", goMessage)

    // Working with C arrays
    cArray := (*C.double)(C.malloc(C.size_t(5) * C.sizeof_double))
    defer C.free(unsafe.Pointer(cArray))

    // Convert to Go slice for easier manipulation
    goSlice := (*[5]C.double)(unsafe.Pointer(cArray))[:5:5]

    // Populate array
    for i := 0; i < 5; i++ {
        goSlice[i] = C.double(float64(i+1) * 2.5)
    }

    fmt.Print("C array values: ")
    for i := 0; i < 5; i++ {
        fmt.Printf("%.1f ", float64(goSlice[i]))
    }
    fmt.Println()
}

// Advanced CGO example with callbacks
/*
#include <stdio.h>

// C function pointer type
typedef void (*callback_func)(int);

// C function that calls a callback
void call_callback(callback_func cb, int value) {
    printf("C: About to call callback with value %d\n", value);
    cb(value);
    printf("C: Callback completed\n");
}
*/

//export goCallback
func goCallback(value C.int) {
    fmt.Printf("Go callback called with value: %d\n", int(value))
}

func demonstrateCGOCallback() {
    fmt.Println("\n=== CGO Callbacks ===")

    // Call C function that will call back to Go
    C.call_callback(C.callback_func(C.goCallback), 42)
}

func main() {
    demonstrateBasicReflection()
    demonstrateStructReflection()
    demonstrateReflectionModification()
    demonstrateDeepCopy()
    demonstrateGenerics()
    demonstrateTypeInference()
    demonstrateStructEmbedding()
    demonstrateInterfaceEmbedding()
    demonstrateCGO()
    demonstrateCGOCallback()
}
```

### ⚠️ Common Pitfalls

1. **Reflection Performance**
```go
// Slow: Using reflection in hot path
func slowProcess(data []interface{}) {
    for _, item := range data {
        v := reflect.ValueOf(item)
        // Heavy reflection operations in loop
        processReflectValue(v)
    }
}

// Better: Use type assertions or interfaces
func fastProcess(data []Processor) {
    for _, item := range data {
        item.Process() // Direct method call
    }
}
```

2. **Generic Type Constraints**
```go
// Wrong: Too restrictive constraint
func BadMax[T int](a, b T) T {
    if a > b { return a }
    return b
}

// Better: Use appropriate constraint
func GoodMax[T constraints.Ordered](a, b T) T {
    if a > b { return a }
    return b
}
```

3. **CGO Memory Management**
```go
// Wrong: Memory leak
func badCGO() {
    cStr := C.CString("hello")
    // Missing: C.free(unsafe.Pointer(cStr))
}

// Correct: Always free C memory
func goodCGO() {
    cStr := C.CString("hello")
    defer C.free(unsafe.Pointer(cStr))
    // Use cStr...
}
```

### ✅ Best Practices

1. **Use Reflection Sparingly**
```go
// Good: Use interfaces for polymorphism
type Processor interface {
    Process() error
}

// Avoid: Heavy reflection in performance-critical code
func process(items []interface{}) {
    for _, item := range items {
        v := reflect.ValueOf(item)
        // Expensive reflection operations...
    }
}
```

2. **Design Generic APIs Carefully**
```go
// Good: Focused generic function
func Filter[T any](slice []T, predicate func(T) bool) []T {
    var result []T
    for _, item := range slice {
        if predicate(item) {
            result = append(result, item)
        }
    }
    return result
}

// Avoid: Over-generic interfaces
type Everything[T any] interface {
    DoEverything(T) T
}
```

3. **Prefer Composition over Embedding**
```go
// Good: Clear composition
type UserService struct {
    repo UserRepository
    logger Logger
}

// Sometimes appropriate: Embedding for "is-a" relationships
type Manager struct {
    Employee // Manager is an Employee
    teamSize int
}
```

### 🏋️ Exercise 10: Advanced Go Features
**Difficulty:** 🔴 Advanced
**Estimated Time:** 60 minutes

Create a comprehensive plugin system that demonstrates:

1. Reflection for dynamic type discovery and method invocation
2. Generics for type-safe plugin interfaces
3. Embedding for plugin composition
4. Build tags for platform-specific implementations
5. Advanced error handling with custom types

Build a "Data Processing Pipeline" that can load and execute plugins dynamically.

<details>
<summary>💡 Click to see hints</summary>

- Use reflection to discover available plugins at runtime
- Create generic plugin interfaces that work with different data types
- Use embedding to compose complex plugin behaviors
- Implement build tags for different processing engines
- Create a plugin registry with type-safe registration

</details>

<details>
<summary>✅ Click to see solution</summary>

```go
package main

import (
    "fmt"
    "reflect"
    "strings"
    "sync"
    "time"
)

// Generic plugin interfaces
type DataProcessor[T any] interface {
    Process(data T) (T, error)
    Name() string
    Version() string
}

type DataValidator[T any] interface {
    Validate(data T) error
}

type DataTransformer[T any] interface {
    Transform(data T) (interface{}, error)
}

// Plugin registry using generics and reflection
type PluginRegistry struct {
    mu        sync.RWMutex
    processors map[string]interface{}
    metadata   map[string]PluginMetadata
}

type PluginMetadata struct {
    Name        string
    Version     string
    Description string
    Type        reflect.Type
    InputType   reflect.Type
    OutputType  reflect.Type
}

func NewPluginRegistry() *PluginRegistry {
    return &PluginRegistry{
        processors: make(map[string]interface{}),
        metadata:   make(map[string]PluginMetadata),
    }
}

func (pr *PluginRegistry) Register(plugin interface{}) error {
    pr.mu.Lock()
    defer pr.mu.Unlock()

    pluginType := reflect.TypeOf(plugin)
    pluginValue := reflect.ValueOf(plugin)

    // Use reflection to extract metadata
    nameMethod := pluginValue.MethodByName("Name")
    if !nameMethod.IsValid() {
        return fmt.Errorf("plugin must implement Name() method")
    }

    results := nameMethod.Call([]reflect.Value{})
    if len(results) != 1 || results[0].Type().Kind() != reflect.String {
        return fmt.Errorf("Name() method must return string")
    }

    name := results[0].String()

    // Extract version
    versionMethod := pluginValue.MethodByName("Version")
    version := "unknown"
    if versionMethod.IsValid() {
        results := versionMethod.Call([]reflect.Value{})
        if len(results) == 1 && results[0].Type().Kind() == reflect.String {
            version = results[0].String()
        }
    }

    // Determine plugin interfaces
    var inputType, outputType reflect.Type
    for i := 0; i < pluginType.NumMethod(); i++ {
        method := pluginType.Method(i)
        if method.Name == "Process" {
            methodType := method.Type
            if methodType.NumIn() >= 2 { // receiver + input
                inputType = methodType.In(1)
            }
            if methodType.NumOut() >= 1 {
                outputType = methodType.Out(0)
            }
            break
        }
    }

    metadata := PluginMetadata{
        Name:        name,
        Version:     version,
        Description: fmt.Sprintf("Plugin: %s", pluginType.String()),
        Type:        pluginType,
        InputType:   inputType,
        OutputType:  outputType,
    }

    pr.processors[name] = plugin
    pr.metadata[name] = metadata

    fmt.Printf("🔌 Registered plugin: %s v%s\n", name, version)
    return nil
}

func (pr *PluginRegistry) GetPlugin(name string) (interface{}, bool) {
    pr.mu.RLock()
    defer pr.mu.RUnlock()
    plugin, exists := pr.processors[name]
    return plugin, exists
}

func (pr *PluginRegistry) ListPlugins() []PluginMetadata {
    pr.mu.RLock()
    defer pr.mu.RUnlock()

    plugins := make([]PluginMetadata, 0, len(pr.metadata))
    for _, meta := range pr.metadata {
        plugins = append(plugins, meta)
    }
    return plugins
}

// Base plugin with embedding
type BasePlugin struct {
    name        string
    version     string
    description string
}

func NewBasePlugin(name, version, description string) BasePlugin {
    return BasePlugin{
        name:        name,
        version:     version,
        description: description,
    }
}

func (bp BasePlugin) Name() string { return bp.name }
func (bp BasePlugin) Version() string { return bp.version }
func (bp BasePlugin) Description() string { return bp.description }

// String processing plugins
type StringUppercasePlugin struct {
    BasePlugin
}

func NewStringUppercasePlugin() *StringUppercasePlugin {
    return &StringUppercasePlugin{
        BasePlugin: NewBasePlugin("uppercase", "1.0.0", "Converts strings to uppercase"),
    }
}

func (sup *StringUppercasePlugin) Process(data string) (string, error) {
    if data == "" {
        return "", fmt.Errorf("empty string cannot be processed")
    }
    return strings.ToUpper(data), nil
}

func (sup *StringUppercasePlugin) Validate(data string) error {
    if len(data) > 1000 {
        return fmt.Errorf("string too long: %d characters", len(data))
    }
    return nil
}

type StringReversePlugin struct {
    BasePlugin
}

func NewStringReversePlugin() *StringReversePlugin {
    return &StringReversePlugin{
        BasePlugin: NewBasePlugin("reverse", "1.2.0", "Reverses string content"),
    }
}

func (srp *StringReversePlugin) Process(data string) (string, error) {
    runes := []rune(data)
    for i, j := 0, len(runes)-1; i < j; i, j = i+1, j-1 {
        runes[i], runes[j] = runes[j], runes[i]
    }
    return string(runes), nil
}

// Numeric processing plugins
type NumberDoublePlugin struct {
    BasePlugin
    multiplier float64
}

func NewNumberDoublePlugin() *NumberDoublePlugin {
    return &NumberDoublePlugin{
        BasePlugin: NewBasePlugin("double", "2.0.0", "Doubles numeric values"),
        multiplier: 2.0,
    }
}

func (ndp *NumberDoublePlugin) Process(data float64) (float64, error) {
    return data * ndp.multiplier, nil
}

func (ndp *NumberDoublePlugin) SetMultiplier(m float64) {
    ndp.multiplier = m
}

// Generic pipeline processor
type Pipeline[T any] struct {
    processors []DataProcessor[T]
    validators []DataValidator[T]
    name       string
}

func NewPipeline[T any](name string) *Pipeline[T] {
    return &Pipeline[T]{
        processors: make([]DataProcessor[T], 0),
        validators: make([]DataValidator[T], 0),
        name:       name,
    }
}

func (p *Pipeline[T]) AddProcessor(processor DataProcessor[T]) {
    p.processors = append(p.processors, processor)
}

func (p *Pipeline[T]) AddValidator(validator DataValidator[T]) {
    p.validators = append(p.validators, validator)
}

func (p *Pipeline[T]) Execute(data T) (T, error) {
    fmt.Printf("🔄 Executing pipeline: %s\n", p.name)

    // Validation phase
    for _, validator := range p.validators {
        if err := validator.Validate(data); err != nil {
            return data, fmt.Errorf("validation failed: %w", err)
        }
    }

    // Processing phase
    current := data
    for i, processor := range p.processors {
        fmt.Printf("  Step %d: %s v%s\n", i+1, processor.Name(), processor.Version())

        result, err := processor.Process(current)
        if err != nil {
            return current, fmt.Errorf("processor %s failed: %w", processor.Name(), err)
        }
        current = result
    }

    return current, nil
}

// Advanced plugin with embedding and composition
type CompositeStringPlugin struct {
    BasePlugin
    plugins []DataProcessor[string]
}

func NewCompositeStringPlugin() *CompositeStringPlugin {
    return &CompositeStringPlugin{
        BasePlugin: NewBasePlugin("composite", "1.0.0", "Composite string processor"),
        plugins:    make([]DataProcessor[string], 0),
    }
}

func (csp *CompositeStringPlugin) AddPlugin(plugin DataProcessor[string]) {
    csp.plugins = append(csp.plugins, plugin)
}

func (csp *CompositeStringPlugin) Process(data string) (string, error) {
    current := data
    for _, plugin := range csp.plugins {
        result, err := plugin.Process(current)
        if err != nil {
            return current, fmt.Errorf("composite plugin step failed: %w", err)
        }
        current = result
    }
    return current, nil
}

// Plugin discovery using reflection
func DiscoverPlugins(registry *PluginRegistry) {
    fmt.Println("🔍 Discovering plugins...")

    // Create instances of all available plugins
    plugins := []interface{}{
        NewStringUppercasePlugin(),
        NewStringReversePlugin(),
        NewNumberDoublePlugin(),
    }

    for _, plugin := range plugins {
        pluginType := reflect.TypeOf(plugin)
        fmt.Printf("  Found plugin type: %s\n", pluginType.String())

        // Check if it implements required interfaces
        processorInterface := reflect.TypeOf((*DataProcessor[string])(nil)).Elem()
        if pluginType.Implements(processorInterface) {
            fmt.Printf("    ✅ Implements DataProcessor[string]\n")
            registry.Register(plugin)
        } else {
            // Try other types using reflection
            for i := 0; i < pluginType.NumMethod(); i++ {
                method := pluginType.Method(i)
                if method.Name == "Process" {
                    fmt.Printf("    ✅ Has Process method: %s\n", method.Type.String())
                    registry.Register(plugin)
                    break
                }
            }
        }
    }
}

// Dynamic plugin execution using reflection
func ExecutePluginByName(registry *PluginRegistry, pluginName string, data interface{}) (interface{}, error) {
    plugin, exists := registry.GetPlugin(pluginName)
    if !exists {
        return nil, fmt.Errorf("plugin %s not found", pluginName)
    }

    pluginValue := reflect.ValueOf(plugin)
    processMethod := pluginValue.MethodByName("Process")

    if !processMethod.IsValid() {
        return nil, fmt.Errorf("plugin %s does not have Process method", pluginName)
    }

    // Prepare arguments
    args := []reflect.Value{reflect.ValueOf(data)}

    // Call method using reflection
    results := processMethod.Call(args)
    if len(results) < 2 {
        return nil, fmt.Errorf("Process method should return (result, error)")
    }

    // Check for error
    if !results[1].IsNil() {
        err := results[1].Interface().(error)
        return nil, err
    }

    return results[0].Interface(), nil
}

func main() {
    fmt.Println("🚀 Advanced Go Features: Plugin System Demo")
    fmt.Println("===========================================")

    // Create registry and discover plugins
    registry := NewPluginRegistry()
    DiscoverPlugins(registry)

    // List all registered plugins
    fmt.Println("\n📋 Registered Plugins:")
    for _, meta := range registry.ListPlugins() {
        fmt.Printf("  • %s v%s - %s\n", meta.Name, meta.Version, meta.Description)
        if meta.InputType != nil {
            fmt.Printf("    Input: %s, Output: %s\n", meta.InputType, meta.OutputType)
        }
    }

    // Create and execute string processing pipeline
    fmt.Println("\n🔧 String Processing Pipeline:")
    stringPipeline := NewPipeline[string]("String Processor")

    // Add plugins to pipeline
    if plugin, ok := registry.GetPlugin("uppercase"); ok {
        if stringProcessor, ok := plugin.(DataProcessor[string]); ok {
            stringPipeline.AddProcessor(stringProcessor)
        }
    }

    if plugin, ok := registry.GetPlugin("reverse"); ok {
        if stringProcessor, ok := plugin.(DataProcessor[string]); ok {
            stringPipeline.AddProcessor(stringProcessor)
        }
    }

    // Execute pipeline
    input := "hello world"
    result, err := stringPipeline.Execute(input)
    if err != nil {
        fmt.Printf("Pipeline error: %v\n", err)
    } else {
        fmt.Printf("Input: '%s' → Output: '%s'\n", input, result)
    }

    // Dynamic plugin execution using reflection
    fmt.Println("\n🔄 Dynamic Plugin Execution:")
    dynamicResult, err := ExecutePluginByName(registry, "uppercase", "dynamic execution")
    if err != nil {
        fmt.Printf("Dynamic execution error: %v\n", err)
    } else {
        fmt.Printf("Dynamic result: %v\n", dynamicResult)
    }

    // Demonstrate composite plugin with embedding
    fmt.Println("\n🔗 Composite Plugin Demo:")
    composite := NewCompositeStringPlugin()
    composite.AddPlugin(NewStringUppercasePlugin())
    composite.AddPlugin(NewStringReversePlugin())

    registry.Register(composite)

    compositeResult, err := composite.Process("composite test")
    if err != nil {
        fmt.Printf("Composite error: %v\n", err)
    } else {
        fmt.Printf("Composite result: %s\n", compositeResult)
    }

    // Performance comparison
    fmt.Println("\n⚡ Performance Comparison:")
    iterations := 100000
    testString := "performance test string"

    // Direct method call
    start := time.Now()
    upperPlugin := NewStringUppercasePlugin()
    for i := 0; i < iterations; i++ {
        upperPlugin.Process(testString)
    }
    directTime := time.Since(start)

    // Reflection-based call
    start = time.Now()
    for i := 0; i < iterations; i++ {
        ExecutePluginByName(registry, "uppercase", testString)
    }
    reflectionTime := time.Since(start)

    fmt.Printf("Direct calls (%d iterations): %v\n", iterations, directTime)
    fmt.Printf("Reflection calls (%d iterations): %v\n", iterations, reflectionTime)
    fmt.Printf("Reflection overhead: %.2fx slower\n",
               float64(reflectionTime.Nanoseconds())/float64(directTime.Nanoseconds()))
}
```

**Explanation:**

This comprehensive solution demonstrates all advanced Go features:

**Key concepts demonstrated:**
1. **Reflection**: Dynamic plugin discovery, type inspection, method invocation
2. **Generics**: Type-safe pipeline processing with `Pipeline[T]` and `DataProcessor[T]`
3. **Embedding**: `BasePlugin` embedded in specific plugin implementations
4. **Interface composition**: Multiple interfaces combined for plugin capabilities
5. **Advanced error handling**: Wrapped errors with context information

**Advanced patterns shown:**
- **Plugin architecture**: Registry pattern with dynamic plugin discovery
- **Generic programming**: Type-safe pipelines that work with any data type
- **Reflection-based execution**: Dynamic method invocation with error handling
- **Composite pattern**: Plugins that contain other plugins
- **Performance analysis**: Comparing direct calls vs. reflection

**Performance considerations:**
- Reflection overhead measurement and comparison
- Efficient use of sync.RWMutex for concurrent access
- Memory-efficient plugin registration and discovery
- Type-safe generic interfaces to avoid runtime type errors

**Best practices demonstrated:**
- Clear separation of concerns with focused interfaces
- Comprehensive error handling with context preservation
- Thread-safe plugin registry implementation
- Performance-conscious design with benchmarking
- Clean plugin lifecycle management

</details>

---

## Chapter 11: Standard Library Deep Dive
📊 **Progress:** Chapter 11 of 12 | ⏱️ **Estimated reading time:** 35 minutes

🎯 **Learning Objectives:**
- Master I/O operations and file system interactions
- Understand network programming with Go's net package
- Learn JSON/XML processing for data interchange
- Explore time and date handling
- Work with HTTP clients and servers

📋 **Prerequisites:** Understanding of interfaces, error handling, and concurrency

### I/O Operations

Go provides powerful I/O abstractions through the `io` package and related packages.

#### Basic I/O Interfaces

```go
package main

import (
    "bytes"
    "fmt"
    "io"
    "strings"
)

func demonstrateBasicIO() {
    fmt.Println("=== Basic I/O Operations ===")

    // Reader interface demonstration
    text := "Hello, Go I/O world!"
    reader := strings.NewReader(text)

    // Read all at once
    data, err := io.ReadAll(reader)
    if err != nil {
        fmt.Printf("Error reading: %v\n", err)
        return
    }
    fmt.Printf("Read all: %s\n", string(data))

    // Buffer reading
    reader.Reset(text) // Reset to beginning
    buffer := make([]byte, 5)

    fmt.Println("Reading in chunks:")
    for {
        n, err := reader.Read(buffer)
        if err != nil {
            if err == io.EOF {
                fmt.Println("Reached end of data")
            } else {
                fmt.Printf("Error: %v\n", err)
            }
            break
        }
        fmt.Printf("Read %d bytes: %q\n", n, string(buffer[:n]))
    }

    // Writer interface demonstration
    var buf bytes.Buffer

    message := "Writing to buffer"
    n, err := buf.WriteString(message)
    if err != nil {
        fmt.Printf("Write error: %v\n", err)
    } else {
        fmt.Printf("Wrote %d bytes\n", n)
    }

    fmt.Printf("Buffer content: %s\n", buf.String())

    // Copy operations
    source := strings.NewReader("Data to copy")
    var destination bytes.Buffer

    copied, err := io.Copy(&destination, source)
    if err != nil {
        fmt.Printf("Copy error: %v\n", err)
    } else {
        fmt.Printf("Copied %d bytes: %s\n", copied, destination.String())
    }
}

// Custom Reader implementation
type RotReader struct {
    source io.Reader
    key    byte
}

func NewRotReader(source io.Reader, key byte) *RotReader {
    return &RotReader{source: source, key: key}
}

func (rr *RotReader) Read(p []byte) (int, error) {
    n, err := rr.source.Read(p)

    // Apply ROT transformation
    for i := 0; i < n; i++ {
        if p[i] >= 'A' && p[i] <= 'Z' {
            p[i] = ((p[i] - 'A' + rr.key) % 26) + 'A'
        } else if p[i] >= 'a' && p[i] <= 'z' {
            p[i] = ((p[i] - 'a' + rr.key) % 26) + 'a'
        }
    }

    return n, err
}

func demonstrateCustomReader() {
    fmt.Println("\n=== Custom Reader Implementation ===")

    original := "Hello, World!"
    reader := strings.NewReader(original)
    rotReader := NewRotReader(reader, 13) // ROT13

    encoded, err := io.ReadAll(rotReader)
    if err != nil {
        fmt.Printf("Error: %v\n", err)
        return
    }

    fmt.Printf("Original: %s\n", original)
    fmt.Printf("ROT13: %s\n", string(encoded))

    // Decode back
    decoder := NewRotReader(bytes.NewReader(encoded), 13) // ROT13 again to decode
    decoded, err := io.ReadAll(decoder)
    if err != nil {
        fmt.Printf("Error: %v\n", err)
        return
    }
    fmt.Printf("Decoded: %s\n", string(decoded))
}
```

### File System Operations

Working with files and directories using the `os` and `path/filepath` packages.

#### File Operations

```go
import (
    "bufio"
    "fmt"
    "os"
    "path/filepath"
    "time"
)

func demonstrateFileOperations() {
    fmt.Println("\n=== File Operations ===")

    filename := "example.txt"
    content := "Hello, Go file operations!\nThis is line 2.\nAnd this is line 3."

    // Write file
    err := os.WriteFile(filename, []byte(content), 0644)
    if err != nil {
        fmt.Printf("Error writing file: %v\n", err)
        return
    }
    fmt.Printf("Created file: %s\n", filename)

    // Read file
    data, err := os.ReadFile(filename)
    if err != nil {
        fmt.Printf("Error reading file: %v\n", err)
        return
    }
    fmt.Printf("File content:\n%s\n", string(data))

    // File info
    info, err := os.Stat(filename)
    if err != nil {
        fmt.Printf("Error getting file info: %v\n", err)
        return
    }

    fmt.Printf("File info:\n")
    fmt.Printf("  Name: %s\n", info.Name())
    fmt.Printf("  Size: %d bytes\n", info.Size())
    fmt.Printf("  Mode: %s\n", info.Mode())
    fmt.Printf("  ModTime: %s\n", info.ModTime().Format(time.RFC3339))
    fmt.Printf("  Is Directory: %t\n", info.IsDir())

    // Open file for reading with scanner
    file, err := os.Open(filename)
    if err != nil {
        fmt.Printf("Error opening file: %v\n", err)
        return
    }
    defer file.Close()

    fmt.Println("Reading file line by line:")
    scanner := bufio.NewScanner(file)
    lineNum := 1
    for scanner.Scan() {
        fmt.Printf("  Line %d: %s\n", lineNum, scanner.Text())
        lineNum++
    }

    if err := scanner.Err(); err != nil {
        fmt.Printf("Scanner error: %v\n", err)
    }

    // Append to file
    file, err = os.OpenFile(filename, os.O_APPEND|os.O_WRONLY, 0644)
    if err != nil {
        fmt.Printf("Error opening file for append: %v\n", err)
        return
    }
    defer file.Close()

    _, err = file.WriteString("\nAppended line.\n")
    if err != nil {
        fmt.Printf("Error appending to file: %v\n", err)
        return
    }
    fmt.Println("Appended to file")

    // Clean up
    defer os.Remove(filename)
}

func demonstrateDirectoryOperations() {
    fmt.Println("\n=== Directory Operations ===")

    // Create directory
    dirName := "testdir"
    err := os.Mkdir(dirName, 0755)
    if err != nil {
        fmt.Printf("Error creating directory: %v\n", err)
        return
    }
    fmt.Printf("Created directory: %s\n", dirName)

    // Create nested directories
    nestedDir := filepath.Join(dirName, "nested", "deep")
    err = os.MkdirAll(nestedDir, 0755)
    if err != nil {
        fmt.Printf("Error creating nested directories: %v\n", err)
        return
    }
    fmt.Printf("Created nested directories: %s\n", nestedDir)

    // Create files in directories
    files := []string{
        filepath.Join(dirName, "file1.txt"),
        filepath.Join(dirName, "file2.txt"),
        filepath.Join(nestedDir, "deep_file.txt"),
    }

    for i, filename := range files {
        content := fmt.Sprintf("Content of file %d", i+1)
        err := os.WriteFile(filename, []byte(content), 0644)
        if err != nil {
            fmt.Printf("Error creating file %s: %v\n", filename, err)
            continue
        }
        fmt.Printf("Created file: %s\n", filename)
    }

    // List directory contents
    fmt.Printf("Contents of %s:\n", dirName)
    entries, err := os.ReadDir(dirName)
    if err != nil {
        fmt.Printf("Error reading directory: %v\n", err)
        return
    }

    for _, entry := range entries {
        info, err := entry.Info()
        if err != nil {
            fmt.Printf("Error getting info for %s: %v\n", entry.Name(), err)
            continue
        }

        entryType := "file"
        if entry.IsDir() {
            entryType = "directory"
        }

        fmt.Printf("  %s: %s (%d bytes)\n", entryType, entry.Name(), info.Size())
    }

    // Walk directory tree
    fmt.Printf("Walking directory tree from %s:\n", dirName)
    err = filepath.Walk(dirName, func(path string, info os.FileInfo, err error) error {
        if err != nil {
            return err
        }

        relPath, _ := filepath.Rel(dirName, path)
        if relPath == "." {
            relPath = dirName
        }

        entryType := "file"
        if info.IsDir() {
            entryType = "dir "
        }

        fmt.Printf("  %s: %s\n", entryType, relPath)
        return nil
    })

    if err != nil {
        fmt.Printf("Error walking directory: %v\n", err)
    }

    // Clean up
    defer os.RemoveAll(dirName)
}
```

### Network Programming

Go's `net` package provides comprehensive networking capabilities.

#### TCP Server and Client

```go
import (
    "bufio"
    "fmt"
    "net"
    "time"
)

func startTCPServer() {
    fmt.Println("\n=== TCP Server ===")

    // Listen on TCP port 8080
    listener, err := net.Listen("tcp", ":8080")
    if err != nil {
        fmt.Printf("Error starting server: %v\n", err)
        return
    }
    defer listener.Close()

    fmt.Println("Server listening on :8080")

    for {
        // Accept incoming connections
        conn, err := listener.Accept()
        if err != nil {
            fmt.Printf("Error accepting connection: %v\n", err)
            continue
        }

        // Handle connection in a goroutine
        go handleConnection(conn)
    }
}

func handleConnection(conn net.Conn) {
    defer conn.Close()

    fmt.Printf("New connection from %s\n", conn.RemoteAddr())

    // Set connection timeout
    conn.SetDeadline(time.Now().Add(30 * time.Second))

    scanner := bufio.NewScanner(conn)
    for scanner.Scan() {
        message := scanner.Text()
        fmt.Printf("Received: %s\n", message)

        // Echo the message back
        response := fmt.Sprintf("Echo: %s\n", message)
        _, err := conn.Write([]byte(response))
        if err != nil {
            fmt.Printf("Error sending response: %v\n", err)
            break
        }

        // Special command to close connection
        if message == "quit" {
            break
        }
    }

    if err := scanner.Err(); err != nil {
        fmt.Printf("Connection error: %v\n", err)
    }

    fmt.Printf("Connection from %s closed\n", conn.RemoteAddr())
}

func demonstrateTCPClient() {
    fmt.Println("\n=== TCP Client ===")

    // Connect to server
    conn, err := net.Dial("tcp", "localhost:8080")
    if err != nil {
        fmt.Printf("Error connecting to server: %v\n", err)
        return
    }
    defer conn.Close()

    fmt.Println("Connected to server")

    // Send messages
    messages := []string{"Hello, server!", "How are you?", "quit"}

    for _, msg := range messages {
        // Send message
        _, err := conn.Write([]byte(msg + "\n"))
        if err != nil {
            fmt.Printf("Error sending message: %v\n", err)
            break
        }

        // Read response
        response := make([]byte, 1024)
        n, err := conn.Read(response)
        if err != nil {
            fmt.Printf("Error reading response: %v\n", err)
            break
        }

        fmt.Printf("Server response: %s", string(response[:n]))

        time.Sleep(100 * time.Millisecond)
    }

    fmt.Println("Client disconnected")
}

#### UDP Communication

```go
import (
    "fmt"
    "net"
    "time"
)

func startUDPServer() {
    fmt.Println("\n=== UDP Server ===")

    // Listen on UDP port 8081
    addr, err := net.ResolveUDPAddr("udp", ":8081")
    if err != nil {
        fmt.Printf("Error resolving address: %v\n", err)
        return
    }

    conn, err := net.ListenUDP("udp", addr)
    if err != nil {
        fmt.Printf("Error starting UDP server: %v\n", err)
        return
    }
    defer conn.Close()

    fmt.Println("UDP server listening on :8081")

    buffer := make([]byte, 1024)
    for {
        // Read from UDP connection
        n, clientAddr, err := conn.ReadFromUDP(buffer)
        if err != nil {
            fmt.Printf("Error reading UDP message: %v\n", err)
            continue
        }

        message := string(buffer[:n])
        fmt.Printf("Received from %s: %s\n", clientAddr, message)

        // Echo the message back
        response := fmt.Sprintf("Echo: %s", message)
        _, err = conn.WriteToUDP([]byte(response), clientAddr)
        if err != nil {
            fmt.Printf("Error sending UDP response: %v\n", err)
        }
    }
}

func demonstrateUDPClient() {
    fmt.Println("\n=== UDP Client ===")

    // Resolve server address
    serverAddr, err := net.ResolveUDPAddr("udp", "localhost:8081")
    if err != nil {
        fmt.Printf("Error resolving server address: %v\n", err)
        return
    }

    // Create UDP connection
    conn, err := net.DialUDP("udp", nil, serverAddr)
    if err != nil {
        fmt.Printf("Error creating UDP connection: %v\n", err)
        return
    }
    defer conn.Close()

    // Send messages
    messages := []string{"Hello UDP!", "How are you?", "Goodbye!"}

    for _, msg := range messages {
        // Send message
        _, err := conn.Write([]byte(msg))
        if err != nil {
            fmt.Printf("Error sending UDP message: %v\n", err)
            continue
        }

        // Read response
        buffer := make([]byte, 1024)
        conn.SetReadDeadline(time.Now().Add(5 * time.Second))
        n, err := conn.Read(buffer)
        if err != nil {
            fmt.Printf("Error reading UDP response: %v\n", err)
            continue
        }

        fmt.Printf("Server response: %s\n", string(buffer[:n]))
        time.Sleep(100 * time.Millisecond)
    }
}
```

#### HTTP Client and Server

```go
import (
    "encoding/json"
    "fmt"
    "io"
    "net/http"
    "strings"
    "time"
)

type User struct {
    ID    int    `json:"id"`
    Name  string `json:"name"`
    Email string `json:"email"`
}

func startHTTPServer() {
    fmt.Println("\n=== HTTP Server ===")

    users := []User{
        {ID: 1, Name: "Alice", Email: "alice@example.com"},
        {ID: 2, Name: "Bob", Email: "bob@example.com"},
    }

    // Handle GET /users
    http.HandleFunc("/users", func(w http.ResponseWriter, r *http.Request) {
        switch r.Method {
        case "GET":
            w.Header().Set("Content-Type", "application/json")
            json.NewEncoder(w).Encode(users)
        case "POST":
            var newUser User
            if err := json.NewDecoder(r.Body).Decode(&newUser); err != nil {
                http.Error(w, "Invalid JSON", http.StatusBadRequest)
                return
            }
            newUser.ID = len(users) + 1
            users = append(users, newUser)
            w.Header().Set("Content-Type", "application/json")
            w.WriteHeader(http.StatusCreated)
            json.NewEncoder(w).Encode(newUser)
        default:
            http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
        }
    })

    // Handle GET /health
    http.HandleFunc("/health", func(w http.ResponseWriter, r *http.Request) {
        w.WriteHeader(http.StatusOK)
        fmt.Fprintf(w, "OK")
    })

    fmt.Println("HTTP server starting on :8080")
    if err := http.ListenAndServe(":8080", nil); err != nil {
        fmt.Printf("Server error: %v\n", err)
    }
}

func demonstrateHTTPClient() {
    fmt.Println("\n=== HTTP Client ===")

    client := &http.Client{
        Timeout: 10 * time.Second,
    }

    // GET request
    resp, err := client.Get("http://localhost:8080/users")
    if err != nil {
        fmt.Printf("Error making GET request: %v\n", err)
        return
    }
    defer resp.Body.Close()

    body, err := io.ReadAll(resp.Body)
    if err != nil {
        fmt.Printf("Error reading response: %v\n", err)
        return
    }

    fmt.Printf("GET /users response: %s\n", string(body))

    // POST request
    newUser := User{Name: "Charlie", Email: "charlie@example.com"}
    userJSON, _ := json.Marshal(newUser)

    resp, err = client.Post(
        "http://localhost:8080/users",
        "application/json",
        strings.NewReader(string(userJSON)),
    )
    if err != nil {
        fmt.Printf("Error making POST request: %v\n", err)
        return
    }
    defer resp.Body.Close()

    body, err = io.ReadAll(resp.Body)
    if err != nil {
        fmt.Printf("Error reading POST response: %v\n", err)
        return
    }

    fmt.Printf("POST /users response: %s\n", string(body))
}
```

### JSON and XML Processing

#### Working with JSON

Go provides excellent built-in support for JSON through the `encoding/json` package:

```go
import (
    "encoding/json"
    "fmt"
    "time"
)

type User struct {
    ID       int       `json:"id"`
    Name     string    `json:"name"`
    Email    string    `json:"email"`
    Age      int       `json:"age,omitempty"`
    Active   bool      `json:"active"`
    Created  time.Time `json:"created_at"`
    Password string    `json:"-"` // Never serialize
}

func demonstrateJSON() {
    fmt.Println("\n=== JSON Processing ===")

    // Create a user
    user := User{
        ID:      1,
        Name:    "Alice Johnson",
        Email:   "alice@example.com",
        Age:     30,
        Active:  true,
        Created: time.Now(),
    }

    // Marshal to JSON
    jsonData, err := json.Marshal(user)
    if err != nil {
        fmt.Printf("Error marshaling JSON: %v\n", err)
        return
    }

    fmt.Printf("JSON: %s\n", string(jsonData))

    // Pretty print JSON
    prettyJSON, err := json.MarshalIndent(user, "", "  ")
    if err != nil {
        fmt.Printf("Error creating pretty JSON: %v\n", err)
        return
    }

    fmt.Printf("Pretty JSON:\n%s\n", string(prettyJSON))

    // Unmarshal from JSON
    var decodedUser User
    if err := json.Unmarshal(jsonData, &decodedUser); err != nil {
        fmt.Printf("Error unmarshaling JSON: %v\n", err)
        return
    }

    fmt.Printf("Decoded user: %+v\n", decodedUser)

    // Working with raw JSON
    rawJSON := `{"name":"Bob","age":25,"active":true,"tags":["developer","golang"]}`
    
    var data map[string]interface{}
    if err := json.Unmarshal([]byte(rawJSON), &data); err != nil {
        fmt.Printf("Error parsing raw JSON: %v\n", err)
        return
    }

    fmt.Printf("Raw JSON data: %+v\n", data)

    // Accessing nested values
    if name, ok := data["name"].(string); ok {
        fmt.Printf("Name: %s\n", name)
    }

    if tags, ok := data["tags"].([]interface{}); ok {
        fmt.Print("Tags: ")
        for _, tag := range tags {
            fmt.Printf("%s ", tag)
        }
        fmt.Println()
    }
}
```

#### Working with XML

```go
import (
    "encoding/xml"
    "fmt"
)

type Book struct {
    XMLName xml.Name `xml:"book"`
    ID      int      `xml:"id,attr"`
    Title   string   `xml:"title"`
    Author  Author   `xml:"author"`
    Price   float64  `xml:"price"`
    Genre   string   `xml:"genre"`
}

type Author struct {
    Name  string `xml:"name"`
    Email string `xml:"email"`
}

type Library struct {
    XMLName xml.Name `xml:"library"`
    Name    string   `xml:"name,attr"`
    Books   []Book   `xml:"book"`
}

func demonstrateXML() {
    fmt.Println("\n=== XML Processing ===")

    // Create sample data
    library := Library{
        Name: "City Library",
        Books: []Book{
            {
                ID:    1,
                Title: "Go Programming",
                Author: Author{
                    Name:  "John Doe",
                    Email: "john@example.com",
                },
                Price: 29.99,
                Genre: "Programming",
            },
            {
                ID:    2,
                Title: "Web Development",
                Author: Author{
                    Name:  "Jane Smith",
                    Email: "jane@example.com",
                },
                Price: 34.99,
                Genre: "Web",
            },
        },
    }

    // Marshal to XML
    xmlData, err := xml.MarshalIndent(library, "", "  ")
    if err != nil {
        fmt.Printf("Error marshaling XML: %v\n", err)
        return
    }

    fmt.Printf("XML:\n%s\n", string(xmlData))

    // Unmarshal from XML
    xmlInput := `
    <library name="Tech Library">
        <book id="1">
            <title>Advanced Go</title>
            <author>
                <name>Alice Johnson</name>
                <email>alice@tech.com</email>
            </author>
            <price>39.99</price>
            <genre>Programming</genre>
        </book>
    </library>`

    var parsedLibrary Library
    if err := xml.Unmarshal([]byte(xmlInput), &parsedLibrary); err != nil {
        fmt.Printf("Error unmarshaling XML: %v\n", err)
        return
    }

    fmt.Printf("Parsed library: %+v\n", parsedLibrary)
}
```

### Time and Date

#### Working with Time

Go's `time` package provides comprehensive time and date functionality:

```go
import (
    "fmt"
    "time"
)

func demonstrateTime() {
    fmt.Println("\n=== Time and Date Operations ===")

    // Current time
    now := time.Now()
    fmt.Printf("Current time: %v\n", now)
    fmt.Printf("Unix timestamp: %d\n", now.Unix())
    fmt.Printf("Nanosecond timestamp: %d\n", now.UnixNano())

    // Time formatting
    fmt.Printf("RFC3339: %s\n", now.Format(time.RFC3339))
    fmt.Printf("Custom format: %s\n", now.Format("2006-01-02 15:04:05"))
    fmt.Printf("Date only: %s\n", now.Format("2006-01-02"))
    fmt.Printf("Time only: %s\n", now.Format("15:04:05"))

    // Parsing time strings
    dateStr := "2024-12-25 15:30:45"
    parsed, err := time.Parse("2006-01-02 15:04:05", dateStr)
    if err != nil {
        fmt.Printf("Error parsing time: %v\n", err)
    } else {
        fmt.Printf("Parsed time: %v\n", parsed)
    }

    // Time arithmetic
    future := now.Add(24 * time.Hour)
    past := now.Add(-2 * time.Hour)
    fmt.Printf("24 hours from now: %v\n", future)
    fmt.Printf("2 hours ago: %v\n", past)

    // Duration calculations
    duration := future.Sub(now)
    fmt.Printf("Duration until future: %v\n", duration)
    fmt.Printf("Duration in hours: %f\n", duration.Hours())
    fmt.Printf("Duration in minutes: %f\n", duration.Minutes())

    // Time comparison
    earlier := time.Date(2024, 1, 1, 0, 0, 0, 0, time.UTC)
    later := time.Date(2024, 12, 31, 23, 59, 59, 0, time.UTC)

    fmt.Printf("Earlier before later: %t\n", earlier.Before(later))
    fmt.Printf("Later after earlier: %t\n", later.After(earlier))
    fmt.Printf("Times equal: %t\n", earlier.Equal(later))

    // Working with time zones
    utc := time.Now().UTC()
    eastern, _ := time.LoadLocation("America/New_York")
    pacific, _ := time.LoadLocation("America/Los_Angeles")

    fmt.Printf("UTC time: %v\n", utc)
    fmt.Printf("Eastern time: %v\n", utc.In(eastern))
    fmt.Printf("Pacific time: %v\n", utc.In(pacific))

    // Timers and tickers
    fmt.Println("\n=== Timers and Tickers ===")
    
    // One-time timer
    timer := time.NewTimer(2 * time.Second)
    go func() {
        <-timer.C
        fmt.Println("Timer expired!")
    }()

    // Repeating ticker
    ticker := time.NewTicker(500 * time.Millisecond)
    go func() {
        count := 0
        for range ticker.C {
            count++
            fmt.Printf("Tick %d\n", count)
            if count >= 3 {
                ticker.Stop()
                return
            }
        }
    }()

    // Wait for timer and ticker to complete
    time.Sleep(3 * time.Second)
}
```

#### Time Zones and Locations

```go
func demonstrateTimeZones() {
    fmt.Println("\n=== Time Zones ===")

    // Load different time zones
    locations := []string{
        "UTC",
        "America/New_York",
        "America/Los_Angeles",
        "Europe/London",
        "Asia/Tokyo",
        "Australia/Sydney",
    }

    baseTime := time.Date(2024, 6, 15, 12, 0, 0, 0, time.UTC)

    for _, locName := range locations {
        loc, err := time.LoadLocation(locName)
        if err != nil {
            fmt.Printf("Error loading location %s: %v\n", locName, err)
            continue
        }

        localTime := baseTime.In(loc)
        fmt.Printf("%-20s: %s\n", locName, localTime.Format("2006-01-02 15:04:05 MST"))
    }

    // Working with local time
    local := time.Now()
    utc := local.UTC()
    
    fmt.Printf("Local time: %v\n", local)
    fmt.Printf("UTC time: %v\n", utc)
    fmt.Printf("Time zone offset: %v\n", local.Format("-07:00"))
}
```

### ⚠️ Common Pitfalls

1. **File Handle Leaks**
```go
// Bad: Not closing file
file, _ := os.Open("file.txt")
// file never closed - resource leak

// Good: Always defer Close()
file, err := os.Open("file.txt")
if err != nil {
    return err
}
defer file.Close()
```

2. **Network Connection Leaks**
```go
// Bad: Not closing connection
conn, _ := net.Dial("tcp", "localhost:8080")
// connection never closed

// Good: Always defer Close()
conn, err := net.Dial("tcp", "localhost:8080")
if err != nil {
    return err
}
defer conn.Close()
```

3. **Ignoring Errors in I/O Operations**
```go
// Bad: Ignoring errors
file.Write(data)

// Good: Check all errors
if _, err := file.Write(data); err != nil {
    return err
}
```

### ✅ Best Practices

1. **Always Handle Errors**
```go
if file, err := os.Open("file.txt"); err != nil {
    return fmt.Errorf("failed to open file: %w", err)
} else {
    defer file.Close()
    // process file
}
```

2. **Use Context for Cancellation**
```go
func downloadFile(ctx context.Context, url string) error {
    req, err := http.NewRequestWithContext(ctx, "GET", url, nil)
    if err != nil {
        return err
    }

    resp, err := http.DefaultClient.Do(req)
    if err != nil {
        return err
    }
    defer resp.Body.Close()

    // Process response...
    return nil
}
```

3. **Set Appropriate Timeouts**
```go
client := &http.Client{
    Timeout: 30 * time.Second,
}

conn.SetDeadline(time.Now().Add(10 * time.Second))
```



### ⚠️ Common Pitfalls

1. **File Handle Leaks**
```go
// Bad: Not closing file
file, _ := os.Open("file.txt")
// file never closed - resource leak

// Good: Always defer Close()
file, err := os.Open("file.txt")
if err != nil {
    return err
}
defer file.Close()
```

2. **Network Connection Leaks**
```go
// Bad: Not closing connection
conn, _ := net.Dial("tcp", "localhost:8080")
// connection never closed

// Good: Always defer Close()
conn, err := net.Dial("tcp", "localhost:8080")
if err != nil {
    return err
}
defer conn.Close()
```

3. **Ignoring Errors in I/O Operations**
```go
// Bad: Ignoring errors
file.Write(data)

// Good: Check all errors
if _, err := file.Write(data); err != nil {
    return err
}
```

### ✅ Best Practices

1. **Always Handle Errors**
```go
if file, err := os.Open("file.txt"); err != nil {
    return fmt.Errorf("failed to open file: %w", err)
} else {
    defer file.Close()
    // process file
}
```

2. **Use Context for Cancellation**
```go
func downloadFile(ctx context.Context, url string) error {
    req, err := http.NewRequestWithContext(ctx, "GET", url, nil)
    if err != nil {
        return err
    }

    resp, err := http.DefaultClient.Do(req)
    if err != nil {
        return err
    }
    defer resp.Body.Close()

    // Process response...
    return nil
}
```

3. **Set Appropriate Timeouts**
```go
client := &http.Client{
    Timeout: 30 * time.Second,
}

conn.SetDeadline(time.Now().Add(10 * time.Second))
```

### 🏋️ Exercise 11: Network Programming

Create a complete chat server and client system.

```go
package main

import (
    "bufio"
    "encoding/json"
    "fmt"
    "log"
    "net"
    "strings"
    "sync"
    "time"
)

type Message struct {
    Username  string    `json:"username"`
    Content   string    `json:"content"`
    Timestamp time.Time `json:"timestamp"`
    Type      string    `json:"type"` // "message", "join", "leave"
}

type Client struct {
    conn     net.Conn
    username string
    room     *ChatRoom
}

type ChatRoom struct {
    clients    map[*Client]bool
    broadcast  chan Message
    register   chan *Client
    unregister chan *Client
    mutex      sync.RWMutex
}

func NewChatRoom() *ChatRoom {
    return &ChatRoom{
        clients:    make(map[*Client]bool),
        broadcast:  make(chan Message),
        register:   make(chan *Client),
        unregister: make(chan *Client),
    }
}

func (room *ChatRoom) Run() {
    for {
        select {
        case client := <-room.register:
            room.mutex.Lock()
            room.clients[client] = true
            room.mutex.Unlock()

            // Notify others about new user
            joinMsg := Message{
                Username:  "System",
                Content:   fmt.Sprintf("%s joined the chat", client.username),
                Timestamp: time.Now(),
                Type:      "join",
            }
            room.broadcast <- joinMsg

            log.Printf("Client %s connected", client.username)

        case client := <-room.unregister:
            room.mutex.Lock()
            if _, ok := room.clients[client]; ok {
                delete(room.clients, client)
                close(client
.conn.(*net.TCPConn).CloseWrite())
                
                // Notify others about user leaving
                leaveMsg := Message{
                    Username:  "System",
                    Content:   fmt.Sprintf("%s left the chat", client.username),
                    Timestamp: time.Now(),
                    Type:      "leave",
                }
                room.broadcast <- leaveMsg
                
                log.Printf("Client %s disconnected", client.username)
            }
            room.mutex.Unlock()
            
        case message := <-room.broadcast:
            room.mutex.RLock()
            for client := range room.clients {
                select {
                case <-time.After(1 * time.Second):
                    // Client is not responding, disconnect
                    room.unregister <- client
                default:
                    if err := client.sendMessage(message); err != nil {
                        log.Printf("Error sending message to %s: %v", client.username, err)
                        room.unregister <- client
                    }
                }
            }
            room.mutex.RUnlock()
        }
    }
}

func (c *Client) sendMessage(message Message) error {
    data, err := json.Marshal(message)
    if err != nil {
        return err
    }
    
    _, err = c.conn.Write(append(data, '\n'))
    return err
}

func (c *Client) readMessages() {
    defer func() {
        c.room.unregister <- c
        c.conn.Close()
    }()
    
    scanner := bufio.NewScanner(c.conn)
    for scanner.Scan() {
        line := strings.TrimSpace(scanner.Text())
        if line == "" {
            continue
        }
        
        // Handle commands
        if strings.HasPrefix(line, "/") {
            c.handleCommand(line)
            continue
        }
        
        // Regular message
        message := Message{
            Username:  c.username,
            Content:   line,
            Timestamp: time.Now(),
            Type:      "message",
        }
        
        c.room.broadcast <- message
    }
    
    if err := scanner.Err(); err != nil {
        log.Printf("Error reading from client %s: %v", c.username, err)
    }
}

func (c *Client) handleCommand(command string) {
    parts := strings.Fields(command)
    if len(parts) == 0 {
        return
    }
    
    switch parts[0] {
    case "/quit", "/exit":
        c.conn.Close()
    case "/users":
        c.room.mutex.RLock()
        userList := make([]string, 0, len(c.room.clients))
        for client := range c.room.clients {
            userList = append(userList, client.username)
        }
        c.room.mutex.RUnlock()
        
        response := Message{
            Username:  "System",
            Content:   fmt.Sprintf("Online users: %s", strings.Join(userList, ", ")),
            Timestamp: time.Now(),
            Type:      "system",
        }
        c.sendMessage(response)
    case "/help":
        helpMsg := Message{
            Username:  "System",
            Content:   "Commands: /quit, /users, /help",
            Timestamp: time.Now(),
            Type:      "system",
        }
        c.sendMessage(helpMsg)
    }
}

func startChatServer() {
    listener, err := net.Listen("tcp", ":8080")
    if err != nil {
        log.Fatal("Error starting server:", err)
    }
    defer listener.Close()
    
    chatRoom := NewChatRoom()
    go chatRoom.Run()
    
    log.Println("Chat server started on :8080")
    
    for {
        conn, err := listener.Accept()
        if err != nil {
            log.Printf("Error accepting connection: %v", err)
            continue
        }
        
        go handleChatClient(conn, chatRoom)
    }
}

func handleChatClient(conn net.Conn, room *ChatRoom) {
    // Get username from client
    conn.Write([]byte("Enter your username: "))
    
    scanner := bufio.NewScanner(conn)
    if !scanner.Scan() {
        conn.Close()
        return
    }
    
    username := strings.TrimSpace(scanner.Text())
    if username == "" {
        conn.Write([]byte("Invalid username\n"))
        conn.Close()
        return
    }
    
    client := &Client{
        conn:     conn,
        username: username,
        room:     room,
    }
    
    room.register <- client
    
    // Send welcome message
    welcome := Message{
        Username:  "System",
        Content:   fmt.Sprintf("Welcome to the chat, %s!", username),
        Timestamp: time.Now(),
        Type:      "system",
    }
    client.sendMessage(welcome)
    
    // Start reading messages from client
    client.readMessages()
}

func startChatClient() {
    conn, err := net.Dial("tcp", "localhost:8080")
    if err != nil {
        log.Fatal("Error connecting to server:", err)
    }
    defer conn.Close()
    
    // Read messages from server in a goroutine
    go func() {
        scanner := bufio.NewScanner(conn)
        for scanner.Scan() {
            line := scanner.Text()
            
            // Try to parse as JSON message
            var msg Message
            if err := json.Unmarshal([]byte(line), &msg); err == nil {
                timestamp := msg.Timestamp.Format("15:04:05")
                switch msg.Type {
                case "message":
                    fmt.Printf("[%s] %s: %s\n", timestamp, msg.Username, msg.Content)
                case "join", "leave", "system":
                    fmt.Printf("[%s] %s\n", timestamp, msg.Content)
                }
            } else {
                // Plain text message (like username prompt)
                fmt.Print(line)
            }
        }
    }()
    
    // Read input from user and send to server
    scanner := bufio.NewScanner(os.Stdin)
    for scanner.Scan() {
        line := scanner.Text()
        if line == "" {
            continue
        }
        
        _, err := conn.Write([]byte(line + "\n"))
        if err != nil {
            log.Printf("Error sending message: %v", err)
            break
        }
        
        if line == "/quit" || line == "/exit" {
            break
        }
    }
}

func main() {
    if len(os.Args) < 2 {
        fmt.Println("Usage: go run main.go [server|client]")
        return
    }
    
    switch os.Args[1] {
    case "server":
        startChatServer()
    case "client":
        startChatClient()
    default:
        fmt.Println("Usage: go run main.go [server|client]")
    }
}
```

## Chapter 12: Real-World Applications

### Building a REST API

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
    "net/http"
    "strconv"
    "strings"
    "sync"
    "time"
    
    "github.com/gorilla/mux"
)

type Task struct {
    ID          int       `json:"id"`
    Title       string    `json:"title"`
    Description string    `json:"description"`
    Completed   bool      `json:"completed"`
    CreatedAt   time.Time `json:"created_at"`
    UpdatedAt   time.Time `json:"updated_at"`
}

type TaskStore struct {
    mutex sync.RWMutex
    tasks map[int]*Task
    nextID int
}

func NewTaskStore() *TaskStore {
    return &TaskStore{
        tasks:  make(map[int]*Task),
        nextID: 1,
    }
}

func (ts *TaskStore) GetAll() []*Task {
    ts.mutex.RLock()
    defer ts.mutex.RUnlock()
    
    tasks := make([]*Task, 0, len(ts.tasks))
    for _, task := range ts.tasks {
        tasks = append(tasks, task)
    }
    return tasks
}

func (ts *TaskStore) GetByID(id int) (*Task, bool) {
    ts.mutex.RLock()
    defer ts.mutex.RUnlock()
    
    task, exists := ts.tasks[id]
    return task, exists
}

func (ts *TaskStore) Create(title, description string) *Task {
    ts.mutex.Lock()
    defer ts.mutex.Unlock()
    
    task := &Task{
        ID:          ts.nextID,
        Title:       title,
        Description: description,
        Completed:   false,
        CreatedAt:   time.Now(),
        UpdatedAt:   time.Now(),
    }
    
    ts.tasks[ts.nextID] = task
    ts.nextID++
    
    return task
}

func (ts *TaskStore) Update(id int, title, description string, completed *bool) (*Task, bool) {
    ts.mutex.Lock()
    defer ts.mutex.Unlock()
    
    task, exists := ts.tasks[id]
    if !exists {
        return nil, false
    }
    
    if title != "" {
        task.Title = title
    }
    if description != "" {
        task.Description = description
    }
    if completed != nil {
        task.Completed = *completed
    }
    task.UpdatedAt = time.Now()
    
    return task, true
}

func (ts *TaskStore) Delete(id int) bool {
    ts.mutex.Lock()
    defer ts.mutex.Unlock()
    
    _, exists := ts.tasks[id]
    if exists {
        delete(ts.tasks, id)
    }
    return exists
}

type TaskAPI struct {
    store *TaskStore
}

func NewTaskAPI(store *TaskStore) *TaskAPI {
    return &TaskAPI{store: store}
}

func (api *TaskAPI) handleTasks(w http.ResponseWriter, r *http.Request) {
    switch r.Method {
    case "GET":
        api.getTasks(w, r)
    case "POST":
        api.createTask(w, r)
    default:
        http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
    }
}

func (api *TaskAPI) handleTask(w http.ResponseWriter, r *http.Request) {
    vars := mux.Vars(r)
    idStr, exists := vars["id"]
    if !exists {
        http.Error(w, "Task ID required", http.StatusBadRequest)
        return
    }
    
    id, err := strconv.Atoi(idStr)
    if err != nil {
        http.Error(w, "Invalid task ID", http.StatusBadRequest)
        return
    }
    
    switch r.Method {
    case "GET":
        api.getTask(w, r, id)
    case "PUT":
        api.updateTask(w, r, id)
    case "DELETE":
        api.deleteTask(w, r, id)
    default:
        http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
    }
}

func (api *TaskAPI) getTasks(w http.ResponseWriter, r *http.Request) {
    tasks := api.store.GetAll()
    
    w.Header().Set("Content-Type", "application/json")
    json.NewEncoder(w).Encode(map[string]interface{}{
        "tasks": tasks,
        "count": len(tasks),
    })
}

func (api *TaskAPI) getTask(w http.ResponseWriter, r *http.Request, id int) {
    task, exists := api.store.GetByID(id)
    if !exists {
        http.Error(w, "Task not found", http.StatusNotFound)
        return
    }
    
    w.Header().Set("Content-Type", "application/json")
    json.NewEncoder(w).Encode(task)
}

func (api *TaskAPI) createTask(w http.ResponseWriter, r *http.Request) {
    var req struct {
        Title       string `json:"title"`
        Description string `json:"description"`
    }
    
    if err := json.NewDecoder(r.Body).Decode(&req); err != nil {
        http.Error(w, "Invalid JSON", http.StatusBadRequest)
        return
    }
    
    if strings.TrimSpace(req.Title) == "" {
        http.Error(w, "Title is required", http.StatusBadRequest)
        return
    }
    
    task := api.store.Create(req.Title, req.Description)
    
    w.Header().Set("Content-Type", "application/json")
    w.WriteHeader(http.StatusCreated)
    json.NewEncoder(w).Encode(task)
}

func (api *TaskAPI) updateTask(w http.ResponseWriter, r *http.Request, id int) {
    var req struct {
        Title       string `json:"title"`
        Description string `json:"description"`
        Completed   *bool  `json:"completed"`
    }
    
    if err := json.NewDecoder(r.Body).Decode(&req); err != nil {
        http.Error(w, "Invalid JSON", http.StatusBadRequest)
        return
    }
    
    task, exists := api.store.Update(id, req.Title, req.Description, req.Completed)
    if !exists {
        http.Error(w, "Task not found", http.StatusNotFound)
        return
    }
    
    w.Header().Set("Content-Type", "application/json")
    json.NewEncoder(w).Encode(task)
}

func (api *TaskAPI) deleteTask(w http.ResponseWriter, r *http.Request, id int) {
    if !api.store.Delete(id) {
        http.Error(w, "Task not found", http.StatusNotFound)
        return
    }
    
    w.WriteHeader(http.StatusNoContent)
}

func (api *TaskAPI) setupRoutes() http.Handler {
    r := mux.NewRouter()
    
    // Middleware
    r.Use(func(next http.Handler) http.Handler {
        return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
            log.Printf("%s %s %s", r.Method, r.URL.Path, r.RemoteAddr)
            next.ServeHTTP(w, r)
        })
    })
    
    // Routes
    r.HandleFunc("/api/tasks", api.handleTasks).Methods("GET", "POST")
    r.HandleFunc("/api/tasks/{id:[0-9]+}", api.handleTask).Methods("GET", "PUT", "DELETE")
    
    // Health check
    r.HandleFunc("/health", func(w http.ResponseWriter, r *http.Request) {
        w.WriteHeader(http.StatusOK)
        json.NewEncoder(w).Encode(map[string]string{
            "status": "healthy",
            "time":   time.Now().Format(time.RFC3339),
        })
    }).Methods("GET")
    
    return r
}

func main() {
    store := NewTaskStore()
    api := NewTaskAPI(store)
    
    // Add some sample tasks
    store.Create("Learn Go", "Complete Go tutorial")
    store.Create("Build API", "Create REST API with Go")
    
    handler := api.setupRoutes()
    
    fmt.Println("Server starting on :8080")
    log.Fatal(http.ListenAndServe(":8080", handler))
}
```

### Web Development with Go

#### Building Web Servers

Go's `net/http` package makes it easy to build web servers and APIs:

```go
package main

import (
    "fmt"
    "html/template"
    "log"
    "net/http"
    "strconv"
    "time"
)

type User struct {
    ID       int
    Name     string
    Email    string
    JoinDate time.Time
}

type WebApp struct {
    users    []User
    template *template.Template
}

func NewWebApp() *WebApp {
    // Sample users
    users := []User{
        {1, "Alice Johnson", "alice@example.com", time.Now().AddDate(0, -3, 0)},
        {2, "Bob Smith", "bob@example.com", time.Now().AddDate(0, -1, -15)},
        {3, "Carol Davis", "carol@example.com", time.Now().AddDate(0, 0, -7)},
    }

    // Parse templates
    tmpl := template.Must(template.New("").Funcs(template.FuncMap{
        "formatDate": func(t time.Time) string {
            return t.Format("2006-01-02")
        },
    }).ParseGlob("templates/*.html"))

    return &WebApp{
        users:    users,
        template: tmpl,
    }
}

func (wa *WebApp) homeHandler(w http.ResponseWriter, r *http.Request) {
    data := struct {
        Title string
        Users []User
    }{
        Title: "User Management System",
        Users: wa.users,
    }

    if err := wa.template.ExecuteTemplate(w, "home.html", data); err != nil {
        http.Error(w, err.Error(), http.StatusInternalServerError)
        return
    }
}

func (wa *WebApp) userHandler(w http.ResponseWriter, r *http.Request) {
    idStr := r.URL.Query().Get("id")
    if idStr == "" {
        http.Error(w, "Missing user ID", http.StatusBadRequest)
        return
    }

    id, err := strconv.Atoi(idStr)
    if err != nil {
        http.Error(w, "Invalid user ID", http.StatusBadRequest)
        return
    }

    var user *User
    for _, u := range wa.users {
        if u.ID == id {
            user = &u
            break
        }
    }

    if user == nil {
        http.Error(w, "User not found", http.StatusNotFound)
        return
    }

    data := struct {
        Title string
        User  User
    }{
        Title: fmt.Sprintf("User: %s", user.Name),
        User:  *user,
    }

    if err := wa.template.ExecuteTemplate(w, "user.html", data); err != nil {
        http.Error(w, err.Error(), http.StatusInternalServerError)
        return
    }
}

func (wa *WebApp) apiUsersHandler(w http.ResponseWriter, r *http.Request) {
    w.Header().Set("Content-Type", "application/json")
    
    switch r.Method {
    case "GET":
        // Return all users as JSON
        jsonData, err := json.Marshal(wa.users)
        if err != nil {
            http.Error(w, err.Error(), http.StatusInternalServerError)
            return
        }
        w.Write(jsonData)
        
    case "POST":
        // Add new user (simplified example)
        var newUser User
        if err := json.NewDecoder(r.Body).Decode(&newUser); err != nil {
            http.Error(w, err.Error(), http.StatusBadRequest)
            return
        }
        
        newUser.ID = len(wa.users) + 1
        newUser.JoinDate = time.Now()
        wa.users = append(wa.users, newUser)
        
        w.WriteHeader(http.StatusCreated)
        json.NewEncoder(w).Encode(newUser)
        
    default:
        http.Error(w, "Method not allowed", http.StatusMethodNotAllowed)
    }
}

func (wa *WebApp) setupRoutes() {
    // Serve static files
    http.Handle("/static/", http.StripPrefix("/static/", http.FileServer(http.Dir("static"))))
    
    // Web pages
    http.HandleFunc("/", wa.homeHandler)
    http.HandleFunc("/user", wa.userHandler)
    
    // API endpoints
    http.HandleFunc("/api/users", wa.apiUsersHandler)
    
    // Health check
    http.HandleFunc("/health", func(w http.ResponseWriter, r *http.Request) {
        w.WriteHeader(http.StatusOK)
        fmt.Fprintf(w, "OK")
    })
}

func startWebServer() {
    app := NewWebApp()
    app.setupRoutes()
    
    fmt.Println("Web server starting on http://localhost:8080")
    log.Fatal(http.ListenAndServe(":8080", nil))
}
```

#### Middleware and Advanced Patterns

```go
import (
    "context"
    "log"
    "net/http"
    "time"
)

// Middleware for logging requests
func loggingMiddleware(next http.Handler) http.Handler {
    return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
        start := time.Now()
        
        // Create a custom ResponseWriter to capture status code
        ww := &responseWriter{ResponseWriter: w, statusCode: http.StatusOK}
        
        next.ServeHTTP(ww, r)
        
        duration := time.Since(start)
        log.Printf("%s %s %d %v", r.Method, r.URL.Path, ww.statusCode, duration)
    })
}

type responseWriter struct {
    http.ResponseWriter
    statusCode int
}

func (rw *responseWriter) WriteHeader(code int) {
    rw.statusCode = code
    rw.ResponseWriter.WriteHeader(code)
}

// Authentication middleware
func authMiddleware(next http.Handler) http.Handler {
    return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
        apiKey := r.Header.Get("X-API-Key")
        if apiKey == "" {
            http.Error(w, "Missing API key", http.StatusUnauthorized)
            return
        }
        
        // In a real app, validate the API key against a database
        if apiKey != "valid-api-key" {
            http.Error(w, "Invalid API key", http.StatusUnauthorized)
            return
        }
        
        // Add user info to context
        ctx := context.WithValue(r.Context(), "user", "authenticated-user")
        next.ServeHTTP(w, r.WithContext(ctx))
    })
}

// CORS middleware
func corsMiddleware(next http.Handler) http.Handler {
    return http.HandlerFunc(func(w http.ResponseWriter, r *http.Request) {
        w.Header().Set("Access-Control-Allow-Origin", "*")
        w.Header().Set("Access-Control-Allow-Methods", "GET, POST, PUT, DELETE, OPTIONS")
        w.Header().Set("Access-Control-Allow-Headers", "Content-Type, Authorization, X-API-Key")
        
        if r.Method == "OPTIONS" {
            w.WriteHeader(http.StatusOK)
            return
        }
        
        next.ServeHTTP(w, r)
    })
}

// Chain multiple middleware
func chainMiddleware(h http.Handler, middleware ...func(http.Handler) http.Handler) http.Handler {
    for _, m := range middleware {
        h = m(h)
    }
    return h
}
```

### Testing in Go

#### Unit Testing Fundamentals

Go has excellent built-in testing support through the `testing` package:

```go
// math_utils.go
package mathutils

import (
    "errors"
    "math"
)

// Add two numbers
func Add(a, b float64) float64 {
    return a + b
}

// Subtract two numbers
func Subtract(a, b float64) float64 {
    return a - b
}

// Divide two numbers
func Divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}

// Calculate square root
func Sqrt(x float64) (float64, error) {
    if x < 0 {
        return 0, errors.New("square root of negative number")
    }
    return math.Sqrt(x), nil
}

// IsPrime checks if a number is prime
func IsPrime(n int) bool {
    if n < 2 {
        return false
    }
    if n == 2 {
        return true
    }
    if n%2 == 0 {
        return false
    }
    
    for i := 3; i*i <= n; i += 2 {
        if n%i == 0 {
            return false
        }
    }
    return true
}
```

```go
// math_utils_test.go
package mathutils

import (
    "math"
    "testing"
)

func TestAdd(t *testing.T) {
    tests := []struct {
        name string
        a, b float64
        want float64
    }{
        {"positive numbers", 2.5, 3.7, 6.2},
        {"negative numbers", -1.5, -2.3, -3.8},
        {"mixed signs", -5, 3, -2},
        {"zeros", 0, 0, 0},
        {"large numbers", 1e10, 2e10, 3e10},
    }

    for _, tt := range tests {
        t.Run(tt.name, func(t *testing.T) {
            got := Add(tt.a, tt.b)
            if math.Abs(got-tt.want) > 1e-9 {
                t.Errorf("Add(%v, %v) = %v, want %v", tt.a, tt.b, got, tt.want)
            }
        })
    }
}

func TestDivide(t *testing.T) {
    t.Run("normal division", func(t *testing.T) {
        got, err := Divide(10, 2)
        if err != nil {
            t.Errorf("Divide(10, 2) returned unexpected error: %v", err)
        }
        if got != 5 {
            t.Errorf("Divide(10, 2) = %v, want 5", got)
        }
    })

    t.Run("division by zero", func(t *testing.T) {
        _, err := Divide(10, 0)
        if err == nil {
            t.Error("Divide(10, 0) should return an error")
        }
        if err.Error() != "division by zero" {
            t.Errorf("Divide(10, 0) error = %v, want 'division by zero'", err)
        }
    })
}

func TestSqrt(t *testing.T) {
    tests := []struct {
        name    string
        input   float64
        want    float64
        wantErr bool
    }{
        {"positive number", 16, 4, false},
        {"zero", 0, 0, false},
        {"perfect square", 25, 5, false},
        {"negative number", -4, 0, true},
    }

    for _, tt := range tests {
        t.Run(tt.name, func(t *testing.T) {
            got, err := Sqrt(tt.input)
            
            if tt.wantErr {
                if err == nil {
                    t.Errorf("Sqrt(%v) should return an error", tt.input)
                }
                return
            }
            
            if err != nil {
                t.Errorf("Sqrt(%v) returned unexpected error: %v", tt.input, err)
            }
            
            if math.Abs(got-tt.want) > 1e-9 {
                t.Errorf("Sqrt(%v) = %v, want %v", tt.input, got, tt.want)
            }
        })
    }
}

func TestIsPrime(t *testing.T) {
    primes := []int{2, 3, 5, 7, 11, 13, 17, 19, 23, 29}
    composites := []int{4, 6, 8, 9, 10, 12, 14, 15, 16, 18}
    
    for _, p := range primes {
        t.Run(fmt.Sprintf("prime_%d", p), func(t *testing.T) {
            if !IsPrime(p) {
                t.Errorf("IsPrime(%d) = false, want true", p)
            }
        })
    }
    
    for _, c := range composites {
        t.Run(fmt.Sprintf("composite_%d", c), func(t *testing.T) {
            if IsPrime(c) {
                t.Errorf("IsPrime(%d) = true, want false", c)
            }
        })
    }
    
    // Edge cases
    if IsPrime(0) {
        t.Error("IsPrime(0) = true, want false")
    }
    if IsPrime(1) {
        t.Error("IsPrime(1) = true, want false")
    }
}
```

#### Benchmarking and Performance Testing

```go
func BenchmarkAdd(b *testing.B) {
    for i := 0; i < b.N; i++ {
        Add(123.456, 789.012)
    }
}

func BenchmarkIsPrime(b *testing.B) {
    numbers := []int{997, 1009, 1013, 1019, 1021}
    
    b.ResetTimer()
    for i := 0; i < b.N; i++ {
        for _, num := range numbers {
            IsPrime(num)
        }
    }
}

func BenchmarkIsPrimeLarge(b *testing.B) {
    largeNumber := 1000003 // Large prime number
    
    b.ResetTimer()
    for i := 0; i < b.N; i++ {
        IsPrime(largeNumber)
    }
}

// Example of table-driven benchmarks
func BenchmarkSqrt(b *testing.B) {
    benchmarks := []struct {
        name  string
        input float64
    }{
        {"small", 4},
        {"medium", 1000},
        {"large", 1000000},
    }
    
    for _, bm := range benchmarks {
        b.Run(bm.name, func(b *testing.B) {
            for i := 0; i < b.N; i++ {
                Sqrt(bm.input)
            }
        })
    }
}
```

#### Integration Testing and Test Helpers

```go
// user_service.go
package main

import (
    "database/sql"
    "fmt"
)

type UserService struct {
    db *sql.DB
}

type User struct {
    ID    int    `json:"id"`
    Name  string `json:"name"`
    Email string `json:"email"`
}

func NewUserService(db *sql.DB) *UserService {
    return &UserService{db: db}
}

func (s *UserService) CreateUser(name, email string) (*User, error) {
    query := `INSERT INTO users (name, email) VALUES (?, ?) RETURNING id`
    var id int
    err := s.db.QueryRow(query, name, email).Scan(&id)
    if err != nil {
        return nil, fmt.Errorf("failed to create user: %w", err)
    }
    
    return &User{ID: id, Name: name, Email: email}, nil
}

func (s *UserService) GetUser(id int) (*User, error) {
    query := `SELECT id, name, email FROM users WHERE id = ?`
    user := &User{}
    err := s.db.QueryRow(query, id).Scan(&user.ID, &user.Name, &user.Email)
    if err != nil {
        return nil, fmt.Errorf("failed to get user: %w", err)
    }
    
    return user, nil
}
```

```go
// user_service_test.go
package main

import (
    "database/sql"
    "testing"
    
    _ "github.com/mattn/go-sqlite3"
)

func setupTestDB(t *testing.T) *sql.DB {
    db, err := sql.Open("sqlite3", ":memory:")
    if err != nil {
        t.Fatalf("Failed to open test database: %v", err)
    }
    
    // Create table
    query := `
    CREATE TABLE users (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        name TEXT NOT NULL,
        email TEXT NOT NULL UNIQUE
    )`
    
    if _, err := db.Exec(query); err != nil {
        t.Fatalf("Failed to create table: %v", err)
    }
    
    return db
}

func TestUserService_CreateUser(t *testing.T) {
    db := setupTestDB(t)
    defer db.Close()
    
    service := NewUserService(db)
    
    user, err := service.CreateUser("John Doe", "john@example.com")
    if err != nil {
        t.Fatalf("CreateUser failed: %v", err)
    }
    
    if user.Name != "John Doe" {
        t.Errorf("Expected name 'John Doe', got '%s'", user.Name)
    }
    
    if user.Email != "john@example.com" {
        t.Errorf("Expected email 'john@example.com', got '%s'", user.Email)
    }
    
    if user.ID <= 0 {
        t.Errorf("Expected positive ID, got %d", user.ID)
    }
}

func TestUserService_GetUser(t *testing.T) {
    db := setupTestDB(t)
    defer db.Close()
    
    service := NewUserService(db)
    
    // Create a user first
    created, err := service.CreateUser("Jane Smith", "jane@example.com")
    if err != nil {
        t.Fatalf("Setup failed: %v", err)
    }
    
    // Get the user
    retrieved, err := service.GetUser(created.ID)
    if err != nil {
        t.Fatalf("GetUser failed: %v", err)
    }
    
    if retrieved.ID != created.ID {
        t.Errorf("Expected ID %d, got %d", created.ID, retrieved.ID)
    }
    
    if retrieved.Name != created.Name {
        t.Errorf("Expected name '%s', got '%s'", created.Name, retrieved.Name)
    }
    
    if retrieved.Email != created.Email {
        t.Errorf("Expected email '%s', got '%s'", created.Email, retrieved.Email)
    }
}

// Test helper for creating test users
func createTestUser(t *testing.T, service *UserService, name, email string) *User {
    t.Helper()
    
    user, err := service.CreateUser(name, email)
    if err != nil {
        t.Fatalf("Failed to create test user: %v", err)
    }
    
    return user
}

func TestUserService_Integration(t *testing.T) {
    db := setupTestDB(t)
    defer db.Close()
    
    service := NewUserService(db)
    
    // Create multiple users using helper
    users := []*User{
        createTestUser(t, service, "Alice", "alice@example.com"),
        createTestUser(t, service, "Bob", "bob@example.com"),
        createTestUser(t, service, "Carol", "carol@example.com"),
    }
    
    // Verify all users can be retrieved
    for _, expected := range users {
        retrieved, err := service.GetUser(expected.ID)
        if err != nil {
            t.Errorf("Failed to retrieve user %d: %v", expected.ID, err)
            continue
        }
        
        if retrieved.Name != expected.Name {
            t.Errorf("User %d: expected name '%s', got '%s'", 
                expected.ID, expected.Name, retrieved.Name)
        }
    }
}
```

### Command Line Tool

```go
package main

import (
    "encoding/json"
    "flag"
    "fmt"
    "os"
    "path/filepath"
    "strings"
    "time"
)

type Config struct {
    DataDir     string `json:"data_dir"`
    DateFormat  string `json:"date_format"`
    DefaultTags []string `json:"default_tags"`
}

type Note struct {
    ID        string    `json:"id"`
    Title     string    `json:"title"`
    Content   string    `json:"content"`
    Tags      []string  `json:"tags"`
    CreatedAt time.Time `json:"created_at"`
    UpdatedAt time.Time `json:"updated_at"`
}

type NoteCLI struct {
    config *Config
    dataDir string
}

func NewNoteCLI() *NoteCLI {
    homeDir, _ := os.UserHomeDir()
    dataDir := filepath.Join(homeDir, ".notes")
    
    config := &Config{
        DataDir:     dataDir,
        DateFormat:  "2006-01-02 15:04:05",
        DefaultTags: []string{},
    }
    
    return &NoteCLI{
        config:  config,
        dataDir: dataDir,
    }
}

func (cli *NoteCLI) ensureDataDir() error {
    return os.MkdirAll(cli.dataDir, 0755)
}

func (cli *NoteCLI) generateID() string {
    return fmt.Sprintf("note_%d", time.Now().Unix())
}

func (cli *NoteCLI) getNotePath(id string) string {
    return filepath.Join(cli.dataDir, id+".json")
}

func (cli *NoteCLI) saveNote(note *Note) error {
    if err := cli.ensureDataDir(); err != nil {
        return err
    }
    
    path := cli.getNotePath(note.ID)
    file, err := os.Create(path)
    if err != nil {
        return err
    }
    defer file.Close()
    
    encoder := json.NewEncoder(file)
    encoder.SetIndent("", "  ")
    return encoder.Encode(note)
}

func (cli *NoteCLI) loadNote(id string) (*Note, error) {
    path := cli.getNotePath(id)
    file, err := os.Open(path)
    if err != nil {
        return nil, err
    }
    defer file.Close()
    
    var note Note
    if err := json.NewDecoder(file).Decode(&note); err != nil {
        return nil, err
    }
    
    return &note, nil
}

func (cli *NoteCLI) listNotes() ([]*Note, error) {
    if err := cli.ensureDataDir(); err != nil {
        return nil, err
    }
    
    entries, err := os.ReadDir(cli.dataDir)
    if err != nil {
        return nil, err
    }
    
    var notes []*Note
    for _, entry := range entries {
        if !entry.IsDir() && strings.HasSuffix(entry.Name(), ".json") {
            id := strings.TrimSuffix(entry.Name(), ".json")
            if note, err := cli.loadNote(id); err == nil {
                notes = append(notes, note)
            }
        }
    }
    
    return notes, nil
}

func (cli *NoteCLI) deleteNote(id string) error {
    path := cli.getNotePath(id)
    return os.Remove(path)
}

func (cli *NoteCLI) createNote(title, content string, tags []string) error {
    note := &Note{
        ID:        cli.generateID(),
        Title:     title,
        Content:   content,
        Tags:      tags,
        CreatedAt: time.Now(),
        UpdatedAt: time.Now(),
    }
    
    if err := cli.saveNote(note); err != nil {
        return err
    }
    
    fmt.Printf("Created note: %s (ID: %s)\n", note.Title, note.ID)
    return nil
}

func (cli *NoteCLI) showNote(id string) error {
    note, err := cli.loadNote(id)
    if err != nil {
        return fmt.Errorf("note not found: %s", id)
    }
    
    fmt.Printf("ID: %s\n", note.ID)
    fmt.Printf("Title: %s\n", note.Title)
    fmt.Printf("Tags: %s\n", strings.Join(note.Tags, ", "))
    fmt.Printf("Created: %s\n", note.CreatedAt.Format(cli.config.DateFormat))
    fmt.Printf("Updated: %s\n", note.UpdatedAt.Format(cli.config.DateFormat))
    fmt.Printf("\nContent:\n%s\n", note.Content)
    
    return nil
}

func (cli *NoteCLI) listAllNotes() error {
    notes, err := cli.listNotes()
    if err != nil {
        return err
    }
    
    if len(notes) == 0 {
        fmt.Println("No notes found.")
        return nil
    }
    
    fmt.Printf("Found %d note(s):\n\n", len(notes))
    for _, note := range notes {
        fmt.Printf("ID: %s\n", note.ID)
        fmt.Printf("Title: %s\n", note.Title)
        fmt.Printf("Tags: %s\n", strings.Join(note.Tags, ", "))
        fmt.Printf("Created: %s\n", note.CreatedAt.Format(cli.config.DateFormat))
        fmt.Printf("Updated: %s\n", note.UpdatedAt.Format(cli.config.DateFormat))
        fmt.Printf("Content preview: %s...\n", truncateString(note.Content, 50))
        fmt.Println(strings.Repeat("-", 40))
    }
    
    return nil
}

func truncateString(s string, length int) string {
    if len(s) <= length {
        return s
    }
    return s[:length] + "..."
}

func main() {
    if len(os.Args) < 2 {
        fmt.Println("Usage: notes <command> [args...]")
        fmt.Println("Commands:")
        fmt.Println("  create <title> <content> [tags...]  - Create a new note")
        fmt.Println("  show <id>                          - Show a note")
        fmt.Println("  list                               - List all notes")
        fmt.Println("  delete <id>                        - Delete a note")
        return
    }

    cli := NewNoteCLI()
    
    command := os.Args[1]
    switch command {
    case "create":
        if len(os.Args) < 4 {
            fmt.Println("Usage: notes create <title> <content> [tags...]")
            return
        }
        
        title := os.Args[2]
        content := os.Args[3]
        tags := cli.config.DefaultTags
        
        if len(os.Args) > 4 {
            tags = append(tags, os.Args[4:]...)
        }
        
        if err := cli.createNote(title, content, tags); err != nil {
            fmt.Printf("Error creating note: %v\n", err)
        }
        
    case "show":
        if len(os.Args) < 3 {
            fmt.Println("Usage: notes show <id>")
            return
        }
        
        if err := cli.showNote(os.Args[2]); err != nil {
            fmt.Printf("Error showing note: %v\n", err)
        }
        
    case "list":
        if err := cli.listAllNotes(); err != nil {
            fmt.Printf("Error listing notes: %v\n", err)
        }
        
    case "delete":
        if len(os.Args) < 3 {
            fmt.Println("Usage: notes delete <id>")
            return
        }
        
        if err := cli.deleteNote(os.Args[2]); err != nil {
            fmt.Printf("Error deleting note: %v\n", err)
        } else {
            fmt.Printf("Note %s deleted successfully\n", os.Args[2])
        }
        
    default:
        fmt.Printf("Unknown command: %s\n", command)
        fmt.Println("Use 'notes' without arguments to see usage information")
    }
}
```

---

## 🎯 Conclusion

Congratulations! You've completed this comprehensive Go programming guide. Throughout this journey, you've learned:

### Key Takeaways

1. **Language Fundamentals**
   - Go's simple yet powerful syntax
   - Strong type system with inference
   - Excellent error handling patterns
   - Built-in concurrency primitives

2. **Advanced Features**
   - Goroutines and channels for concurrent programming
   - Interfaces for clean abstractions
   - Reflection for dynamic programming
   - Generics for type-safe generic code

3. **Real-World Applications**
   - Building REST APIs and microservices
   - Network programming and protocols
   - Command-line tools and utilities
   - Concurrent and parallel processing

4. **Best Practices**
   - Clear, readable code structure
   - Proper error handling and resource management
   - Effective use of Go's concurrency model
   - Testing and documentation strategies

### Final Words

Go's philosophy of simplicity, clarity, and efficiency makes it an excellent choice for modern software development. Whether you're building web services, command-line tools, or distributed systems, Go provides the tools and patterns you need to write reliable, maintainable code.

Remember:
- **Keep it simple** - Go rewards straightforward solutions
- **Handle errors explicitly** - Don't ignore what can go wrong
- **Use goroutines wisely** - Concurrency is powerful but requires careful design
- **Write tests** - Go's testing tools make it easy to ensure code quality
- **Read the standard library** - It's well-designed and full of examples

Continue exploring Go's ecosystem, contribute to open source projects, and most importantly, keep building! The Go community is welcoming and always ready to help.

Happy coding with Go! 🚀

---

## 📋 Appendices

### 📖 Glossary

**Channel** - A typed conduit through which you can send and receive values with the channel operator, `<-`.

**Concurrency** - The composition of independently executing processes, while parallelism is the simultaneous execution of (possibly related) computations.

**Defer** - A Go statement that schedules a function call to be run immediately before the function executing the defer returns.

**Embedding** - A way to include one struct type as a field of another struct type, providing a form of inheritance-like behavior.

**Garbage Collection** - Automatic memory management feature that reclaims memory occupied by objects that are no longer in use.

**Generic** - A programming paradigm that allows writing functions and data structures that work with any type.

**Go Module** - A collection of Go packages stored in a file tree with a go.mod file at its root.

**Goroutine** - A lightweight thread managed by the Go runtime. Goroutines run in the same address space.

**Interface** - A type that specifies a method set. A variable of interface type can store a value of any type that implements those methods.

**Method** - A function with a special receiver argument that appears between the func keyword and the method name.

**Package** - A way to group related Go source files together. Every Go source file belongs to a package.

**Panic** - A built-in function that stops the ordinary flow of control and begins panicking.

**Pointer** - A variable that stores the memory address of another variable.

**Receiver** - The argument that appears between the func keyword and the method name in a method declaration.

**Reflection** - The ability of a program to examine its own structure, particularly through types.

**Slice** - A flexible view into the elements of an array. Unlike arrays, slices are dynamic and can grow and shrink.

**Struct** - A composite data type that groups together variables under a single name.

**Type Assertion** - An operation applied to an interface value to extract the concrete value stored in the interface.

**Variadic Function** - A function that accepts a variable number of arguments.

### 🔗 Quick Reference Card

#### Basic Syntax
```go
var name string                    // Variable declaration
var x, y int = 1, 2               // Multiple variables

const Pi = 3.14159                // Constant
const (                           // Constant block
    Red = iota
    Green
    Blue
)

func add(a, b int) int {          // Function
    return a + b
}

func divmod(a, b int) (int, int) { // Multiple returns
    return a / b, a % b
}
```

#### Control Structures
```go
// If statement
if x > 0 {
    // do something
} else if x < 0 {
    // do something else
} else {
    // do default
}

// For loop
for i := 0; i < 10; i++ {
    // loop body
}

// While-style loop
for condition {
    // loop body
}

// Range loop
for i, v := range slice {
    // use i and v
}

// Switch statement
switch value {
case 1:
    // case 1
case 2, 3:
    // case 2 or 3
default:
    // default case
}
```

#### Data Structures
```go
var arr [5]int                    // Array
slice := []int{1, 2, 3}          // Slice
slice = append(slice, 4)         // Append to slice

var m map[string]int             // Map
m = make(map[string]int)         // Initialize map
m["key"] = 42                    // Set value

type Person struct {             // Struct
    Name string
    Age  int
}

var p Person                     // Struct instance
p = Person{                      // Struct literal
    Name: "Alice",
    Age:  30,
}
```

#### Error Handling
```go
func doSomething() error {
    if somethingWrong {
        return errors.New("something went wrong")
    }
    return nil
}

result, err := doSomething()
if err != nil {
    log.Fatal(err)
}
```

#### Concurrency
```go
go func() {                      // Goroutine
    // concurrent code
}()

ch := make(chan int)             // Channel
go func() {
    ch <- 42                     // Send to channel
}()
value := <-ch                    // Receive from channel

select {                         // Select statement
case v := <-ch1:
    // handle v from ch1
case ch2 <- value:
    // send value to ch2
default:
    // no channel ready
}
```

### 📚 Further Reading

#### Official Resources
- **Go Official Website**: [golang.org](https://golang.org)
- **Go Documentation**: [pkg.go.dev](https://pkg.go.dev)
- **Go Blog**: [blog.golang.org](https://blog.golang.org)
- **Go Specification**: [golang.org/ref/spec](https://golang.org/ref/spec)

#### Essential Books
- **"The Go Programming Language"** by Alan Donovan and Brian Kernighan
- **"Go in Action"** by William Kennedy, Brian Ketelsen, and Erik St. Martin
- **"Concurrency in Go"** by Katherine Cox-Buday
- **"Go Web Programming"** by Sau Sheong Chang

#### Advanced Topics
- **Go Memory Model**: [golang.org/ref/mem](https://golang.org/ref/mem)
- **Effective Go**: [golang.org/doc/effective_go](https://golang.org/doc/effective_go)
- **Go Code Review Comments**: [github.com/golang/go/wiki/CodeReviewComments](https://github.com/golang/go/wiki/CodeReviewComments)

#### Tools and Libraries
- **Popular Go Libraries**: [awesome-go.com](https://awesome-go.com)
- **Go Modules Reference**: [golang.org/ref/mod](https://golang.org/ref/mod)
- **Go Testing**: [golang.org/doc/tutorial/add-a-test](https://golang.org/doc/tutorial/add-a-test)

### 🤝 Community Resources

#### Online Communities
- **Go Forum**: [forum.golangbridge.org](https://forum.golangbridge.org)
- **Reddit**: [r/golang](https://reddit.com/r/golang)
- **Stack Overflow**: [stackoverflow.com/questions/tagged/go](https://stackoverflow.com/questions/tagged/go)
- **Gopher Slack**: [gophers.slack.com](https://gophers.slack.com)

#### Conferences and Events
- **GopherCon**: The largest Go conference worldwide
- **dotGo**: European Go conference
- **Go meetups**: Local Go user groups in major cities
- **Go training workshops**: Official and community-run training sessions

#### Learning Platforms
- **Go by Example**: [gobyexample.com](https://gobyexample.com)
- **A Tour of Go**: [tour.golang.org](https://tour.golang.org)
- **Go Playground**: [play.golang.org](https://play.golang.org)
- **Exercism Go Track**: [exercism.io/tracks/go](https://exercism.io/tracks/go)

#### Open Source Projects
- **Kubernetes**: Container orchestration platform
- **Docker**: Container platform (partially written in Go)
- **Prometheus**: Monitoring and alerting toolkit
- **Terraform**: Infrastructure as code tool
- **Hugo**: Static site generator
- **Gin**: HTTP web framework

### 💝 Contributing Guidelines

#### Getting Started with Go Development
1. **Set up your development environment**
   - Install Go from [golang.org/dl](https://golang.org/dl)
   - Configure your GOPATH and GOROOT
   - Choose an IDE or editor with Go support

2. **Learn Go conventions**
   - Read the Go Code Review Comments
   - Study the standard library code
   - Use `gofmt` to format your code
   - Run `go vet` to catch common errors

3. **Practice with small projects**
   - Start with simple command-line tools
   - Build web APIs using standard library
   - Experiment with goroutines and channels
   - Write comprehensive tests for your code

4. **Engage with the community**
   - Join Go forums and slack channels
   - Attend local Go meetups
   - Follow Go blogs and newsletters
   - Share your Go projects and learnings

#### Contributing to Open Source Go Projects
1. **Find projects that interest you**
   - Look for "good first issue" labels
   - Start with documentation improvements
   - Fix small bugs or add minor features
   - Contribute to testing and code review

2. **Follow project guidelines**
   - Read the CONTRIBUTING.md file
   - Follow the project's code style
   - Write clear commit messages
   - Include tests with your changes

3. **Best practices for contributions**
   - Start small and build trust
   - Ask questions when unsure
   - Be responsive to feedback
   - Help review other contributors' work

---

*This documentation covers Go fundamentals through advanced topics. For the latest updates and additional resources, visit [golang.org](https://golang.org) and [pkg.go.dev](https://pkg.go.dev).*