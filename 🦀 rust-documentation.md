# 🦀 Rust Documentation
*Version: 1.70+ | Last Updated: December 2024*

Rust is a systems programming language that runs blazingly fast, prevents segfaults, and guarantees thread safety. It combines the performance of low-level languages with the safety and expressiveness of high-level languages.

## 📋 Table of Contents

### 🚀 [Chapter 1: Introduction & Setup](#chapter-1-introduction--setup)
- [What is Rust?](#what-is-rust)
- [Why Choose Rust?](#why-choose-rust)
- [Installation and Setup](#installation-and-setup)
- [Development Environment](#development-environment)
- [Hello World](#hello-world)

### 🎯 [Chapter 2: Rust Fundamentals](#chapter-2-rust-fundamentals)
- [Basic Syntax](#basic-syntax)
- [Variables and Mutability](#variables-and-mutability)
- [Data Types](#data-types)
- [Functions](#functions)
- [Control Flow](#control-flow)

### 🔐 [Chapter 3: Ownership and Borrowing](#chapter-3-ownership-and-borrowing)
- [Understanding Ownership](#understanding-ownership)
- [References and Borrowing](#references-and-borrowing)
- [The Slice Type](#the-slice-type)
- [Lifetime Annotations](#lifetime-annotations)

### 📦 [Chapter 4: Structs and Enums](#chapter-4-structs-and-enums)
- [Defining Structs](#defining-structs)
- [Method Syntax](#method-syntax)
- [Enumerations](#enumerations)
- [Pattern Matching](#pattern-matching)

### 🔧 [Chapter 5: Collections and Iterators](#chapter-5-collections-and-iterators)
- [Vectors](#vectors)
- [Hash Maps](#hash-maps)
- [Strings](#strings)
- [Iterator Patterns](#iterator-patterns)

### ⚠️ [Chapter 6: Error Handling](#chapter-6-error-handling)
- [Panic and Unrecoverable Errors](#panic-and-unrecoverable-errors)
- [Result Type](#result-type)
- [Error Propagation](#error-propagation)
- [Custom Error Types](#custom-error-types)

### 📚 [Chapter 7: Modules and Packages](#chapter-7-modules-and-packages)
- [Module System](#module-system)
- [Packages and Crates](#packages-and-crates)
- [Use Keyword](#use-keyword)
- [Publishing Crates](#publishing-crates)

### 🧬 [Chapter 8: Generic Types and Traits](#chapter-8-generic-types-and-traits)
- [Generic Functions and Structs](#generic-functions-and-structs)
- [Trait Definitions](#trait-definitions)
- [Trait Bounds](#trait-bounds)
- [Associated Types](#associated-types)

### 🔄 [Chapter 9: Advanced Features](#chapter-9-advanced-features)
- [Closures](#closures)
- [Smart Pointers](#smart-pointers)
- [Unsafe Rust](#unsafe-rust)
- [Macros](#macros)

### ⚡ [Chapter 10: Concurrency](#chapter-10-concurrency)
- [Threads](#threads)
- [Message Passing](#message-passing)
- [Shared State](#shared-state)
- [Async Programming](#async-programming)

### 🚀 [Chapter 11: Real-World Applications](#chapter-11-real-world-applications)
- [CLI Application Project](#cli-application-project)
- [Web Server Project](#web-server-project)
- [System Programming](#system-programming)
- [Performance Optimization](#performance-optimization)

### 📖 [Appendices](#appendices)
- [Glossary](#glossary)
- [Quick Reference Card](#quick-reference-card)
- [Further Reading](#further-reading)
- [Community Resources](#community-resources)
- [Contributing Guidelines](#contributing-guidelines)

---

## Chapter 1: Introduction & Setup
📊 **Progress:** Chapter 1 of 11 | 🎯 **Learning Objectives:** Understanding Rust basics, setting up development environment | ⏱️ **Estimated Time:** 30 minutes | 📋 **Prerequisites:** Basic programming knowledge

### What is Rust?

Rust is a modern systems programming language developed by Mozilla Research, first appearing in 2010 and reaching version 1.0 in 2015. It was designed to be a safe, concurrent, and practical language that prevents common programming errors like null pointer dereferences, buffer overflows, and memory leaks at compile time.

Rust achieves memory safety without garbage collection by using a unique ownership system that tracks how memory is used throughout a program's lifecycle. This makes it ideal for applications where performance and safety are critical, such as operating systems, web browsers, game engines, and blockchain systems.

The language combines the performance characteristics of low-level languages like C and C++ with the safety guarantees typically found in high-level languages. This unique positioning has made Rust increasingly popular for system-level programming, web services, and even application development.

### Why Choose Rust?

Rust offers several compelling advantages that make it an excellent choice for modern software development:

**Memory Safety Without Garbage Collection**: Rust's ownership system prevents memory-related bugs like use-after-free, double-free, and memory leaks at compile time, without the runtime overhead of garbage collection. This makes programs both safe and fast.

**Zero-Cost Abstractions**: High-level features in Rust compile down to the same assembly code you would write by hand. You get the expressiveness of high-level programming without sacrificing performance.

**Fearless Concurrency**: Rust's type system prevents data races at compile time, making concurrent programming safer and more accessible. You can write parallel code with confidence that it won't crash or corrupt data.

**Cross-Platform Support**: Rust runs on many platforms and architectures, from embedded systems to cloud servers. The same code can often run unchanged across different environments.

**Growing Ecosystem**: The Rust ecosystem is rapidly expanding, with high-quality libraries (called "crates") available for everything from web development to machine learning.

**Industry Adoption**: Major companies like Microsoft, Facebook, Dropbox, and Discord use Rust in production for critical systems, demonstrating its real-world viability.

### Installation and Setup

Installing Rust is straightforward thanks to `rustup`, the official Rust toolchain installer. Here's how to get started on different platforms:

**Linux and macOS:**
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

**Windows:**
Download and run the installer from [rustup.rs](https://rustup.rs/), or use the command above in WSL (Windows Subsystem for Linux).

**Verification:**
After installation, restart your terminal and verify the installation:
```bash
rustc --version
cargo --version
```

You should see output similar to:
```
rustc 1.70.0 (90c541806 2023-05-31)
cargo 1.70.0 (ec8a8a0ca 2023-04-25)
```

**Updating Rust:**
Rust is updated frequently with new features and improvements. Update your installation with:
```bash
rustup update
```

**Managing Toolchains:**
You can install and manage multiple Rust versions:
```bash
rustup install stable
rustup install beta
rustup install nightly
rustup default stable
```

### Development Environment

While you can write Rust code in any text editor, several development environments provide excellent Rust support:

**Visual Studio Code with rust-analyzer:**
The most popular choice, offering:
- Intelligent code completion
- Real-time error checking
- Integrated debugging
- Code formatting and refactoring

Install the "rust-analyzer" extension for the best experience.

**IntelliJ IDEA with Rust Plugin:**
Comprehensive IDE support with:
- Advanced code analysis
- Integrated testing tools
- Database integration
- Version control integration

**Vim/Neovim:**
For terminal enthusiasts, use plugins like:
- `rust.vim` for syntax highlighting
- `coc.nvim` with `coc-rust-analyzer`

**Emacs:**
Use `rustic-mode` for comprehensive Rust support.

**Essential Tools:**
```bash
# Code formatter
rustup component add rustfmt

# Linter
rustup component add clippy

# Documentation generator
cargo install cargo-doc
```

### Hello World

Let's start with the traditional "Hello, World!" program to ensure everything is working correctly.

**Create a new project:**
```bash
cargo new hello_world
cd hello_world
```

This creates a new directory with the following structure:
```
hello_world/
├── Cargo.toml
└── src/
    └── main.rs
```

**The source code (src/main.rs):**
```rust
fn main() {
    println!("Hello, World!");
}
```

**Run the program:**
```bash
cargo run
```

**Expected output:**
```
   Compiling hello_world v0.1.0 (/path/to/hello_world)
    Finished dev [unoptimized + debuginfo] target(s) in 1.23s
     Running `target/debug/hello_world`
Hello, World!
```

**Understanding the code:**
- `fn main()` defines the main function, the entry point of every Rust program
- `println!` is a macro (note the `!`) that prints text to the console
- The program is automatically compiled and run by Cargo

**Alternative compilation method:**
```bash
rustc src/main.rs
./main  # or main.exe on Windows
```

### ⚠️ Common Pitfalls

1. **Forgetting the exclamation mark in `println!`**: This is a macro, not a function
2. **Missing semicolons**: Most statements in Rust end with semicolons
3. **Case sensitivity**: Rust is case-sensitive; `Main()` is not the same as `main()`
4. **Path issues**: Ensure you're in the correct directory when running commands

### ✅ Best Practices

1. **Use Cargo for project management**: It handles dependencies, building, and testing
2. **Follow naming conventions**: Use `snake_case` for variables and functions
3. **Enable all compiler warnings**: Add `#[warn(clippy::all)]` to your main.rs
4. **Format your code**: Run `cargo fmt` regularly
5. **Use descriptive variable names**: Rust encourages clear, readable code

### 🏋️ Exercise 1: Your First Rust Program
**Difficulty:** 🟢 Beginner
**Estimated Time:** 10 minutes

Create a Rust program that prints your name, favorite programming language, and the current year.

<details>
<summary>💡 Click to see hints</summary>

- Use multiple `println!` statements
- You can include variables in the output
- Remember that the main function is the entry point

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
fn main() {
    let name = "Alice";
    let favorite_language = "Rust";
    let year = 2024;
    
    println!("Hello! My name is {}", name);
    println!("My favorite programming language is {}", favorite_language);
    println!("The current year is {}", year);
    
    // Alternative: all in one line
    println!("Name: {}, Language: {}, Year: {}", name, favorite_language, year);
}
```

**Explanation:**
This solution demonstrates several key Rust concepts:
- Variable declaration with `let`
- String literals and integer literals
- The `println!` macro with placeholder `{}`
- Multiple ways to format output

The `{}` placeholders are filled in order with the variables provided after the format string. Rust's type system ensures that the correct formatting is used for each type.

</details>

---

## Chapter 2: Rust Fundamentals
📊 **Progress:** Chapter 2 of 11 | 🎯 **Learning Objectives:** Master basic Rust syntax, understand variables, data types, and control structures | ⏱️ **Estimated Time:** 60 minutes | 📋 **Prerequisites:** Chapter 1 completed

### Basic Syntax

Rust syntax is designed to be clear and expressive while maintaining performance. Understanding the fundamental syntax elements is crucial for writing effective Rust code.

**Comments:**
```rust
// Single-line comment

/* Multi-line comment
   can span several lines */

/// Documentation comment for the item that follows
/// These comments can use Markdown formatting
fn documented_function() {
    //! Inner documentation comment
    //! Documents the enclosing item
    println!("Hello from a documented function!");
}
```

**Statement vs Expression:**
Rust is an expression-based language, which means most code constructs return values:
```rust
fn main() {
    // Statement: does not return a value
    let x = 5;
    
    // Expression: returns a value
    let y = {
        let inner = x * 2;
        inner + 1  // No semicolon: this is the return value
    };
    
    println!("x = {}, y = {}", x, y);  // Output: x = 5, y = 11
}
```

**Identifiers and Keywords:**
Rust uses `snake_case` for variables and functions, `PascalCase` for types:
```rust
let variable_name = 42;
let another_var = "hello";

struct MyStruct {
    field_name: i32,
}

fn function_name() -> i32 {
    42
}
```

**Reserved Keywords:**
Rust has reserved keywords that cannot be used as identifiers: `as`, `break`, `const`, `continue`, `crate`, `else`, `enum`, `extern`, `false`, `fn`, `for`, `if`, `impl`, `in`, `let`, `loop`, `match`, `mod`, `move`, `mut`, `pub`, `ref`, `return`, `self`, `Self`, `static`, `struct`, `super`, `trait`, `true`, `type`, `unsafe`, `use`, `where`, `while`.

### Variables and Mutability

One of Rust's core principles is immutability by default. Variables are immutable unless explicitly marked as mutable.

**Immutable Variables:**
```rust
fn main() {
    let x = 5;
    println!("The value of x is: {}", x);
    
    // This would cause a compile error:
    // x = 6;  // Error: cannot assign twice to immutable variable
}
```

**Mutable Variables:**
```rust
fn main() {
    let mut x = 5;
    println!("The value of x is: {}", x);
    
    x = 6;  // This is allowed because x is mutable
    println!("The value of x is: {}", x);
}
```

**Variable Shadowing:**
Rust allows you to declare a new variable with the same name as a previous variable:
```rust
fn main() {
    let x = 5;
    let x = x + 1;  // Shadow the previous x
    let x = x * 2;  // Shadow again
    
    println!("The value of x is: {}", x);  // Output: 12
    
    // Shadowing can change the type
    let spaces = "   ";
    let spaces = spaces.len();  // Now spaces is a number
    println!("Number of spaces: {}", spaces);
}
```

**Constants:**
Constants are always immutable and must be annotated with their type:
```rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;

fn main() {
    println!("Three hours in seconds: {}", THREE_HOURS_IN_SECONDS);
}
```

**Difference between `let` and `const`:**
- Constants can be declared in any scope, including global
- Constants must be set to a constant expression, not a function result
- Constants are valid for the entire program runtime
- Constant names should be in `SCREAMING_SNAKE_CASE`

### Data Types

Rust is a statically typed language, meaning all variable types must be known at compile time. The compiler can often infer types, but sometimes explicit annotation is required.

**Scalar Types:**

**Integers:**
```rust
fn main() {
    // Signed integers (can be negative)
    let signed_8bit: i8 = -128;
    let signed_16bit: i16 = 32_000;
    let signed_32bit: i32 = 2_147_483_647;  // Default integer type
    let signed_64bit: i64 = 9_223_372_036_854_775_807;
    let signed_128bit: i128 = 170_141_183_460_469_231_731_687_303_715_884_105_727;
    let signed_arch: isize = 1000;  // Architecture-dependent size
    
    // Unsigned integers (only positive)
    let unsigned_8bit: u8 = 255;
    let unsigned_16bit: u16 = 65_535;
    let unsigned_32bit: u32 = 4_294_967_295;
    let unsigned_64bit: u64 = 18_446_744_073_709_551_615;
    let unsigned_128bit: u128 = 340_282_366_920_938_463_463_374_607_431_768_211_455;
    let unsigned_arch: usize = 1000;  // Architecture-dependent size
    
    // Number literals
    let decimal = 98_222;
    let hex = 0xff;
    let octal = 0o77;
    let binary = 0b1111_0000;
    let byte = b'A';  // u8 only
    
    println!("Decimal: {}, Hex: {}, Octal: {}, Binary: {}, Byte: {}", 
             decimal, hex, octal, binary, byte);
}
```

**Floating-Point Numbers:**
```rust
fn main() {
    let f32_number: f32 = 3.14159;  // Single precision
    let f64_number: f64 = 2.718281828459;  // Double precision (default)
    let inferred = 2.0;  // f64 by default
    
    println!("f32: {}, f64: {}, inferred: {}", f32_number, f64_number, inferred);
    
    // Mathematical operations
    let sum = f64_number + inferred;
    let difference = f64_number - inferred;
    let product = f32_number * 2.0;
    let quotient = f64_number / inferred;
    
    println!("Math results: {}, {}, {}, {}", sum, difference, product, quotient);
}
```

**Boolean:**
```rust
fn main() {
    let true_value = true;
    let false_value: bool = false;  // Explicit type annotation
    
    let result = true_value && false_value;  // AND operation
    let result2 = true_value || false_value;  // OR operation
    let result3 = !true_value;  // NOT operation
    
    println!("Boolean results: {}, {}, {}", result, result2, result3);
}
```

**Character:**
```rust
fn main() {
    let c = 'z';
    let z = 'ℤ';
    let heart_eyed_cat = '😻';  // Unicode scalar values
    
    println!("Characters: {}, {}, {}", c, z, heart_eyed_cat);
    
    // Characters are 4 bytes and represent a Unicode Scalar Value
    println!("Size of char: {} bytes", std::mem::size_of::<char>());
}
```

**Compound Types:**

**Tuples:**
```rust
fn main() {
    let tuple: (i32, f64, u8) = (500, 6.4, 1);
    
    // Destructuring
    let (x, y, z) = tuple;
    println!("Tuple values: {}, {}, {}", x, y, z);
    
    // Direct access
    let first = tuple.0;
    let second = tuple.1;
    let third = tuple.2;
    println!("Direct access: {}, {}, {}", first, second, third);
    
    // Unit tuple (empty tuple)
    let unit = ();
    println!("Unit tuple: {:?}", unit);
}
```

**Arrays:**
```rust
fn main() {
    let array = [1, 2, 3, 4, 5];
    let months = ["January", "February", "March", "April", "May"];
    
    // Explicit type and size
    let array_with_type: [i32; 5] = [1, 2, 3, 4, 5];
    
    // Initialize with same value
    let repeated = [3; 5];  // [3, 3, 3, 3, 3]
    
    // Accessing elements
    let first = array[0];
    let second = array[1];
    
    println!("Array elements: {}, {}", first, second);
    println!("Array length: {}", array.len());
    
    // Arrays are stack-allocated and have fixed size
    println!("Array size: {} bytes", std::mem::size_of_val(&array));
}
```

### Functions

Functions are the primary way to organize and reuse code in Rust. They follow a consistent syntax and have several important characteristics.

**Basic Function Definition:**
```rust
fn main() {
    println!("Hello, world!");
    
    another_function();
    function_with_parameter(42);
    
    let result = function_with_return_value();
    println!("Returned value: {}", result);
    
    let sum = add_numbers(5, 3);
    println!("5 + 3 = {}", sum);
}

fn another_function() {
    println!("Another function.");
}

fn function_with_parameter(x: i32) {
    println!("The value of x is: {}", x);
}

fn function_with_return_value() -> i32 {
    5  // No semicolon: this is an expression that returns the value
}

fn add_numbers(x: i32, y: i32) -> i32 {
    x + y  // Expression return (no semicolon)
    // or: return x + y;  // Statement return (with semicolon)
}
```

**Functions with Multiple Return Types:**
```rust
fn get_user_info() -> (String, i32, bool) {
    let name = String::from("Alice");
    let age = 30;
    let is_student = false;
    
    (name, age, is_student)  // Return a tuple
}

fn main() {
    let (name, age, is_student) = get_user_info();
    println!("Name: {}, Age: {}, Student: {}", name, age, is_student);
}
```

**Early Returns:**
```rust
fn divide(numerator: f64, denominator: f64) -> Option<f64> {
    if denominator == 0.0 {
        return None;  // Early return
    }
    
    Some(numerator / denominator)  // Expression return
}

fn main() {
    match divide(10.0, 3.0) {
        Some(result) => println!("Result: {}", result),
        None => println!("Cannot divide by zero!"),
    }
}
```

### Control Flow

Control flow constructs allow you to control the execution path of your program based on conditions and repetitions.

**If Expressions:**
```rust
fn main() {
    let number = 6;
    
    if number % 4 == 0 {
        println!("number is divisible by 4");
    } else if number % 3 == 0 {
        println!("number is divisible by 3");
    } else if number % 2 == 0 {
        println!("number is divisible by 2");
    } else {
        println!("number is not divisible by 4, 3, or 2");
    }
    
    // If as an expression
    let condition = true;
    let number = if condition { 5 } else { 6 };
    println!("The value of number is: {}", number);
    
    // Complex conditions
    let a = 10;
    let b = 20;
    if a > 5 && b < 30 {
        println!("Both conditions are true");
    }
}
```

**Loops:**

**`loop` - Infinite Loop:**
```rust
fn main() {
    let mut counter = 0;
    
    let result = loop {
        counter += 1;
        
        if counter == 10 {
            break counter * 2;  // Return value from loop
        }
    };
    
    println!("The result is {}", result);
}
```

**`while` - Conditional Loop:**
```rust
fn main() {
    let mut number = 3;
    
    while number != 0 {
        println!("{}!", number);
        number -= 1;
    }
    
    println!("LIFTOFF!!!");
    
    // While with complex conditions
    let mut x = 10;
    let mut y = 20;
    while x < 15 && y > 10 {
        x += 1;
        y -= 1;
        println!("x: {}, y: {}", x, y);
    }
}
```

**`for` - Iteration Loop:**
```rust
fn main() {
    let arr = [10, 20, 30, 40, 50];
    
    // Iterate over array elements
    for element in arr {
        println!("the value is: {}", element);
    }
    
    // Iterate over a range
    for number in 1..4 {  // 1, 2, 3 (exclusive end)
        println!("{}!", number);
    }
    
    // Inclusive range
    for number in 1..=4 {  // 1, 2, 3, 4 (inclusive end)
        println!("{}!", number);
    }
    
    // Reverse iteration
    for number in (1..4).rev() {
        println!("{}!", number);
    }
    
    // Iterate with index
    for (index, value) in arr.iter().enumerate() {
        println!("Index: {}, Value: {}", index, value);
    }
}
```

**Loop Labels:**
```rust
fn main() {
    let mut count = 0;
    'counting_up: loop {
        println!("count = {}", count);
        let mut remaining = 10;

        loop {
            println!("remaining = {}", remaining);
            if remaining == 9 {
                break;
            }
            if count == 2 {
                break 'counting_up;  // Break the outer loop
            }
            remaining -= 1;
        }

        count += 1;
    }
    println!("End count = {}", count);
}
```

### ⚠️ Common Pitfalls

1. **Forgetting return types**: Functions that return values must specify the return type
2. **Mixing statements and expressions**: Remember that expressions don't end with semicolons when used as return values
3. **Integer overflow in debug mode**: Rust panics on integer overflow in debug mode but wraps in release mode
4. **Array bounds checking**: Rust checks array bounds at runtime and panics on out-of-bounds access
5. **Infinite loops**: Be careful with `loop` constructs; ensure there's always a way to break out

### ✅ Best Practices

1. **Use descriptive function names**: `calculate_area()` is better than `calc()`
2. **Keep functions small**: Aim for functions that do one thing well
3. **Use `for` loops over `while` loops**: They're generally safer and more idiomatic
4. **Prefer expressions over statements**: Use `if` expressions when assigning values
5. **Use early returns**: Return early from functions to reduce nesting
6. **Comment complex logic**: Especially mathematical calculations or business rules

### 🏋️ Exercise 2: Temperature Converter
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 20 minutes

Write a program that converts temperatures between Celsius, Fahrenheit, and Kelvin. The program should have separate functions for each conversion and demonstrate the use of control flow.

<details>
<summary>💡 Click to see hints</summary>

- Create functions like `celsius_to_fahrenheit`, `fahrenheit_to_celsius`, etc.
- Use the formulas: F = C * 9/5 + 32, K = C + 273.15
- Use a match statement or if-else chain to select conversion type
- Consider using an enum for temperature units

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
fn main() {
    let temp_celsius = 25.0;
    let temp_fahrenheit = 77.0;
    let temp_kelvin = 298.15;
    
    println!("=== Temperature Conversions ===");
    
    // Convert from Celsius
    println!("{}°C to Fahrenheit: {:.2}°F", 
             temp_celsius, celsius_to_fahrenheit(temp_celsius));
    println!("{}°C to Kelvin: {:.2}K", 
             temp_celsius, celsius_to_kelvin(temp_celsius));
    
    // Convert from Fahrenheit
    println!("{}°F to Celsius: {:.2}°C", 
             temp_fahrenheit, fahrenheit_to_celsius(temp_fahrenheit));
    println!("{}°F to Kelvin: {:.2}K", 
             temp_fahrenheit, fahrenheit_to_kelvin(temp_fahrenheit));
    
    // Convert from Kelvin
    println!("{}K to Celsius: {:.2}°C", 
             temp_kelvin, kelvin_to_celsius(temp_kelvin));
    println!("{}K to Fahrenheit: {:.2}°F", 
             temp_kelvin, kelvin_to_fahrenheit(temp_kelvin));
    
    // Interactive conversion
    convert_temperature(100.0, TemperatureUnit::Celsius, TemperatureUnit::Fahrenheit);
}

#[derive(Debug)]
enum TemperatureUnit {
    Celsius,
    Fahrenheit,
    Kelvin,
}

fn celsius_to_fahrenheit(celsius: f64) -> f64 {
    celsius * 9.0 / 5.0 + 32.0
}

fn celsius_to_kelvin(celsius: f64) -> f64 {
    celsius + 273.15
}

fn fahrenheit_to_celsius(fahrenheit: f64) -> f64 {
    (fahrenheit - 32.0) * 5.0 / 9.0
}

fn fahrenheit_to_kelvin(fahrenheit: f64) -> f64 {
    celsius_to_kelvin(fahrenheit_to_celsius(fahrenheit))
}

fn kelvin_to_celsius(kelvin: f64) -> f64 {
    kelvin - 273.15
}

fn kelvin_to_fahrenheit(kelvin: f64) -> f64 {
    celsius_to_fahrenheit(kelvin_to_celsius(kelvin))
}

fn convert_temperature(value: f64, from: TemperatureUnit, to: TemperatureUnit) {
    let result = match (from, to) {
        (TemperatureUnit::Celsius, TemperatureUnit::Fahrenheit) => celsius_to_fahrenheit(value),
        (TemperatureUnit::Celsius, TemperatureUnit::Kelvin) => celsius_to_kelvin(value),
        (TemperatureUnit::Fahrenheit, TemperatureUnit::Celsius) => fahrenheit_to_celsius(value),
        (TemperatureUnit::Fahrenheit, TemperatureUnit::Kelvin) => fahrenheit_to_kelvin(value),
        (TemperatureUnit::Kelvin, TemperatureUnit::Celsius) => kelvin_to_celsius(value),
        (TemperatureUnit::Kelvin, TemperatureUnit::Fahrenheit) => kelvin_to_fahrenheit(value),
        _ => {
            println!("Same unit conversion: {}", value);
            return;
        }
    };
    
    println!("Converting {} {:?} to {:?}: {:.2}", value, from, to, result);
}
```

**Explanation:**
This solution demonstrates several key concepts:
- **Function organization**: Each conversion is a separate function for clarity and reusability
- **Enum usage**: `TemperatureUnit` enum makes the code more type-safe and readable
- **Pattern matching**: The `match` statement handles all conversion combinations elegantly
- **Function composition**: Complex conversions reuse simpler ones (e.g., Fahrenheit to Kelvin goes through Celsius)
- **Floating-point precision**: Using `f64` for accurate temperature calculations
- **Formatted output**: The `{:.2}` format specifier shows 2 decimal places

</details>

### 🏋️ Exercise 3: Fibonacci Sequence
**Difficulty:** 🟡 Intermediate  
**Estimated Time:** 15 minutes

Write a function that calculates the nth Fibonacci number using both iterative and recursive approaches.

<details>
<summary>💡 Click to see hints</summary>

- Fibonacci sequence: F(0) = 0, F(1) = 1, F(n) = F(n-1) + F(n-2)
- For the iterative approach, use a loop with two variables
- For recursion, handle base cases first
- Compare performance between both approaches

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
fn main() {
    let n = 10;
    
    println!("=== Fibonacci Sequence ===");
    println!("Calculating F({}) using different methods:", n);
    
    let iterative_result = fibonacci_iterative(n);
    println!("Iterative approach: {}", iterative_result);
    
    let recursive_result = fibonacci_recursive(n);
    println!("Recursive approach: {}", recursive_result);
    
    // Print first 15 Fibonacci numbers
    println!("\nFirst 15 Fibonacci numbers:");
    for i in 0..15 {
        print!("{} ", fibonacci_iterative(i));
    }
    println!();
}

fn fibonacci_iterative(n: u32) -> u64 {
    if n <= 1 {
        return n as u64;
    }
    
    let mut prev = 0u64;
    let mut curr = 1u64;
    
    for _ in 2..=n {
        let next = prev + curr;
        prev = curr;
        curr = next;
    }
    
    curr
}

fn fibonacci_recursive(n: u32) -> u64 {
    match n {
        0 => 0,
        1 => 1,
        _ => fibonacci_recursive(n - 1) + fibonacci_recursive(n - 2),
    }
}
```

**Explanation:**
- **Iterative approach**: More efficient with O(n) time complexity and O(1) space complexity
- **Recursive approach**: Simpler to understand but less efficient with O(2^n) time complexity
- **Base case handling**: Both functions properly handle the base cases F(0) = 0 and F(1) = 1
- **Type considerations**: Using `u64` to handle larger Fibonacci numbers without overflow

</details>

---

## Chapter 3: Ownership and Borrowing
📊 **Progress:** Chapter 3 of 11 | 🎯 **Learning Objectives:** Master Rust's ownership system, understand borrowing and lifetimes | ⏱️ **Estimated Time:** 90 minutes | 📋 **Prerequisites:** Chapters 1-2 completed

### Understanding Ownership

Ownership is Rust's most unique feature and the key to its memory safety guarantees. It enables Rust to make memory safety guarantees without needing a garbage collector.

**The Ownership Rules:**
1. Each value in Rust has an owner
2. There can only be one owner at a time
3. When the owner goes out of scope, the value will be dropped

**Variable Scope:**
```rust
fn main() {
    {                      // s is not valid here, it's not yet declared
        let s = "hello";   // s is valid from this point forward
        
        // do stuff with s
        println!("s is: {}", s);
    }                      // this scope is now over, and s is no longer valid
}
```

**The String Type:**
Unlike string literals, the `String` type manages heap-allocated data:
```rust
fn main() {
    let mut s = String::from("hello");
    s.push_str(", world!"); // push_str() appends a literal to a String
    println!("{}", s); // This will print `hello, world!`
    
    // String is heap-allocated and can grow
    let s1 = String::from("hello");
    let s2 = String::from("world");
    let s3 = format!("{} {}", s1, s2); // s1 and s2 are still valid here
    
    println!("s1: {}, s2: {}, s3: {}", s1, s2, s3);
}
```

**Memory and Allocation:**
```rust
fn main() {
    {
        let s = String::from("hello"); // s is valid from this point forward
        
        // Memory is automatically returned when s goes out of scope
        // Rust calls `drop` function automatically
    } // s goes out of scope and `drop` is called, memory is freed
}
```

**Move Semantics:**
```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1; // s1 is moved to s2
    
    // println!("{}", s1); // This would cause a compile error!
    println!("{}", s2); // This works fine
    
    // For simple types (Copy trait), assignment copies instead of moves
    let x = 5;
    let y = x; // x is copied to y
    println!("x: {}, y: {}", x, y); // Both x and y are valid
}
```

**Clone vs Copy:**
```rust
fn main() {
    // Clone: deep copy for heap data
    let s1 = String::from("hello");
    let s2 = s1.clone(); // Expensive operation
    println!("s1: {}, s2: {}", s1, s2); // Both are valid
    
    // Copy: automatic for stack-only data
    let x = 5;
    let y = x; // Automatic copy (cheap)
    println!("x: {}, y: {}", x, y);
    
    // Types with Copy trait: integers, booleans, floats, char, tuples of Copy types
    let tuple = (5, 10.5, 'a');
    let another_tuple = tuple; // Copied, not moved
    println!("Original: {:?}, Copy: {:?}", tuple, another_tuple);
}
```

**Ownership and Functions:**
```rust
fn main() {
    let s = String::from("hello");  // s comes into scope
    takes_ownership(s);             // s's value moves into the function...
                                    // ... and so is no longer valid here
    
    let x = 5;                      // x comes into scope
    makes_copy(x);                  // x would move into the function,
                                    // but i32 is Copy, so it's okay to still
                                    // use x afterward
    
    println!("x is still valid: {}", x);
    // println!("s is no longer valid: {}", s); // This would error!
}

fn takes_ownership(some_string: String) { // some_string comes into scope
    println!("{}", some_string);
} // Here, some_string goes out of scope and `drop` is called

fn makes_copy(some_integer: i32) { // some_integer comes into scope
    println!("{}", some_integer);
} // Here, some_integer goes out of scope, but nothing special happens
```

**Return Values and Scope:**
```rust
fn main() {
    let s1 = gives_ownership();         // gives_ownership moves its return value into s1
    let s2 = String::from("hello");     // s2 comes into scope
    let s3 = takes_and_gives_back(s2);  // s2 is moved into takes_and_gives_back,
                                        // which also moves its return value into s3
    
    println!("s1: {}, s3: {}", s1, s3);
    // println!("s2: {}", s2); // s2 is no longer valid
} // s3 goes out of scope and is dropped. s1 goes out of scope and is dropped.
  // s2 was moved, so nothing happens.

fn gives_ownership() -> String {             // gives_ownership will move its
                                             // return value into the function
                                             // that calls it
    let some_string = String::from("yours"); // some_string comes into scope
    some_string                              // some_string is returned and
                                             // moves out to the calling function
}

fn takes_and_gives_back(a_string: String) -> String { // a_string comes into scope
    a_string  // a_string is returned and moves out to the calling function
}
```

### References and Borrowing

Borrowing allows you to refer to a value without taking ownership of it. This is crucial for writing efficient and safe code.

**Immutable References:**
```rust
fn main() {
    let s1 = String::from("hello");
    let len = calculate_length(&s1); // Pass a reference
    println!("The length of '{}' is {}.", s1, len); // s1 is still valid
}

fn calculate_length(s: &String) -> usize { // s is a reference to a String
    s.len()
} // Here, s goes out of scope. But because it does not have ownership of what
  // it refers to, nothing happens.
```

**Mutable References:**
```rust
fn main() {
    let mut s = String::from("hello");
    change(&mut s); // Pass a mutable reference
    println!("{}", s); // Prints "hello, world"
}

fn change(some_string: &mut String) {
    some_string.push_str(", world");
}
```

**Reference Rules:**
```rust
fn main() {
    let mut s = String::from("hello");
    
    // Rule 1: You can have either one mutable reference or any number of immutable references
    let r1 = &s; // no problem
    let r2 = &s; // no problem
    println!("{} and {}", r1, r2);
    // r1 and r2 are no longer used after this point
    
    let r3 = &mut s; // no problem
    println!("{}", r3);
    
    // Rule 2: References must always be valid (no dangling references)
    // let reference_to_nothing = dangle(); // This won't compile!
}

// fn dangle() -> &String { // This function would return a reference to a String
//     let s = String::from("hello");
//     &s // We return a reference to the String, s
// } // Here, s goes out of scope, and is dropped. Its memory goes away.
//   // Danger! This would be a dangling reference
```

**Multiple References:**
```rust
fn main() {
    let mut s = String::from("hello");
    
    // Multiple immutable references are allowed
    let r1 = &s;
    let r2 = &s;
    println!("{} and {}", r1, r2);
    // Variables r1 and r2 will not be used after this point
    
    let r3 = &mut s; // This is allowed because r1 and r2 are no longer used
    println!("{}", r3);
    
    // But this would cause an error:
    // let r4 = &s; // Cannot have immutable reference while mutable exists
    // println!("{} and {}", r3, r4);
}
```

**Borrowing in Functions:**
```rust
fn main() {
    let mut s = String::from("hello");
    
    let len = calculate_length(&s);
    println!("Length: {}", len);
    
    change_string(&mut s);
    println!("Changed: {}", s);
    
    let (s2, len) = calculate_length_with_ownership(s);
    println!("String: {}, Length: {}", s2, len);
}

fn calculate_length(s: &String) -> usize {
    s.len()
}

fn change_string(s: &mut String) {
    s.push_str(" world");
}

// Alternative that takes ownership and returns it
fn calculate_length_with_ownership(s: String) -> (String, usize) {
    let length = s.len();
    (s, length)
}
```

### The Slice Type

Slices let you reference a contiguous sequence of elements in a collection rather than the whole collection.

**String Slices:**
```rust
fn main() {
    let s = String::from("hello world");
    
    let hello = &s[0..5];  // &str slice
    let world = &s[6..11];
    let hello2 = &s[..5];   // Same as &s[0..5]
    let world2 = &s[6..];   // From index 6 to end
    let entire = &s[..];    // Entire string
    
    println!("hello: {}, world: {}", hello, world);
    println!("hello2: {}, world2: {}", hello2, world2);
    println!("entire: {}", entire);
    
    // String literals are slices
    let s = "Hello, world!"; // s is &str
    
    let word = first_word(&s);
    println!("First word: {}", word);
}

fn first_word(s: &str) -> &str {
    let bytes = s.as_bytes();
    
    for (i, &item) in bytes.iter().enumerate() {
        if item == b' ' {
            return &s[0..i];
        }
    }
    
    &s[..]
}
```

**Array Slices:**
```rust
fn main() {
    let a = [1, 2, 3, 4, 5];
    
    let slice = &a[1..3]; // &[i32] slice
    assert_eq!(slice, &[2, 3]);
    
    println!("Array slice: {:?}", slice);
    
    // Iterating over slices
    for element in slice {
        println!("Element: {}", element);
    }
    
    // Slices have length and can be indexed
    println!("Slice length: {}", slice.len());
    println!("First element: {}", slice[0]);
}
```

**Practical String Slice Usage:**
```rust
fn main() {
    let my_string = String::from("hello world");
    
    // first_word works on slices of `String`s
    let word = first_word(&my_string[0..6]);
    println!("Word from String: {}", word);
    
    let word = first_word(&my_string[..]);
    println!("Word from full String: {}", word);
    
    // first_word also works on references to `String`s, which are equivalent
    // to whole slices of `String`s
    let word = first_word(&my_string);
    println!("Word from String reference: {}", word);
    
    let my_string_literal = "hello world";
    
    // first_word works on slices of string literals
    let word = first_word(&my_string_literal[0..6]);
    println!("Word from string literal slice: {}", word);
    
    let word = first_word(&my_string_literal[..]);
    println!("Word from full string literal: {}", word);
    
    // Because string literals *are* string slices already,
    // this works too, without the slice syntax!
    let word = first_word(my_string_literal);
    println!("Word from string literal: {}", word);
}

fn first_word(s: &str) -> &str {
    let bytes = s.as_bytes();
    
    for (i, &item) in bytes.iter().enumerate() {
        if item == b' ' {
            return &s[0..i];
        }
    }
    
    &s[..]
}
```

### Lifetime Annotations

Lifetimes ensure that references are valid as long as we need them to be. Most of the time, lifetimes are implicit and inferred.

**Lifetime Annotation Syntax:**
```rust
fn main() {
    let string1 = String::from("abcd");
    let string2 = "xyz";
    
    let result = longest(string1.as_str(), string2);
    println!("The longest string is {}", result);
    
    // Example with different scopes
    let string1 = String::from("long string is long");
    {
        let string2 = String::from("xyz");
        let result = longest(string1.as_str(), string2.as_str());
        println!("The longest string is {}", result);
    } // string2 goes out of scope, but result was used before this
}

// The lifetime parameter 'a specifies that the returned reference
// will be valid as long as both input references are valid
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

**Lifetime Annotations in Structs:**
```rust
struct ImportantExcerpt<'a> {
    part: &'a str,
}

fn main() {
    let novel = String::from("Call me Ishmael. Some years ago...");
    let first_sentence = novel.split('.').next().expect("Could not find a '.'");
    
    let i = ImportantExcerpt {
        part: first_sentence,
    };
    
    println!("Important excerpt: {}", i.part);
}

impl<'a> ImportantExcerpt<'a> {
    fn level(&self) -> i32 {
        3
    }
    
    fn announce_and_return_part(&self, announcement: &str) -> &str {
        println!("Attention please: {}", announcement);
        self.part
    }
}
```

**Lifetime Elision Rules:**
```rust
// These functions don't need explicit lifetime annotations
// due to lifetime elision rules

fn first_word(s: &str) -> &str {
    let bytes = s.as_bytes();
    
    for (i, &item) in bytes.iter().enumerate() {
        if item == b' ' {
            return &s[0..i];
        }
    }
    
    &s[..]
}

// This is equivalent to:
// fn first_word<'a>(s: &'a str) -> &'a str

fn main() {
    let s = "hello world";
    let word = first_word(s);
    println!("First word: {}", word);
}
```

**The Static Lifetime:**
```rust
fn main() {
    // String literals have 'static lifetime
    let s: &'static str = "I have a static lifetime.";
    println!("{}", s);
    
    // Static variables also have 'static lifetime
    static HELLO_WORLD: &str = "Hello, world!";
    println!("{}", HELLO_WORLD);
}
```

### ⚠️ Common Pitfalls

1. **Moving when you meant to borrow**: Use `&` for borrowing instead of transferring ownership
2. **Multiple mutable references**: You can only have one mutable reference at a time
3. **Dangling references**: References must always point to valid data
4. **Mixing mutable and immutable references**: Can't have both simultaneously in use
5. **Overthinking lifetimes**: Often the compiler can infer lifetimes automatically

### ✅ Best Practices

1. **Prefer borrowing over taking ownership**: Use references when you don't need ownership
2. **Use string slices (`&str`) in function parameters**: More flexible than `String`
3. **Keep borrow scopes minimal**: Release references as soon as you're done with them
4. **Clone only when necessary**: Moving is usually more efficient than cloning
5. **Trust the borrow checker**: It prevents memory safety issues at compile time
6. **Use lifetime elision**: Let the compiler infer lifetimes when possible

### 🏋️ Exercise 4: Text Analyzer
**Difficulty:** 🔴 Advanced
**Estimated Time:** 30 minutes

Create a text analyzer that counts words, characters, and finds the longest word using ownership and borrowing principles.

<details>
<summary>💡 Click to see hints</summary>

- Use string slices for function parameters
- Implement functions that borrow rather than take ownership
- Handle edge cases like empty strings and multiple spaces
- Consider using iterators and the `split_whitespace()` method

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
fn main() {
    let text = "Hello world! This is a sample text for analysis. Programming in Rust is fantastic!";
    
    println!("=== Text Analysis ===");
    println!("Text: {}", text);
    println!();
    
    let word_count = count_words(text);
    println!("Word count: {}", word_count);
    
    let char_count = count_characters(text);
    println!("Character count: {}", char_count);
    
    let longest = find_longest_word(text);
    match longest {
        Some(word) => println!("Longest word: '{}'", word),
        None => println!("No words found"),
    }
    
    let stats = analyze_text(text);
    println!("\n=== Detailed Analysis ===");
    println!("Words: {}", stats.word_count);
    println!("Characters: {}", stats.char_count);
    println!("Characters (no spaces): {}", stats.char_count_no_spaces);
    println!("Sentences: {}", stats.sentence_count);
    println!("Average word length: {:.2}", stats.average_word_length);
    println!("Longest word: {}", stats.longest_word.unwrap_or("None"));
    println!("Shortest word: {}", stats.shortest_word.unwrap_or("None"));
}

fn count_words(text: &str) -> usize {
    text.split_whitespace().count()
}

fn count_characters(text: &str) -> usize {
    text.chars().count()
}

fn find_longest_word(text: &str) -> Option<&str> {
    text.split_whitespace()
        .max_by_key(|word| word.len())
}

fn find_shortest_word(text: &str) -> Option<&str> {
    text.split_whitespace()
        .min_by_key(|word| word.len())
}

fn count_sentences(text: &str) -> usize {
    text.chars()
        .filter(|&c| c == '.' || c == '!' || c == '?')
        .count()
}

fn calculate_average_word_length(text: &str) -> f64 {
    let words: Vec<&str> = text.split_whitespace().collect();
    if words.is_empty() {
        return 0.0;
    }
    
    let total_length: usize = words.iter().map(|word| word.len()).sum();
    total_length as f64 / words.len() as f64
}

#[derive(Debug)]
struct TextStats<'a> {
    word_count: usize,
    char_count: usize,
    char_count_no_spaces: usize,
    sentence_count: usize,
    average_word_length: f64,
    longest_word: Option<&'a str>,
    shortest_word: Option<&'a str>,
}

fn analyze_text(text: &str) -> TextStats {
    TextStats {
        word_count: count_words(text),
        char_count: count_characters(text),
        char_count_no_spaces: text.chars().filter(|&c| c != ' ').count(),
        sentence_count: count_sentences(text),
        average_word_length: calculate_average_word_length(text),
        longest_word: find_longest_word(text),
        shortest_word: find_shortest_word(text),
    }
}
```

**Explanation:**
- **Borrowing**: All functions take `&str` parameters, borrowing instead of taking ownership
- **Lifetime annotations**: `TextStats` struct uses lifetime parameter for string references
- **Iterator usage**: Efficient text processing using iterator methods
- **Option handling**: Gracefully handles edge cases like empty text
- **Composition**: `analyze_text` function reuses smaller functions for comprehensive analysis
- **Memory efficiency**: No unnecessary string allocations or cloning

</details>

---

## Chapter 4: Structs and Enums
📊 **Progress:** Chapter 4 of 11 | 🎯 **Learning Objectives:** Learn to define custom data types with structs and enums | ⏱️ **Estimated Time:** 75 minutes | 📋 **Prerequisites:** Chapters 1-3 completed

### Defining Structs

Structs allow you to create custom data types that group related pieces of data together. They're similar to objects in other languages but without methods (those come later).

**Basic Struct Definition:**
```rust
struct User {
    active: bool,
    username: String,
    email: String,
    sign_in_count: u64,
}

fn main() {
    let user1 = User {
        email: String::from("someone@example.com"),
        username: String::from("someusername123"),
        active: true,
        sign_in_count: 1,
    };
    
    println!("User email: {}", user1.email);
    println!("Username: {}", user1.username);
    println!("Active: {}, Sign-ins: {}", user1.active, user1.sign_in_count);
}
```

**Mutable Structs:**
```rust
struct User {
    active: bool,
    username: String,
    email: String,
    sign_in_count: u64,
}

fn main() {
    let mut user1 = User {
        email: String::from("someone@example.com"),
        username: String::from("someusername123"),
        active: true,
        sign_in_count: 1,
    };
    
    user1.email = String::from("anotheremail@example.com");
    user1.sign_in_count += 1;
    
    println!("Updated email: {}", user1.email);
    println!("Sign-in count: {}", user1.sign_in_count);
}
```

**Struct Update Syntax:**
```rust
struct User {
    active: bool,
    username: String,
    email: String,
    sign_in_count: u64,
}

fn main() {
    let user1 = User {
        email: String::from("someone@example.com"),
        username: String::from("someusername123"),
        active: true,
        sign_in_count: 1,
    };
    
    // Create a new user based on user1
    let user2 = User {
        email: String::from("another@example.com"),
        ..user1  // Use the rest of the fields from user1
    };
    
    // Note: user1 is no longer valid because username was moved to user2
    println!("User2 email: {}", user2.email);
    println!("User2 username: {}", user2.username);
}
```

**Constructor Functions:**
```rust
struct User {
    active: bool,
    username: String,
    email: String,
    sign_in_count: u64,
}

fn build_user(email: String, username: String) -> User {
    User {
        email,  // Field init shorthand when parameter name matches field name
        username,
        active: true,
        sign_in_count: 1,
    }
}

fn main() {
    let user1 = build_user(
        String::from("someone@example.com"),
        String::from("someusername123"),
    );
    
    println!("Created user: {}", user1.email);
}
```

**Tuple Structs:**
```rust
struct Color(i32, i32, i32);
struct Point(i32, i32, i32);

fn main() {
    let black = Color(0, 0, 0);
    let origin = Point(0, 0, 0);
    
    // Access tuple struct fields by index
    println!("Black color: ({}, {}, {})", black.0, black.1, black.2);
    println!("Origin point: ({}, {}, {})", origin.0, origin.1, origin.2);
    
    // Destructuring tuple structs
    let Color(r, g, b) = black;
    println!("RGB values: r={}, g={}, b={}", r, g, b);
}
```

**Unit-Like Structs:**
```rust
struct AlwaysEqual;

fn main() {
    let subject = AlwaysEqual;
    // Useful for traits (covered later)
}
```

**Debugging Structs:**
```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

fn main() {
    let rect1 = Rectangle {
        width: 30,
        height: 50,
    };
    
    println!("rect1 is {:?}", rect1);
    println!("rect1 is {:#?}", rect1);  // Pretty print
}
```

### Method Syntax

Methods are similar to functions but are defined within the context of a struct, enum, or trait object.

**Defining Methods:**
```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    fn area(&self) -> u32 {
        self.width * self.height
    }
    
    fn width(&self) -> bool {
        self.width > 0
    }
    
    fn can_hold(&self, other: &Rectangle) -> bool {
        self.width > other.width && self.height > other.height
    }
}

fn main() {
    let rect1 = Rectangle {
        width: 30,
        height: 50,
    };
    
    let rect2 = Rectangle {
        width: 10,
        height: 40,
    };
    
    let rect3 = Rectangle {
        width: 60,
        height: 45,
    };
    
    println!("The area of the rectangle is {} square pixels.", rect1.area());
    println!("The rectangle has a nonzero width; it is {}", rect1.width());
    println!("Can rect1 hold rect2? {}", rect1.can_hold(&rect2));
    println!("Can rect1 hold rect3? {}", rect1.can_hold(&rect3));
}
```

**Associated Functions:**
```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    // Associated function (like static methods in other languages)
    fn square(size: u32) -> Self {
        Self {
            width: size,
            height: size,
        }
    }
    
    fn new(width: u32, height: u32) -> Self {
        Self { width, height }
    }
}

fn main() {
    let sq = Rectangle::square(3);
    let rect = Rectangle::new(10, 20);
    
    println!("Square: {:?}", sq);
    println!("Rectangle: {:?}", rect);
}
```

**Multiple impl Blocks:**
```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    fn area(&self) -> u32 {
        self.width * self.height
    }
}

impl Rectangle {
    fn can_hold(&self, other: &Rectangle) -> bool {
        self.width > other.width && self.height > other.height
    }
}

fn main() {
    let rect1 = Rectangle {
        width: 30,
        height: 50,
    };
    
    let rect2 = Rectangle {
        width: 10,
        height: 40,
    };
    
    println!("The area of rect1 is {} square pixels.", rect1.area());
    println!("Can rect1 hold rect2? {}", rect1.can_hold(&rect2));
}
```

### Enumerations

Enums allow you to define types by enumerating their possible variants. They're incredibly powerful in Rust.

**Basic Enum Definition:**
```rust
enum IpAddrKind {
    V4,
    V6,
}

fn main() {
    let four = IpAddrKind::V4;
    let six = IpAddrKind::V6;
    
    route(IpAddrKind::V4);
    route(IpAddrKind::V6);
}

fn route(ip_kind: IpAddrKind) {
    // Function body here
}
```

**Enums with Data:**
```rust
enum IpAddr {
    V4(u8, u8, u8, u8),
    V6(String),
}

enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    ChangeColor(i32, i32, i32),
}

fn main() {
    let home = IpAddr::V4(127, 0, 0, 1);
    let loopback = IpAddr::V6(String::from("::1"));
    
    let m1 = Message::Quit;
    let m2 = Message::Move { x: 10, y: 20 };
    let m3 = Message::Write(String::from("hello"));
    let m4 = Message::ChangeColor(255, 0, 0);
}
```

**Methods on Enums:**
```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    ChangeColor(i32, i32, i32),
}

impl Message {
    fn call(&self) {
        match self {
            Message::Quit => println!("Quit message"),
            Message::Move { x, y } => println!("Move to x: {}, y: {}", x, y),
            Message::Write(text) => println!("Text message: {}", text),
            Message::ChangeColor(r, g, b) => println!("Change color to RGB({}, {}, {})", r, g, b),
        }
    }
    
    fn is_quit(&self) -> bool {
        matches!(self, Message::Quit)
    }
}

fn main() {
    let m = Message::Write(String::from("hello"));
    m.call();
    
    let quit_msg = Message::Quit;
    println!("Is quit message: {}", quit_msg.is_quit());
}
```

**The Option Enum:**
```rust
fn main() {
    let some_number = Some(5);
    let some_string = Some("a string");
    let absent_number: Option<i32> = None;
    
    println!("some_number: {:?}", some_number);
    println!("some_string: {:?}", some_string);
    println!("absent_number: {:?}", absent_number);
    
    // Using Option in functions
    let x: i8 = 5;
    let y: Option<i8> = Some(5);
    
    if let Some(value) = y {
        let sum = x + value;
        println!("Sum: {}", sum);
    }
    
    // Pattern matching with Option
    match some_number {
        Some(value) => println!("Got a value: {}", value),
        None => println!("Got nothing"),
    }
}

fn divide(numerator: f64, denominator: f64) -> Option<f64> {
    if denominator == 0.0 {
        None
    } else {
        Some(numerator / denominator)
    }
}
```

### Pattern Matching

Pattern matching is one of Rust's most powerful features, allowing you to compare values against patterns and execute code based on which pattern matches.

**Match Control Flow:**
```rust
enum Coin {
    Penny,
    Nickel,
    Dime,
    Quarter(UsState),
}

#[derive(Debug)]
enum UsState {
    Alabama,
    Alaska,
    California,
    // ... etc
}

fn value_in_cents(coin: Coin) -> u8 {
    match coin {
        Coin::Penny => {
            println!("Lucky penny!");
            1
        }
        Coin::Nickel => 5,
        Coin::Dime => 10,
        Coin::Quarter(state) => {
            println!("State quarter from {:?}!", state);
            25
        }
    }
}

fn main() {
    let coin = Coin::Quarter(UsState::Alaska);
    let value = value_in_cents(coin);
    println!("Value: {} cents", value);
}
```

**Matching with Option:**
```rust
fn plus_one(x: Option<i32>) -> Option<i32> {
    match x {
        None => None,
        Some(i) => Some(i + 1),
    }
}

fn main() {
    let five = Some(5);
    let six = plus_one(five);
    let none = plus_one(None);
    
    println!("five: {:?}", five);
    println!("six: {:?}", six);
    println!("none: {:?}", none);
}
```

**Catch-all Patterns:**
```rust
fn main() {
    let dice_roll = 9;
    
    match dice_roll {
        3 => add_fancy_hat(),
        7 => remove_fancy_hat(),
        other => move_player(other),  // Use the value
    }
    
    // Alternative: ignore the value
    match dice_roll {
        3 => add_fancy_hat(),
        7 => remove_fancy_hat(),
        _ => reroll(),  // Don't use the value
    }
}

fn add_fancy_hat() {}
fn remove_fancy_hat() {}
fn move_player(num_spaces: u8) {}
fn reroll() {}
```

**If Let Syntax:**
```rust
fn main() {
    let config_max = Some(3u8);
    
    // Instead of this:
    match config_max {
        Some(max) => println!("The maximum is configured to be {}", max),
        _ => (),
    }
    
    // You can write this:
    if let Some(max) = config_max {
        println!("The maximum is configured to be {}", max);
    }
    
    // With else
    let coin = Coin::Penny;
    let mut count = 0;
    if let Coin::Quarter(state) = coin {
        println!("State quarter from {:?}!", state);
    } else {
        count += 1;
    }
    
    println!("Count: {}", count);
}

enum Coin {
    Penny,
    Nickel,
    Dime,
    Quarter(UsState),
}

#[derive(Debug)]
enum UsState {
    Alabama,
    Alaska,
}
```

**While Let Loops:**
```rust
fn main() {
    let mut stack = Vec::new();
    stack.push(1);
    stack.push(2);
    stack.push(3);
    
    while let Some(top) = stack.pop() {
        println!("{}", top);
    }
}
```

**Complex Pattern Matching:**
```rust
fn main() {
    let x = 1;
    
    match x {
        1 | 2 => println!("one or two"),
        3..=5 => println!("three through five"),
        _ => println!("anything else"),
    }
    
    let x = 'c';
    match x {
        'a'..='j' => println!("early ASCII letter"),
        'k'..='z' => println!("late ASCII letter"),
        _ => println!("something else"),
    }
}
```

**Destructuring:**
```rust
struct Point {
    x: i32,
    y: i32,
}

enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    ChangeColor(i32, i32, i32),
}

fn main() {
    let p = Point { x: 0, y: 7 };
    
    let Point { x: a, y: b } = p;
    assert_eq!(0, a);
    assert_eq!(7, b);
    
    // Shorthand
    let Point { x, y } = p;
    assert_eq!(0, x);
    assert_eq!(7, y);
    
    match p {
        Point { x, y: 0 } => println!("On the x axis at {}", x),
        Point { x: 0, y } => println!("On the y axis at {}", y),
        Point { x, y } => println!("On neither axis: ({}, {})", x, y),
    }
    
    // Destructuring enums
    let msg = Message::ChangeColor(0, 160, 255);
    
    match msg {
        Message::Quit => {
            println!("The Quit variant has no data to destructure.")
        }
        Message::Move { x, y } => {
            println!("Move in the x direction {} and in the y direction {}", x, y);
        }
        Message::Write(text) => println!("Text message: {}", text),
        Message::ChangeColor(r, g, b) => {
            println!("Change the color to red {}, green {}, and blue {}", r, g, b)
        }
    }
}
```

### ⚠️ Common Pitfalls

1. **Forgetting to handle all enum variants**: Match expressions must be exhaustive
2. **Not using pattern matching**: Don't use if-else chains when match would be clearer
3. **Overusing unwrap() with Option**: Use pattern matching or if let instead
4. **Confusing struct field order**: Order doesn't matter in struct creation but does in tuple structs
5. **Forgetting self parameter**: Methods need &self, &mut self, or self as first parameter

### ✅ Best Practices

1. **Use enums for state modeling**: They're perfect for representing different states
2. **Prefer pattern matching over if-else**: More expressive and safer
3. **Use Option instead of null values**: Rust's type system will ensure you handle None cases
4. **Keep structs focused**: Group related data but don't create "god structs"
5. **Use derive macros**: Add #[derive(Debug, Clone, PartialEq)] when appropriate
6. **Name enum variants clearly**: Use descriptive names that indicate their purpose

### 🏋️ Exercise 5: Library Management System
**Difficulty:** 🔴 Advanced
**Estimated Time:** 45 minutes

Create a library management system using structs, enums, and pattern matching to represent books, users, and borrowing operations.

<details>
<summary>💡 Click to see hints</summary>

- Define structs for Book, User, and Library
- Use enums for book genres and borrowing status
- Implement methods for borrowing and returning books
- Use pattern matching to handle different operations
- Consider using Option for handling cases where books might not be found

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
use std::collections::HashMap;

#[derive(Debug, Clone, PartialEq)]
enum Genre {
    Fiction,
    NonFiction,
    Mystery,
    Romance,
    SciFi,
    Biography,
}

#[derive(Debug, Clone, PartialEq)]
enum BookStatus {
    Available,
    Borrowed(u32), // user_id
    Reserved(u32), // user_id
}

#[derive(Debug, Clone)]
struct Book {
    id: u32,
    title: String,
    author: String,
    genre: Genre,
    status: BookStatus,
}

#[derive(Debug, Clone)]
struct User {
    id: u32,
    name: String,
    email: String,
    borrowed_books: Vec<u32>, // book_ids
}

#[derive(Debug)]
struct Library {
    books: HashMap<u32, Book>,
    users: HashMap<u32, User>,
    next_book_id: u32,
    next_user_id: u32,
}

impl Library {
    fn new() -> Self {
        Library {
            books: HashMap::new(),
            users: HashMap::new(),
            next_book_id: 1,
            next_user_id: 1,
        }
    }
    
    fn add_book(&mut self, title: String, author: String, genre: Genre) -> u32 {
        let book_id = self.next_book_id;
        let book = Book {
            id: book_id,
            title,
            author,
            genre,
            status: BookStatus::Available,
        };
        
        self.books.insert(book_id, book);
        self.next_book_id += 1;
        book_id
    }
    
    fn add_user(&mut self, name: String, email: String) -> u32 {
        let user_id = self.next_user_id;
        let user = User {
            id: user_id,
            name,
            email,
            borrowed_books: Vec::new(),
        };
        
        self.users.insert(user_id, user);
        self.next_user_id += 1;
        user_id
    }
    
    fn borrow_book(&mut self, user_id: u32, book_id: u32) -> Result<String, String> {
        let book = match self.books.get_mut(&book_id) {
            Some(book) => book,
            None => return Err("Book not found".to_string()),
        };
        
        let user = match self.users.get_mut(&user_id) {
            Some(user) => user,
            None => return Err("User not found".to_string()),
        };
        
        match book.status {
            BookStatus::Available => {
                book.status = BookStatus::Borrowed(user_id);
                user.borrowed_books.push(book_id);
                Ok(format!("Book '{}' borrowed successfully by {}", book.title, user.name))
            }
            BookStatus::Borrowed(borrower_id) => {
                if borrower_id == user_id {
                    Err("You have already borrowed this book".to_string())
                } else {
                    let borrower_name = self.users.get(&borrower_id)
                        .map(|u| &u.name)
                        .unwrap_or(&"Unknown".to_string());
                    Err(format!("Book is currently borrowed by {}", borrower_name))
                }
            }
            BookStatus::Reserved(reserver_id) => {
                if reserver_id == user_id {
                    book.status = BookStatus::Borrowed(user_id);
                    user.borrowed_books.push(book_id);
                    Ok(format!("Reserved book '{}' borrowed successfully", book.title))
                } else {
                    Err("Book is reserved by another user".to_string())
                }
            }
        }
    }
    
    fn return_book(&mut self, user_id: u32, book_id: u32) -> Result<String, String> {
        let book = match self.books.get_mut(&book_id) {
            Some(book) => book,
            None => return Err("Book not found".to_string()),
        };
        
        let user = match self.users.get_mut(&user_id) {
            Some(user) => user,
            None => return Err("User not found".to_string()),
        };
        
        match book.status {
            BookStatus::Borrowed(borrower_id) if borrower_id == user_id => {
                book.status = BookStatus::Available;
                user.borrowed_books.retain(|&id| id != book_id);
                Ok(format!("Book '{}' returned successfully", book.title))
            }
            BookStatus::Borrowed(_) => {
                Err("You haven't borrowed this book".to_string())
            }
            BookStatus::Available => {
                Err("Book is already available".to_string())
            }
            BookStatus::Reserved(_) => {
                Err("Book is reserved and cannot be returned".to_string())
            }
        }
    }
    
    fn search_books_by_genre(&self, genre: &Genre) -> Vec<&Book> {
        self.books
            .values()
            .filter(|book| &book.genre == genre)
            .collect()
    }
    
    fn get_available_books(&self) -> Vec<&Book> {
        self.books
            .values()
            .filter(|book| matches!(book.status, BookStatus::Available))
            .collect()
    }
    
    fn get_user_borrowed_books(&self, user_id: u32) -> Option<Vec<&Book>> {
        let user = self.users.get(&user_id)?;
        let books: Vec<&Book> = user.borrowed_books
            .iter()
            .filter_map(|&book_id| self.books.get(&book_id))
            .collect();
        Some(books)
    }
}

fn main() {
    let mut library = Library::new();
    
    // Add some books
    let book1 = library.add_book("The Rust Programming Language".to_string(), 
                                "Steve Klabnik".to_string(), Genre::NonFiction);
    let book2 = library.add_book("Dune".to_string(), 
                                "Frank Herbert".to_string(), Genre::SciFi);
    let book3 = library.add_book("The Murder of Roger Ackroyd".to_string(), 
                                "Agatha Christie".to_string(), Genre::Mystery);
    
    // Add users
    let user1 = library.add_user("Alice Johnson".to_string(), "alice@email.com".to_string());
    let user2 = library.add_user("Bob Smith".to_string(), "bob@email.com".to_string());
    
    println!("=== Library Management System ===\n");
    
    // Borrow some books
    match library.borrow_book(user1, book1) {
        Ok(message) => println!("✅ {}", message),
        Err(error) => println!("❌ {}", error),
    }
    
    match library.borrow_book(user2, book2) {
        Ok(message) => println!("✅ {}", message),
        Err(error) => println!("❌ {}", error),
    }
    
    // Try to borrow an already borrowed book
    match library.borrow_book(user2, book1) {
        Ok(message) => println!("✅ {}", message),
        Err(error) => println!("❌ {}", error),
    }
    
    // Show available books
    println!("\n=== Available Books ===");
    for book in library.get_available_books() {
        println!("📚 {} by {} ({:?})", book.title, book.author, book.genre);
    }
    
    // Show user's borrowed books
    if let Some(borrowed_books) = library.get_user_borrowed_books(user1) {
        println!("\n=== Alice's Borrowed Books ===");
        for book in borrowed_books {
            println!("📖 {} by {}", book.title, book.author);
        }
    }
    
    // Return a book
    match library.return_book(user1, book1) {
        Ok(message) => println!("\n✅ {}", message),
        Err(error) => println!("\n❌ {}", error),
    }
    
    // Search books by genre
    println!("\n=== Science Fiction Books ===");
    for book in library.search_books_by_genre(&Genre::SciFi) {
        let status = match book.status {
            BookStatus::Available => "Available".to_string(),
            BookStatus::Borrowed(user_id) => {
                let user_name = library.users.get(&user_id)
                    .map(|u| &u.name)
                    .unwrap_or(&"Unknown".to_string());
                format!("Borrowed by {}", user_name)
            }
            BookStatus::Reserved(user_id) => {
                let user_name = library.users.get(&user_id)
                    .map(|u| &u.name)
                    .unwrap_or(&"Unknown".to_string());
                format!("Reserved by {}", user_name)
            }
        };
        println!("🚀 {} by {} - {}", book.title, book.author, status);
    }
}
```

**Explanation:**
This solution demonstrates advanced usage of structs and enums:
- **Complex enums**: `BookStatus` with associated data tracks who borrowed/reserved books
- **Struct composition**: `Library` contains collections of `Book` and `User` structs
- **Pattern matching**: Extensive use in borrow/return operations to handle different states
- **Error handling**: Returns `Result` types for operations that might fail
- **Method implementations**: Rich behavior through impl blocks
- **Data relationships**: Users track borrowed books, books track their status

</details>

---

## Chapter 5: Collections and Iterators
📊 **Progress:** Chapter 5 of 11 | 🎯 **Learning Objectives:** Master Rust's built-in collections and iterator patterns | ⏱️ **Estimated Time:** 85 minutes | 📋 **Prerequisites:** Chapters 1-4 completed

### Vectors

Vectors are resizable arrays that store elements of the same type in contiguous memory. They're one of the most commonly used collections in Rust.

**Creating Vectors:**
```rust
fn main() {
    // Creating empty vectors
    let v: Vec<i32> = Vec::new();
    let mut v2 = Vec::new();
    v2.push(5); // Type is inferred
    
    // Creating vectors with initial values
    let v3 = vec![1, 2, 3, 4, 5];
    let v4 = vec![0; 5]; // [0, 0, 0, 0, 0]
    
    println!("v3: {:?}", v3);
    println!("v4: {:?}", v4);
}
```

**Adding and Removing Elements:**
```rust
fn main() {
    let mut v = Vec::new();
    
    // Adding elements
    v.push(5);
    v.push(6);
    v.push(7);
    v.push(8);
    
    println!("After pushes: {:?}", v);
    
    // Removing elements
    let last = v.pop(); // Returns Option<T>
    println!("Popped: {:?}", last);
    println!("After pop: {:?}", v);
    
    // Insert at specific index
    v.insert(1, 10);
    println!("After insert: {:?}", v);
    
    // Remove at specific index
    let removed = v.remove(0);
    println!("Removed: {}", removed);
    println!("After remove: {:?}", v);
}
```

**Accessing Elements:**
```rust
fn main() {
    let v = vec![1, 2, 3, 4, 5];
    
    // Indexing (can panic)
    let third: &i32 = &v[2];
    println!("The third element is {}", third);
    
    // Using get method (returns Option)
    let third: Option<&i32> = v.get(2);
    match third {
        Some(third) => println!("The third element is {}", third),
        None => println!("There is no third element."),
    }
    
    // Safe indexing
    if let Some(element) = v.get(10) {
        println!("Element at index 10: {}", element);
    } else {
        println!("Index 10 is out of bounds");
    }
}
```

**Iterating Over Vectors:**
```rust
fn main() {
    let v = vec![100, 32, 57];
    
    // Iterating over values
    for i in &v {
        println!("{}", i);
    }
    
    // Iterating with indices
    for (index, value) in v.iter().enumerate() {
        println!("Index: {}, Value: {}", index, value);
    }
    
    // Mutable iteration
    let mut v = vec![100, 32, 57];
    for i in &mut v {
        *i += 50; // Dereference and modify
    }
    println!("Modified vector: {:?}", v);
}
```

**Vector with Different Types:**
```rust
enum SpreadsheetCell {
    Int(i32),
    Float(f64),
    Text(String),
}

fn main() {
    let row = vec![
        SpreadsheetCell::Int(3),
        SpreadsheetCell::Text(String::from("blue")),
        SpreadsheetCell::Float(10.12),
    ];
    
    for cell in &row {
        match cell {
            SpreadsheetCell::Int(i) => println!("Integer: {}", i),
            SpreadsheetCell::Float(f) => println!("Float: {}", f),
            SpreadsheetCell::Text(s) => println!("Text: {}", s),
        }
    }
}
```

**Vector Operations:**
```rust
fn main() {
    let mut v1 = vec![1, 2, 3];
    let v2 = vec![4, 5, 6];
    
    // Extend with another vector
    v1.extend(v2);
    println!("Extended: {:?}", v1);
    
    // Capacity and length
    let mut v = Vec::with_capacity(10);
    println!("Capacity: {}, Length: {}", v.capacity(), v.len());
    
    v.push(1);
    v.push(2);
    println!("Capacity: {}, Length: {}", v.capacity(), v.len());
    
    // Shrink to fit
    v.shrink_to_fit();
    println!("After shrink - Capacity: {}, Length: {}", v.capacity(), v.len());
    
    // Clear all elements
    v.clear();
    println!("After clear - Length: {}", v.len());
}
```

### Hash Maps

Hash maps store key-value pairs and are useful when you want to look up data using a key rather than an index.

**Creating Hash Maps:**
```rust
use std::collections::HashMap;

fn main() {
    // Creating empty hash map
    let mut scores = HashMap::new();
    scores.insert(String::from("Blue"), 10);
    scores.insert(String::from("Yellow"), 50);
    
    // Creating from vectors
    let teams = vec![String::from("Blue"), String::from("Yellow")];
    let initial_scores = vec![10, 50];
    let scores: HashMap<_, _> = teams.into_iter().zip(initial_scores.into_iter()).collect();
    
    println!("Scores: {:?}", scores);
}
```

**Accessing Values:**
```rust
use std::collections::HashMap;

fn main() {
    let mut scores = HashMap::new();
    scores.insert(String::from("Blue"), 10);
    scores.insert(String::from("Yellow"), 50);
    
    let team_name = String::from("Blue");
    let score = scores.get(&team_name).copied().unwrap_or(0);
    println!("Score for {}: {}", team_name, score);
    
    // Iterating over key-value pairs
    for (key, value) in &scores {
        println!("{}: {}", key, value);
    }
}
```

**Updating Hash Maps:**
```rust
use std::collections::HashMap;

fn main() {
    let mut scores = HashMap::new();
    
    // Overwriting values
    scores.insert(String::from("Blue"), 10);
    scores.insert(String::from("Blue"), 25); // Overwrites 10
    
    println!("{:?}", scores);
    
    // Insert only if key doesn't exist
    scores.entry(String::from("Yellow")).or_insert(50);
    scores.entry(String::from("Blue")).or_insert(50); // Won't change Blue
    
    println!("{:?}", scores);
    
    // Update based on old value
    let text = "hello world wonderful world";
    let mut map = HashMap::new();
    
    for word in text.split_whitespace() {
        let count = map.entry(word).or_insert(0);
        *count += 1;
    }
    
    println!("Word counts: {:?}", map);
}
```

**Advanced HashMap Operations:**
```rust
use std::collections::HashMap;

fn main() {
    let mut scores = HashMap::new();
    scores.insert("Alice", 95);
    scores.insert("Bob", 87);
    scores.insert("Charlie", 92);
    
    // Check if key exists
    if scores.contains_key("Alice") {
        println!("Alice's score is in the map");
    }
    
    // Remove entry
    let alice_score = scores.remove("Alice");
    println!("Removed Alice's score: {:?}", alice_score);
    
    // Retain only certain entries
    scores.retain(|_name, score| *score >= 90);
    println!("High scores: {:?}", scores);
    
    // Get keys and values
    let keys: Vec<&str> = scores.keys().cloned().collect();
    let values: Vec<i32> = scores.values().cloned().collect();
    println!("Keys: {:?}", keys);
    println!("Values: {:?}", values);
}
```

### Strings

Strings in Rust are more complex than in many other languages due to Rust's focus on safety and UTF-8 support.

**Creating Strings:**
```rust
fn main() {
    // Different ways to create strings
    let data = "initial contents";
    let s = data.to_string();
    let s = "initial contents".to_string();
    let s = String::from("initial contents");
    
    // Empty string
    let mut s = String::new();
    
    // UTF-8 strings
    let hello = String::from("السلام عليكم");
    let hello = String::from("Dobrý den");
    let hello = String::from("Hello");
    let hello = String::from("שָׁלוֹם");
    let hello = String::from("नमस्ते");
    let hello = String::from("こんにちは");
    let hello = String::from("안녕하세요");
    let hello = String::from("你好");
    let hello = String::from("Olá");
    let hello = String::from("Здравствуйте");
    let hello = String::from("Hola");
    
    println!("Multi-language hello: {}", hello);
}
```

**Growing Strings:**
```rust
fn main() {
    let mut s = String::from("foo");
    s.push_str("bar"); // Append string slice
    s.push('!'); // Append single character
    
    println!("s: {}", s);
    
    // Concatenation with +
    let s1 = String::from("Hello, ");
    let s2 = String::from("world!");
    let s3 = s1 + &s2; // s1 has been moved and can no longer be used
    
    println!("s3: {}", s3);
    
    // Format macro for complex concatenation
    let s1 = String::from("tic");
    let s2 = String::from("tac");
    let s3 = String::from("toe");
    let s = format!("{}-{}-{}", s1, s2, s3);
    println!("Formatted: {}", s);
}
```

**String Slicing:**
```rust
fn main() {
    let hello = "Здравствуйте";
    let s = &hello[0..4]; // Be careful with UTF-8!
    println!("Slice: {}", s);
    
    // Safer string slicing
    let hello = String::from("hello");
    if hello.len() >= 2 {
        let slice = &hello[0..2];
        println!("Safe slice: {}", slice);
    }
    
    // Iterating over characters
    for c in "नमस्ते".chars() {
        println!("{}", c);
    }
    
    // Iterating over bytes
    for b in "नमस्ते".bytes() {
        println!("{}", b);
    }
}
```

**String Methods:**
```rust
fn main() {
    let mut s = String::from("  Hello, World!  ");
    
    println!("Original: '{}'", s);
    println!("Length: {}", s.len());
    println!("Is empty: {}", s.is_empty());
    
    // Trimming whitespace
    let trimmed = s.trim();
    println!("Trimmed: '{}'", trimmed);
    
    // Case conversion
    println!("Uppercase: {}", s.to_uppercase());
    println!("Lowercase: {}", s.to_lowercase());
    
    // Contains and searching
    println!("Contains 'Hello': {}", s.contains("Hello"));
    println!("Starts with '  H': {}", s.starts_with("  H"));
    println!("Ends with '!  ': {}", s.ends_with("!  "));
    
    // Replace
    let replaced = s.replace("World", "Rust");
    println!("Replaced: '{}'", replaced);
    
    // Split
    let words: Vec<&str> = "apple,banana,orange".split(',').collect();
    println!("Split words: {:?}", words);
    
    // Lines
    let text = "line1\nline2\nline3";
    for line in text.lines() {
        println!("Line: {}", line);
    }
}
```

### Iterator Patterns

Iterators are a powerful feature in Rust that allow you to process collections in a functional programming style.

**Creating Iterators:**
```rust
fn main() {
    let v = vec![1, 2, 3];
    
    // iter() creates an iterator over references
    let v1_iter = v.iter();
    for val in v1_iter {
        println!("Got: {}", val);
    }
    
    // into_iter() creates an iterator that takes ownership
    let v = vec![1, 2, 3];
    let v1_iter = v.into_iter();
    for val in v1_iter {
        println!("Owned: {}", val);
    }
    // v is no longer valid here
    
    // iter_mut() creates an iterator over mutable references
    let mut v = vec![1, 2, 3];
    let v1_iter = v.iter_mut();
    for val in v1_iter {
        *val = *val * 2;
    }
    println!("Doubled: {:?}", v);
}
```

**Iterator Adaptors:**
```rust
fn main() {
    let v1: Vec<i32> = vec![1, 2, 3];
    
    // map transforms each element
    let v2: Vec<_> = v1.iter().map(|x| x + 1).collect();
    println!("Mapped: {:?}", v2);
    
    // filter keeps elements that match predicate
    let v3: Vec<_> = v1.iter().filter(|&x| *x > 1).collect();
    println!("Filtered: {:?}", v3);
    
    // Chain multiple operations
    let v4: Vec<_> = v1
        .iter()
        .map(|x| x * 2)
        .filter(|&x| *x > 2)
        .collect();
    println!("Chained: {:?}", v4);
    
    // enumerate adds indices
    for (i, value) in v1.iter().enumerate() {
        println!("Index: {}, Value: {}", i, value);
    }
    
    // zip combines two iterators
    let names = vec!["Alice", "Bob", "Charlie"];
    let ages = vec![25, 30, 35];
    for (name, age) in names.iter().zip(ages.iter()) {
        println!("{} is {} years old", name, age);
    }
}
```

**Consuming Adaptors:**
```rust
fn main() {
    let v1 = vec![1, 2, 3, 4, 5];
    
    // collect() consumes iterator into collection
    let v2: Vec<i32> = v1.iter().cloned().collect();
    println!("Collected: {:?}", v2);
    
    // reduce/fold accumulates values
    let sum = v1.iter().fold(0, |acc, x| acc + x);
    println!("Sum: {}", sum);
    
    let product = v1.iter().reduce(|acc, x| acc * x);
    println!("Product: {:?}", product);
    
    // find returns first matching element
    let found = v1.iter().find(|&x| *x > 3);
    println!("First > 3: {:?}", found);
    
    // any/all check conditions
    let any_even = v1.iter().any(|&x| x % 2 == 0);
    let all_positive = v1.iter().all(|&x| x > 0);
    println!("Any even: {}, All positive: {}", any_even, all_positive);
    
    // count elements
    let count = v1.iter().filter(|&x| *x > 2).count();
    println!("Count > 2: {}", count);
    
    // max/min
    let max = v1.iter().max();
    let min = v1.iter().min();
    println!("Max: {:?}, Min: {:?}", max, min);
}
```

**Custom Iterators:**
```rust
struct Counter {
    current: usize,
    max: usize,
}

impl Counter {
    fn new(max: usize) -> Counter {
        Counter { current: 0, max }
    }
}

impl Iterator for Counter {
    type Item = usize;
    
    fn next(&mut self) -> Option<Self::Item> {
        if self.current < self.max {
            let current = self.current;
            self.current += 1;
            Some(current)
        } else {
            None
        }
    }
}

fn main() {
    let counter = Counter::new(5);
    
    for n in counter {
        println!("Count: {}", n);
    }
    
    // Use with iterator methods
    let sum: usize = Counter::new(5).sum();
    println!("Sum of 0..5: {}", sum);
    
    let squares: Vec<usize> = Counter::new(5)
        .map(|x| x * x)
        .collect();
    println!("Squares: {:?}", squares);
}
```

**Performance Considerations:**
```rust
fn main() {
    let large_vec: Vec<i32> = (0..1_000_000).collect();
    
    // Iterator version (zero-cost abstraction)
    let sum: i32 = large_vec.iter().map(|x| x * 2).filter(|&x| *x > 1000).sum();
    println!("Iterator sum: {}", sum);
    
    // Equivalent manual loop
    let mut manual_sum = 0;
    for &item in &large_vec {
        let doubled = item * 2;
        if doubled > 1000 {
            manual_sum += doubled;
        }
    }
    println!("Manual sum: {}", manual_sum);
    
    // Both compile to similar assembly code!
}
```

### ⚠️ Common Pitfalls

1. **Iterator invalidation**: Don't modify collections while iterating
2. **Forgetting to consume**: Iterator adaptors are lazy and need collect() or similar
3. **Cloning unnecessarily**: Use references when possible in iterator chains
4. **String indexing**: Don't index strings directly, use chars() or bytes()
5. **HashMap key ownership**: Be careful about owned vs borrowed keys

### ✅ Best Practices

1. **Prefer iterators over indices**: More expressive and often faster
2. **Use collect() sparingly**: Only when you need the entire result
3. **Chain operations**: Combine map, filter, and other adaptors
4. **Use appropriate string types**: &str for parameters, String for owned data
5. **Pre-allocate collections**: Use with_capacity() when you know the size
6. **Leverage zero-cost abstractions**: Iterators compile to efficient code

### 🏋️ Exercise 6: Data Processing Pipeline
**Difficulty:** 🔴 Advanced
**Estimated Time:** 40 minutes

Create a data processing pipeline that reads sales data, processes it using iterators, and generates reports using various collection types.

<details>
<summary>💡 Click to see hints</summary>

- Define structs for Sale and SalesReport
- Use HashMap to group sales by region/product
- Implement iterator chains for filtering and aggregating data
- Use custom iterators for specific data processing needs
- Handle edge cases like empty data sets

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
use std::collections::HashMap;

#[derive(Debug, Clone)]
struct Sale {
    id: u32,
    product: String,
    region: String,
    amount: f64,
    quantity: u32,
    date: String,
}

#[derive(Debug)]
struct SalesReport {
    total_sales: f64,
    total_quantity: u32,
    average_sale: f64,
    top_products: Vec<(String, f64)>,
    region_breakdown: HashMap<String, f64>,
}

struct SalesProcessor {
    sales: Vec<Sale>,
}

impl SalesProcessor {
    fn new() -> Self {
        SalesProcessor { sales: Vec::new() }
    }
    
    fn add_sale(&mut self, sale: Sale) {
        self.sales.push(sale);
    }
    
    fn load_sample_data(&mut self) {
        let sample_sales = vec![
            Sale { id: 1, product: "Laptop".to_string(), region: "North".to_string(), 
                   amount: 1200.0, quantity: 1, date: "2024-01-15".to_string() },
            Sale { id: 2, product: "Mouse".to_string(), region: "South".to_string(), 
                   amount: 25.0, quantity: 2, date: "2024-01-16".to_string() },
            Sale { id: 3, product: "Keyboard".to_string(), region: "East".to_string(), 
                   amount: 75.0, quantity: 1, date: "2024-01-17".to_string() },
            Sale { id: 4, product: "Laptop".to_string(), region: "West".to_string(), 
                   amount: 1200.0, quantity: 1, date: "2024-01-18".to_string() },
            Sale { id: 5, product: "Monitor".to_string(), region: "North".to_string(), 
                   amount: 300.0, quantity: 2, date: "2024-01-19".to_string() },
            Sale { id: 6, product: "Mouse".to_string(), region: "East".to_string(), 
                   amount: 25.0, quantity: 3, date: "2024-01-20".to_string() },
            Sale { id: 7, product: "Laptop".to_string(), region: "South".to_string(), 
                   amount: 1200.0, quantity: 1, date: "2024-01-21".to_string() },
        ];
        
        for sale in sample_sales {
            self.add_sale(sale);
        }
    }
    
    fn generate_report(&self) -> SalesReport {
        let total_sales = self.sales.iter()
            .map(|sale| sale.amount)
            .sum();
            
        let total_quantity = self.sales.iter()
            .map(|sale| sale.quantity)
            .sum();
            
        let average_sale = if self.sales.is_empty() { 
            0.0 
        } else { 
            total_sales / self.sales.len() as f64 
        };
        
        // Top products by total revenue
        let mut product_sales: HashMap<String, f64> = HashMap::new();
        for sale in &self.sales {
            *product_sales.entry(sale.product.clone()).or_insert(0.0) += sale.amount;
        }
        
        let mut top_products: Vec<(String, f64)> = product_sales
            .into_iter()
            .collect();
        top_products.sort_by(|a, b| b.1.partial_cmp(&a.1).unwrap());
        top_products.truncate(3);
        
        // Region breakdown
        let region_breakdown = self.sales.iter()
            .fold(HashMap::new(), |mut acc, sale| {
                *acc.entry(sale.region.clone()).or_insert(0.0) += sale.amount;
                acc
            });
        
        SalesReport {
            total_sales,
            total_quantity,
            average_sale,
            top_products,
            region_breakdown,
        }
    }
    
    fn filter_by_region(&self, region: &str) -> Vec<&Sale> {
        self.sales.iter()
            .filter(|sale| sale.region == region)
            .collect()
    }
    
    fn filter_by_amount_range(&self, min: f64, max: f64) -> Vec<&Sale> {
        self.sales.iter()
            .filter(|sale| sale.amount >= min && sale.amount <= max)
            .collect()
    }
    
    fn get_high_value_sales(&self, threshold: f64) -> impl Iterator<Item = &Sale> {
        self.sales.iter()
            .filter(move |sale| sale.amount > threshold)
    }
    
    fn product_summary(&self) -> HashMap<String, ProductSummary> {
        self.sales.iter()
            .fold(HashMap::new(), |mut acc, sale| {
                let summary = acc.entry(sale.product.clone())
                    .or_insert(ProductSummary::new());
                summary.add_sale(sale.amount, sale.quantity);
                acc
            })
    }
    
    fn find_best_selling_product(&self) -> Option<String> {
        let product_quantities: HashMap<String, u32> = self.sales.iter()
            .fold(HashMap::new(), |mut acc, sale| {
                *acc.entry(sale.product.clone()).or_insert(0) += sale.quantity;
                acc
            });
            
        product_quantities.into_iter()
            .max_by_key(|&(_, quantity)| quantity)
            .map(|(product, _)| product)
    }
}

#[derive(Debug)]
struct ProductSummary {
    total_revenue: f64,
    total_quantity: u32,
    sale_count: u32,
    average_price: f64,
}

impl ProductSummary {
    fn new() -> Self {
        ProductSummary {
            total_revenue: 0.0,
            total_quantity: 0,
            sale_count: 0,
            average_price: 0.0,
        }
    }
    
    fn add_sale(&mut self, amount: f64, quantity: u32) {
        self.total_revenue += amount;
        self.total_quantity += quantity;
        self.sale_count += 1;
        self.average_price = self.total_revenue / self.sale_count as f64;
    }
}

// Custom iterator for processing sales data
struct SalesIterator<'a> {
    sales: &'a [Sale],
    current: usize,
    filter_fn: Box<dyn Fn(&Sale) -> bool + 'a>,
}

impl<'a> SalesIterator<'a> {
    fn new<F>(sales: &'a [Sale], filter_fn: F) -> Self 
    where F: Fn(&Sale) -> bool + 'a {
        SalesIterator {
            sales,
            current: 0,
            filter_fn: Box::new(filter_fn),
        }
    }
}

impl<'a> Iterator for SalesIterator<'a> {
    type Item = &'a Sale;
    
    fn next(&mut self) -> Option<Self::Item> {
        while self.current < self.sales.len() {
            let sale = &self.sales[self.current];
            self.current += 1;
            if (self.filter_fn)(sale) {
                return Some(sale);
            }
        }
        None
    }
}

fn main() {
    let mut processor = SalesProcessor::new();
    processor.load_sample_data();
    
    println!("=== Sales Data Processing Pipeline ===\n");
    
    // Generate comprehensive report
    let report = processor.generate_report();
    println!("📊 Sales Report:");
    println!("Total Sales: ${:.2}", report.total_sales);
    println!("Total Quantity: {} items", report.total_quantity);
    println!("Average Sale: ${:.2}", report.average_sale);
    
    println!("\n🏆 Top Products:");
    for (i, (product, revenue)) in report.top_products.iter().enumerate() {
        println!("{}. {} - ${:.2}", i + 1, product, revenue);
    }
    
    println!("\n🌍 Region Breakdown:");
    let mut regions: Vec<_> = report.region_breakdown.iter().collect();
    regions.sort_by(|a, b| b.1.partial_cmp(a.1).unwrap());
    for (region, revenue) in regions {
        println!("{}: ${:.2}", region, revenue);
    }
    
    // Filter operations
    println!("\n🔍 Filtered Results:");
    let north_sales = processor.filter_by_region("North");
    println!("North region sales: {} transactions", north_sales.len());
    
    let high_value_sales: Vec<_> = processor.filter_by_amount_range(100.0, 2000.0);
    println!("Sales between $100-$2000: {} transactions", high_value_sales.len());
    
    // Iterator operations
    let premium_sales: Vec<_> = processor.get_high_value_sales(500.0).collect();
    println!("Premium sales (>$500): {} transactions", premium_sales.len());
    
    // Product analysis
    let product_summaries = processor.product_summary();
    println!("\n📈 Product Analysis:");
    for (product, summary) in &product_summaries {
        println!("{}: {} sales, ${:.2} revenue, avg ${:.2}", 
                 product, summary.sale_count, summary.total_revenue, summary.average_price);
    }
    
    // Best selling product
    if let Some(best_product) = processor.find_best_selling_product() {
        println!("\n⭐ Best selling product: {}", best_product);
    }
    
    // Custom iterator usage
    println!("\n🔄 Custom Iterator - High Value North Sales:");
    let custom_iter = SalesIterator::new(&processor.sales, |sale| {
        sale.region == "North" && sale.amount > 200.0
    });
    
    for sale in custom_iter {
        println!("${:.2} - {} in {}", sale.amount, sale.product, sale.region);
    }
    
    // Complex iterator chain
    let complex_analysis: HashMap<String, f64> = processor.sales
        .iter()
        .filter(|sale| sale.amount > 50.0)
        .filter(|sale| sale.quantity > 0)
        .map(|sale| (sale.region.clone(), sale.amount / sale.quantity as f64))
        .fold(HashMap::new(), |mut acc, (region, price_per_unit)| {
            let entry = acc.entry(region).or_insert(0.0);
            *entry += price_per_unit;
            acc
        });
    
    println!("\n💰 Average Price per Unit by Region (filtered):");
    for (region, avg_price) in complex_analysis {
        println!("{}: ${:.2} per unit", region, avg_price);
    }
}
```

**Explanation:**
This comprehensive solution demonstrates advanced collection and iterator usage:
- **Multiple collection types**: Vec for sales data, HashMap for aggregations
- **Iterator chains**: Complex filtering, mapping, and reduction operations
- **Custom iterators**: Implementing the Iterator trait for specialized processing
- **Functional programming**: Extensive use of closures and higher-order functions
- **Performance optimization**: Efficient data processing using zero-cost abstractions
- **Real-world patterns**: Data analysis, reporting, and business logic implementation

</details>

---

## Chapter 6: Error Handling
📊 **Progress:** Chapter 6 of 11 | 🎯 **Learning Objectives:** Master Rust's error handling with Result and Option types | ⏱️ **Estimated Time:** 70 minutes | 📋 **Prerequisites:** Chapters 1-5 completed

### Panic and Unrecoverable Errors

Sometimes bad things happen in your code, and there's nothing you can do about it. In these cases, Rust provides the `panic!` macro.

**When to Panic:**
```rust
fn main() {
    // Explicit panic
    panic!("crash and burn");
    
    // This code will never run
    println!("This won't be printed");
}
```

**Array Out of Bounds:**
```rust
fn main() {
    let v = vec![1, 2, 3];
    
    // This will panic at runtime
    v[99];
}
```

**Backtrace Information:**
```rust
fn main() {
    // Set RUST_BACKTRACE=1 environment variable to see backtrace
    let v = vec![1, 2, 3];
    
    let element = v.get(99).unwrap(); // Will panic with message
    println!("Element: {}", element);
}
```

**Custom Panic Handling:**
```rust
use std::panic;

fn main() {
    // Set custom panic hook
    panic::set_hook(Box::new(|panic_info| {
        println!("Custom panic handler: {}", panic_info);
    }));
    
    let result = panic::catch_unwind(|| {
        panic!("Something went wrong!");
    });
    
    match result {
        Ok(_) => println!("No panic occurred"),
        Err(_) => println!("Panic was caught"),
    }
}
```

### Result Type

The `Result` enum is used for recoverable errors. It's defined as:

```rust
enum Result<T, E> {
    Ok(T),
    Err(E),
}
```

**Basic Result Usage:**
```rust
use std::fs::File;
use std::io::ErrorKind;

fn main() {
    let greeting_file_result = File::open("hello.txt");
    
    let greeting_file = match greeting_file_result {
        Ok(file) => file,
        Err(error) => match error.kind() {
            ErrorKind::NotFound => match File::create("hello.txt") {
                Ok(fc) => fc,
                Err(e) => panic!("Problem creating the file: {:?}", e),
            },
            other_error => {
                panic!("Problem opening the file: {:?}", other_error);
            }
        },
    };
    
    println!("File opened successfully");
}
```

**Unwrap and Expect:**
```rust
use std::fs::File;

fn main() {
    // unwrap() panics on Err
    let greeting_file = File::open("hello.txt").unwrap();
    
    // expect() panics with custom message
    let greeting_file = File::open("hello.txt")
        .expect("hello.txt should be included in this project");
}
```

**Result with Custom Types:**
```rust
#[derive(Debug)]
enum CalculationError {
    DivisionByZero,
    Overflow,
    InvalidInput,
}

fn divide(a: f64, b: f64) -> Result<f64, CalculationError> {
    if b == 0.0 {
        Err(CalculationError::DivisionByZero)
    } else if a.is_infinite() || b.is_infinite() {
        Err(CalculationError::Overflow)
    } else if a.is_nan() || b.is_nan() {
        Err(CalculationError::InvalidInput)
    } else {
        Ok(a / b)
    }
}

fn main() {
    match divide(10.0, 2.0) {
        Ok(result) => println!("Result: {}", result),
        Err(e) => println!("Error: {:?}", e),
    }
    
    match divide(10.0, 0.0) {
        Ok(result) => println!("Result: {}", result),
        Err(e) => println!("Error: {:?}", e),
    }
}
```

### Error Propagation

The `?` operator makes error propagation concise and idiomatic.

**Manual Error Propagation:**
```rust
use std::fs::File;
use std::io::{self, Read};

fn read_username_from_file() -> Result<String, io::Error> {
    let username_file_result = File::open("username.txt");
    
    let mut username_file = match username_file_result {
        Ok(file) => file,
        Err(e) => return Err(e),
    };
    
    let mut username = String::new();
    
    match username_file.read_to_string(&mut username) {
        Ok(_) => Ok(username),
        Err(e) => Err(e),
    }
}

fn main() {
    match read_username_from_file() {
        Ok(username) => println!("Username: {}", username),
        Err(e) => println!("Error reading username: {}", e),
    }
}
```

**Using the ? Operator:**
```rust
use std::fs::File;
use std::io::{self, Read};

fn read_username_from_file() -> Result<String, io::Error> {
    let mut username_file = File::open("username.txt")?;
    let mut username = String::new();
    username_file.read_to_string(&mut username)?;
    Ok(username)
}

// Even more concise
fn read_username_from_file_concise() -> Result<String, io::Error> {
    let mut username = String::new();
    File::open("username.txt")?.read_to_string(&mut username)?;
    Ok(username)
}

// Most concise using fs::read_to_string
fn read_username_from_file_shortest() -> Result<String, io::Error> {
    std::fs::read_to_string("username.txt")
}

fn main() {
    match read_username_from_file_shortest() {
        Ok(username) => println!("Username: {}", username),
        Err(e) => println!("Error: {}", e),
    }
}
```

**? Operator with Option:**
```rust
fn last_char_of_first_line(text: &str) -> Option<char> {
    text.lines().next()?.chars().last()
}

fn main() {
    let text = "Hello\nWorld";
    match last_char_of_first_line(text) {
        Some(c) => println!("Last char: {}", c),
        None => println!("No last char found"),
    }
    
    let empty_text = "";
    match last_char_of_first_line(empty_text) {
        Some(c) => println!("Last char: {}", c),
        None => println!("No last char found"),
    }
}
```

**Converting Between Result and Option:**
```rust
fn main() {
    let some_value: Option<i32> = Some(42);
    let none_value: Option<i32> = None;
    
    // Option to Result
    let result1: Result<i32, &str> = some_value.ok_or("No value present");
    let result2: Result<i32, &str> = none_value.ok_or("No value present");
    
    println!("Result1: {:?}", result1);
    println!("Result2: {:?}", result2);
    
    // Result to Option
    let ok_result: Result<i32, &str> = Ok(42);
    let err_result: Result<i32, &str> = Err("Something went wrong");
    
    let option1 = ok_result.ok();
    let option2 = err_result.ok();
    
    println!("Option1: {:?}", option1);
    println!("Option2: {:?}", option2);
}
```

### Custom Error Types

Creating custom error types makes your code more expressive and easier to debug.

**Simple Custom Error:**
```rust
use std::fmt;

#[derive(Debug)]
struct CustomError {
    message: String,
}

impl CustomError {
    fn new(msg: &str) -> CustomError {
        CustomError {
            message: msg.to_string(),
        }
    }
}

impl fmt::Display for CustomError {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "Custom error: {}", self.message)
    }
}

impl std::error::Error for CustomError {}

fn risky_operation(should_fail: bool) -> Result<String, CustomError> {
    if should_fail {
        Err(CustomError::new("Something went wrong"))
    } else {
        Ok("Success!".to_string())
    }
}

fn main() {
    match risky_operation(false) {
        Ok(result) => println!("Success: {}", result),
        Err(e) => println!("Error: {}", e),
    }
    
    match risky_operation(true) {
        Ok(result) => println!("Success: {}", result),
        Err(e) => println!("Error: {}", e),
    }
}
```

**Complex Error Types with Enum:**
```rust
use std::fmt;
use std::io;
use std::num::ParseIntError;

#[derive(Debug)]
enum DataError {
    Io(io::Error),
    Parse(ParseIntError),
    Validation(String),
}

impl fmt::Display for DataError {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        match self {
            DataError::Io(err) => write!(f, "IO error: {}", err),
            DataError::Parse(err) => write!(f, "Parse error: {}", err),
            DataError::Validation(msg) => write!(f, "Validation error: {}", msg),
        }
    }
}

impl std::error::Error for DataError {}

impl From<io::Error> for DataError {
    fn from(error: io::Error) -> Self {
        DataError::Io(error)
    }
}

impl From<ParseIntError> for DataError {
    fn from(error: ParseIntError) -> Self {
        DataError::Parse(error)
    }
}

fn process_data(data: &str) -> Result<Vec<i32>, DataError> {
    if data.is_empty() {
        return Err(DataError::Validation("Data cannot be empty".to_string()));
    }
    
    let numbers: Result<Vec<i32>, ParseIntError> = data
        .split(',')
        .map(|s| s.trim().parse())
        .collect();
        
    let numbers = numbers?;
    
    if numbers.is_empty() {
        return Err(DataError::Validation("No valid numbers found".to_string()));
    }
    
    Ok(numbers)
}

fn main() {
    let test_data = vec!["1,2,3,4", "1,two,3", "", "1, 2, 3"];
    
    for data in test_data {
        match process_data(data) {
            Ok(numbers) => println!("Parsed numbers: {:?}", numbers),
            Err(e) => println!("Error processing '{}': {}", data, e),
        }
    }
}
```

**Error Handling Best Practices:**
```rust
use std::error::Error;
use std::fmt;

// Use thiserror crate for easier error handling (in real projects)
#[derive(Debug)]
enum AppError {
    Config(String),
    Database(String),
    Network(String),
}

impl fmt::Display for AppError {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        match self {
            AppError::Config(msg) => write!(f, "Configuration error: {}", msg),
            AppError::Database(msg) => write!(f, "Database error: {}", msg),
            AppError::Network(msg) => write!(f, "Network error: {}", msg),
        }
    }
}

impl Error for AppError {}

type AppResult<T> = Result<T, AppError>;

fn load_config() -> AppResult<String> {
    // Simulate configuration loading
    Ok("config loaded".to_string())
}

fn connect_database() -> AppResult<String> {
    // Simulate database connection
    Err(AppError::Database("Connection refused".to_string()))
}

fn fetch_data() -> AppResult<Vec<String>> {
    // Simulate network request
    Ok(vec!["data1".to_string(), "data2".to_string()])
}

fn run_app() -> AppResult<()> {
    let _config = load_config()?;
    let _db = connect_database()?;
    let _data = fetch_data()?;
    
    println!("App running successfully");
    Ok(())
}

fn main() {
    if let Err(e) = run_app() {
        eprintln!("Application error: {}", e);
        
        // Print error chain
        let mut source = e.source();
        while let Some(err) = source {
            eprintln!("Caused by: {}", err);
            source = err.source();
        }
    }
}
```

### ⚠️ Common Pitfalls

1. **Overusing panic!**: Reserve panic for truly unrecoverable errors
2. **Ignoring Result types**: Always handle Result and Option values
3. **Using unwrap() in production**: Prefer expect() with descriptive messages
4. **Not propagating errors**: Use ? operator instead of unwrap/expect
5. **Poor error messages**: Provide context about what operation failed

### ✅ Best Practices

1. **Use Result for recoverable errors**: Let callers decide how to handle errors
2. **Create meaningful error types**: Custom enums provide better error information
3. **Use the ? operator**: Makes error propagation clean and readable
4. **Provide context**: Include relevant information in error messages
5. **Handle errors at appropriate levels**: Don't catch errors too early
6. **Use type aliases**: Create `type Result<T> = std::result::Result<T, MyError>`

### 🏋️ Exercise 7: File Processing System
**Difficulty:** 🔴 Advanced
**Estimated Time:** 35 minutes

Create a file processing system that handles various types of errors when reading, parsing, and validating data files.

<details>
<summary>💡 Click to see hints</summary>

- Define custom error types for different failure modes
- Use the ? operator for error propagation
- Implement proper error conversion with From trait
- Handle both recoverable and unrecoverable errors appropriately
- Provide meaningful error messages with context

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
use std::fs::File;
use std::io::{self, BufRead, BufReader};
use std::num::ParseIntError;
use std::fmt;

#[derive(Debug)]
enum ProcessingError {
    Io(io::Error),
    Parse(ParseIntError),
    Validation(String),
    Format(String),
}

impl fmt::Display for ProcessingError {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        match self {
            ProcessingError::Io(err) => write!(f, "IO error: {}", err),
            ProcessingError::Parse(err) => write!(f, "Parse error: {}", err),
            ProcessingError::Validation(msg) => write!(f, "Validation error: {}", msg),
            ProcessingError::Format(msg) => write!(f, "Format error: {}", msg),
        }
    }
}

impl std::error::Error for ProcessingError {}

impl From<io::Error> for ProcessingError {
    fn from(error: io::Error) -> Self {
        ProcessingError::Io(error)
    }
}

impl From<ParseIntError> for ProcessingError {
    fn from(error: ParseIntError) -> Self {
        ProcessingError::Parse(error)
    }
}

#[derive(Debug)]
struct DataRecord {
    id: u32,
    name: String,
    value: f64,
    active: bool,
}

impl DataRecord {
    fn from_csv_line(line: &str, line_number: usize) -> Result<Self, ProcessingError> {
        let fields: Vec<&str> = line.split(',').map(|s| s.trim()).collect();
        
        if fields.len() != 4 {
            return Err(ProcessingError::Format(
                format!("Line {}: Expected 4 fields, found {}", line_number, fields.len())
            ));
        }
        
        let id = fields[0].parse::<u32>()
            .map_err(|e| ProcessingError::Format(
                format!("Line {}: Invalid ID '{}': {}", line_number, fields[0], e)
            ))?;
            
        let name = fields[1].to_string();
        if name.is_empty() {
            return Err(ProcessingError::Validation(
                format!("Line {}: Name cannot be empty", line_number)
            ));
        }
        
        let value = fields[2].parse::<f64>()
            .map_err(|e| ProcessingError::Format(
                format!("Line {}: Invalid value '{}': {}", line_number, fields[2], e)
            ))?;
            
        if value < 0.0 {
            return Err(ProcessingError::Validation(
                format!("Line {}: Value cannot be negative: {}", line_number, value)
            ));
        }
        
        let active = match fields[3].to_lowercase().as_str() {
            "true" | "yes" | "1" => true,
            "false" | "no" | "0" => false,
            _ => return Err(ProcessingError::Format(
                format!("Line {}: Invalid boolean value '{}'", line_number, fields[3])
            )),
        };
        
        Ok(DataRecord { id, name, value, active })
    }
    
    fn validate(&self) -> Result<(), ProcessingError> {
        if self.name.len() < 2 {
            return Err(ProcessingError::Validation(
                format!("Record {}: Name too short: '{}'", self.id, self.name)
            ));
        }
        
        if self.value > 1000000.0 {
            return Err(ProcessingError::Validation(
                format!("Record {}: Value too large: {}", self.id, self.value)
            ));
        }
        
        Ok(())
    }
}

struct FileProcessor {
    filename: String,
}

impl FileProcessor {
    fn new(filename: String) -> Self {
        FileProcessor { filename }
    }
    
    fn process_file(&self) -> Result<Vec<DataRecord>, ProcessingError> {
        let file = File::open(&self.filename)?;
        let reader = BufReader::new(file);
        let mut records = Vec::new();
        let mut errors = Vec::new();
        
        for (line_number, line_result) in reader.lines().enumerate() {
            let line_number = line_number + 1; // 1-based line numbers
            let line = line_result?;
            
            // Skip empty lines and comments
            if line.trim().is_empty() || line.trim().starts_with('#') {
                continue;
            }
            
            match DataRecord::from_csv_line(&line, line_number) {
                Ok(record) => {
                    match record.validate() {
                        Ok(()) => records.push(record),
                        Err(e) => errors.push(e),
                    }
                },
                Err(e) => errors.push(e),
            }
        }
        
        if !errors.is_empty() {
            // In a real application, you might want to return partial results
            // For this example, we'll fail if there are any errors
            let error_messages: Vec<String> = errors.iter().map(|e| e.to_string()).collect();
            return Err(ProcessingError::Validation(
                format!("Multiple errors found:\n{}", error_messages.join("\n"))
            ));
        }
        
        Ok(records)
    }
    
    fn process_file_lenient(&self) -> Result<(Vec<DataRecord>, Vec<ProcessingError>), ProcessingError> {
        let file = File::open(&self.filename)?;
        let reader = BufReader::new(file);
        let mut records = Vec::new();
        let mut errors = Vec::new();
        
        for (line_number, line_result) in reader.lines().enumerate() {
            let line_number = line_number + 1;
            let line = line_result?;
            
            if line.trim().is_empty() || line.trim().starts_with('#') {
                continue;
            }
            
            match DataRecord::from_csv_line(&line, line_number) {
                Ok(record) => {
                    match record.validate() {
                        Ok(()) => records.push(record),
                        Err(e) => errors.push(e),
                    }
                },
                Err(e) => errors.push(e),
            }
        }
        
        Ok((records, errors))
    }
    
    fn get_summary(&self) -> Result<ProcessingSummary, ProcessingError> {
        let (records, errors) = self.process_file_lenient()?;
        
        let total_value = records.iter().map(|r| r.value).sum();
        let active_count = records.iter().filter(|r| r.active).count();
        let average_value = if records.is_empty() { 
            0.0 
        } else { 
            total_value / records.len() as f64 
        };
        
        Ok(ProcessingSummary {
            total_records: records.len(),
            error_count: errors.len(),
            total_value,
            active_count,
            average_value,
            errors,
        })
    }
}

#[derive(Debug)]
struct ProcessingSummary {
    total_records: usize,
    error_count: usize,
    total_value: f64,
    active_count: usize,
    average_value: f64,
    errors: Vec<ProcessingError>,
}

fn create_sample_file() -> io::Result<()> {
    use std::io::Write;
    
    let mut file = File::create("sample_data.csv")?;
    writeln!(file, "# Sample data file")?;
    writeln!(file, "1, Alice, 100.5, true")?;
    writeln!(file, "2, Bob, 250.0, false")?;
    writeln!(file, "3, Charlie, 75.25, yes")?;
    writeln!(file, "4, Diana, 500.0, 1")?;
    writeln!(file, "5, Eve, -50.0, true")?; // Invalid: negative value
    writeln!(file, "invalid, Frank, 200.0, true")?; // Invalid: non-numeric ID
    writeln!(file, "7, , 150.0, false")?; // Invalid: empty name
    writeln!(file, "8, Grace, abc, true")?; // Invalid: non-numeric value
    
    Ok(())
}

fn main() {
    // Create sample file
    if let Err(e) = create_sample_file() {
        eprintln!("Failed to create sample file: {}", e);
        return;
    }
    
    let processor = FileProcessor::new("sample_data.csv".to_string());
    
    println!("=== File Processing System ===\n");
    
    // Strict processing (fails on any error)
    println!("🔍 Strict Processing:");
    match processor.process_file() {
        Ok(records) => {
            println!("✅ Successfully processed {} records", records.len());
            for record in records {
                println!("  {:?}", record);
            }
        },
        Err(e) => println!("❌ Processing failed: {}", e),
    }
    
    // Lenient processing (collects errors but continues)
    println!("\n🔄 Lenient Processing:");
    match processor.process_file_lenient() {
        Ok((records, errors)) => {
            println!("✅ Processed {} valid records", records.len());
            for record in &records {
                println!("  Record {}: {} (${:.2}) - {}", 
                         record.id, record.name, record.value, 
                         if record.active { "Active" } else { "Inactive" });
            }
            
            if !errors.is_empty() {
                println!("\n⚠️  {} errors encountered:", errors.len());
                for error in errors {
                    println!("  • {}", error);
                }
            }
        },
        Err(e) => println!("❌ Failed to read file: {}", e),
    }
    
    // Summary processing
    println!("\n📊 Processing Summary:");
    match processor.get_summary() {
        Ok(summary) => {
            println!("Total records: {}", summary.total_records);
            println!("Errors: {}", summary.error_count);
            println!("Total value: ${:.2}", summary.total_value);
            println!("Active records: {}", summary.active_count);
            println!("Average value: ${:.2}", summary.average_value);
        },
        Err(e) => println!("❌ Failed to generate summary: {}", e),
    }
    
    // Cleanup
    if let Err(e) = std::fs::remove_file("sample_data.csv") {
        eprintln!("Warning: Failed to cleanup sample file: {}", e);
    }
}
```

**Explanation:**
This solution demonstrates comprehensive error handling:
- **Custom error types**: Enum covering different error categories
- **Error conversion**: Automatic conversion from standard library errors
- **Context preservation**: Line numbers and detailed error messages
- **Graceful degradation**: Lenient processing mode that collects errors
- **Error propagation**: Proper use of ? operator throughout
- **Validation logic**: Business rule validation with meaningful messages

</details>

---

## Chapter 7: Modules and Packages
📊 **Progress:** Chapter 7 of 11 | 🎯 **Learning Objectives:** Organize code with modules, packages, and crates | ⏱️ **Estimated Time:** 65 minutes | 📋 **Prerequisites:** Chapters 1-6 completed

### Module System

Rust's module system helps you organize code into namespaces and control privacy.

**Basic Module Definition:**
```rust
mod front_of_house {
    mod hosting {
        fn add_to_waitlist() {}
        fn seat_at_table() {}
    }
    
    mod serving {
        fn take_order() {}
        fn serve_order() {}
        fn take_payment() {}
    }
}

fn main() {
    // This won't work - modules are private by default
    // front_of_house::hosting::add_to_waitlist();
}
```

**Public Modules and Functions:**
```rust
mod front_of_house {
    pub mod hosting {
        pub fn add_to_waitlist() {
            println!("Adding to waitlist");
        }
        
        fn seat_at_table() {
            println!("Seating at table");
        }
    }
    
    pub mod serving {
        pub fn take_order() {
            println!("Taking order");
        }
        
        pub fn serve_order() {
            println!("Serving order");
        }
        
        fn take_payment() {
            println!("Taking payment");
        }
    }
}

fn main() {
    // Now this works
    front_of_house::hosting::add_to_waitlist();
    front_of_house::serving::take_order();
    
    // This still won't work - seat_at_table is private
    // front_of_house::hosting::seat_at_table();
}
```

**Relative Paths with super:**
```rust
mod front_of_house {
    pub mod hosting {
        pub fn add_to_waitlist() {
            println!("Adding to waitlist");
        }
    }
}

fn deliver_order() {
    println!("Delivering order");
}

mod back_of_house {
    pub struct Breakfast {
        pub toast: String,
        seasonal_fruit: String, // private field
    }
    
    impl Breakfast {
        pub fn summer(toast: &str) -> Breakfast {
            Breakfast {
                toast: String::from(toast),
                seasonal_fruit: String::from("peaches"),
            }
        }
    }
    
    pub enum Appetizer {
        Soup,
        Salad,
    }
    
    fn fix_incorrect_order() {
        cook_order();
        super::deliver_order(); // Call function in parent module
    }
    
    fn cook_order() {
        println!("Cooking order");
    }
}

fn main() {
    let mut meal = back_of_house::Breakfast::summer("Rye");
    meal.toast = String::from("Wheat"); // Can modify public field
    println!("I'd like {} toast please", meal.toast);
    
    // This won't work - seasonal_fruit is private
    // meal.seasonal_fruit = String::from("blueberries");
    
    let order1 = back_of_house::Appetizer::Soup;
    let order2 = back_of_house::Appetizer::Salad;
}
```

**Module Files:**
```rust
// src/lib.rs or src/main.rs
mod garden;

pub use crate::garden::vegetables::Asparagus;

fn main() {
    let plant = Asparagus {};
    println!("I'm growing {:?}!", plant);
}

// src/garden.rs
pub mod vegetables;

// src/garden/vegetables.rs
#[derive(Debug)]
pub struct Asparagus {}
```

**Inline Module Example:**
```rust
mod math {
    pub mod arithmetic {
        pub fn add(a: i32, b: i32) -> i32 {
            a + b
        }
        
        pub fn subtract(a: i32, b: i32) -> i32 {
            a - b
        }
        
        pub fn multiply(a: i32, b: i32) -> i32 {
            a * b
        }
        
        pub fn divide(a: i32, b: i32) -> Option<i32> {
            if b != 0 {
                Some(a / b)
            } else {
                None
            }
        }
    }
    
    pub mod geometry {
        pub struct Rectangle {
            pub width: f64,
            pub height: f64,
        }
        
        impl Rectangle {
            pub fn new(width: f64, height: f64) -> Self {
                Rectangle { width, height }
            }
            
            pub fn area(&self) -> f64 {
                self.width * self.height
            }
            
            pub fn perimeter(&self) -> f64 {
                2.0 * (self.width + self.height)
            }
        }
        
        pub fn circle_area(radius: f64) -> f64 {
            std::f64::consts::PI * radius * radius
        }
    }
}

fn main() {
    // Using arithmetic functions
    let sum = math::arithmetic::add(5, 3);
    let difference = math::arithmetic::subtract(10, 4);
    let product = math::arithmetic::multiply(6, 7);
    
    println!("Sum: {}, Difference: {}, Product: {}", sum, difference, product);
    
    match math::arithmetic::divide(15, 3) {
        Some(result) => println!("Division result: {}", result),
        None => println!("Cannot divide by zero"),
    }
    
    // Using geometry functions
    let rect = math::geometry::Rectangle::new(5.0, 3.0);
    println!("Rectangle area: {:.2}", rect.area());
    println!("Rectangle perimeter: {:.2}", rect.perimeter());
    
    let circle_area = math::geometry::circle_area(2.5);
    println!("Circle area: {:.2}", circle_area);
}
```

### Packages and Crates

A package is a bundle of one or more crates. A crate is a compilation unit in Rust.

**Package Structure:**
```
my_project/
├── Cargo.toml
├── src/
│   ├── main.rs          # Binary crate root
│   ├── lib.rs           # Library crate root
│   └── bin/
│       ├── another_binary.rs
│       └── yet_another.rs
├── tests/
│   └── integration_test.rs
├── examples/
│   └── simple_example.rs
└── benches/
    └── my_benchmark.rs
```

**Cargo.toml Example:**
```toml
[package]
name = "my_restaurant"
version = "0.1.0"
edition = "2021"
authors = ["Your Name <you@example.com>"]
description = "A sample restaurant management system"
license = "MIT"
repository = "https://github.com/username/my_restaurant"
keywords = ["restaurant", "management"]
categories = ["command-line-utilities"]

[dependencies]
serde = { version = "1.0", features = ["derive"] }
tokio = { version = "1.0", features = ["full"] }
clap = "4.0"

[dev-dependencies]
criterion = "0.4"

[lib]
name = "restaurant"
path = "src/lib.rs"

[[bin]]
name = "restaurant_server"
path = "src/bin/server.rs"

[[bin]]
name = "restaurant_cli"
path = "src/bin/cli.rs"

[features]
default = ["cli"]
cli = ["clap"]
server = ["tokio"]
```

**Library Crate (src/lib.rs):**
```rust
//! # Restaurant Library
//! 
//! A library for managing restaurant operations.

pub mod front_of_house;
pub mod back_of_house;

pub use crate::front_of_house::hosting;
pub use crate::back_of_house::{Breakfast, Appetizer};

/// Simulate eating at the restaurant
pub fn eat_at_restaurant() {
    // Order a breakfast in the summer with Rye toast
    let mut meal = Breakfast::summer("Rye");
    
    // Change our mind about what bread we'd like
    meal.toast = String::from("Wheat");
    println!("I'd like {} toast please", meal.toast);
    
    // The next line won't compile if we uncomment it; we're not allowed
    // to see or modify the seasonal fruit that comes with the meal
    // meal.seasonal_fruit = String::from("blueberries");
    
    let order1 = Appetizer::Soup;
    let order2 = Appetizer::Salad;
    
    hosting::add_to_waitlist();
    hosting::seat_at_table();
}

#[cfg(test)]
mod tests {
    use super::*;
    
    #[test]
    fn test_eat_at_restaurant() {
        eat_at_restaurant();
    }
}
```

**Binary Crate (src/main.rs):**
```rust
use my_restaurant::{eat_at_restaurant, hosting};

fn main() {
    eat_at_restaurant();
    hosting::add_to_waitlist();
}
```

### Use Keyword

The `use` keyword brings paths into scope so you don't have to write the full path each time.

**Basic Use Statements:**
```rust
mod front_of_house {
    pub mod hosting {
        pub fn add_to_waitlist() {}
        pub fn seat_at_table() {}
    }
}

// Bring the hosting module into scope
use crate::front_of_house::hosting;

// Bring specific functions into scope
use crate::front_of_house::hosting::add_to_waitlist;

fn main() {
    hosting::seat_at_table();
    add_to_waitlist();
}
```

**Use with Aliases:**
```rust
use std::collections::HashMap as Map;
use std::io::Result as IoResult;

fn main() {
    let mut scores: Map<String, i32> = Map::new();
    scores.insert(String::from("Blue"), 10);
    
    // Function that returns IoResult instead of std::io::Result
    fn read_file() -> IoResult<String> {
        Ok(String::from("file contents"))
    }
}
```

**Nested Paths:**
```rust
// Instead of:
// use std::cmp::Ordering;
// use std::io;

// You can write:
use std::{cmp::Ordering, io};

// Instead of:
// use std::io;
// use std::io::Write;

// You can write:
use std::io::{self, Write};

// Glob operator brings all public items into scope
use std::collections::*;
```

**Re-exporting with pub use:**
```rust
mod front_of_house {
    pub mod hosting {
        pub fn add_to_waitlist() {}
    }
}

// Re-export hosting so external code can use it directly
pub use crate::front_of_house::hosting;

// Now external code can call this crate's hosting::add_to_waitlist()
// instead of this_crate::front_of_house::hosting::add_to_waitlist()
```

**Conditional Use:**
```rust
// Use different modules based on target OS
#[cfg(target_os = "windows")]
use std::os::windows::fs::MetadataExt;

#[cfg(target_os = "linux")]
use std::os::linux::fs::MetadataExt;

// Use for testing only
#[cfg(test)]
use std::collections::HashMap;
```

### Publishing Crates

Publishing your crates to crates.io makes them available to the entire Rust community.

**Preparing for Publication:**
```toml
[package]
name = "my_awesome_crate"
version = "0.1.0"
edition = "2021"
authors = ["Your Name <you@example.com>"]
description = "An awesome crate that does awesome things"
license = "MIT OR Apache-2.0"
repository = "https://github.com/yourusername/my_awesome_crate"
documentation = "https://docs.rs/my_awesome_crate"
homepage = "https://github.com/yourusername/my_awesome_crate"
readme = "README.md"
keywords = ["awesome", "utility", "example"]
categories = ["command-line-utilities", "development-tools"]

[dependencies]
# Your dependencies here
```

**Documentation Comments:**
```rust
//! # My Awesome Crate
//! 
//! This crate provides awesome functionality for doing awesome things.
//! 
//! ## Examples
//! 
//! ```
//! use my_awesome_crate::awesome_function;
//! 
//! let result = awesome_function(42);
//! assert_eq!(result, 42);
//! ```

/// Performs an awesome operation on the input.
/// 
/// # Arguments
/// 
/// * `input` - The input value to process
/// 
/// # Returns
/// 
/// Returns the processed value.
/// 
/// # Examples
/// 
/// ```
/// use my_awesome_crate::awesome_function;
/// 
/// let result = awesome_function(10);
/// assert_eq!(result, 10);
/// ```
/// 
/// # Panics
/// 
/// This function panics if the input is negative.
/// 
/// # Errors
/// 
/// This function returns an error if something goes wrong.
/// 
/// # Safety
/// 
/// This function is safe to call from any thread.
pub fn awesome_function(input: i32) -> i32 {
    if input < 0 {
        panic!("Input cannot be negative");
    }
    input
}

/// Configuration struct for awesome operations.
/// 
/// # Examples
/// 
/// ```
/// use my_awesome_crate::AwesomeConfig;
/// 
/// let config = AwesomeConfig {
///     enabled: true,
///     max_value: 100,
/// };
/// ```
pub struct AwesomeConfig {
    /// Whether the awesome feature is enabled
    pub enabled: bool,
    /// Maximum value for awesome operations
    pub max_value: i32,
}

impl AwesomeConfig {
    /// Creates a new configuration with default values.
    /// 
    /// # Examples
    /// 
    /// ```
    /// use my_awesome_crate::AwesomeConfig;
    /// 
    /// let config = AwesomeConfig::new();
    /// assert_eq!(config.enabled, true);
    /// ```
    pub fn new() -> Self {
        AwesomeConfig {
            enabled: true,
            max_value: 1000,
        }
    }
}
```

**Publishing Commands:**
```bash
# Login to crates.io (get API token from crates.io)
cargo login [your-api-token]

# Check that your crate can be packaged
cargo package

# Publish your crate
cargo publish

# Yank a version (doesn't delete, but prevents new usage)
cargo yank --vers 1.0.1

# Un-yank a version
cargo yank --vers 1.0.1 --undo
```

### ⚠️ Common Pitfalls

1. **Circular dependencies**: Avoid modules that depend on each other
2. **Overly deep nesting**: Keep module hierarchies reasonable
3. **Forgetting pub**: Private items aren't accessible from outside
4. **Incorrect use paths**: Use relative paths (crate::) vs absolute paths
5. **Not documenting public APIs**: Always document public functions and types

### ✅ Best Practices

1. **Organize by functionality**: Group related code in modules
2. **Use clear naming**: Module names should indicate their purpose
3. **Minimize public APIs**: Only expose what users need
5. **Write good documentation**: Include examples in doc comments
6. **Use semantic versioning**: Follow semver for version numbers
7. **Test your public API**: Ensure examples in documentation work

### 🏋️ Exercise 8: Multi-Module Library
**Difficulty:** 🔴 Advanced
**Estimated Time:** 40 minutes

Create a multi-module library for a task management system with proper organization, documentation, and public APIs.

<details>
<summary>💡 Click to see hints</summary>

- Organize modules by domain (tasks, users, projects)
- Use proper visibility modifiers (pub, pub(crate), private)
- Implement re-exports for clean public API
- Write comprehensive documentation with examples
- Include both unit and integration tests

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
//! # Task Management Library
//! 
//! A comprehensive library for managing tasks, users, and projects.
//! 
//! ## Quick Start
//! 
//! ```rust
//! use task_manager::{Task, User, Project, TaskManager};
//! 
//! let mut manager = TaskManager::new();
//! let user_id = manager.create_user("Alice".to_string(), "alice@example.com".to_string());
//! let project_id = manager.create_project("My Project".to_string(), "A sample project".to_string());
//! let task_id = manager.create_task("Complete documentation".to_string(), user_id, project_id);
//! ```

pub mod tasks;
pub mod users;
pub mod projects;
pub mod manager;

// Re-export main types for easy access
pub use tasks::{Task, TaskStatus, Priority};
pub use users::User;
pub use projects::Project;
pub use manager::TaskManager;

/// Result type used throughout the library
pub type Result<T> = std::result::Result<T, Error>;

/// Library-specific error types
#[derive(Debug, Clone)]
pub enum Error {
    /// User not found
    UserNotFound(u32),
    /// Task not found
    TaskNotFound(u32),
    /// Project not found
    ProjectNotFound(u32),
    /// Validation error
    ValidationError(String),
    /// Permission denied
    PermissionDenied(String),
}

impl std::fmt::Display for Error {
    fn fmt(&self, f: &mut std::fmt::Formatter<'_>) -> std::fmt::Result {
        match self {
            Error::UserNotFound(id) => write!(f, "User with ID {} not found", id),
            Error::TaskNotFound(id) => write!(f, "Task with ID {} not found", id),
            Error::ProjectNotFound(id) => write!(f, "Project with ID {} not found", id),
            Error::ValidationError(msg) => write!(f, "Validation error: {}", msg),
            Error::PermissionDenied(msg) => write!(f, "Permission denied: {}", msg),
        }
    }
}

impl std::error::Error for Error {}

// src/tasks.rs
/// Task management module
use crate::{Error, Result};
use std::collections::HashMap;

/// Task priority levels
#[derive(Debug, Clone, Copy, PartialEq, Eq, Hash)]
pub enum Priority {
    Low,
    Medium,
    High,
    Critical,
}

/// Task status
#[derive(Debug, Clone, Copy, PartialEq, Eq)]
pub enum TaskStatus {
    Todo,
    InProgress,
    Review,
    Done,
    Cancelled,
}

/// A task in the system
#[derive(Debug, Clone)]
pub struct Task {
    pub id: u32,
    pub title: String,
    pub description: String,
    pub status: TaskStatus,
    pub priority: Priority,
    pub assignee_id: Option<u32>,
    pub project_id: u32,
    pub created_at: String,
    pub updated_at: String,
    pub due_date: Option<String>,
    pub tags: Vec<String>,
}

impl Task {
    /// Creates a new task
    /// 
    /// # Arguments
    /// 
    /// * `id` - Unique task identifier
    /// * `title` - Task title
    /// * `project_id` - ID of the project this task belongs to
    /// 
    /// # Examples
    /// 
    /// ```
    /// use task_manager::tasks::{Task, TaskStatus, Priority};
    /// 
    /// let task = Task::new(1, "Complete feature".to_string(), 100);
    /// assert_eq!(task.status, TaskStatus::Todo);
    /// assert_eq!(task.priority, Priority::Medium);
    /// ```
    pub fn new(id: u32, title: String, project_id: u32) -> Self {
        let now = chrono::Utc::now().to_rfc3339();
        Task {
            id,
            title,
            description: String::new(),
            status: TaskStatus::Todo,
            priority: Priority::Medium,
            assignee_id: None,
            project_id,
            created_at: now.clone(),
            updated_at: now,
            due_date: None,
            tags: Vec::new(),
        }
    }
    
    /// Assigns the task to a user
    pub fn assign_to(&mut self, user_id: u32) {
        self.assignee_id = Some(user_id);
        self.update_timestamp();
    }
    
    /// Updates the task status
    pub fn set_status(&mut self, status: TaskStatus) {
        self.status = status;
        self.update_timestamp();
    }
    
    /// Sets the task priority
    pub fn set_priority(&mut self, priority: Priority) {
        self.priority = priority;
        self.update_timestamp();
    }
    
    /// Adds a tag to the task
    pub fn add_tag(&mut self, tag: String) {
        if !self.tags.contains(&tag) {
            self.tags.push(tag);
            self.update_timestamp();
        }
    }
    
    /// Checks if the task is overdue
    pub fn is_overdue(&self) -> bool {
        if let Some(due_date) = &self.due_date {
            let now = chrono::Utc::now().to_rfc3339();
            due_date < &now && self.status != TaskStatus::Done
        } else {
            false
        }
    }
    
    fn update_timestamp(&mut self) {
        self.updated_at = chrono::Utc::now().to_rfc3339();
    }
}

/// Task repository for managing task persistence
pub struct TaskRepository {
    tasks: HashMap<u32, Task>,
    next_id: u32,
}

impl TaskRepository {
    pub fn new() -> Self {
        TaskRepository {
            tasks: HashMap::new(),
            next_id: 1,
        }
    }
    
    pub fn create_task(&mut self, title: String, project_id: u32) -> u32 {
        let id = self.next_id;
        let task = Task::new(id, title, project_id);
        self.tasks.insert(id, task);
        self.next_id += 1;
        id
    }
    
    pub fn get_task(&self, id: u32) -> Result<&Task> {
        self.tasks.get(&id).ok_or(Error::TaskNotFound(id))
    }
    
    pub fn get_task_mut(&mut self, id: u32) -> Result<&mut Task> {
        self.tasks.get_mut(&id).ok_or(Error::TaskNotFound(id))
    }
    
    pub fn list_tasks_by_project(&self, project_id: u32) -> Vec<&Task> {
        self.tasks.values()
            .filter(|task| task.project_id == project_id)
            .collect()
    }
    
    pub fn list_tasks_by_assignee(&self, user_id: u32) -> Vec<&Task> {
        self.tasks.values()
            .filter(|task| task.assignee_id == Some(user_id))
            .collect()
    }
    
    pub fn delete_task(&mut self, id: u32) -> Result<Task> {
        self.tasks.remove(&id).ok_or(Error::TaskNotFound(id))
    }
}

// src/users.rs
/// User management module
use crate::{Error, Result};
use std::collections::HashMap;

/// A user in the system
#[derive(Debug, Clone)]
pub struct User {
    pub id: u32,
    pub name: String,
    pub email: String,
    pub role: UserRole,
    pub created_at: String,
    pub is_active: bool,
}

/// User roles in the system
#[derive(Debug, Clone, Copy, PartialEq, Eq)]
pub enum UserRole {
    Admin,
    Manager,
    Developer,
    Viewer,
}

impl User {
    /// Creates a new user
    /// 
    /// # Arguments
    /// 
    /// * `id` - Unique user identifier
    /// * `name` - User's full name
    /// * `email` - User's email address
    /// 
    /// # Examples
    /// 
    /// ```
    /// use task_manager::users::{User, UserRole};
    /// 
    /// let user = User::new(1, "John Doe".to_string(), "john@example.com".to_string());
    /// assert_eq!(user.role, UserRole::Developer);
    /// assert_eq!(user.is_active, true);
    /// ```
    pub fn new(id: u32, name: String, email: String) -> Self {
        User {
            id,
            name,
            email,
            role: UserRole::Developer,
            created_at: chrono::Utc::now().to_rfc3339(),
            is_active: true,
        }
    }
    
    /// Sets the user's role
    pub fn set_role(&mut self, role: UserRole) {
        self.role = role;
    }
    
    /// Deactivates the user
    pub fn deactivate(&mut self) {
        self.is_active = false;
    }
    
    /// Activates the user
    pub fn activate(&mut self) {
        self.is_active = true;
    }
    
    /// Checks if user has admin privileges
    pub fn is_admin(&self) -> bool {
        matches!(self.role, UserRole::Admin)
    }
    
    /// Checks if user can manage projects
    pub fn can_manage_projects(&self) -> bool {
        matches!(self.role, UserRole::Admin | UserRole::Manager)
    }
}

/// User repository for managing user persistence
pub struct UserRepository {
    users: HashMap<u32, User>,
    next_id: u32,
}

impl UserRepository {
    pub fn new() -> Self {
        UserRepository {
            users: HashMap::new(),
            next_id: 1,
        }
    }
    
    pub fn create_user(&mut self, name: String, email: String) -> Result<u32> {
        // Validate email format (simple check)
        if !email.contains('@') {
            return Err(Error::ValidationError("Invalid email format".to_string()));
        }
        
        // Check for duplicate emails
        if self.users.values().any(|u| u.email == email) {
            return Err(Error::ValidationError("Email already exists".to_string()));
        }
        
        let id = self.next_id;
        let user = User::new(id, name, email);
        self.users.insert(id, user);
        self.next_id += 1;
        Ok(id)
    }
    
    pub fn get_user(&self, id: u32) -> Result<&User> {
        self.users.get(&id).ok_or(Error::UserNotFound(id))
    }
    
    pub fn get_user_mut(&mut self, id: u32) -> Result<&mut User> {
        self.users.get_mut(&id).ok_or(Error::UserNotFound(id))
    }
    
    pub fn list_users(&self) -> Vec<&User> {
        self.users.values().collect()
    }
    
    pub fn find_user_by_email(&self, email: &str) -> Option<&User> {
        self.users.values().find(|u| u.email == email)
    }
}

// src/projects.rs
/// Project management module
use crate::{Error, Result};
use std::collections::HashMap;

/// A project in the system
#[derive(Debug, Clone)]
pub struct Project {
    pub id: u32,
    pub name: String,
    pub description: String,
    pub owner_id: u32,
    pub status: ProjectStatus,
    pub created_at: String,
    pub updated_at: String,
    pub members: Vec<u32>,
}

/// Project status
#[derive(Debug, Clone, Copy, PartialEq, Eq)]
pub enum ProjectStatus {
    Planning,
    Active,
    OnHold,
    Completed,
    Cancelled,
}

impl Project {
    /// Creates a new project
    /// 
    /// # Arguments
    /// 
    /// * `id` - Unique project identifier
    /// * `name` - Project name
    /// * `description` - Project description
    /// * `owner_id` - ID of the project owner
    /// 
    /// # Examples
    /// 
    /// ```
    /// use task_manager::projects::{Project, ProjectStatus};
    /// 
    /// let project = Project::new(1, "Web App".to_string(), "A web application".to_string(), 100);
    /// assert_eq!(project.status, ProjectStatus::Planning);
    /// ```
    pub fn new(id: u32, name: String, description: String, owner_id: u32) -> Self {
        let now = chrono::Utc::now().to_rfc3339();
        Project {
            id,
            name,
            description,
            owner_id,
            status: ProjectStatus::Planning,
            created_at: now.clone(),
            updated_at: now,
            members: vec![owner_id],
        }
    }
    
    /// Adds a member to the project
    pub fn add_member(&mut self, user_id: u32) {
        if !self.members.contains(&user_id) {
            self.members.push(user_id);
            self.update_timestamp();
        }
    }
    
    /// Removes a member from the project
    pub fn remove_member(&mut self, user_id: u32) -> Result<()> {
        if user_id == self.owner_id {
            return Err(Error::ValidationError("Cannot remove project owner".to_string()));
        }
        
        self.members.retain(|&id| id != user_id);
        self.update_timestamp();
        Ok(())
    }
    
    /// Sets the project status
    pub fn set_status(&mut self, status: ProjectStatus) {
        self.status = status;
        self.update_timestamp();
    }
    
    /// Checks if user is a member of the project
    pub fn is_member(&self, user_id: u32) -> bool {
        self.members.contains(&user_id)
    }
    
    fn update_timestamp(&mut self) {
        self.updated_at = chrono::Utc::now().to_rfc3339();
    }
}

/// Project repository for managing project persistence
pub struct ProjectRepository {
    projects: HashMap<u32, Project>,
    next_id: u32,
}

impl ProjectRepository {
    pub fn new() -> Self {
        ProjectRepository {
            projects: HashMap::new(),
            next_id: 1,
        }
    }
    
    pub fn create_project(&mut self, name: String, description: String, owner_id: u32) -> u32 {
        let id = self.next_id;
        let project = Project::new(id, name, description, owner_id);
        self.projects.insert(id, project);
        self.next_id += 1;
        id
    }
    
    pub fn get_project(&self, id: u32) -> Result<&Project> {
        self.projects.get(&id).ok_or(Error::ProjectNotFound(id))
    }
    
    pub fn get_project_mut(&mut self, id: u32) -> Result<&mut Project> {
        self.projects.get_mut(&id).ok_or(Error::ProjectNotFound(id))
    }
    
    pub fn list_projects(&self) -> Vec<&Project> {
        self.projects.values().collect()
    }
    
    pub fn list_projects_by_owner(&self, owner_id: u32) -> Vec<&Project> {
        self.projects.values()
            .filter(|project| project.owner_id == owner_id)
            .collect()
    }
    
    pub fn list_projects_by_member(&self, user_id: u32) -> Vec<&Project> {
        self.projects.values()
            .filter(|project| project.is_member(user_id))
            .collect()
    }
}

// src/manager.rs
/// Main task manager orchestrating all operations
use crate::{
    Error, Result,
    tasks::{TaskRepository, TaskStatus, Priority},
    users::{UserRepository, UserRole},
    projects::{ProjectRepository, ProjectStatus},
};

/// Main task management system
pub struct TaskManager {
    task_repo: TaskRepository,
    user_repo: UserRepository,
    project_repo: ProjectRepository,
}

impl TaskManager {
    /// Creates a new task manager instance
    pub fn new() -> Self {
        TaskManager {
            task_repo: TaskRepository::new(),
            user_repo: UserRepository::new(),
            project_repo: ProjectRepository::new(),
        }
    }
    
    /// Creates a new user
    pub fn create_user(&mut self, name: String, email: String) -> Result<u32> {
        self.user_repo.create_user(name, email)
    }
    
    /// Creates a new project
    pub fn create_project(&mut self, name: String, description: String, owner_id: u32) -> Result<u32> {
        // Verify owner exists
        self.user_repo.get_user(owner_id)?;
        Ok(self.project_repo.create_project(name, description, owner_id))
    }
    
    /// Creates a new task
    pub fn create_task(&mut self, title: String, assignee_id: u32, project_id: u32) -> Result<u32> {
        // Verify assignee and project exist
        self.user_repo.get_user(assignee_id)?;
        let project = self.project_repo.get_project(project_id)?;
        
        // Check if assignee is a member of the project
        if !project.is_member(assignee_id) {
            return Err(Error::PermissionDenied(
                "User is not a member of this project".to_string()
            ));
        }
        
        let task_id = self.task_repo.create_task(title, project_id);
        let task = self.task_repo.get_task_mut(task_id)?;
        task.assign_to(assignee_id);
        
        Ok(task_id)
    }
    
    /// Assigns a task to a different user
    pub fn reassign_task(&mut self, task_id: u32, new_assignee_id: u32) -> Result<()> {
        let task = self.task_repo.get_task_mut(task_id)?;
        let project = self.project_repo.get_project(task.project_id)?;
        
        // Verify new assignee exists and is project member
        self.user_repo.get_user(new_assignee_id)?;
        if !project.is_member(new_assignee_id) {
            return Err(Error::PermissionDenied(
                "User is not a member of this project".to_string()
            ));
        }
        
        task.assign_to(new_assignee_id);
        Ok(())
    }
    
    /// Updates task status
    pub fn update_task_status(&mut self, task_id: u32, status: TaskStatus) -> Result<()> {
        let task = self.task_repo.get_task_mut(task_id)?;
        task.set_status(status);
        Ok(())
    }
    
    /// Gets project statistics
    pub fn get_project_stats(&self, project_id: u32) -> Result<ProjectStats> {
        let project = self.project_repo.get_project(project_id)?;
        let tasks = self.task_repo.list_tasks_by_project(project_id);
        
        let total_tasks = tasks.len();
        let completed_tasks = tasks.iter().filter(|t| t.status == TaskStatus::Done).count();
        let in_progress_tasks = tasks.iter().filter(|t| t.status == TaskStatus::InProgress).count();
        let overdue_tasks = tasks.iter().filter(|t| t.is_overdue()).count();
        
        Ok(ProjectStats {
            project_name: project.name.clone(),
            total_tasks,
            completed_tasks,
            in_progress_tasks,
            overdue_tasks,
            completion_rate: if total_tasks > 0 {
                completed_tasks as f64 / total_tasks as f64
            } else {
                0.0
            },
        })
    }
}

/// Project statistics
#[derive(Debug)]
pub struct ProjectStats {
    pub project_name: String,
    pub total_tasks: usize,
    pub completed_tasks: usize,
    pub in_progress_tasks: usize,
    pub overdue_tasks: usize,
    pub completion_rate: f64,
}

// Example usage in main.rs or integration tests
fn main() {
    let mut manager = TaskManager::new();
    
    // Create users
    let alice_id = manager.create_user("Alice".to_string(), "alice@example.com".to_string()).unwrap();
    let bob_id = manager.create_user("Bob".to_string(), "bob@example.com".to_string()).unwrap();
    
    // Create project
    let project_id = manager.create_project(
        "Web Application".to_string(),
        "A modern web application".to_string(),
        alice_id
    ).unwrap();
    
    // Create tasks
    let task1_id = manager.create_task(
        "Set up development environment".to_string(),
        alice_id,
        project_id
    ).unwrap();
    
    let task2_id = manager.create_task(
        "Implement user authentication".to_string(),
        bob_id,
        project_id
    ).unwrap();
    
    // Update task status
    manager.update_task_status(task1_id, TaskStatus::Done).unwrap();
    manager.update_task_status(task2_id, TaskStatus::InProgress).unwrap();
    
    // Get project statistics
    let stats = manager.get_project_stats(project_id).unwrap();
    println!("Project: {}", stats.project_name);
    println!("Total tasks: {}", stats.total_tasks);
    println!("Completed: {}", stats.completed_tasks);
    println!("Completion rate: {:.1}%", stats.completion_rate * 100.0);
}

#[cfg(test)]
mod tests {
    use super::*;
    
    #[test]
    fn test_create_user() {
        let mut manager = TaskManager::new();
        let user_id = manager.create_user("Test User".to_string(), "test@example.com".to_string()).unwrap();
        assert_eq!(user_id, 1);
    }
    
    #[test]
    fn test_create_project() {
        let mut manager = TaskManager::new();
        let user_id = manager.create_user("Owner".to_string(), "owner@example.com".to_string()).unwrap();
        let project_id = manager.create_project("Test Project".to_string(), "Description".to_string(), user_id).unwrap();
        assert_eq!(project_id, 1);
    }
    
    #[test]
    fn test_task_workflow() {
        let mut manager = TaskManager::new();
        let user_id = manager.create_user("Developer".to_string(), "dev@example.com".to_string()).unwrap();
        let project_id = manager.create_project("Project".to_string(), "Test project".to_string(), user_id).unwrap();
        let task_id = manager.create_task("Task".to_string(), user_id, project_id).unwrap();
        
        manager.update_task_status(task_id, TaskStatus::InProgress).unwrap();
        manager.update_task_status(task_id, TaskStatus::Done).unwrap();
        
        let stats = manager.get_project_stats(project_id).unwrap();
        assert_eq!(stats.completed_tasks, 1);
        assert_eq!(stats.completion_rate, 1.0);
    }
}
```

**Explanation:**
This comprehensive solution demonstrates professional module organization:
- **Domain-driven structure**: Separate modules for tasks, users, projects, and management
- **Clean public API**: Re-exports and type aliases for easy consumption
- **Comprehensive documentation**: Detailed doc comments with examples
- **Error handling**: Custom error types with proper error propagation
- **Repository pattern**: Separation of data access from business logic
- **Integration**: Main manager orchestrates all operations with proper validation
- **Testing**: Unit tests covering core functionality

</details>

---

## Chapter 8: Generic Types and Traits
📊 **Progress:** Chapter 8 of 11 | 🎯 **Learning Objectives:** Master generic programming and trait system | ⏱️ **Estimated Time:** 80 minutes | 📋 **Prerequisites:** Chapters 1-7 completed

### Generic Functions and Structs

Generics allow you to write flexible, reusable code by defining functions, structs, enums, and methods in terms of types to be specified later.

**Generic Functions:**
```rust
fn largest<T: PartialOrd + Copy>(list: &[T]) -> T {
    let mut largest = list[0];
    
    for &item in list {
        if item > largest {
            largest = item;
        }
    }
    
    largest
}

fn main() {
    let number_list = vec![34, 50, 25, 100, 65];
    let result = largest(&number_list);
    println!("The largest number is {}", result);
    
    let char_list = vec!['y', 'm', 'a', 'q'];
    let result = largest(&char_list);
    println!("The largest char is {}", result);
}
```

**Generic Structs:**
```rust
#[derive(Debug)]
struct Point<T> {
    x: T,
    y: T,
}

#[derive(Debug)]
struct MixedPoint<T, U> {
    x: T,
    y: U,
}

impl<T> Point<T> {
    fn new(x: T, y: T) -> Self {
        Point { x, y }
    }
    
    fn x(&self) -> &T {
        &self.x
    }
}

impl<T, U> MixedPoint<T, U> {
    fn mixup<V, W>(self, other: MixedPoint<V, W>) -> MixedPoint<T, W> {
        MixedPoint {
            x: self.x,
            y: other.y,
        }
    }
}

// Specific implementation for f32
impl Point<f32> {
    fn distance_from_origin(&self) -> f32 {
        (self.x.powi(2) + self.y.powi(2)).sqrt()
    }
}

fn main() {
    let integer_point = Point::new(5, 10);
    let float_point = Point::new(1.0, 4.0);
    let mixed_point = MixedPoint { x: 5, y: 4.0 };
    
    println!("integer_point: {:?}", integer_point);
    println!("float_point: {:?}", float_point);
    println!("mixed_point: {:?}", mixed_point);
    
    println!("Distance from origin: {}", float_point.distance_from_origin());
    
    let p1 = MixedPoint { x: 5, y: 10.4 };
    let p2 = MixedPoint { x: "Hello", y: 'c' };
    let p3 = p1.mixup(p2);
    println!("p3.x = {}, p3.y = {}", p3.x, p3.y);
}
```

**Generic Enums:**
```rust
#[derive(Debug)]
enum Result<T, E> {
    Ok(T),
    Err(E),
}

#[derive(Debug)]
enum Option<T> {
    Some(T),
    None,
}

// Custom generic enum
#[derive(Debug)]
enum Message<T> {
    Text(String),
    Data(T),
    Empty,
}

impl<T> Message<T> {
    fn is_empty(&self) -> bool {
        matches!(self, Message::Empty)
    }
    
    fn unwrap_data(self) -> Option<T> {
        match self {
            Message::Data(data) => Some(data),
            _ => None,
        }
    }
}

fn main() {
    let text_msg = Message::Text("Hello".to_string());
    let data_msg = Message::Data(42);
    let empty_msg: Message<i32> = Message::Empty;
    
    println!("Text message: {:?}", text_msg);
    println!("Data message: {:?}", data_msg);
    println!("Empty message: {:?}", empty_msg);
    
    println!("Is empty: {}", empty_msg.is_empty());
    
    if let Some(data) = data_msg.unwrap_data() {
        println!("Unwrapped data: {}", data);
    }
}
```

### Trait Definitions

Traits define functionality that a particular type has and can share with other types.

**Basic Trait Definition:**
```rust
trait Summary {
    fn summarize(&self) -> String;
    
    // Default implementation
    fn summarize_author(&self) -> String {
        String::from("(Read more...)")
    }
}

struct NewsArticle {
    headline: String,
    location: String,
    author: String,
    content: String,
}

impl Summary for NewsArticle {
    fn summarize(&self) -> String {
        format!("{}, by {} ({})", self.headline, self.author, self.location)
    }
    
    fn summarize_author(&self) -> String {
        format!("@{}", self.author)
    }
}

struct Tweet {
    username: String,
    content: String,
    reply: bool,
    retweet: bool,
}

impl Summary for Tweet {
    fn summarize(&self) -> String {
        format!("{}: {}", self.username, self.content)
    }
}

fn main() {
    let article = NewsArticle {
        headline: String::from("Rust 1.70 Released"),
        location: String::from("Online"),
        author: String::from("Rust Team"),
        content: String::from("The Rust team has released version 1.70..."),
    };
    
    let tweet = Tweet {
        username: String::from("rustlang"),
        content: String::from("Announcing Rust 1.70.0!"),
        reply: false,
        retweet: false,
    };
    
    println!("Article: {}", article.summarize());
    println!("Tweet: {}", tweet.summarize());
    println!("Article author: {}", article.summarize_author());
    println!("Tweet author: {}", tweet.summarize_author()); // Uses default implementation
}
```

**Traits as Parameters:**
```rust
fn notify(item: &impl Summary) {
    println!("Breaking news! {}", item.summarize());
}

// Equivalent syntax
fn notify_verbose<T: Summary>(item: &T) {
    println!("Breaking news! {}", item.summarize());
}

// Multiple trait bounds
fn notify_multiple<T: Summary + Display>(item: &T) {
    println!("Breaking news! {}", item.summarize());
}

// Where clauses for complex bounds
fn some_function<T, U>(t: &T, u: &U) -> i32
where
    T: Display + Clone,
    U: Clone + Debug,
{
    // Function body
    42
}

fn main() {
    let article = NewsArticle {
        headline: String::from("Major Discovery"),
        location: String::from("Lab"),
        author: String::from("Dr. Smith"),
        content: String::from("Scientists have made..."),
    };
    
    notify(&article);
}
```

**Returning Types that Implement Traits:**
```rust
fn returns_summarizable() -> impl Summary {
    Tweet {
        username: String::from("horse_ebooks"),
        content: String::from("of course, as you probably already know, people"),
        reply: false,
        retweet: false,
    }
}

// This won't work - can only return one concrete type
// fn returns_summarizable(switch: bool) -> impl Summary {
//     if switch {
//         NewsArticle { ... }
//     } else {
//         Tweet { ... }  // Error: mismatched types
//     }
// }
```

### Trait Bounds

Trait bounds specify that a generic type must implement particular traits.

**Using Trait Bounds:**
```rust
use std::fmt::Display;

#[derive(Debug, PartialEq, Clone)]
struct Pair<T> {
    x: T,
    y: T,
}

impl<T> Pair<T> {
    fn new(x: T, y: T) -> Self {
        Self { x, y }
    }
}

impl<T: Display + PartialOrd> Pair<T> {
    fn cmp_display(&self) {
        if self.x >= self.y {
            println!("The largest member is x = {}", self.x);
        } else {
            println!("The largest member is y = {}", self.y);
        }
    }
}

// Conditionally implement methods
impl<T: Display> Pair<T> {
    fn print(&self) {
        println!("Pair: ({}, {})", self.x, self.y);
    }
}

fn largest_with_trait<T: PartialOrd + Copy>(list: &[T]) -> T {
    let mut largest = list[0];
    
    for &item in list {
        if item > largest {
            largest = item;
        }
    }
    
    largest
}

fn main() {
    let pair = Pair::new(10, 20);
    pair.cmp_display();
    pair.print();
    
    let numbers = vec![1, 5, 3, 9, 2];
    println!("Largest: {}", largest_with_trait(&numbers));
}
```

**Complex Trait Bounds:**
```rust
use std::fmt::{Debug, Display};

// Multiple bounds
fn compare_and_print<T: Debug + Display + PartialEq>(t1: &T, t2: &T) {
    if t1 == t2 {
        println!("Equal: {} == {}", t1, t2);
    } else {
        println!("Not equal: {} != {}", t1, t2);
    }
    println!("Debug: {:?} vs {:?}", t1, t2);
}

// Lifetime bounds
fn longest_with_an_announcement<'a, T>(
    x: &'a str,
    y: &'a str,
    ann: T,
) -> &'a str
where
    T: Display,
{
    println!("Announcement! {}", ann);
    if x.len() > y.len() {
        x
    } else {
        y
    }
}

fn main() {
    let num1 = 42;
    let num2 = 42;
    compare_and_print(&num1, &num2);
    
    let string1 = "hello";
    let string2 = "world!";
    let announcement = "Today is a great day!";
    let result = longest_with_an_announcement(string1, string2, announcement);
    println!("Longest string: {}", result);
}
```

### Associated Types

Associated types connect a type placeholder with a trait such that the trait method definitions can use these placeholder types.

**Iterator Trait with Associated Types:**
```rust
trait Iterator {
    type Item;
    
    fn next(&mut self) -> Option<Self::Item>;
    
    // Default implementations using associated types
    fn map<B, F>(self, f: F) -> Map<Self, F>
    where
        Self: Sized,
        F: FnMut(Self::Item) -> B,
    {
        Map::new(self, f)
    }
}

struct Counter {
    current: usize,
    max: usize,
}

impl Counter {
    fn new(max: usize) -> Counter {
        Counter { current: 0, max }
    }
}

impl Iterator for Counter {
    type Item = usize;
    
    fn next(&mut self) -> Option<Self::Item> {
        if self.current < self.max {
            let current = self.current;
            self.current += 1;
            Some(current)
        } else {
            None
        }
    }
}

// Generic vs Associated Types comparison
trait Add<Rhs = Self> {
    type Output;
    
    fn add(self, rhs: Rhs) -> Self::Output;
}

#[derive(Debug, PartialEq)]
struct Point {
    x: i32,
    y: i32,
}

impl Add for Point {
    type Output = Point;
    
    fn add(self, other: Point) -> Point {
        Point {
            x: self.x + other.x,
            y: self.y + other.y,
        }
    }
}

// Associated types with generic traits
trait Graph {
    type Node;
    type Edge;
    
    fn has_edge(&self, node1: &Self::Node, node2: &Self::Node) -> bool;
    fn edges(&self, node: &Self::Node) -> Vec<Self::Edge>;
}

struct MyGraph {
    edges: Vec<(usize, usize)>,
}

impl Graph for MyGraph {
    type Node = usize;
    type Edge = (usize, usize);
    
    fn has_edge(&self, node1: &Self::Node, node2: &Self::Node) -> bool {
        self.edges.contains(&(*node1, *node2))
    }
    
    fn edges(&self, node: &Self::Node) -> Vec<Self::Edge> {
        self.edges.iter()
            .filter(|(from, _)| from == node)
            .copied()
            .collect()
    }
}

fn main() {
    let mut counter = Counter::new(3);
    
    while let Some(n) = counter.next() {
        println!("Counter: {}", n);
    }
    
    let point1 = Point { x: 1, y: 0 };
    let point2 = Point { x: 2, y: 3 };
    let point3 = point1 + point2;
    println!("Point addition: {:?}", point3);
    
    let graph = MyGraph {
        edges: vec![(0, 1), (1, 2), (0, 2)],
    };
    
    println!("Has edge 0->1: {}", graph.has_edge(&0, &1));
    println!("Edges from 0: {:?}", graph.edges(&0));
}
```

**Advanced Associated Types:**
```rust
use std::collections::HashMap;

trait Collect<T> {
    type Output;
    
    fn collect(self) -> Self::Output;
}

trait FromIterator<T> {
    fn from_iter<I: IntoIterator<Item = T>>(iter: I) -> Self;
}

// Implementing for Vec
impl<T> FromIterator<T> for Vec<T> {
    fn from_iter<I: IntoIterator<Item = T>>(iter: I) -> Self {
        let mut vec = Vec::new();
        for item in iter {
            vec.push(item);
        }
        vec
    }
}

// Associated type with constraints
trait IntoIterator {
    type Item;
    type IntoIter: Iterator<Item = Self::Item>;
    
    fn into_iter(self) -> Self::IntoIter;
}

// Custom collection with associated types
struct MyCollection<T> {
    items: Vec<T>,
}

impl<T> MyCollection<T> {
    fn new() -> Self {
        MyCollection { items: Vec::new() }
    }
    
    fn add(&mut self, item: T) {
        self.items.push(item);
    }
}

struct MyCollectionIterator<T> {
    items: Vec<T>,
    index: usize,
}

impl<T> Iterator for MyCollectionIterator<T> {
    type Item = T;
    
    fn next(&mut self) -> Option<Self::Item> {
        if self.index < self.items.len() {
            let item = self.items.remove(0);
            Some(item)
        } else {
            None
        }
    }
}

impl<T> IntoIterator for MyCollection<T> {
    type Item = T;
    type IntoIter = MyCollectionIterator<T>;
    
    fn into_iter(self) -> Self::IntoIter {
        MyCollectionIterator {
            items: self.items,
            index: 0,
        }
    }
}

fn main() {
    let mut collection = MyCollection::new();
    collection.add(1);
    collection.add(2);
    collection.add(3);
    
    for item in collection {
        println!("Item: {}", item);
    }
}
```

### ⚠️ Common Pitfalls

1. **Over-constraining generics**: Don't add unnecessary trait bounds
2. **Lifetime conflicts**: Be careful with lifetimes in generic contexts
3. **Type inference issues**: Sometimes you need explicit type annotations
4. **Orphan rule violations**: You can only implement traits you own or for types you own
5. **Associated types vs generics**: Use associated types when there should be one logical implementation

### ✅ Best Practices

1. **Use meaningful type parameter names**: `T` for single types, descriptive names for multiple
2. **Minimize trait bounds**: Only add bounds where actually needed
3. **Prefer associated types**: When there's a natural one-to-one relationship
4. **Document generic constraints**: Explain why certain bounds are required
5. **Use blanket implementations carefully**: They can cause conflicts
6. **Consider coherence rules**: Plan your trait implementations to avoid conflicts

### 🏋️ Exercise 9: Generic Data Structure Library
**Difficulty:** 🔴 Advanced
**Estimated Time:** 50 minutes

Create a generic library for data structures including a binary tree, stack, and queue with comprehensive trait implementations.

<details>
<summary>💡 Click to see hints</summary>

- Define traits for common operations (Insert, Remove, Search)
- Implement generic data structures with appropriate constraints
- Use associated types where appropriate
- Implement standard library traits (Debug, Clone, Iterator)
- Create trait objects for dynamic dispatch where useful

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
use std::fmt::{self, Debug, Display};
use std::cmp::Ordering;

// Common traits for data structures
trait Insert<T> {
    fn insert(&mut self, item: T);
}

trait Remove<T> {
    fn remove(&mut self) -> Option<T>;
}

trait Peek<T> {
    fn peek(&self) -> Option<&T>;
}

trait Search<T> {
    fn contains(&self, item: &T) -> bool;
    fn find(&self, item: &T) -> Option<&T>;
}

trait Size {
    fn len(&self) -> usize;
    fn is_empty(&self) -> bool {
        self.len() == 0
    }
}

// Generic Binary Search Tree
#[derive(Debug, Clone)]
pub struct BinaryTree<T> {
    root: Option<Box<Node<T>>>,
    size: usize,
}

#[derive(Debug, Clone)]
struct Node<T> {
    value: T,
    left: Option<Box<Node<T>>>,
    right: Option<Box<Node<T>>>,
}

impl<T> Node<T> {
    fn new(value: T) -> Self {
        Node {
            value,
            left: None,
            right: None,
        }
    }
}

impl<T> BinaryTree<T> {
    pub fn new() -> Self {
        BinaryTree {
            root: None,
            size: 0,
        }
    }
}

impl<T: Ord> Insert<T> for BinaryTree<T> {
    fn insert(&mut self, item: T) {
        if self.root.is_none() {
            self.root = Some(Box::new(Node::new(item)));
            self.size += 1;
            return;
        }
        
        fn insert_node<T: Ord>(node: &mut Box<Node<T>>, item: T) -> bool {
            match item.cmp(&node.value) {
                Ordering::Less => {
                    if let Some(ref mut left) = node.left {
                        insert_node(left, item)
                    } else {
                        node.left = Some(Box::new(Node::new(item)));
                        true
                    }
                }
                Ordering::Greater => {
                    if let Some(ref mut right) = node.right {
                        insert_node(right, item)
                    } else {
                        node.right = Some(Box::new(Node::new(item)));
                        true
                    }
                }
                Ordering::Equal => false, // Item already exists
            }
        }
        
        if let Some(ref mut root) = self.root {
            if insert_node(root, item) {
                self.size += 1;
            }
        }
    }
}

impl<T: Ord> Search<T> for BinaryTree<T> {
    fn contains(&self, item: &T) -> bool {
        self.find(item).is_some()
    }
    
    fn find(&self, item: &T) -> Option<&T> {
        fn find_node<T: Ord>(node: &Node<T>, item: &T) -> Option<&T> {
            match item.cmp(&node.value) {
                Ordering::Equal => Some(&node.value),
                Ordering::Less => {
                    node.left.as_ref().and_then(|left| find_node(left, item))
                }
                Ordering::Greater => {
                    node.right.as_ref().and_then(|right| find_node(right, item))
                }
            }
        }
        
        self.root.as_ref().and_then(|root| find_node(root, item))
    }
}

impl<T> Size for BinaryTree<T> {
    fn len(&self) -> usize {
        self.size
    }
}

// Tree iterator
pub struct TreeIterator<T> {
    stack: Vec<T>,
}

impl<T: Clone> BinaryTree<T> {
    pub fn iter(&self) -> TreeIterator<T> {
        let mut stack = Vec::new();
        self.collect_inorder(&mut stack);
        TreeIterator { stack }
    }
    
    fn collect_inorder(&self, collection: &mut Vec<T>) {
        fn inorder<T: Clone>(node: &Option<Box<Node<T>>>, collection: &mut Vec<T>) {
            if let Some(ref n) = node {
                inorder(&n.left, collection);
                collection.push(n.value.clone());
                inorder(&n.right, collection);
            }
        }
        inorder(&self.root, collection);
    }
}

impl<T> Iterator for TreeIterator<T> {
    type Item = T;
    
    fn next(&mut self) -> Option<Self::Item> {
        self.stack.pop()
    }
}

// Generic Stack
#[derive(Debug, Clone)]
pub struct Stack<T> {
    items: Vec<T>,
}

impl<T> Stack<T> {
    pub fn new() -> Self {
        Stack { items: Vec::new() }
    }
    
    pub fn with_capacity(capacity: usize) -> Self {
        Stack {
            items: Vec::with_capacity(capacity),
        }
    }
}

impl<T> Insert<T> for Stack<T> {
    fn insert(&mut self, item: T) {
        self.items.push(item);
    }
}

impl<T> Remove<T> for Stack<T> {
    fn remove(&mut self) -> Option<T> {
        self.items.pop()
    }
}

impl<T> Peek<T> for Stack<T> {
    fn peek(&self) -> Option<&T> {
        self.items.last()
    }
}

impl<T> Size for Stack<T> {
    fn len(&self) -> usize {
        self.items.len()
    }
}

// Stack-specific methods
impl<T> Stack<T> {
    pub fn push(&mut self, item: T) {
        self.insert(item);
    }
    
    pub fn pop(&mut self) -> Option<T> {
        self.remove()
    }
    
    pub fn top(&self) -> Option<&T> {
        self.peek()
    }
}

// Generic Queue
#[derive(Debug, Clone)]
pub struct Queue<T> {
    items: Vec<T>,
}

impl<T> Queue<T> {
    pub fn new() -> Self {
        Queue { items: Vec::new() }
    }
    
    pub fn with_capacity(capacity: usize) -> Self {
        Queue {
            items: Vec::with_capacity(capacity),
        }
    }
}

impl<T> Insert<T> for Queue<T> {
    fn insert(&mut self, item: T) {
        self.items.push(item);
    }
}

impl<T> Remove<T> for Queue<T> {
    fn remove(&mut self) -> Option<T> {
        if self.items.is_empty() {
            None
        } else {
            Some(self.items.remove(0))
        }
    }
}

impl<T> Peek<T> for Queue<T> {
    fn peek(&self) -> Option<&T> {
        self.items.first()
    }
}

impl<T> Size for Queue<T> {
    fn len(&self) -> usize {
        self.items.len()
    }
}

// Queue-specific methods
impl<T> Queue<T> {
    pub fn enqueue(&mut self, item: T) {
        self.insert(item);
    }
    
    pub fn dequeue(&mut self) -> Option<T> {
        self.remove()
    }
    
    pub fn front(&self) -> Option<&T> {
        self.peek()
    }
}

// Generic container trait for dynamic dispatch
trait Container<T>: Debug {
    fn add(&mut self, item: T);
    fn size(&self) -> usize;
    fn is_empty(&self) -> bool {
        self.size() == 0
    }
}

impl<T: Debug> Container<T> for Stack<T> {
    fn add(&mut self, item: T) {
        self.push(item);
    }
    
    fn size(&self) -> usize {
        self.len()
    }
}

impl<T: Debug> Container<T> for Queue<T> {
    fn add(&mut self, item: T) {
        self.enqueue(item);
    }
    
    fn size(&self) -> usize {
        self.len()
    }
}

// Generic function working with any container
fn fill_container<T: Debug, C: Container<T>>(container: &mut C, items: Vec<T>) {
    println!("Filling container with {} items", items.len());
    for item in items {
        container.add(item);
    }
    println!("Container now has {} items", container.size());
}

// Trait object example
fn process_containers(containers: &mut [Box<dyn Container<i32>>]) {
    for (i, container) in containers.iter_mut().enumerate() {
        println!("Processing container {}: size = {}", i, container.size());
        for j in 1..=3 {
            container.add(j * 10 + i as i32);
        }
        println!("After adding items: size = {}", container.size());
    }
}

fn main() {
    println!("=== Generic Data Structure Library Demo ===\n");
    
    // Binary Tree Demo
    println!("🌳 Binary Search Tree:");
    let mut tree: BinaryTree<i32> = BinaryTree::new();
    let values = vec![5, 3, 7, 2, 4, 6, 8];
    
    for value in values {
        tree.insert(value);
    }
    
    println!("Tree size: {}", tree.len());
    println!("Contains 4: {}", tree.contains(&4));
    println!("Contains 9: {}", tree.contains(&9));
    
    print!("Tree values (inorder): ");
    for value in tree.iter() {
        print!("{} ", value);
    }
    println!("\n");
    
    // Stack Demo
    println!("📚 Stack:");
    let mut stack: Stack<String> = Stack::new();
    stack.push("First".to_string());
    stack.push("Second".to_string());
    stack.push("Third".to_string());
    
    println!("Stack size: {}", stack.len());
    println!("Top element: {:?}", stack.top());
    
    while let Some(item) = stack.pop() {
        println!("Popped: {}", item);
    }
    println!("Stack is empty: {}\n", stack.is_empty());
    
    // Queue Demo
    println!("📋 Queue:");
    let mut queue: Queue<char> = Queue::new();
    queue.enqueue('A');
    queue.enqueue('B');
    queue.enqueue('C');
    
    println!("Queue size: {}", queue.len());
    println!("Front element: {:?}", queue.front());
    
    while let Some(item) = queue.dequeue() {
        println!("Dequeued: {}", item);
    }
    println!("Queue is empty: {}\n", queue.is_empty());
    
    // Generic container usage
    println!("🔧 Generic Container Functions:");
    let mut stack: Stack<i32> = Stack::new();
    let mut queue: Queue<i32> = Queue::new();
    
    fill_container(&mut stack, vec![1, 2, 3]);
    fill_container(&mut queue, vec![4, 5, 6]);
    
    // Trait objects
    println!("\n📦 Trait Objects:");
    let mut containers: Vec<Box<dyn Container<i32>>> = vec![
        Box::new(Stack::new()),
        Box::new(Queue::new()),
    ];
    
    process_containers(&mut containers);
    
    // Advanced generic usage
    println!("\n🎯 Advanced Generic Usage:");
    let mut numbers = BinaryTree::new();
    let mut words = BinaryTree::new();
    
    for i in [10, 5, 15, 3, 7, 12, 18] {
        numbers.insert(i);
    }
    
    for word in ["banana", "apple", "cherry", "date"] {
        words.insert(word.to_string());
    }
    
    println!("Numbers tree: {:?}", numbers.iter().collect::<Vec<_>>());
    println!("Words tree: {:?}", words.iter().collect::<Vec<_>>());
}

#[cfg(test)]
mod tests {
    use super::*;
    
    #[test]
    fn test_binary_tree() {
        let mut tree = BinaryTree::new();
        assert!(tree.is_empty());
        
        tree.insert(5);
        tree.insert(3);
        tree.insert(7);
        
        assert_eq!(tree.len(), 3);
        assert!(tree.contains(&5));
        assert!(!tree.contains(&10));
    }
    
    #[test]
    fn test_stack() {
        let mut stack = Stack::new();
        assert!(stack.is_empty());
        
        stack.push(1);
        stack.push(2);
        
        assert_eq!(stack.len(), 2);
        assert_eq!(stack.pop(), Some(2));
        assert_eq!(stack.pop(), Some(1));
        assert!(stack.is_empty());
    }
    
    #[test]
    fn test_queue() {
        let mut queue = Queue::new();
        assert!(queue.is_empty());
        
        queue.enqueue('A');
        queue.enqueue('B');
        
        assert_eq!(queue.len(), 2);
        assert_eq!(queue.dequeue(), Some('A'));
        assert_eq!(queue.dequeue(), Some('B'));
        assert!(queue.is_empty());
    }
}
```

**Explanation:**
This comprehensive solution demonstrates advanced generic programming:
- **Trait definitions**: Common interfaces for data structure operations
- **Generic constraints**: Appropriate bounds like `Ord` for searchable structures
- **Associated types**: Used in Iterator implementation
- **Blanket implementations**: Container trait for multiple types
- **Trait objects**: Dynamic dispatch for heterogeneous collections
- **Advanced patterns**: Generic functions, trait bounds, and type relationships

</details>

---

## Chapter 9: Advanced Features
📊 **Progress:** Chapter 9 of 11 | 🎯 **Learning Objectives:** Explore closures, smart pointers, unsafe code, and macros | ⏱️ **Estimated Time:** 95 minutes | 📋 **Prerequisites:** Chapters 1-8 completed

### Closures

Closures are anonymous functions that can capture values from their surrounding scope.

**Basic Closures:**
```rust
fn main() {
    let x = 4;
    
    // Simple closure
    let equal_to_x = |z| z == x;
    
    let y = 4;
    assert!(equal_to_x(y));
    
    // Closure with explicit types
    let expensive_closure = |num: i32| -> i32 {
        println!("calculating slowly...");
        std::thread::sleep(std::time::Duration::from_secs(2));
        num
    };
    
    // Closures can capture their environment
    let list = vec![1, 2, 3];
    println!("Before defining closure: {:?}", list);
    
    let only_borrows = || println!("From closure: {:?}", list);
    
    println!("Before calling closure: {:?}", list);
    only_borrows();
    println!("After calling closure: {:?}", list);
}
```

**Closure Capture Modes:**
```rust
fn main() {
    // Immutable borrow
    let list = vec![1, 2, 3];
    println!("Before defining closure: {:?}", list);
    
    let borrows_immutably = || println!("From closure: {:?}", list);
    
    println!("Before calling closure: {:?}", list);
    borrows_immutably();
    println!("After calling closure: {:?}", list);
    
    // Mutable borrow
    let mut list = vec![1, 2, 3];
    println!("Before defining closure: {:?}", list);
    
    let mut borrows_mutably = || list.push(7);
    
    borrows_mutably();
    println!("After calling closure: {:?}", list);
    
    // Taking ownership with move
    let list = vec![1, 2, 3];
    println!("Before defining closure: {:?}", list);
    
    std::thread::spawn(move || println!("From thread: {:?}", list))
        .join()
        .unwrap();
    
    // println!("After thread: {:?}", list); // Won't compile - list was moved
}
```

**Closure Traits:**
```rust
// Fn, FnMut, and FnOnce traits
fn call_fn<F>(f: F) 
where
    F: Fn() -> String,
{
    println!("Fn result: {}", f());
}

fn call_fn_mut<F>(mut f: F) 
where
    F: FnMut() -> String,
{
    println!("FnMut result: {}", f());
}

fn call_fn_once<F>(f: F) 
where
    F: FnOnce() -> String,
{
    println!("FnOnce result: {}", f());
}

fn main() {
    let s = String::from("hello");
    
    // Closure that implements Fn (immutable borrow)
    let closure_fn = || format!("{} world", s);
    call_fn(closure_fn);
    
    // Closure that implements FnMut (mutable borrow)
    let mut count = 0;
    let mut closure_fn_mut = || {
        count += 1;
        format!("Count: {}", count)
    };
    call_fn_mut(&mut closure_fn_mut);
    
    // Closure that implements FnOnce (takes ownership)
    let s = String::from("owned");
    let closure_fn_once = || s; // Takes ownership of s
    call_fn_once(closure_fn_once);
}
```

**Closures in Iterators:**
```rust
#[derive(Debug)]
struct Shoe {
    size: u32,
    style: String,
}

fn shoes_in_size(shoes: Vec<Shoe>, shoe_size: u32) -> Vec<Shoe> {
    shoes.into_iter().filter(|s| s.size == shoe_size).collect()
}

fn main() {
    let shoes = vec![
        Shoe {
            size: 10,
            style: String::from("sneaker"),
        },
        Shoe {
            size: 13,
            style: String::from("sandal"),
        },
        Shoe {
            size: 10,
            style: String::from("boot"),
        },
    ];
    
    let in_my_size = shoes_in_size(shoes, 10);
    println!("Shoes in my size: {:?}", in_my_size);
    
    // Complex closure with capture
    let multiplier = 3;
    let numbers = vec![1, 2, 3, 4, 5];
    
    let results: Vec<i32> = numbers
        .iter()
        .map(|x| x * multiplier)
        .filter(|&x| x > 5)
        .collect();
    
    println!("Filtered results: {:?}", results);
}
```

### Smart Pointers

Smart pointers provide functionality beyond ordinary references, such as reference counting and interior mutability.

**Box<T> for Heap Allocation:**
```rust
use std::boxed::Box;

enum List {
    Cons(i32, Box<List>),
    Nil,
}

use List::{Cons, Nil};

impl List {
    fn len(&self) -> usize {
        match self {
            Cons(_, tail) => 1 + tail.len(),
            Nil => 0,
        }
    }
    
    fn push(&mut self, value: i32) {
        let new_node = Box::new(Cons(value, Box::new(std::mem::replace(self, Nil))));
        *self = Cons(value, new_node);
    }
}

fn main() {
    let b = Box::new(5);
    println!("b = {}", b);
    
    // Recursive data structure
    let list = Cons(1, Box::new(Cons(2, Box::new(Cons(3, Box::new(Nil))))));
    println!("List length: {}", list.len());
    
    // Box allows heap allocation
    let large_array = Box::new([0; 1000]);
    println!("First element: {}", large_array[0]);
}
```

**Rc<T> for Reference Counting:**
```rust
use std::rc::Rc;

enum List {
    Cons(i32, Rc<List>),
    Nil,
}

use List::{Cons, Nil};

fn main() {
    let a = Rc::new(Cons(5, Rc::new(Cons(10, Rc::new(Nil)))));
    println!("Count after creating a: {}", Rc::strong_count(&a));
    
    let b = Cons(3, Rc::clone(&a));
    println!("Count after creating b: {}", Rc::strong_count(&a));
    
    {
        let c = Cons(4, Rc::clone(&a));
        println!("Count after creating c: {}", Rc::strong_count(&a));
    }
    
    println!("Count after c goes out of scope: {}", Rc::strong_count(&a));
}
```

**RefCell<T> for Interior Mutability:**
```rust
use std::cell::RefCell;
use std::rc::Rc;

#[derive(Debug)]
struct Node {
    value: i32,
    children: RefCell<Vec<Rc<Node>>>,
}

impl Node {
    fn new(value: i32) -> Rc<Self> {
        Rc::new(Node {
            value,
            children: RefCell::new(vec![]),
        })
    }
    
    fn add_child(parent: &Rc<Node>, child: Rc<Node>) {
        parent.children.borrow_mut().push(child);
    }
}

trait Messenger {
    fn send(&self, msg: &str);
}

struct LimitTracker<'a, T: Messenger> {
    messenger: &'a T,
    value: usize,
    max: usize,
}

impl<'a, T> LimitTracker<'a, T>
where
    T: Messenger,
{
    pub fn new(messenger: &'a T, max: usize) -> LimitTracker<'a, T> {
        LimitTracker {
            messenger,
            value: 0,
            max,
        }
    }
    
    pub fn set_value(&mut self, value: usize) {
        self.value = value;
        
        let percentage_of_max = self.value as f64 / self.max as f64;
        
        if percentage_of_max >= 1.0 {
            self.messenger.send("Error: You are over your quota!");
        } else if percentage_of_max >= 0.9 {
            self.messenger.send("Urgent warning: You've used up over 90% of your quota!");
        } else if percentage_of_max >= 0.75 {
            self.messenger.send("Warning: You've used up over 75% of your quota");
        }
    }
}

struct MockMessenger {
    sent_messages: RefCell<Vec<String>>,
}

impl MockMessenger {
    fn new() -> MockMessenger {
        MockMessenger {
            sent_messages: RefCell::new(vec![]),
        }
    }
}

impl Messenger for MockMessenger {
    fn send(&self, message: &str) {
        self.sent_messages.borrow_mut().push(String::from(message));
    }
}

fn main() {
    // Tree structure with shared ownership
    let root = Node::new(1);
    let child1 = Node::new(2);
    let child2 = Node::new(3);
    
    Node::add_child(&root, child1);
    Node::add_child(&root, child2);
    
    println!("Root: {:?}", root);
    
    // Interior mutability pattern
    let mock_messenger = MockMessenger::new();
    let mut limit_tracker = LimitTracker::new(&mock_messenger, 100);
    
    limit_tracker.set_value(80);
    
    let messages = mock_messenger.sent_messages.borrow();
    println!("Messages sent: {:?}", *messages);
}
```

### Unsafe Rust

Unsafe Rust allows you to bypass Rust's safety guarantees when you know what you're doing.

**Unsafe Superpowers:**
```rust
fn main() {
    let mut num = 5;
    
    // Creating raw pointers
    let r1 = &num as *const i32;
    let r2 = &mut num as *mut i32;
    
    // Raw pointer to arbitrary memory location
    let address = 0x012345usize;
    let r = address as *const i32;
    
    // Dereferencing raw pointers (unsafe)
    unsafe {
        println!("r1 is: {}", *r1);
        println!("r2 is: {}", *r2);
        // println!("r is: {}", *r); // This could crash!
    }
    
    // Calling unsafe functions
    unsafe fn dangerous() {
        println!("This is dangerous!");
    }
    
    unsafe {
        dangerous();
    }
    
    // Safe abstraction over unsafe code
    use std::slice;
    
    fn split_at_mut(slice: &mut [i32], mid: usize) -> (&mut [i32], &mut [i32]) {
        let len = slice.len();
        let ptr = slice.as_mut_ptr();
        
        assert!(mid <= len);
        
        unsafe {
            (
                slice::from_raw_parts_mut(ptr, mid),
                slice::from_raw_parts_mut(ptr.add(mid), len - mid),
            )
        }
    }
    
    let mut v = vec![1, 2, 3, 4, 5, 6];
    let (left, right) = split_at_mut(&mut v, 3);
    
    println!("Left: {:?}", left);
    println!("Right: {:?}", right);
}
```

**Unsafe Traits:**
```rust
unsafe trait Foo {
    fn foo(&self);
}

unsafe impl Foo for i32 {
    fn foo(&self) {
        println!("Foo for i32: {}", self);
    }
}

// Accessing static variables
static HELLO_WORLD: &str = "Hello, world!";

static mut COUNTER: usize = 0;

fn add_to_count(inc: usize) {
    unsafe {
        COUNTER += inc;
    }
}

fn main() {
    println!("Static string: {}", HELLO_WORLD);
    
    add_to_count(3);
    
    unsafe {
        println!("COUNTER: {}", COUNTER);
    }
}
```

### Macros

Macros allow you to write code that writes other code (metaprogramming).

**Declarative Macros:**
```rust
macro_rules! vec_custom {
    ( $( $x:expr ),* ) => {
        {
            let mut temp_vec = Vec::new();
            $(
                temp_vec.push($x);
            )*
            temp_vec
        }
    };
}

macro_rules! say_hello {
    () => {
        println!("Hello!");
    };
    ($name:expr) => {
        println!("Hello, {}!", $name);
    };
    ($($name:expr),*) => {
        $(
            println!("Hello, {}!", $name);
        )*
    };
}

macro_rules! calculate {
    (eval $e:expr) => {{
        let val: usize = $e;
        println!("{} = {}", stringify!{$e}, val);
    }};
}

fn main() {
    let v: Vec<u32> = vec_custom![1, 2, 3];
    println!("Custom vec: {:?}", v);
    
    say_hello!();
    say_hello!("Alice");
    say_hello!("Bob", "Charlie", "Diana");
    
    calculate! {
        eval 1 + 2 // prints "1 + 2 = 3"
    };
    
    calculate! {
        eval (1 + 2) * 3 // prints "(1 + 2) * 3 = 9"
    };
}
```

**Procedural Macros (overview):**
```rust
// This would be in a separate crate
use proc_macro::TokenStream;
use quote::quote;
use syn;

#[proc_macro_derive(HelloMacro)]
pub fn hello_macro_derive(input: TokenStream) -> TokenStream {
    let ast = syn::parse(input).unwrap();
    impl_hello_macro(&ast)
}

fn impl_hello_macro(ast: &syn::DeriveInput) -> TokenStream {
    let name = &ast.ident;
    let gen = quote! {
        impl HelloMacro for #name {
            fn hello_macro() {
                println!("Hello, Macro! My name is {}!", stringify!(#name));
            }
        }
    };
    gen.into()
}

// Usage in another crate:
// use hello_macro::HelloMacro;
// use hello_macro_derive::HelloMacro;
// 
// #[derive(HelloMacro)]
// struct Pancakes;
// 
// fn main() {
//     Pancakes::hello_macro();
// }
```

### ⚠️ Common Pitfalls

1. **Unnecessary unsafe code**: Only use unsafe when absolutely necessary
2. **Memory leaks with Rc cycles**: Use Weak references to break cycles
3. **Panic in RefCell**: Multiple mutable borrows cause runtime panics
4. **Complex macro debugging**: Macros can be hard to debug when they fail
5. **Closure lifetime issues**: Be careful with captured references

### ✅ Best Practices

1. **Prefer safe abstractions**: Encapsulate unsafe code in safe interfaces
2. **Use smart pointers appropriately**: Box for single ownership, Rc for shared immutable data
3. **Document unsafe code thoroughly**: Explain why it's safe
4. **Keep unsafe blocks minimal**: Minimize the scope of unsafe operations
5. **Test unsafe code extensively**: It bypasses Rust's safety guarantees
6. **Use procedural macros sparingly**: They increase compile times and complexity

### 🏋️ Exercise 10: Custom Smart Pointer
**Difficulty:** 🔴 Advanced
**Estimated Time:** 45 minutes

Create a custom smart pointer with reference counting and weak references to prevent memory leaks.

<details>
<summary>💡 Click to see hints</summary>

- Implement Drop trait for cleanup
- Use unsafe code for raw pointer manipulation
- Implement Deref trait for transparent access
- Handle strong and weak reference counting
- Prevent cycles with weak references

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
use std::ptr::NonNull;
use std::marker::PhantomData;
use std::ops::Deref;

struct MyRc<T> {
    ptr: NonNull<MyRcBox<T>>,
    phantom: PhantomData<MyRcBox<T>>,
}

struct MyWeak<T> {
    ptr: NonNull<MyRcBox<T>>,
    phantom: PhantomData<MyRcBox<T>>,
}

struct MyRcBox<T> {
    strong_count: usize,
    weak_count: usize,
    value: T,
}

impl<T> MyRc<T> {
    fn new(value: T) -> Self {
        let boxed = Box::new(MyRcBox {
            strong_count: 1,
            weak_count: 1, // The Rc itself holds a weak count
            value,
        });
        
        MyRc {
            ptr: unsafe { NonNull::new_unchecked(Box::into_raw(boxed)) },
            phantom: PhantomData,
        }
    }
    
    fn strong_count(this: &Self) -> usize {
        unsafe { this.ptr.as_ref().strong_count }
    }
    
    fn weak_count(this: &Self) -> usize {
        unsafe { this.ptr.as_ref().weak_count - 1 }
    }
    
    fn downgrade(this: &Self) -> MyWeak<T> {
        unsafe {
            let mut inner = this.ptr.as_ref();
            let inner_mut = &mut *(inner as *const _ as *mut MyRcBox<T>);
            inner_mut.weak_count += 1;
        }
        
        MyWeak {
            ptr: this.ptr,
            phantom: PhantomData,
        }
    }
    
    unsafe fn inner(&self) -> &MyRcBox<T> {
        self.ptr.as_ref()
    }
}

impl<T> Clone for MyRc<T> {
    fn clone(&self) -> Self {
        unsafe {
            let inner = self.ptr.as_ref();
            let inner_mut = &mut *(inner as *const _ as *mut MyRcBox<T>);
            inner_mut.strong_count += 1;
        }
        
        MyRc {
            ptr: self.ptr,
            phantom: PhantomData,
        }
    }
}

impl<T> Deref for MyRc<T> {
    type Target = T;
    
    fn deref(&self) -> &T {
        unsafe { &self.ptr.as_ref().value }
    }
}

impl<T> Drop for MyRc<T> {
    fn drop(&mut self) {
        unsafe {
            let inner = self.ptr.as_ref();
            let inner_mut = &mut *(inner as *const _ as *mut MyRcBox<T>);
            
            inner_mut.strong_count -= 1;
            
            if inner_mut.strong_count == 0 {
                // Drop the value
                std::ptr::drop_in_place(&mut inner_mut.value);
                
                inner_mut.weak_count -= 1;
                if inner_mut.weak_count == 0 {
                    // Deallocate the box
                    let _ = Box::from_raw(self.ptr.as_ptr());
                }
            }
        }
    }
}

impl<T> MyWeak<T> {
    fn upgrade(&self) -> Option<MyRc<T>> {
        unsafe {
            let inner = self.ptr.as_ref();
            let inner_mut = &mut *(inner as *const _ as *mut MyRcBox<T>);
            
            if inner_mut.strong_count > 0 {
                inner_mut.strong_count += 1;
                Some(MyRc {
                    ptr: self.ptr,
                    phantom: PhantomData,
                })
            } else {
                None
            }
        }
    }
    
    fn strong_count(&self) -> usize {
        unsafe { self.ptr.as_ref().strong_count }
    }
    
    fn weak_count(&self) -> usize {
        unsafe { self.ptr.as_ref().weak_count - 1 }
    }
}

impl<T> Clone for MyWeak<T> {
    fn clone(&self) -> Self {
        unsafe {
            let inner = self.ptr.as_ref();
            let inner_mut = &mut *(inner as *const _ as *mut MyRcBox<T>);
            inner_mut.weak_count += 1;
        }
        
        MyWeak {
            ptr: self.ptr,
            phantom: PhantomData,
        }
    }
}

impl<T> Drop for MyWeak<T> {
    fn drop(&mut self) {
        unsafe {
            let inner = self.ptr.as_ref();
            let inner_mut = &mut *(inner as *const _ as *mut MyRcBox<T>);
            
            inner_mut.weak_count -= 1;
            
            if inner_mut.weak_count == 0 && inner_mut.strong_count == 0 {
                let _ = Box::from_raw(self.ptr.as_ptr());
            }
        }
    }
}

// Example usage preventing cycles
#[derive(Debug)]
struct Node {
    value: i32,
    children: Vec<MyRc<Node>>,
    parent: Option<MyWeak<Node>>,
}

impl Node {
    fn new(value: i32) -> MyRc<Self> {
        MyRc::new(Node {
            value,
            children: Vec::new(),
            parent: None,
        })
    }
    
    fn add_child(parent: &MyRc<Node>, child: MyRc<Node>) {
        unsafe {
            let parent_mut = &mut *(parent.deref() as *const _ as *mut Node);
            let child_mut = &mut *(child.deref() as *const _ as *mut Node);
            
            child_mut.parent = Some(MyRc::downgrade(parent));
            parent_mut.children.push(child);
        }
    }
}

fn main() {
    println!("=== Custom Smart Pointer Demo ===");
    
    let data = MyRc::new("Hello, World!".to_string());
    println!("Initial strong count: {}", MyRc::strong_count(&data));
    println!("Data: {}", *data);
    
    {
        let data2 = MyRc::clone(&data);
        println!("Strong count after clone: {}", MyRc::strong_count(&data));
        
        let weak = MyRc::downgrade(&data);
        println!("Weak count: {}", MyRc::weak_count(&data));
        
        // Try to upgrade weak reference
        if let Some(strong_from_weak) = weak.upgrade() {
            println!("Upgraded weak reference: {}", *strong_from_weak);
            println!("Strong count after upgrade: {}", MyRc::strong_count(&data));
        }
        
        println!("About to drop data2...");
    }
    
    println!("Strong count after data2 drop: {}", MyRc::strong_count(&data));
    
    // Tree structure demo
    let root = Node::new(1);
    let child1 = Node::new(2);
    let child2 = Node::new(3);
    
    Node::add_child(&root, child1);
    Node::add_child(&root, child2);
    
    println!("\nTree structure created successfully!");
    println!("Root value: {}", root.value);
    println!("Root has {} children", root.children.len());
    
    for (i, child) in root.children.iter().enumerate() {
        println!("Child {}: value = {}", i, child.value);
        if let Some(parent_weak) = &child.parent {
            if let Some(parent) = parent_weak.upgrade() {
                println!("  Parent value: {}", parent.value);
            }
        }
    }
    
    println!("Final strong count: {}", MyRc::strong_count(&data));
}
```

**Explanation:**
This solution demonstrates advanced unsafe Rust concepts:
- **Custom smart pointer**: Implementing reference counting manually
- **Unsafe memory management**: Raw pointer manipulation with proper safety
- **Trait implementations**: Drop, Clone, Deref for transparent usage
- **Cycle prevention**: Using weak references to prevent memory leaks
- **Memory safety**: Proper cleanup and deallocation handling

</details>

---

## Chapter 10: Concurrency
📊 **Progress:** Chapter 10 of 11 | 🎯 **Learning Objectives:** Master concurrent programming in Rust | ⏱️ **Estimated Time:** 85 minutes | 📋 **Prerequisites:** Chapters 1-9 completed

### Threads

Rust provides excellent support for concurrent programming with threads, channels, and synchronization primitives.

**Creating Threads:**
```rust
use std::thread;
use std::time::Duration;

fn main() {
    // Spawning a thread
    let handle = thread::spawn(|| {
        for i in 1..10 {
            println!("Hi number {} from the spawned thread!", i);
            thread::sleep(Duration::from_millis(1));
        }
    });
    
    // Main thread work
    for i in 1..5 {
        println!("Hi number {} from the main thread!", i);
        thread::sleep(Duration::from_millis(1));
    }
    
    // Wait for thread to complete
    handle.join().unwrap();
}
```

**Moving Data into Threads:**
```rust
use std::thread;

fn main() {
    let v = vec![1, 2, 3];
    
    let handle = thread::spawn(move || {
        println!("Here's a vector: {:?}", v);
    });
    
    handle.join().unwrap();
    
    // v is no longer accessible here due to move
}
```

**Thread Builders:**
```rust
use std::thread;

fn main() {
    let builder = thread::Builder::new()
        .name("worker".to_string())
        .stack_size(32 * 1024);
    
    let handle = builder.spawn(|| {
        println!("Hello from named thread: {}", thread::current().name().unwrap());
        42
    }).unwrap();
    
    let result = handle.join().unwrap();
    println!("Thread returned: {}", result);
}
```

### Message Passing

Rust's channels provide a safe way to communicate between threads using the message passing paradigm.

**Basic Channels:**
```rust
use std::sync::mpsc;
use std::thread;

fn main() {
    let (tx, rx) = mpsc::channel();
    
    thread::spawn(move || {
        let val = String::from("hi");
        tx.send(val).unwrap();
        // val is no longer accessible here
    });
    
    let received = rx.recv().unwrap();
    println!("Got: {}", received);
}
```

**Multiple Messages:**
```rust
use std::sync::mpsc;
use std::thread;
use std::time::Duration;

fn main() {
    let (tx, rx) = mpsc::channel();
    
    thread::spawn(move || {
        let vals = vec![
            String::from("hi"),
            String::from("from"),
            String::from("the"),
            String::from("thread"),
        ];
        
        for val in vals {
            tx.send(val).unwrap();
            thread::sleep(Duration::from_secs(1));
        }
    });
    
    for received in rx {
        println!("Got: {}", received);
    }
}
```

**Multiple Producers:**
```rust
use std::sync::mpsc;
use std::thread;
use std::time::Duration;

fn main() {
    let (tx, rx) = mpsc::channel();
    let tx1 = tx.clone();
    
    thread::spawn(move || {
        let vals = vec![
            String::from("hi"),
            String::from("from"),
            String::from("the"),
            String::from("thread"),
        ];
        
        for val in vals {
            tx1.send(val).unwrap();
            thread::sleep(Duration::from_secs(1));
        }
    });
    
    thread::spawn(move || {
        let vals = vec![
            String::from("more"),
            String::from("messages"),
            String::from("for"),
            String::from("you"),
        ];
        
        for val in vals {
            tx.send(val).unwrap();
            thread::sleep(Duration::from_secs(1));
        }
    });
    
    for received in rx {
        println!("Got: {}", received);
    }
}
```

**Channel Variations:**
```rust
use std::sync::mpsc;
use std::thread;
use std::time::Duration;

fn main() {
    // Bounded channel
    let (tx, rx) = mpsc::sync_channel(2);
    
    let producer = thread::spawn(move || {
        for i in 1..6 {
            println!("Sending {}", i);
            match tx.send(i) {
                Ok(()) => println!("Sent {}", i),
                Err(e) => println!("Failed to send {}: {:?}", i, e),
            }
            thread::sleep(Duration::from_millis(500));
        }
    });
    
    thread::sleep(Duration::from_secs(2)); // Let messages queue up
    
    let consumer = thread::spawn(move || {
        for msg in rx {
            println!("Received: {}", msg);
            thread::sleep(Duration::from_secs(1));
        }
    });
    
    producer.join().unwrap();
    consumer.join().unwrap();
}
```

### Shared State

Sometimes message passing isn't the best approach, and you need shared state with synchronization.

**Mutex for Mutual Exclusion:**
```rust
use std::sync::{Arc, Mutex};
use std::thread;

fn main() {
    let counter = Arc::new(Mutex::new(0));
    let mut handles = vec![];
    
    for _ in 0..10 {
        let counter = Arc::clone(&counter);
        let handle = thread::spawn(move || {
            let mut num = counter.lock().unwrap();
            *num += 1;
        });
        handles.push(handle);
    }
    
    for handle in handles {
        handle.join().unwrap();
    }
    
    println!("Result: {}", *counter.lock().unwrap());
}
```

**RwLock for Read-Write Access:**
```rust
use std::sync::{Arc, RwLock};
use std::thread;
use std::time::Duration;

fn main() {
    let data = Arc::new(RwLock::new(vec![1, 2, 3, 4, 5]));
    let mut handles = vec![];
    
    // Readers
    for i in 0..3 {
        let data = Arc::clone(&data);
        let handle = thread::spawn(move || {
            let reader_id = i;
            for _ in 0..3 {
                let data = data.read().unwrap();
                println!("Reader {} sees: {:?}", reader_id, *data);
                thread::sleep(Duration::from_millis(100));
            }
        });
        handles.push(handle);
    }
    
    // Writers
    for i in 0..2 {
        let data = Arc::clone(&data);
        let handle = thread::spawn(move || {
            let writer_id = i;
            thread::sleep(Duration::from_millis(200));
            let mut data = data.write().unwrap();
            data.push(writer_id + 10);
            println!("Writer {} added element", writer_id);
        });
        handles.push(handle);
    }
    
    for handle in handles {
        handle.join().unwrap();
    }
    
    println!("Final data: {:?}", *data.read().unwrap());
}
```

**Atomic Operations:**
```rust
use std::sync::atomic::{AtomicUsize, Ordering};
use std::sync::Arc;
use std::thread;

fn main() {
    let counter = Arc::new(AtomicUsize::new(0));
    let mut handles = vec![];
    
    for _ in 0..10 {
        let counter = Arc::clone(&counter);
        let handle = thread::spawn(move || {
            for _ in 0..1000 {
                counter.fetch_add(1, Ordering::SeqCst);
            }
        });
        handles.push(handle);
    }
    
    for handle in handles {
        handle.join().unwrap();
    }
    
    println!("Final count: {}", counter.load(Ordering::SeqCst));
    
    // Different ordering examples
    let flag = Arc::new(AtomicUsize::new(0));
    let flag_reader = Arc::clone(&flag);
    let flag_writer = Arc::clone(&flag);
    
    let writer = thread::spawn(move || {
        flag_writer.store(1, Ordering::Relaxed);
        println!("Flag set!");
    });
    
    let reader = thread::spawn(move || {
        while flag_reader.load(Ordering::Relaxed) == 0 {
            thread::yield_now();
        }
        println!("Flag detected!");
    });
    
    writer.join().unwrap();
    reader.join().unwrap();
}
```

### Async Programming

Rust supports asynchronous programming with async/await syntax and the Future trait.

**Basic Async/Await:**
```rust
use std::future::Future;
use std::pin::Pin;
use std::task::{Context, Poll};
use std::time::{Duration, Instant};

// Simple async function
async fn say_hello(name: &str) {
    println!("Hello, {}!", name);
}

async fn compute_async(x: u32) -> u32 {
    // Simulate async work
    async_sleep(Duration::from_millis(100)).await;
    x * 2
}

// Custom async sleep (simplified)
struct Sleep {
    when: Instant,
}

impl Sleep {
    fn new(duration: Duration) -> Self {
        Sleep {
            when: Instant::now() + duration,
        }
    }
}

impl Future for Sleep {
    type Output = ();
    
    fn poll(self: Pin<&mut Self>, _cx: &mut Context<'_>) -> Poll<Self::Output> {
        if Instant::now() >= self.when {
            Poll::Ready(())
        } else {
            Poll::Pending
        }
    }
}

fn async_sleep(duration: Duration) -> Sleep {
    Sleep::new(duration)
}

// Simple executor (real applications use tokio, async-std, etc.)
struct SimpleExecutor;

impl SimpleExecutor {
    fn block_on<F: Future>(future: F) -> F::Output {
        use std::task::{RawWaker, RawWakerVTable, Waker};
        
        let raw_waker = RawWaker::new(std::ptr::null(), &VTABLE);
        let waker = unsafe { Waker::from_raw(raw_waker) };
        let mut context = Context::from_waker(&waker);
        
        let mut future = Box::pin(future);
        loop {
            match future.as_mut().poll(&mut context) {
                Poll::Ready(result) => return result,
                Poll::Pending => {
                    // In a real executor, we'd wait for a wake-up
                    std::thread::sleep(Duration::from_millis(1));
                }
            }
        }
    }
}

static VTABLE: RawWakerVTable = RawWakerVTable::new(
    |_| RawWaker::new(std::ptr::null(), &VTABLE),
    |_| {},
    |_| {},
    |_| {},
);

async fn example_async_workflow() {
    println!("Starting async workflow...");
    
    say_hello("Rust").await;
    
    let result1 = compute_async(5).await;
    let result2 = compute_async(10).await;
    
    println!("Results: {} and {}", result1, result2);
    println!("Async workflow complete!");
}

fn main() {
    println!("=== Concurrency Examples ===\n");
    
    // Basic async example
    SimpleExecutor::block_on(example_async_workflow());
}
```

**Working with Tokio (Real-world async):**
```rust
// This would require tokio = "1.0" in Cargo.toml
// use tokio;
// use tokio::time::{sleep, Duration};
// 
// #[tokio::main]
// async fn main() {
//     let handles = vec![
//         tokio::spawn(async {
//             sleep(Duration::from_millis(100)).await;
//             println!("Task 1 complete");
//             1
//         }),
//         tokio::spawn(async {
//             sleep(Duration::from_millis(200)).await;
//             println!("Task 2 complete");
//             2
//         }),
//         tokio::spawn(async {
//             sleep(Duration::from_millis(150)).await;
//             println!("Task 3 complete");
//             3
//         }),
//     ];
//     
//     let results: Vec<i32> = futures::future::join_all(handles)
//         .await
//         .into_iter()
//         .map(|r| r.unwrap())
//         .collect();
//     
//     println!("All tasks complete: {:?}", results);
// }
```

### ⚠️ Common Pitfalls

1. **Deadlocks**: Be careful about lock ordering and holding multiple locks
2. **Data races**: Even with Rust's safety, logic errors can still occur
3. **Channel closing**: Senders must be dropped to close channels
4. **Thread panics**: Use proper error handling and recovery
5. **Performance overhead**: Don't create threads for trivial work
6. **Async runtime mixing**: Don't mix different async runtimes

### ✅ Best Practices

1. **Prefer message passing**: Use channels when possible for thread communication
2. **Minimize shared state**: Reduce the scope of shared mutable data
3. **Use atomic operations**: For simple counters and flags
4. **Handle thread panics**: Use `catch_unwind` for critical applications
5. **Choose appropriate synchronization**: Mutex vs RwLock vs atomics
6. **Profile concurrent code**: Measure actual performance benefits

### 🏋️ Exercise 11: Producer-Consumer System
**Difficulty:** 🔴 Advanced
**Estimated Time:** 50 minutes

Create a multi-threaded producer-consumer system with work stealing and graceful shutdown.

<details>
<summary>💡 Click to see hints</summary>

- Use multiple producer and consumer threads
- Implement a shared work queue with proper synchronization
- Add graceful shutdown signaling
- Include monitoring and statistics
- Handle backpressure when queue is full

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
use std::sync::{Arc, Mutex, Condvar, atomic::{AtomicBool, AtomicUsize, Ordering}};
use std::thread;
use std::time::{Duration, Instant};
use std::collections::VecDeque;

#[derive(Debug, Clone)]
struct WorkItem {
    id: usize,
    data: String,
    created_at: Instant,
}

impl WorkItem {
    fn new(id: usize, data: String) -> Self {
        WorkItem {
            id,
            data,
            created_at: Instant::now(),
        }
    }
    
    fn processing_time(&self) -> Duration {
        self.created_at.elapsed()
    }
}

struct WorkQueue {
    queue: Mutex<VecDeque<WorkItem>>,
    not_empty: Condvar,
    not_full: Condvar,
    max_size: usize,
}

impl WorkQueue {
    fn new(max_size: usize) -> Self {
        WorkQueue {
            queue: Mutex::new(VecDeque::new()),
            not_empty: Condvar::new(),
            not_full: Condvar::new(),
            max_size,
        }
    }
    
    fn push(&self, item: WorkItem) -> Result<(), WorkItem> {
        let mut queue = self.queue.lock().unwrap();
        
        // Wait if queue is full
        while queue.len() >= self.max_size {
            queue = self.not_full.wait(queue).unwrap();
        }
        
        queue.push_back(item);
        self.not_empty.notify_one();
        Ok(())
    }
    
    fn pop(&self, timeout: Duration) -> Option<WorkItem> {
        let mut queue = self.queue.lock().unwrap();
        let start = Instant::now();
        
        loop {
            if let Some(item) = queue.pop_front() {
                self.not_full.notify_one();
                return Some(item);
            }
            
            if start.elapsed() >= timeout {
                return None;
            }
            
            let remaining = timeout - start.elapsed();
            let (new_queue, timeout_result) = self.not_empty.wait_timeout(queue, remaining).unwrap();
            queue = new_queue;
            
            if timeout_result.timed_out() {
                return None;
            }
        }
    }
    
    fn len(&self) -> usize {
        self.queue.lock().unwrap().len()
    }
    
    fn is_empty(&self) -> bool {
        self.queue.lock().unwrap().is_empty()
    }
}

struct Statistics {
    items_produced: AtomicUsize,
    items_consumed: AtomicUsize,
    total_processing_time: Mutex<Duration>,
    max_processing_time: Mutex<Duration>,
}

impl Statistics {
    fn new() -> Self {
        Statistics {
            items_produced: AtomicUsize::new(0),
            items_consumed: AtomicUsize::new(0),
            total_processing_time: Mutex::new(Duration::new(0, 0)),
            max_processing_time: Mutex::new(Duration::new(0, 0)),
        }
    }
    
    fn record_production(&self) {
        self.items_produced.fetch_add(1, Ordering::Relaxed);
    }
    
    fn record_consumption(&self, processing_time: Duration) {
        self.items_consumed.fetch_add(1, Ordering::Relaxed);
        
        let mut total = self.total_processing_time.lock().unwrap();
        *total += processing_time;
        
        let mut max = self.max_processing_time.lock().unwrap();
        if processing_time > *max {
            *max = processing_time;
        }
    }
    
    fn print_stats(&self) {
        let produced = self.items_produced.load(Ordering::Relaxed);
        let consumed = self.items_consumed.load(Ordering::Relaxed);
        let total_time = *self.total_processing_time.lock().unwrap();
        let max_time = *self.max_processing_time.lock().unwrap();
        
        println!("=== Statistics ===");
        println!("Items produced: {}", produced);
        println!("Items consumed: {}", consumed);
        println!("Items in queue: {}", produced - consumed);
        if consumed > 0 {
            println!("Average processing time: {:?}", total_time / consumed as u32);
            println!("Max processing time: {:?}", max_time);
        }
        println!("==================");
    }
}

struct ProducerConsumerSystem {
    work_queue: Arc<WorkQueue>,
    shutdown_flag: Arc<AtomicBool>,
    statistics: Arc<Statistics>,
}

impl ProducerConsumerSystem {
    fn new(queue_size: usize) -> Self {
        ProducerConsumerSystem {
            work_queue: Arc::new(WorkQueue::new(queue_size)),
            shutdown_flag: Arc::new(AtomicBool::new(false)),
            statistics: Arc::new(Statistics::new()),
        }
    }
    
    fn start_producer(&self, producer_id: usize, items_to_produce: usize) -> thread::JoinHandle<()> {
        let queue = Arc::clone(&self.work_queue);
        let shutdown = Arc::clone(&self.shutdown_flag);
        let stats = Arc::clone(&self.statistics);
        
        thread::spawn(move || {
            println!("Producer {} started", producer_id);
            
            for i in 0..items_to_produce {
                if shutdown.load(Ordering::Relaxed) {
                    break;
                }
                
                let work_item = WorkItem::new(
                    producer_id * 1000 + i,
                    format!("Data from producer {} item {}", producer_id, i),
                );
                
                match queue.push(work_item) {
                    Ok(()) => {
                        stats.record_production();
                        println!("Producer {} produced item {}", producer_id, i);
                    }
                    Err(_) => {
                        println!("Producer {} failed to produce item {}", producer_id, i);
                        break;
                    }
                }
                
                // Simulate variable production rate
                thread::sleep(Duration::from_millis(50 + (i % 100) as u64));
            }
            
            println!("Producer {} finished", producer_id);
        })
    }
    
    fn start_consumer(&self, consumer_id: usize) -> thread::JoinHandle<()> {
        let queue = Arc::clone(&self.work_queue);
        let shutdown = Arc::clone(&self.shutdown_flag);
        let stats = Arc::clone(&self.statistics);
        
        thread::spawn(move || {
            println!("Consumer {} started", consumer_id);
            
            loop {
                if let Some(work_item) = queue.pop(Duration::from_millis(100)) {
                    // Simulate work processing
                    let work_duration = Duration::from_millis(20 + (work_item.id % 80) as u64);
                    thread::sleep(work_duration);
                    
                    let processing_time = work_item.processing_time();
                    stats.record_consumption(processing_time);
                    
                    println!(
                        "Consumer {} processed item {} (took {:?}, queued for {:?})",
                        consumer_id, work_item.id, work_duration, processing_time
                    );
                } else if shutdown.load(Ordering::Relaxed) && queue.is_empty() {
                    break;
                }
            }
            
            println!("Consumer {} finished", consumer_id);
        })
    }
    
    fn start_monitor(&self) -> thread::JoinHandle<()> {
        let queue = Arc::clone(&self.work_queue);
        let shutdown = Arc::clone(&self.shutdown_flag);
        let stats = Arc::clone(&self.statistics);
        
        thread::spawn(move || {
            println!("Monitor started");
            
            while !shutdown.load(Ordering::Relaxed) {
                println!("Queue size: {}", queue.len());
                stats.print_stats();
                thread::sleep(Duration::from_secs(2));
            }
            
            println!("Monitor finished");
            stats.print_stats();
        })
    }
    
    fn shutdown(&self) {
        println!("Initiating shutdown...");
        self.shutdown_flag.store(true, Ordering::Relaxed);
    }
    
    fn run_simulation(&self) {
        let mut handles = vec![];
        
        // Start monitor
        handles.push(self.start_monitor());
        
        // Start producers
        handles.push(self.start_producer(1, 10));
        handles.push(self.start_producer(2, 8));
        handles.push(self.start_producer(3, 12));
        
        // Start consumers
        handles.push(self.start_consumer(1));
        handles.push(self.start_consumer(2));
        
        // Let system run for a while
        thread::sleep(Duration::from_secs(5));
        
        // Wait for producers to finish
        for (i, handle) in handles.into_iter().enumerate() {
            if i < 4 { // First 4 are producers and monitor
                handle.join().unwrap();
            } else {
                // For consumers, initiate shutdown and wait
                self.shutdown();
                handle.join().unwrap();
            }
        }
        
        println!("Simulation complete!");
    }
}

fn main() {
    println!("=== Producer-Consumer System ===\n");
    
    let system = ProducerConsumerSystem::new(5);
    system.run_simulation();
    
    // Advanced example with work stealing
    println!("\n=== Work Stealing Example ===");
    work_stealing_example();
}

fn work_stealing_example() {
    use std::sync::Arc;
    use std::collections::VecDeque;
    
    struct WorkStealingQueue {
        local_queue: Mutex<VecDeque<i32>>,
        global_queue: Arc<Mutex<VecDeque<i32>>>,
    }
    
    impl WorkStealingQueue {
        fn new(global_queue: Arc<Mutex<VecDeque<i32>>>) -> Self {
            WorkStealingQueue {
                local_queue: Mutex::new(VecDeque::new()),
                global_queue,
            }
        }
        
        fn push_local(&self, item: i32) {
            self.local_queue.lock().unwrap().push_back(item);
        }
        
        fn pop_local(&self) -> Option<i32> {
            self.local_queue.lock().unwrap().pop_back()
        }
        
        fn steal_work(&self) -> Option<i32> {
            // Try local queue first
            if let Some(item) = self.pop_local() {
                return Some(item);
            }
            
            // Try global queue
            self.global_queue.lock().unwrap().pop_front()
        }
    }
    
    let global_queue = Arc::new(Mutex::new(VecDeque::new()));
    
    // Fill global queue with work
    {
        let mut queue = global_queue.lock().unwrap();
        for i in 0..20 {
            queue.push_back(i);
        }
    }
    
    let mut handles = vec![];
    
    for worker_id in 0..3 {
        let global_queue = Arc::clone(&global_queue);
        let handle = thread::spawn(move || {
            let work_queue = WorkStealingQueue::new(global_queue);
            let mut work_done = 0;
            
            loop {
                if let Some(work_item) = work_queue.steal_work() {
                    println!("Worker {} processing item {}", worker_id, work_item);
                    thread::sleep(Duration::from_millis(100));
                    work_done += 1;
                } else {
                    break;
                }
            }
            
            println!("Worker {} completed {} items", worker_id, work_done);
        });
        handles.push(handle);
    }
    
    for handle in handles {
        handle.join().unwrap();
    }
}
```

**Explanation:**
This comprehensive solution demonstrates advanced concurrency patterns:
- **Producer-consumer pattern**: Multiple producers and consumers with shared queue
- **Condition variables**: Proper synchronization with waiting and notification
- **Graceful shutdown**: Coordinated shutdown across all threads
- **Statistics tracking**: Thread-safe counters and timing measurements
- **Work stealing**: Advanced load balancing technique
- **Backpressure handling**: Queue size limits with blocking behavior

</details>

---

## Chapter 11: Real-World Applications
📊 **Progress:** Chapter 11 of 11 | 🎯 **Learning Objectives:** Build complete applications using Rust | ⏱️ **Estimated Time:** 120 minutes | 📋 **Prerequisites:** All previous chapters completed

### CLI Application Project

Let's build a complete command-line tool for file processing and analysis.

**Project Structure:**
```
file_analyzer/
├── Cargo.toml
├── src/
│   ├── main.rs
│   ├── lib.rs
│   ├── analyzer/
│   │   ├── mod.rs
│   │   ├── text.rs
│   │   └── stats.rs
│   ├── config/
│   │   └── mod.rs
│   └── utils/
│       └── mod.rs
└── tests/
    └── integration_tests.rs
```

**Complete CLI Application:**
```rust
// Cargo.toml
[package]
name = "file_analyzer"
version = "0.1.0"
edition = "2021"

[dependencies]
clap = { version = "4.0", features = ["derive"] }
serde = { version = "1.0", features = ["derive"] }
serde_json = "1.0"
colored = "2.0"
indicatif = "0.17"
walkdir = "2.3"
regex = "1.5"

// src/main.rs
use clap::{Parser, Subcommand};
use file_analyzer::{Config, FileAnalyzer, AnalysisResult};
use std::path::PathBuf;

#[derive(Parser)]
#[command(name = "file-analyzer")]
#[command(about = "A file analysis tool")]
struct Cli {
    #[command(subcommand)]
    command: Commands,
}

#[derive(Subcommand)]
enum Commands {
    /// Analyze a single file
    File {
        /// Path to the file
        #[arg(short, long)]
        path: PathBuf,
        /// Output format (json, table, summary)
        #[arg(short, long, default_value = "table")]
        format: String,
    },
    /// Analyze a directory
    Directory {
        /// Path to the directory
        #[arg(short, long)]
        path: PathBuf,
        /// File extensions to include
        #[arg(short, long)]
        extensions: Vec<String>,
        /// Maximum depth
        #[arg(long, default_value = "10")]
        max_depth: usize,
    },
    /// Compare two files
    Compare {
        /// First file path
        file1: PathBuf,
        /// Second file path
        file2: PathBuf,
    },
}

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    let cli = Cli::parse();
    
    match cli.command {
        Commands::File { path, format } => {
            let config = Config::default();
            let analyzer = FileAnalyzer::new(config);
            
            match analyzer.analyze_file(&path).await {
                Ok(result) => {
                    display_result(&result, &format);
                }
                Err(e) => {
                    eprintln!("Error analyzing file: {}", e);
                    std::process::exit(1);
                }
            }
        }
        Commands::Directory { path, extensions, max_depth } => {
            let mut config = Config::default();
            config.extensions = extensions;
            config.max_depth = max_depth;
            
            let analyzer = FileAnalyzer::new(config);
            
            match analyzer.analyze_directory(&path).await {
                Ok(results) => {
                    display_directory_results(&results);
                }
                Err(e) => {
                    eprintln!("Error analyzing directory: {}", e);
                    std::process::exit(1);
                }
            }
        }
        Commands::Compare { file1, file2 } => {
            let config = Config::default();
            let analyzer = FileAnalyzer::new(config);
            
            match analyzer.compare_files(&file1, &file2).await {
                Ok(comparison) => {
                    display_comparison(&comparison);
                }
                Err(e) => {
                    eprintln!("Error comparing files: {}", e);
                    std::process::exit(1);
                }
            }
        }
    }
    
    Ok(())
}

fn display_result(result: &AnalysisResult, format: &str) {
    match format {
        "json" => {
            println!("{}", serde_json::to_string_pretty(result).unwrap());
        }
        "table" => {
            println!("File Analysis Results");
            println!("====================");
            println!("Path: {}", result.path.display());
            println!("Size: {} bytes", result.size);
            println!("Lines: {}", result.lines);
            println!("Words: {}", result.words);
            println!("Characters: {}", result.characters);
        }
        "summary" => {
            println!("{}: {} lines, {} words", 
                     result.path.display(), result.lines, result.words);
        }
        _ => {
            eprintln!("Unknown format: {}", format);
        }
    }
}

// Additional display functions would go here...
```

### Web Server Project

Building a REST API server with async Rust.

**Web Server Implementation:**
```rust
// Cargo.toml for web server
[package]
name = "rust_web_server"
version = "0.1.0"
edition = "2021"

[dependencies]
tokio = { version = "1.0", features = ["full"] }
warp = "0.3"
serde = { version = "1.0", features = ["derive"] }
serde_json = "1.0"
uuid = { version = "1.0", features = ["v4", "serde"] }
chrono = { version = "0.4", features = ["serde"] }
sqlx = { version = "0.6", features = ["runtime-tokio-rustls", "postgres", "chrono", "uuid"] }
tracing = "0.1"
tracing-subscriber = "0.3"

// src/main.rs
use warp::Filter;
use std::collections::HashMap;
use std::sync::{Arc, RwLock};
use uuid::Uuid;
use serde::{Deserialize, Serialize};
use chrono::{DateTime, Utc};

#[derive(Debug, Clone, Serialize, Deserialize)]
struct Task {
    id: Uuid,
    title: String,
    description: Option<String>,
    completed: bool,
    created_at: DateTime<Utc>,
    updated_at: DateTime<Utc>,
}

#[derive(Debug, Deserialize)]
struct CreateTaskRequest {
    title: String,
    description: Option<String>,
}

#[derive(Debug, Deserialize)]
struct UpdateTaskRequest {
    title: Option<String>,
    description: Option<String>,
    completed: Option<bool>,
}

type TaskStorage = Arc<RwLock<HashMap<Uuid, Task>>>;

impl Task {
    fn new(title: String, description: Option<String>) -> Self {
        let now = Utc::now();
        Task {
            id: Uuid::new_v4(),
            title,
            description,
            completed: false,
            created_at: now,
            updated_at: now,
        }
    }
    
    fn update(&mut self, request: UpdateTaskRequest) {
        if let Some(title) = request.title {
            self.title = title;
        }
        if let Some(description) = request.description {
            self.description = Some(description);
        }
        if let Some(completed) = request.completed {
            self.completed = completed;
        }
        self.updated_at = Utc::now();
    }
}

async fn get_tasks(storage: TaskStorage) -> Result<impl warp::Reply, warp::Rejection> {
    let tasks: Vec<Task> = storage.read().unwrap().values().cloned().collect();
    Ok(warp::reply::json(&tasks))
}

async fn get_task(id: Uuid, storage: TaskStorage) -> Result<impl warp::Reply, warp::Rejection> {
    let tasks = storage.read().unwrap();
    match tasks.get(&id) {
        Some(task) => Ok(warp::reply::json(task)),
        None => Err(warp::reject::not_found()),
    }
}

async fn create_task(
    request: CreateTaskRequest,
    storage: TaskStorage,
) -> Result<impl warp::Reply, warp::Rejection> {
    let task = Task::new(request.title, request.description);
    let task_id = task.id;
    
    storage.write().unwrap().insert(task_id, task.clone());
    
    Ok(warp::reply::with_status(
        warp::reply::json(&task),
        warp::http::StatusCode::CREATED,
    ))
}

async fn update_task(
    id: Uuid,
    request: UpdateTaskRequest,
    storage: TaskStorage,
) -> Result<impl warp::Reply, warp::Rejection> {
    let mut tasks = storage.write().unwrap();
    match tasks.get_mut(&id) {
        Some(task) => {
            task.update(request);
            Ok(warp::reply::json(task))
        }
        None => Err(warp::reject::not_found()),
    }
}

async fn delete_task(id: Uuid, storage: TaskStorage) -> Result<impl warp::Reply, warp::Rejection> {
    let mut tasks = storage.write().unwrap();
    match tasks.remove(&id) {
        Some(_) => Ok(warp::reply::with_status(
            warp::reply(),
            warp::http::StatusCode::NO_CONTENT,
        )),
        None => Err(warp::reject::not_found()),
    }
}

fn with_storage(storage: TaskStorage) -> impl Filter<Extract = (TaskStorage,), Error = std::convert::Infallible> + Clone {
    warp::any().map(move || storage.clone())
}

async fn handle_rejection(err: warp::Rejection) -> Result<impl warp::Reply, std::convert::Infallible> {
    let code;
    let message;

    if err.is_not_found() {
        code = warp::http::StatusCode::NOT_FOUND;
        message = "NOT_FOUND";
    } else if let Some(_) = err.find::<warp::filters::body::BodyDeserializeError>() {
        code = warp::http::StatusCode::BAD_REQUEST;
        message = "BAD_REQUEST";
    } else if let Some(_) = err.find::<warp::reject::MethodNotAllowed>() {
        code = warp::http::StatusCode::METHOD_NOT_ALLOWED;
        message = "METHOD_NOT_ALLOWED";
    } else {
        eprintln!("Unhandled rejection: {:?}", err);
        code = warp::http::StatusCode::INTERNAL_SERVER_ERROR;
        message = "INTERNAL_SERVER_ERROR";
    }

    let json = warp::reply::json(&serde_json::json!({
        "code": code.as_u16(),
        "message": message,
    }));

    Ok(warp::reply::with_status(json, code))
}

#[tokio::main]
async fn main() {
    // Initialize tracing
    tracing_subscriber::fmt::init();
    
    let storage: TaskStorage = Arc::new(RwLock::new(HashMap::new()));
    
    let tasks_routes = warp::path("tasks")
        .and(
            // GET /tasks
            warp::get()
                .and(warp::path::end())
                .and(with_storage(storage.clone()))
                .and_then(get_tasks)
            .or(
                // POST /tasks
                warp::post()
                    .and(warp::path::end())
                    .and(warp::body::json())
                    .and(with_storage(storage.clone()))
                    .and_then(create_task)
            )
            .or(
                // GET /tasks/:id
                warp::get()
                    .and(warp::path::param())
                    .and(warp::path::end())
                    .and(with_storage(storage.clone()))
                    .and_then(get_task)
            )
            .or(
                // PUT /tasks/:id
                warp::put()
                    .and(warp::path::param())
                    .and(warp::path::end())
                    .and(warp::body::json())
                    .and(with_storage(storage.clone()))
                    .and_then(update_task)
            )
            .or(
                // DELETE /tasks/:id
                warp::delete()
                    .and(warp::path::param())
                    .and(warp::path::end())
                    .and(with_storage(storage.clone()))
                    .and_then(delete_task)
            )
        );
    
    let routes = tasks_routes
        .with(warp::cors().allow_any_origin())
        .recover(handle_rejection)
        .with(warp::log("api"));
    
    println!("Starting server on http://127.0.0.1:3030");
    warp::serve(routes)
        .run(([127, 0, 0, 1], 3030))
        .await;
}
```

### System Programming

**Memory-mapped file processing:**
```rust
use std::fs::File;
use std::io::{self, BufRead, BufReader};
use memmap2::MmapOptions;

struct LargeFileProcessor {
    chunk_size: usize,
}

impl LargeFileProcessor {
    fn new(chunk_size: usize) -> Self {
        LargeFileProcessor { chunk_size }
    }
    
    // Memory-mapped approach for very large files
    fn process_with_mmap(&self, file_path: &str) -> io::Result<FileStats> {
        let file = File::open(file_path)?;
        let mmap = unsafe { MmapOptions::new().map(&file)? };
        
        let mut stats = FileStats::new();
        let mut current_pos = 0;
        
        while current_pos < mmap.len() {
            let end_pos = std::cmp::min(current_pos + self.chunk_size, mmap.len());
            let chunk = &mmap[current_pos..end_pos];
            
            // Process chunk
            for &byte in chunk {
                if byte == b'\n' {
                    stats.line_count += 1;
                } else if byte.is_ascii_whitespace() {
                    stats.word_count += 1;
                }
                stats.byte_count += 1;
            }
            
            current_pos = end_pos;
        }
        
        Ok(stats)
    }
    
    // Buffered approach for normal files
    fn process_with_buffer(&self, file_path: &str) -> io::Result<FileStats> {
        let file = File::open(file_path)?;
        let reader = BufReader::new(file);
        
        let mut stats = FileStats::new();
        
        for line_result in reader.lines() {
            let line = line_result?;
            stats.line_count += 1;
            stats.word_count += line.split_whitespace().count();
            stats.byte_count += line.len() + 1; // +1 for newline
        }
        
        Ok(stats)
    }
}

#[derive(Debug, Default)]
struct FileStats {
    line_count: usize,
    word_count: usize,
    byte_count: usize,
}

impl FileStats {
    fn new() -> Self {
        FileStats::default()
    }
}
```

### Performance Optimization

**Benchmarking and Profiling:**
```rust
use std::time::Instant;

struct PerformanceTimer {
    start: Instant,
    name: String,
}

impl PerformanceTimer {
    fn new(name: &str) -> Self {
        PerformanceTimer {
            start: Instant::now(),
            name: name.to_string(),
        }
    }
}

impl Drop for PerformanceTimer {
    fn drop(&mut self) {
        let elapsed = self.start.elapsed();
        println!("{} took: {:?}", self.name, elapsed);
    }
}

// Example usage
fn optimized_string_processing(input: &str) -> String {
    let _timer = PerformanceTimer::new("string_processing");
    
    // Pre-allocate with estimated capacity
    let mut result = String::with_capacity(input.len() * 2);
    
    // Process in chunks for better cache locality
    for chunk in input.as_bytes().chunks(1024) {
        for &byte in chunk {
            if byte.is_ascii_alphanumeric() {
                result.push(byte as char);
            }
        }
    }
    
    result
}
```

**SIMD Optimizations:**
```rust
// Using SIMD for parallel processing
#[cfg(target_arch = "x86_64")]
use std::arch::x86_64::*;

fn sum_array_simd(arr: &[f32]) -> f32 {
    let mut sum = 0.0f32;
    
    #[cfg(target_arch = "x86_64")]
    {
        if is_x86_feature_detected!("avx2") {
            unsafe {
                return sum_array_avx2(arr);
            }
        }
    }
    
    // Fallback to regular sum
    arr.iter().sum()
}

#[cfg(target_arch = "x86_64")]
unsafe fn sum_array_avx2(arr: &[f32]) -> f32 {
    let mut sum_vec = _mm256_setzero_ps();
    let chunks = arr.chunks_exact(8);
    let remainder = chunks.remainder();
    
    for chunk in chunks {
        let vec = _mm256_loadu_ps(chunk.as_ptr());
        sum_vec = _mm256_add_ps(sum_vec, vec);
    }
    
    // Extract sum from vector
    let mut result = [0.0f32; 8];
    _mm256_storeu_ps(result.as_mut_ptr(), sum_vec);
    let mut sum = result.iter().sum::<f32>();
    
    // Add remainder
    sum += remainder.iter().sum::<f32>();
    
    sum
}
```

### ⚠️ Common Pitfalls

1. **Premature optimization**: Profile first, optimize second
2. **Memory allocation in loops**: Pre-allocate collections when possible
3. **String concatenation**: Use `format!` or `String::with_capacity`
4. **Unnecessary cloning**: Use references and borrowing appropriately
5. **Blocking in async code**: Don't mix sync and async incorrectly
6. **Resource leaks**: Always handle cleanup properly

### ✅ Best Practices

1. **Profile your code**: Use `cargo bench` and profiling tools
2. **Understand your data**: Choose appropriate data structures
3. **Leverage zero-cost abstractions**: Iterators compile to efficient code
4. **Use appropriate concurrency**: Not everything needs to be parallel
5. **Monitor memory usage**: Watch for allocations in hot paths
6. **Test in production-like environments**: Development != production

### 🏋️ Exercise 12: Complete Application
**Difficulty:** 🔴 Advanced
**Estimated Time:** 90 minutes

Build a complete log analyzer application that processes large log files, extracts metrics, and provides a web dashboard.

<details>
<summary>💡 Click to see hints</summary>

- Use memory mapping for large files
- Implement concurrent processing
- Create a REST API for metrics
- Add real-time monitoring capabilities
- Include comprehensive error handling and logging

</details>

<details>
<summary>✅ Click to see solution</summary>

```rust
// This would be a complete application with multiple files
// Here's the main structure and key components:

use std::collections::HashMap;
use std::sync::{Arc, RwLock};
use tokio::sync::mpsc;
use regex::Regex;
use chrono::{DateTime, Utc};
use serde::{Serialize, Deserialize};

#[derive(Debug, Clone, Serialize, Deserialize)]
struct LogEntry {
    timestamp: DateTime<Utc>,
    level: LogLevel,
    message: String,
    source: String,
    metadata: HashMap<String, String>,
}

#[derive(Debug, Clone, Serialize, Deserialize)]
enum LogLevel {
    Error,
    Warn,
    Info,
    Debug,
    Trace,
}

#[derive(Debug, Clone, Serialize, Deserialize)]
struct Metrics {
    total_entries: usize,
    error_count: usize,
    warn_count: usize,
    entries_per_hour: HashMap<String, usize>,
    top_sources: Vec<(String, usize)>,
    response_times: Vec<f64>,
}

struct LogAnalyzer {
    metrics: Arc<RwLock<Metrics>>,
    log_pattern: Regex,
}

impl LogAnalyzer {
    fn new() -> Self {
        let pattern = Regex::new(
            r"(?P<timestamp>\d{4}-\d{2}-\d{2}T\d{2}:\d{2}:\d{2}Z) (?P<level>\w+) (?P<source>\w+): (?P<message>.*)"
        ).unwrap();
        
        LogAnalyzer {
            metrics: Arc::new(RwLock::new(Metrics::default())),
            log_pattern: pattern,
        }
    }
    
    async fn process_log_file(&self, file_path: &str) -> Result<(), Box<dyn std::error::Error>> {
        use std::fs::File;
        use std::io::{BufRead, BufReader};
        
        let file = File::open(file_path)?;
        let reader = BufReader::new(file);
        
        let (tx, mut rx) = mpsc::channel(1000);
        
        // Spawn processing task
        let metrics = self.metrics.clone();
        let processing_task = tokio::spawn(async move {
            while let Some(entry) = rx.recv().await {
                Self::update_metrics(&metrics, entry);
            }
        });
        
        // Parse and send log entries
        for line in reader.lines() {
            let line = line?;
            if let Ok(entry) = self.parse_log_line(&line) {
                tx.send(entry).await?;
            }
        }
        
        drop(tx); // Signal end of input
        processing_task.await?;
        
        Ok(())
    }
    
    fn parse_log_line(&self, line: &str) -> Result<LogEntry, Box<dyn std::error::Error>> {
        let captures = self.log_pattern.captures(line)
            .ok_or("Invalid log format")?;
        
        let timestamp = captures.name("timestamp").unwrap().as_str();
        let level = captures.name("level").unwrap().as_str();
        let source = captures.name("source").unwrap().as_str();
        let message = captures.name("message").unwrap().as_str();
        
        Ok(LogEntry {
            timestamp: DateTime::parse_from_rfc3339(timestamp)?.with_timezone(&Utc),
            level: match level.to_lowercase().as_str() {
                "error" => LogLevel::Error,
                "warn" => LogLevel::Warn,
                "info" => LogLevel::Info,
                "debug" => LogLevel::Debug,
                _ => LogLevel::Trace,
            },
            message: message.to_string(),
            source: source.to_string(),
            metadata: HashMap::new(),
        })
    }
    
    fn update_metrics(metrics: &Arc<RwLock<Metrics>>, entry: LogEntry) {
        let mut metrics = metrics.write().unwrap();
        
        metrics.total_entries += 1;
        
        match entry.level {
            LogLevel::Error => metrics.error_count += 1,
            LogLevel::Warn => metrics.warn_count += 1,
            _ => {}
        }
        
        // Update hourly counts
        let hour_key = entry.timestamp.format("%Y-%m-%d %H").to_string();
        *metrics.entries_per_hour.entry(hour_key).or_insert(0) += 1;
        
        // Track source frequency
        // Update top_sources logic here
    }
    
    fn get_metrics(&self) -> Metrics {
        self.metrics.read().unwrap().clone()
    }
}

impl Default for Metrics {
    fn default() -> Self {
        Metrics {
            total_entries: 0,
            error_count: 0,
            warn_count: 0,
            entries_per_hour: HashMap::new(),
            top_sources: Vec::new(),
            response_times: Vec::new(),
        }
    }
}

#[tokio::main]
async fn main() -> Result<(), Box<dyn std::error::Error>> {
    println!("=== Log Analyzer Application ===");
    
    let analyzer = LogAnalyzer::new();
    
    // Process log files
    if let Err(e) = analyzer.process_log_file("application.log").await {
        eprintln!("Error processing log file: {}", e);
    }
    
    // Display metrics
    let metrics = analyzer.get_metrics();
    println!("Total entries: {}", metrics.total_entries);
    println!("Error count: {}", metrics.error_count);
    println!("Warning count: {}", metrics.warn_count);
    
    Ok(())
}
```

**Complete Application Features:**
- **Concurrent log processing**: Multi-threaded parsing and analysis
- **Memory-efficient**: Streaming processing for large files
- **Real-time metrics**: Live updating statistics
- **Web dashboard**: REST API and WebSocket updates
- **Configurable parsing**: Regex-based log format detection
- **Performance monitoring**: Built-in benchmarking and profiling

</details>

---

## Appendices

### Glossary

**Borrow Checker**: Rust's compile-time system that ensures memory safety by tracking ownership and borrowing rules.

**Cargo**: Rust's package manager and build system that handles dependencies, compilation, and project management.

**Crate**: A compilation unit in Rust, either a library or binary, containing one or more modules.

**Lifetime**: A construct that ensures references are valid for as long as needed, preventing dangling pointers.

**Macro**: Code that writes other code, expanding at compile time to generate additional functionality.

**Ownership**: Rust's system for managing memory through ownership rules that eliminate the need for garbage collection.

**Pattern Matching**: A control flow construct that allows matching values against patterns and executing code based on the match.

**Smart Pointer**: A data structure that acts like a pointer but has additional metadata and capabilities.

**Trait**: A way to define shared behavior across different types, similar to interfaces in other languages.

**Zero-Cost Abstraction**: High-level programming constructs that compile down to the same performance as hand-written low-level code.

### Quick Reference Card

**Variable Declaration:**
```rust
let x = 5;              // Immutable
let mut x = 5;          // Mutable
const X: i32 = 5;       // Constant
```

**Function Definition:**
```rust
fn function_name(param: Type) -> ReturnType {
    // function body
}
```

**Control Flow:**
```rust
if condition { } else { }
match value { pattern => action, }
for item in collection { }
while condition { }
loop { }
```

**Ownership:**
```rust
let s1 = String::from("hello");
let s2 = s1;           // s1 moved to s2
let s3 = s2.clone();   // Deep copy
let len = calculate_length(&s2);  // Borrow
```

**Error Handling:**
```rust
Result<T, E>           // Recoverable errors
Option<T>              // Nullable values
?                      // Error propagation
panic!("message")      // Unrecoverable error
```

**Collections:**
```rust
Vec<T>                 // Dynamic array
HashMap<K, V>          // Hash map
&str / String          // String types
```

**Traits and Generics:**
```rust
trait TraitName { }
impl TraitName for Type { }
fn generic_function<T>(param: T) { }
```

### Further Reading

**Official Resources:**
- [The Rust Programming Language Book](https://doc.rust-lang.org/book/)
- [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/)
- [The Rustonomicon](https://doc.rust-lang.org/nomicon/) (Unsafe Rust)
- [Rust Reference](https://doc.rust-lang.org/reference/)

**Advanced Topics:**
- [Async Programming in Rust](https://rust-lang.github.io/async-book/)
- [The Cargo Book](https://doc.rust-lang.org/cargo/)
- [Rust Performance Book](https://nnethercote.github.io/perf-book/)
- [The Little Book of Rust Macros](https://veykril.github.io/tlborm/)

**Community Resources:**
- [Rust Users Forum](https://users.rust-lang.org/)
- [r/rust subreddit](https://reddit.com/r/rust)
- [Rust Discord Server](https://discord.gg/rust-lang)
- [This Week in Rust Newsletter](https://this-week-in-rust.org/)

### Community Resources

**Learning Platforms:**
- [Rustlings](https://github.com/rust-lang/rustlings) - Interactive Rust exercises
- [Exercism Rust Track](https://exercism.io/tracks/rust) - Programming exercises with mentoring
- [Rust Koans](https://github.com/crazymykl/rust-koans) - Learning through failing tests
- [Tour of Rust](https://tourofrust.com/) - Interactive tour of Rust features

**Development Tools:**
- [Clippy](https://github.com/rust-lang/rust-clippy) - Linting tool for Rust
- [Rustfmt](https://github.com/rust-lang/rustfmt) - Code formatting tool
- [Miri](https://github.com/rust-lang/miri) - Interpreter for unsafe code detection
- [Cargo Expand](https://github.com/dtolnay/cargo-expand) - Macro expansion viewer

**Popular Crates:**
- **Web Development**: actix-web, warp, axum, rocket
- **Async Runtime**: tokio, async-std
- **Serialization**: serde, bincode
- **CLI Tools**: clap, structopt
- **Database**: sqlx, diesel
- **HTTP Clients**: reqwest, hyper

### Contributing Guidelines

**Getting Started with Rust Development:**

1. **Set up your environment**:
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   rustup component add clippy rustfmt
   ```

2. **Create a new project**:
   ```bash
   cargo new my_project
   cd my_project
   ```

3. **Development workflow**:
   ```bash
   cargo check        # Fast compilation check
   cargo test         # Run tests
   cargo clippy       # Linting
   cargo fmt          # Format code
   cargo build        # Debug build
   cargo build --release  # Optimized build
   ```

**Best Practices for Contributing:**
- Follow the [Rust API Guidelines](https://rust-lang.github.io/api-guidelines/)
- Write comprehensive tests and documentation
- Use `cargo fmt` and `cargo clippy` before committing
- Include examples in documentation comments
- Follow semantic versioning for library crates
- Be mindful of backwards compatibility

**Code Style:**
- Use `snake_case` for variables and functions
- Use `PascalCase` for types and traits  
- Use `SCREAMING_SNAKE_CASE` for constants
- Keep line length under 100 characters
- Use meaningful variable and function names
- Document public APIs with examples

**Testing Guidelines:**
- Unit tests go in the same file as the code
- Integration tests go in the `tests/` directory
- Use descriptive test names
- Test both success and error cases
- Use property-based testing for complex logic
- Mock external dependencies appropriately

This comprehensive Rust documentation provides a thorough foundation for learning and mastering the Rust programming language, from basic concepts to advanced real-world applications. The language's emphasis on safety, performance, and concurrency makes it an excellent choice for system programming, web development, and many other domains.




