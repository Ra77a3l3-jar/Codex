# ☕️ Java Documentation
*Version: JDK 21 | Last Updated: December 2024*

Java is a versatile, object-oriented programming language designed for platform independence through the "write once, run anywhere" philosophy. Originally developed by Sun Microsystems in 1995, Java has become one of the world's most popular programming languages for enterprise applications, web development, mobile applications, and large-scale distributed systems.

---

## 📚 Table of Contents

### 🚀 Getting Started
- [1. Introduction & Overview](#1-introduction--overview)
- [2. Installation & Environment Setup](#2-installation--environment-setup)
- [3. Your First Java Program](#3-your-first-java-program)

### 🏗️ Core Language Fundamentals
- [4. Java Syntax & Structure](#4-java-syntax--structure)
- [5. Data Types & Variables](#5-data-types--variables)
- [6. Operators & Expressions](#6-operators--expressions)
- [7. Control Flow Statements](#7-control-flow-statements)

### 🎯 Object-Oriented Programming
- [8. Classes & Objects](#8-classes--objects)
- [9. Inheritance & Polymorphism](#9-inheritance--polymorphism)
- [10. Encapsulation & Access Modifiers](#10-encapsulation--access-modifiers)
- [11. Abstract Classes & Interfaces](#11-abstract-classes--interfaces)

### 🛠️ Advanced Language Features
- [12. Exception Handling](#12-exception-handling)
- [13. Generics](#13-generics)
- [14. Collections Framework](#14-collections-framework)
- [15. Lambda Expressions & Functional Programming](#15-lambda-expressions--functional-programming)
- [16. Streams API](#16-streams-api)

### 🧵 Concurrency & Multithreading
- [17. Thread Fundamentals](#17-thread-fundamentals)
- [18. Synchronization & Thread Safety](#18-synchronization--thread-safety)
- [19. Executor Framework](#19-executor-framework)
- [20. CompletableFuture & Async Programming](#20-completablefuture--async-programming)

### 🏢 Enterprise Features
- [21. Annotations & Reflection](#21-annotations--reflection)
- [22. Modules & JPMS](#22-modules--jpms)
- [23. Records & Pattern Matching](#23-records--pattern-matching)
- [24. Virtual Threads (Project Loom)](#24-virtual-threads-project-loom)

### 🌐 I/O & Networking
- [25. File I/O & NIO.2](#25-file-io--nio2)
- [26. Networking & HTTP Client](#26-networking--http-client)
- [27. Serialization](#27-serialization)

### 🚀 Real-World Applications
- [28. Building a REST API Service](#28-building-a-rest-api-service)
- [29. Database Integration with JDBC](#29-database-integration-with-jdbc)
- [30. Unit Testing with JUnit 5](#30-unit-testing-with-junit-5)

### 📖 Reference & Resources
- [31. Performance Optimization](#31-performance-optimization)
- [32. Best Practices & Design Patterns](#32-best-practices--design-patterns)
- [33. Glossary](#33-glossary)
- [34. Quick Reference Card](#34-quick-reference-card)
- [35. Further Reading](#35-further-reading)

---

## 1. Introduction & Overview

📊 **Chapter 1 of 35**

🎯 **Learning Objectives:**
- Understand Java's history and philosophy
- Learn about the Java ecosystem and JVM
- Identify Java's key features and benefits
- Explore real-world Java applications

⏱️ **Estimated Reading Time:** 15 minutes
📋 **Prerequisites:** Basic programming knowledge helpful but not required

### What is Java?

Java is a high-level, class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible. It is a general-purpose programming language intended to let programmers write once, run anywhere (WORA), meaning that compiled Java code can run on all platforms that support Java without the need to recompile.

### Key Features of Java

#### Platform Independence
Java's "write once, run anywhere" capability is achieved through the Java Virtual Machine (JVM). Java source code is compiled into platform-independent bytecode, which the JVM then interprets or compiles to native machine code.

```java
// This same code runs on Windows, Linux, macOS, etc.
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World from any platform!");
    }
}
```

#### Object-Oriented Programming
Java is fundamentally object-oriented, organizing code into classes and objects that model real-world entities.

```java
// Everything in Java is organized around classes and objects
public class Car {
    private String make;
    private String model;

    public Car(String make, String model) {
        this.make = make;
        this.model = model;
    }

    public void startEngine() {
        System.out.println(make + " " + model + " engine started!");
    }
}
```

#### Memory Management
Java provides automatic memory management through garbage collection, freeing developers from manual memory allocation and deallocation concerns.

```java
public void demonstrateGarbageCollection() {
    // Objects are automatically created on the heap
    List<String> list = new ArrayList<>();
    list.add("This object will be automatically cleaned up");
    // No need to explicitly free memory - garbage collector handles it
}
```

#### Strong Type System
Java's static type system catches many errors at compile time, improving code reliability and maintainability.

```java
// Type safety prevents runtime errors
String text = "Hello";
int number = 42;
// text = number; // Compilation error - cannot assign int to String
```

### The Java Ecosystem

#### Java Virtual Machine (JVM)
The JVM is the runtime environment that executes Java bytecode. It provides platform independence, memory management, and security features.

#### Java Development Kit (JDK)
The JDK includes the Java Runtime Environment (JRE), compiler (javac), debugger, and other development tools.

#### Java Runtime Environment (JRE)
The JRE contains the JVM and standard libraries needed to run Java applications.

### Java Versions and Evolution

Java has evolved significantly since its inception:

- **Java 8 (2014)**: Lambda expressions, Stream API, Date/Time API
- **Java 11 (2018)**: HTTP Client, Local Variable Type Inference improvements
- **Java 17 (2021)**: Sealed classes, Pattern matching for instanceof
- **Java 21 (2023)**: Virtual threads, Pattern matching for switch, Record patterns

> 💡 **Tip:** Java follows a 6-month release cycle with Long Term Support (LTS) versions every 3 years. Java 8, 11, 17, and 21 are LTS versions.

### Real-World Applications

#### Enterprise Applications
Java dominates enterprise software development with frameworks like Spring, providing robust, scalable solutions for large organizations.

#### Web Development
Java powers millions of web applications through technologies like Spring Boot, JSF, and various microservices frameworks.

#### Mobile Development
Android applications are primarily written in Java (and Kotlin), making Java one of the most widely used mobile development languages.

#### Big Data Processing
Java is extensively used in big data technologies like Apache Hadoop, Apache Spark, and Apache Kafka.

#### Financial Services
Many banking and financial institutions rely on Java for mission-critical applications due to its stability and security features.

### ⚠️ Common Pitfalls
- **Assuming Java is slow**: Modern JVMs are highly optimized with Just-In-Time compilation
- **Ignoring memory management**: While automatic, understanding GC behavior is important for performance
- **Overusing inheritance**: Favor composition over inheritance in many cases

### ✅ Best Practices
- Follow Java naming conventions consistently
- Use meaningful class and method names
- Leverage Java's strong type system for safer code
- Keep classes focused on single responsibilities
- Use standard library classes and methods when available

### 🏋️ Exercise 1: Java Environment Exploration

**Difficulty:** 🟢 Beginner
**Estimated Time:** 10 minutes

Explore your Java installation and understand the basic structure.

<details>
<summary>💡 Click to see hints</summary>

- Use `java -version` to check your Java version
- Use `javac -version` to check your compiler version
- Try compiling and running a simple program

</details>

<details>
<summary>✅ Click to see solution</summary>

```java
// Save as HelloJava.java
public class HelloJava {
    public static void main(String[] args) {
        System.out.println("Java Version: " + System.getProperty("java.version"));
        System.out.println("JVM Vendor: " + System.getProperty("java.vendor"));
        System.out.println("Operating System: " + System.getProperty("os.name"));
        System.out.println("User Directory: " + System.getProperty("user.dir"));
    }
}
```

**Compilation and execution:**
```bash
javac HelloJava.java
java HelloJava
```

**Explanation:**
- `System.getProperty()` accesses system properties
- The program displays environment information
- This demonstrates basic Java compilation and execution

</details>

[↑ Back to Top](#-table-of-contents)

---

## 2. Installation & Environment Setup

📊 **Chapter 2 of 35**

🎯 **Learning Objectives:**
- Install Java Development Kit (JDK) 21
- Set up development environment variables
- Choose and configure an Integrated Development Environment (IDE)
- Understand project structure and build tools

⏱️ **Estimated Reading Time:** 25 minutes
📋 **Prerequisites:** Basic computer administration knowledge

### Installing JDK 21

#### Windows Installation

1. **Download JDK 21**
   - Visit [Oracle JDK](https://www.oracle.com/java/technologies/javase/jdk21-archive-downloads.html) or [OpenJDK](https://openjdk.org/projects/jdk/21/)
   - Download the Windows installer (.msi file)

2. **Run the Installer**
   - Execute the downloaded .msi file
   - Follow the installation wizard
   - Default installation path: `C:\Program Files\Java\jdk-21`

3. **Set Environment Variables**
```bash
# Set JAVA_HOME (System Environment Variables)
JAVA_HOME=C:\Program Files\Java\jdk-21

# Add to PATH
PATH=%JAVA_HOME%\bin;%PATH%
```

4. **Verify Installation**
```bash
java -version
javac -version
```

#### macOS Installation

1. **Using Homebrew (Recommended)**
```bash
# Install Homebrew if not already installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install OpenJDK 21
brew install openjdk@21

# Link the installation
sudo ln -sfn $(brew --prefix)/opt/openjdk@21/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-21.jdk
```

2. **Manual Installation**
   - Download the macOS installer from Oracle or OpenJDK
   - Run the installer package
   - Installation path: `/Library/Java/JavaVirtualMachines/jdk-21.jdk`

3. **Set Environment Variables**
```bash
# Add to ~/.zshrc or ~/.bash_profile
export JAVA_HOME="/Library/Java/JavaVirtualMachines/jdk-21.jdk/Contents/Home"
export PATH="$JAVA_HOME/bin:$PATH"
```

#### Linux Installation (Ubuntu/Debian)

1. **Using Package Manager**
```bash
# Update package list
sudo apt update

# Install OpenJDK 21
sudo apt install openjdk-21-jdk

# Verify installation
java -version
javac -version
```

2. **Set Environment Variables**
```bash
# Add to ~/.bashrc or ~/.profile
export JAVA_HOME="/usr/lib/jvm/java-21-openjdk-amd64"
export PATH="$JAVA_HOME/bin:$PATH"
```

3. **Alternative: SDKMAN Installation**
```bash
# Install SDKMAN
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"

# Install Java 21
sdk install java 21-open
sdk use java 21-open
```

### Development Environment Setup

#### Command Line Tools

**Essential Commands:**
```bash
# Compile Java source files
javac MyClass.java

# Run Java programs
java MyClass

# Create JAR files
jar cf myapp.jar *.class

# View JAR contents
jar tf myapp.jar

# Java documentation tool
javadoc *.java
```

**Useful JDK Tools:**
```bash
# Java debugger
jdb MyClass

# Java profiler
jconsole

# Heap dump analyzer
jhat heapdump.hprof

# Java process status
jps

# Java stack trace
jstack <pid>
```

#### IDE Configuration

#### IntelliJ IDEA Setup

1. **Download and Install**
   - Download from [JetBrains](https://www.jetbrains.com/idea/)
   - Choose Community Edition (free) or Ultimate Edition

2. **Configure JDK**
```java
// File → Project Structure → Project Settings → Project
// Set Project SDK to JDK 21
// Set Project language level to "21 - Pattern matching for switch"
```

3. **Create New Project**
```java
// File → New → Project
// Choose "New Project" → Java
// Select JDK 21
// Choose project template or start empty
```

#### Eclipse Setup

1. **Download Eclipse IDE for Java Developers**
2. **Configure JDK**
   - Window → Preferences → Java → Installed JREs
   - Add JDK 21 installation path
   - Set as default

#### Visual Studio Code Setup

1. **Install Java Extension Pack**
```bash
# Extensions to install:
# - Extension Pack for Java
# - Language Support for Java by Red Hat
# - Debugger for Java
# - Test Runner for Java
```

2. **Configure settings.json**
```json
{
    "java.configuration.runtimes": [
        {
            "name": "JavaSE-21",
            "path": "/path/to/jdk-21"
        }
    ],
    "java.compile.nullAnalysis.mode": "automatic"
}
```

### Build Tools

#### Maven Setup

1. **Install Maven**
```bash
# Windows (using Chocolatey)
choco install maven

# macOS (using Homebrew)
brew install maven

# Linux (Ubuntu/Debian)
sudo apt install maven
```

2. **Basic pom.xml Configuration**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>my-java-app</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>jar</packaging>

    <properties>
        <maven.compiler.source>21</maven.compiler.source>
        <maven.compiler.target>21</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter</artifactId>
            <version>5.10.0</version>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.11.0</version>
                <configuration>
                    <source>21</source>
                    <target>21</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
```

#### Gradle Setup

1. **Install Gradle**
```bash
# Windows (using Chocolatey)
choco install gradle

# macOS (using Homebrew)
brew install gradle

# Linux or using SDKMAN
sdk install gradle
```

2. **Basic build.gradle Configuration**
```gradle
plugins {
    id 'java'
    id 'application'
}

java {
    toolchain {
        languageVersion = JavaLanguageVersion.of(21)
    }
}

repositories {
    mavenCentral()
}

dependencies {
    testImplementation 'org.junit.jupiter:junit-jupiter:5.10.0'
    testRuntimeOnly 'org.junit.platform:junit-platform-launcher'
}

application {
    mainClass = 'com.example.Main'
}

test {
    useJUnitPlatform()
}
```

### Project Structure

#### Standard Maven/Gradle Structure
```
my-java-project/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── example/
│   │   │           └── Main.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       ├── java/
│       │   └── com/
│       │       └── example/
│       │           └── MainTest.java
│       └── resources/
├── target/ (Maven) or build/ (Gradle)
├── pom.xml (Maven) or build.gradle (Gradle)
└── README.md
```

#### Package Naming Conventions
```java
// Reverse domain naming convention
package com.company.project.module;

// Examples:
package com.google.gson;
package org.apache.commons.lang3;
package com.example.myapp.service;
```

### Environment Verification

#### Create a Test Project
```java
// src/main/java/com/example/HelloSetup.java
package com.example;

import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class HelloSetup {
    public static void main(String[] args) {
        System.out.println("Java Setup Verification");
        System.out.println("========================");
        System.out.println("Java Version: " + System.getProperty("java.version"));
        System.out.println("Java Vendor: " + System.getProperty("java.vendor"));
        System.out.println("JVM Version: " + System.getProperty("java.vm.version"));
        System.out.println("Operating System: " + System.getProperty("os.name"));
        System.out.println("Current Time: " +
            LocalDateTime.now().format(DateTimeFormatter.ISO_LOCAL_DATE_TIME));

        // Test Java 21 features
        testJava21Features();
    }

    private static void testJava21Features() {
        System.out.println("\nTesting Java 21 Features:");

        // Pattern matching for switch (Java 21)
        String result = switch ("test") {
            case String s when s.length() > 3 -> "Long string: " + s;
            case String s -> "Short string: " + s;
        };
        System.out.println("Pattern matching result: " + result);

        // Record pattern matching
        record Point(int x, int y) {}
        Point point = new Point(10, 20);

        String description = switch (point) {
            case Point(var x, var y) when x == y -> "Point on diagonal: (" + x + "," + y + ")";
            case Point(var x, var y) -> "Point at (" + x + "," + y + ")";
        };
        System.out.println("Record pattern result: " + description);
    }
}
```

### ⚠️ Common Pitfalls
- **Wrong JDK version**: Ensure you're using JDK 21, not just JRE
- **PATH issues**: Make sure JAVA_HOME and PATH are correctly set
- **IDE configuration**: Verify IDE is using the correct JDK version
- **Build tool version**: Ensure Maven/Gradle supports Java 21

### ✅ Best Practices
- Use a consistent project structure across all projects
- Keep JDK installations organized and documented
- Use build tools (Maven/Gradle) instead of manual compilation for real projects
- Set up proper IDE formatting and code style rules
- Use version control (Git) from the beginning of every project

### 🏋️ Exercise 2: Complete Development Environment Setup

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 30 minutes

Set up a complete Java development environment with build tools and create a working project.

<details>
<summary>💡 Click to see hints</summary>

- Install JDK 21, Maven or Gradle, and an IDE
- Create a new project using the standard directory structure
- Include at least one dependency in your build file
- Create a simple program that uses Java 21 features

</details>

<details>
<summary>✅ Click to see solution</summary>

**1. Create Maven project structure:**
```bash
mkdir my-java-project
cd my-java-project
mkdir -p src/main/java/com/example
mkdir -p src/test/java/com/example
mkdir -p src/main/resources
```

**2. Create pom.xml:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>java21-demo</artifactId>
    <version>1.0.0</version>

    <properties>
        <maven.compiler.source>21</maven.compiler.source>
        <maven.compiler.target>21</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    </properties>

    <dependencies>
        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
            <version>2.15.2</version>
        </dependency>
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter</artifactId>
            <version>5.10.0</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```

**3. Create main class (src/main/java/com/example/App.java):**
```java
package com.example;

import com.fasterxml.jackson.databind.ObjectMapper;
import java.util.List;

public class App {
    public static void main(String[] args) throws Exception {
        System.out.println("Java 21 Development Environment Test");

        // Test dependency
        ObjectMapper mapper = new ObjectMapper();

        // Test Java 21 features
        var data = List.of("apple", "banana", "cherry", "date");

        String result = switch (data.size()) {
            case 0 -> "No items";
            case 1 -> "One item: " + data.getFirst();
            case int n when n > 10 -> "Many items: " + n;
            case int n -> "Several items: " + n;
        };

        System.out.println(result);
        System.out.println("JSON: " + mapper.writeValueAsString(data));
    }
}
```

**4. Build and run:**
```bash
mvn compile exec:java -Dexec.mainClass="com.example.App"
```

**Explanation:**
- Created a standard Maven project structure
- Configured for Java 21 with proper compiler settings
- Added external dependency (Jackson) to demonstrate dependency management
- Used Java 21 pattern matching features to verify language version
- Demonstrated complete build and execution workflow

</details>

[↑ Back to Top](#-table-of-contents)

---

## 3. Your First Java Program

📊 **Chapter 3 of 35**

🎯 **Learning Objectives:**
- Understand Java program structure and anatomy
- Learn about main method and program entry point
- Master basic input/output operations
- Understand compilation and execution process

⏱️ **Estimated Reading Time:** 20 minutes
📋 **Prerequisites:** JDK installation and basic text editor

### Anatomy of a Java Program

Every Java program follows a specific structure. Let's examine a complete program and understand each component:

```java
// File: HelloWorld.java
package com.example.firstprogram;           // Package declaration (optional)

import java.time.LocalDateTime;             // Import statements
import java.time.format.DateTimeFormatter;
import java.util.Scanner;

/**
 * This is a JavaDoc comment describing the class.
 * It demonstrates the basic structure of a Java program.
 *
 * @author Your Name
 * @version 1.0
 * @since Java 21
 */
public class HelloWorld {                   // Class declaration

    // Class-level constants
    private static final String GREETING = "Welcome to Java!";

    /**
     * The main method - entry point of the program
     * @param args command line arguments
     */
    public static void main(String[] args) { // Main method
        // Method body - program logic
        System.out.println(GREETING);

        // Display current date and time
        LocalDateTime now = LocalDateTime.now();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
        System.out.println("Current time: " + now.format(formatter));

        // Interactive user input
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String name = scanner.nextLine();
        System.out.println("Hello, " + name + "!");

        scanner.close();
    }
}
```

#### Key Components Explained

**1. Package Declaration**
```java
package com.example.firstprogram;
```
- Optional but recommended for organizing code
- Must be the first non-comment line if present
- Follows reverse domain naming convention
- Creates a namespace to avoid class name conflicts

**2. Import Statements**
```java
import java.time.LocalDateTime;
import java.util.Scanner;
import java.util.*;  // Wildcard import (use sparingly)
```
- Brings classes from other packages into scope
- Allows using class names without fully qualified names
- Static imports for static methods and constants

**3. Class Declaration**
```java
public class HelloWorld {
    // Class body
}
```
- Every Java program must have at least one class
- Class name must match filename (HelloWorld.java)
- Public classes can be accessed from other packages

**4. Main Method**
```java
public static void main(String[] args) {
    // Program execution starts here
}
```
- Entry point for Java applications
- Must be exactly as shown (signature matters)
- `public`: Accessible from anywhere
- `static`: Can be called without creating class instance
- `void`: Returns no value
- `String[] args`: Command line arguments

### Input and Output Operations

#### Standard Output

```java
public class OutputExamples {
    public static void main(String[] args) {
        // Basic output
        System.out.println("This prints with a newline");
        System.out.print("This prints without newline ");
        System.out.print("on the same line\n");

        // Formatted output (printf-style)
        String name = "Alice";
        int age = 25;
        double salary = 50000.50;

        System.out.printf("Name: %s, Age: %d, Salary: $%.2f%n", name, age, salary);

        // Using String.format()
        String formatted = String.format("Welcome %s! You are %d years old.", name, age);
        System.out.println(formatted);

        // Modern text blocks (Java 13+)
        String multiLine = """
                This is a
                multi-line string
                with preserved formatting
                """;
        System.out.println(multiLine);
    }
}
```

#### Standard Input

```java
import java.util.Scanner;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.IOException;

public class InputExamples {
    public static void main(String[] args) throws IOException {
        // Method 1: Scanner (most common)
        demonstrateScanner();

        // Method 2: BufferedReader (more efficient for large input)
        demonstrateBufferedReader();
    }

    private static void demonstrateScanner() {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        System.out.print("Enter your age: ");
        int age = scanner.nextInt();
        scanner.nextLine(); // Consume the remaining newline

        System.out.print("Enter your GPA: ");
        double gpa = scanner.nextDouble();

        System.out.print("Are you a student? (true/false): ");
        boolean isStudent = scanner.nextBoolean();

        System.out.printf("Name: %s, Age: %d, GPA: %.2f, Student: %b%n",
                         name, age, gpa, isStudent);

        scanner.close();
    }

    private static void demonstrateBufferedReader() throws IOException {
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));

        System.out.print("Enter a message: ");
        String message = reader.readLine();

        System.out.println("You entered: " + message);

        reader.close();
    }
}
```

### Command Line Arguments

Java programs can receive arguments from the command line:

```java
public class CommandLineDemo {
    public static void main(String[] args) {
        System.out.println("Number of arguments: " + args.length);

        if (args.length == 0) {
            System.out.println("No arguments provided.");
            System.out.println("Usage: java CommandLineDemo <name> <age> <city>");
            return;
        }

        // Access individual arguments
        for (int i = 0; i < args.length; i++) {
            System.out.println("Argument " + i + ": " + args[i]);
        }

        // Enhanced for loop
        System.out.println("\nAll arguments:");
        for (String arg : args) {
            System.out.println("  - " + arg);
        }

        // Process arguments with error handling
        if (args.length >= 3) {
            String name = args[0];
            try {
                int age = Integer.parseInt(args[1]);
                String city = args[2];

                System.out.printf("Hello %s, age %d from %s!%n", name, age, city);
            } catch (NumberFormatException e) {
                System.err.println("Error: Age must be a number");
            }
        }
    }
}
```

**Running with command line arguments:**
```bash
javac CommandLineDemo.java
java CommandLineDemo Alice 25 "New York"
```

### Compilation and Execution Process

#### Manual Compilation and Execution

```bash
# Compile Java source file
javac HelloWorld.java

# This creates HelloWorld.class (bytecode)
# Run the compiled program
java HelloWorld

# Compile with specific classpath
javac -cp "lib/*:." HelloWorld.java

# Run with classpath
java -cp "lib/*:." HelloWorld
```

#### Understanding Bytecode

```java
// SimpleExample.java
public class SimpleExample {
    public static void main(String[] args) {
        String message = "Hello, Bytecode!";
        System.out.println(message);
    }
}
```

When compiled, Java source code becomes platform-independent bytecode:

```bash
# View bytecode with javap
javap -c SimpleExample

# Output shows bytecode instructions:
# 0: ldc           #2  // String Hello, Bytecode!
# 2: astore_1
# 3: getstatic     #3  // Field java/lang/System.out
# 6: aload_1
# 7: invokevirtual #4  // Method java/io/PrintStream.println
```

#### Build Tools Integration

**Maven Commands:**
```bash
# Compile project
mvn compile

# Run main class
mvn exec:java -Dexec.mainClass="com.example.HelloWorld"

# Package as JAR
mvn package

# Clean and rebuild
mvn clean compile
```

**Gradle Commands:**
```bash
# Compile project
gradle build

# Run application
gradle run

# Create distribution
gradle distZip
```

### Modern Java Features in First Programs

#### Text Blocks (Java 13+)

```java
public class TextBlockExample {
    public static void main(String[] args) {
        // Traditional string concatenation
        String oldWay = "{\n" +
                       "  \"name\": \"John\",\n" +
                       "  \"age\": 30\n" +
                       "}";

        // Modern text blocks
        String newWay = """
                {
                  "name": "John",
                  "age": 30
                }
                """;

        System.out.println("Old way:");
        System.out.println(oldWay);
        System.out.println("\nNew way:");
        System.out.println(newWay);
    }
}
```

#### Switch Expressions (Java 14+)

```java
public class SwitchExpressionExample {
    public static void main(String[] args) {
        String day = "MONDAY";

        // Traditional switch statement
        String traditionalResult;
        switch (day) {
            case "MONDAY":
            case "TUESDAY":
            case "WEDNESDAY":
            case "THURSDAY":
            case "FRIDAY":
                traditionalResult = "Weekday";
                break;
            case "SATURDAY":
            case "SUNDAY":
                traditionalResult = "Weekend";
                break;
            default:
                traditionalResult = "Unknown";
        }

        // Modern switch expression
        String modernResult = switch (day) {
            case "MONDAY", "TUESDAY", "WEDNESDAY", "THURSDAY", "FRIDAY" -> "Weekday";
            case "SATURDAY", "SUNDAY" -> "Weekend";
            default -> "Unknown";
        };

        System.out.println("Traditional: " + traditionalResult);
        System.out.println("Modern: " + modernResult);
    }
}
```

#### Records (Java 14+)

```java
// Define a record (immutable data carrier)
public record Person(String name, int age, String email) {
    // Compact constructor with validation
    public Person {
        if (age < 0) {
            throw new IllegalArgumentException("Age cannot be negative");
        }
        if (name == null || name.isBlank()) {
            throw new IllegalArgumentException("Name cannot be null or blank");
        }
    }

    // Additional methods can be added
    public boolean isAdult() {
        return age >= 18;
    }
}

public class RecordExample {
    public static void main(String[] args) {
        // Create record instances
        Person person1 = new Person("Alice", 25, "alice@example.com");
        Person person2 = new Person("Bob", 17, "bob@example.com");

        // Automatic getters, equals(), hashCode(), toString()
        System.out.println("Person 1: " + person1);
        System.out.println("Name: " + person1.name());
        System.out.println("Age: " + person1.age());
        System.out.println("Is Adult: " + person1.isAdult());

        System.out.println("\nPerson 2: " + person2);
        System.out.println("Is Adult: " + person2.isAdult());

        // Records provide equals() implementation
        Person person1Copy = new Person("Alice", 25, "alice@example.com");
        System.out.println("person1.equals(person1Copy): " + person1.equals(person1Copy));
    }
}
```

### Error Handling in First Programs

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class ErrorHandlingExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Enter your age: ");
            int age = scanner.nextInt();

            if (age < 0) {
                throw new IllegalArgumentException("Age cannot be negative");
            }

            System.out.println("You are " + age + " years old.");

            // Demonstrate division
            System.out.print("Enter a number to divide 100 by: ");
            int divisor = scanner.nextInt();

            double result = 100.0 / divisor;
            System.out.printf("100 / %d = %.2f%n", divisor, result);

        } catch (InputMismatchException e) {
            System.err.println("Error: Please enter a valid number");
        } catch (ArithmeticException e) {
            System.err.println("Error: Cannot divide by zero");
        } catch (IllegalArgumentException e) {
            System.err.println("Error: " + e.getMessage());
        } catch (Exception e) {
            System.err.println("Unexpected error: " + e.getMessage());
        } finally {
            scanner.close();
            System.out.println("Program completed.");
        }
    }
}
```

### ⚠️ Common Pitfalls
- **Class name mismatch**: Class name must exactly match filename
- **Missing main method**: Ensure correct main method signature
- **Scanner resource leaks**: Always close Scanner instances
- **Forgetting package structure**: File must be in correct directory for package
- **Case sensitivity**: Java is case-sensitive (`String` vs `string`)

### ✅ Best Practices
- Use meaningful class and variable names
- Follow Java naming conventions (camelCase for variables/methods, PascalCase for classes)
- Always handle user input validation
- Use try-with-resources for automatic resource management
- Include proper documentation comments
- Keep main method simple and delegate complex logic to other methods

### 🏋️ Exercise 3: Interactive Calculator
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 25 minutes

Create an interactive calculator that performs basic arithmetic operations and handles various error conditions.

<details>
<summary>💡 Click to see hints</summary>

- Use Scanner for user input
- Implement switch expression for operations
- Handle division by zero and invalid input
- Use proper error messages and validation
- Allow multiple calculations in a loop

</details>

<details>
<summary>✅ Click to see solution</summary>

```java
import java.util.InputMismatchException;
import java.util.Scanner;

/**
 * Interactive Calculator - Demonstrates basic Java concepts
 * Features: Basic arithmetic, error handling, user interaction
 */
public class InteractiveCalculator {

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        System.out.println("=== Interactive Calculator ===");
        System.out.println("Supports: +, -, *, /, % operations");
        System.out.println("Type 'quit' to exit\n");

        boolean continueCalculating = true;

        while (continueCalculating) {
            try {
                double result = performCalculation();
                System.out.printf("Result: %.2f%n%n", result);

                continueCalculating = askToContinue();

            } catch (QuitException e) {
                continueCalculating = false;
            } catch (Exception e) {
                System.err.println("Error: " + e.getMessage());
                System.out.println("Please try again.\n");
            }
        }

        scanner.close();
        System.out.println("Thank you for using the calculator!");
    }

    private static double performCalculation() throws Exception {
        double num1 = getNumber("Enter first number (or 'quit' to exit): ");
        char operator = getOperator("Enter operation (+, -, *, /, %): ");
        double num2 = getNumber("Enter second number: ");

        return calculate(num1, operator, num2);
    }

    private static double getNumber(String prompt) throws QuitException {
        while (true) {
            System.out.print(prompt);
            String input = scanner.nextLine().trim();

            if (input.equalsIgnoreCase("quit")) {
                throw new QuitException();
            }

            try {
                return Double.parseDouble(input);
            } catch (NumberFormatException e) {
                System.err.println("Invalid number format. Please try again.");
            }
        }
    }

    private static char getOperator(String prompt) throws QuitException {
        while (true) {
            System.out.print(prompt);
            String input = scanner.nextLine().trim();

            if (input.equalsIgnoreCase("quit")) {
                throw new QuitException();
            }

            if (input.length() == 1) {
                char op = input.charAt(0);
                if ("+-*/%".indexOf(op) != -1) {
                    return op;
                }
            }

            System.err.println("Invalid operator. Use +, -, *, /, or %");
        }
    }

    private static double calculate(double num1, char operator, double num2) throws Exception {
        return switch (operator) {
            case '+' -> num1 + num2;
            case '-' -> num1 - num2;
            case '*' -> num1 * num2;
            case '/' -> {
                if (num2 == 0) {
                    throw new ArithmeticException("Cannot divide by zero");
                }
                yield num1 / num2;
            }
            case '%' -> {
                if (num2 == 0) {
                    throw new ArithmeticException("Cannot calculate modulo by zero");
                }
                yield num1 % num2;
            }
            default -> throw new IllegalArgumentException("Unsupported operator: " + operator);
        };
    }

    private static boolean askToContinue() throws QuitException {
        while (true) {
            System.out.print("Continue calculating? (y/n/quit): ");
            String input = scanner.nextLine().trim().toLowerCase();

            return switch (input) {
                case "y", "yes" -> true;
                case "n", "no" -> false;
                case "quit" -> throw new QuitException();
                default -> {
                    System.err.println("Please enter 'y', 'n', or 'quit'");
                    yield askToContinue(); // Recursive call for invalid input
                }
            };
        }
    }

    // Custom exception for quit functionality
    private static class QuitException extends Exception {
        public QuitException() {
            super("User requested to quit");
        }
    }
}
```

**Explanation:**
- **Structure**: Well-organized with separate methods for different responsibilities
- **Error Handling**: Comprehensive exception handling for various error conditions
- **User Experience**: Clear prompts and error messages
- **Java 21 Features**: Uses switch expressions and modern syntax
- **Resource Management**: Proper Scanner cleanup
- **Custom Exception**: Demonstrates creating and using custom exceptions
- **Input Validation**: Robust validation for numbers and operators
- **Loop Control**: Clean exit mechanism with multiple ways to quit

**Sample Interaction:**
```
=== Interactive Calculator ===
Supports: +, -, *, /, % operations
Type 'quit' to exit

Enter first number (or 'quit' to exit): 10
Enter operation (+, -, *, /, %): *
Enter second number: 5
Result: 50.00

Continue calculating? (y/n/quit): y
Enter first number (or 'quit' to exit): 15
Enter operation (+, -, *, /, %): /
Enter second number: 0
Error: Cannot divide by zero
Please try again.
```

</details>

### 🏋️ Exercise 4: File-based Configuration Reader
**Difficulty:** 🔴 Advanced
**Estimated Time:** 35 minutes

Create a program that reads configuration from a properties file and displays system information.

<details>
<summary>💡 Click to see hints</summary>

- Create a properties file with application settings
- Use Properties class to read the file
- Handle file not found exceptions
- Display both file-based and system properties
- Use modern Java features like text blocks for output formatting

</details>

<details>
<summary>✅ Click to see solution</summary>

**Create config.properties file:**
```properties
# Application Configuration
app.name=Java Configuration Demo
app.version=1.0.0
app.author=Java Developer

# Display Settings
display.welcome.message=Welcome to the Java Configuration System!
display.format.json=true
display.system.info=true

# Numeric Settings
max.connections=100
timeout.seconds=30
```

**Main Program (ConfigReader.java):**
```java
import java.io.*;
import java.nio.file.*;
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.util.*;

/**
 * Configuration Reader - Advanced Java concepts demonstration
 * Features: File I/O, Properties, Exception handling, Modern Java syntax
 */
public class ConfigReader {

    private static final String CONFIG_FILE = "config.properties";
    private final Properties config;
    private final Map<String, String> systemInfo;

    public ConfigReader() {
        this.config = new Properties();
        this.systemInfo = new LinkedHashMap<>();
        loadConfiguration();
        loadSystemInfo();
    }

    public static void main(String[] args) {
        try {
            ConfigReader reader = new ConfigReader();
            reader.displayConfiguration();
        } catch (Exception e) {
            System.err.println("Application failed to start: " + e.getMessage());
            e.printStackTrace();
        }
    }

    private void loadConfiguration() {
        // Try multiple locations for config file
        String[] possiblePaths = {
            CONFIG_FILE,
            "src/main/resources/" + CONFIG_FILE,
            System.getProperty("user.home") + "/" + CONFIG_FILE
        };

        boolean configLoaded = false;

        for (String path : possiblePaths) {
            try (InputStream input = Files.newInputStream(Paths.get(path))) {
                config.load(input);
                System.out.println("✅ Configuration loaded from: " + path);
                configLoaded = true;
                break;
            } catch (IOException e) {
                // Try next location
                continue;
            }
        }

        if (!configLoaded) {
            System.out.println("⚠️ No configuration file found, using defaults");
            loadDefaultConfiguration();
        }
    }

    private void loadDefaultConfiguration() {
        config.setProperty("app.name", "Java Configuration Demo (Default)");
        config.setProperty("app.version", "1.0.0-default");
        config.setProperty("app.author", "Unknown");
        config.setProperty("display.welcome.message", "Welcome to Java!");
        config.setProperty("display.format.json", "false");
        config.setProperty("display.system.info", "true");
        config.setProperty("max.connections", "50");
        config.setProperty("timeout.seconds", "15");
    }

    private void loadSystemInfo() {
        systemInfo.put("Java Version", System.getProperty("java.version"));
        systemInfo.put("Java Vendor", System.getProperty("java.vendor"));
        systemInfo.put("JVM Name", System.getProperty("java.vm.name"));
        systemInfo.put("Operating System", System.getProperty("os.name"));
        systemInfo.put("OS Version", System.getProperty("os.version"));
        systemInfo.put("Architecture", System.getProperty("os.arch"));
        systemInfo.put("User Name", System.getProperty("user.name"));
        systemInfo.put("User Home", System.getProperty("user.home"));
        systemInfo.put("Working Directory", System.getProperty("user.dir"));
        systemInfo.put("Available Processors", String.valueOf(Runtime.getRuntime().availableProcessors()));
        systemInfo.put("Total Memory", formatBytes(Runtime.getRuntime().totalMemory()));
        systemInfo.put("Free Memory", formatBytes(Runtime.getRuntime().freeMemory()));
        systemInfo.put("Current Time", LocalDateTime.now().format(DateTimeFormatter.ISO_LOCAL_DATE_TIME));
    }

    private void displayConfiguration() {
        // Display welcome message
        String welcomeMessage = config.getProperty("display.welcome.message");
        System.out.println("\n" + "=".repeat(50));
        System.out.println(welcomeMessage);
        System.out.println("=".repeat(50));

        // Display application info
        displayApplicationInfo();

        // Display configuration based on format preference
        boolean useJsonFormat = Boolean.parseBoolean(config.getProperty("display.format.json", "false"));

        if (useJsonFormat) {
            displayConfigurationAsJson();
        } else {
            displayConfigurationAsTable();
        }

        // Display system information if enabled
        boolean showSystemInfo = Boolean.parseBoolean(config.getProperty("display.system.info", "true"));
        if (showSystemInfo) {
            displaySystemInformation();
        }

        displayRuntimeSettings();
    }

    private void displayApplicationInfo() {
        String appInfo = """

                📱 Application Information:
                   Name: %s
                   Version: %s
                   Author: %s
                """.formatted(
                config.getProperty("app.name"),
                config.getProperty("app.version"),
                config.getProperty("app.author")
        );

        System.out.println(appInfo);
    }

    private void displayConfigurationAsJson() {
        System.out.println("\n🔧 Configuration (JSON Format):");
        System.out.println("{");

        List<String> keys = config.stringPropertyNames().stream().sorted().toList();
        for (int i = 0; i < keys.size(); i++) {
            String key = keys.get(i);
            String value = config.getProperty(key);
            boolean isLastItem = (i == keys.size() - 1);

            System.out.printf("  \"%s\": \"%s\"%s%n",
                            key, value, isLastItem ? "" : ",");
        }

        System.out.println("}");
    }

    private void displayConfigurationAsTable() {
        System.out.println("\n🔧 Configuration Settings:");
        System.out.println("-".repeat(60));
        System.out.printf("%-30s | %-25s%n", "Property", "Value");
        System.out.println("-".repeat(60));

        config.stringPropertyNames().stream()
              .sorted()
              .forEach(key -> {
                  String value = config.getProperty(key);
                  System.out.printf("%-30s | %-25s%n", key, value);
              });

        System.out.println("-".repeat(60));
    }

    private void displaySystemInformation() {
        System.out.println("\n💻 System Information:");
        System.out.println("-".repeat(60));
        System.out.printf("%-25s | %-30s%n", "Property", "Value");
        System.out.println("-".repeat(60));

        systemInfo.forEach((key, value) -> {
            System.out.printf("%-25s | %-30s%n", key, value);
        });

        System.out.println("-".repeat(60));
    }

    private void displayRuntimeSettings() {
        System.out.println("\n⚙️ Runtime Settings:");

        try {
            int maxConnections = Integer.parseInt(config.getProperty("max.connections", "0"));
            int timeoutSeconds = Integer.parseInt(config.getProperty("timeout.seconds", "0"));

            String runtimeInfo = """
                    Max Connections: %d
                    Timeout: %d seconds
                    Connection Pool Status: %s
                    """.formatted(
                    maxConnections,
                    timeoutSeconds,
                    maxConnections > 0 ? "Ready" : "Disabled"
            );

            System.out.println(runtimeInfo);

        } catch (NumberFormatException e) {
            System.err.println("⚠️ Invalid numeric configuration values");
        }
    }

    private String formatBytes(long bytes) {
        String[] units = {"B", "KB", "MB", "GB"};
        int unitIndex = 0;
        double size = bytes;

        while (size >= 1024 && unitIndex < units.length - 1) {
            size /= 1024;
            unitIndex++;
        }

        return String.format("%.2f %s", size, units[unitIndex]);
    }
}
```

**To create and run:**
1. Create the `config.properties` file in your project directory
2. Compile: `javac ConfigReader.java`
3. Run: `java ConfigReader`

**Explanation:**
- **File I/O**: Demonstrates reading properties files with error handling
- **Multiple Resource Locations**: Tries different paths for configuration files
- **Default Configuration**: Falls back to defaults if no file is found
- **Modern Java Features**: Uses text blocks, formatted strings, streams, and records
- **Type Safety**: Proper parsing of different data types from properties
- **Resource Management**: Proper use of try-with-resources
- **Error Handling**: Comprehensive exception handling for file operations
- **Flexible Output**: Supports both JSON and table format display
- **System Integration**: Reads and displays system properties and runtime information

</details>

[↑ Back to Top](#-table-of-contents)

---

## 4. Java Syntax & Structure

📊 **Chapter 4 of 35**

🎯 **Learning Objectives:**
- Master Java naming conventions and code organization
- Understand lexical elements: keywords, identifiers, literals
- Learn about Java's case sensitivity and reserved words
- Practice proper code formatting and documentation

⏱️ **Estimated Reading Time:** 18 minutes
📋 **Prerequisites:** Basic understanding of programming concepts

### Naming Conventions

Java follows strict naming conventions that improve code readability and maintainability:

#### Classes and Interfaces
```java
// Classes: PascalCase (first letter uppercase)
public class StudentRecord { }
public class DatabaseConnection { }
public class HTTPResponseHandler { }

// Interfaces: PascalCase, often descriptive adjectives
public interface Serializable { }
public interface Comparable<T> { }
public interface EventListener { }
```

#### Methods and Variables
```java
public class NamingExamples {
    // Variables: camelCase (first letter lowercase)
    private String firstName;
    private int studentAge;
    private boolean isActive;
    private List<String> phoneNumbers;

    // Methods: camelCase, usually verbs
    public String getFirstName() { return firstName; }
    public void setStudentAge(int age) { this.studentAge = age; }
    public boolean isUserActive() { return isActive; }
    public void calculateTotalAmount() { /* implementation */ }
}
```

#### Constants and Enums
```java
public class Constants {
    // Constants: UPPER_SNAKE_CASE
    public static final int MAX_RETRY_COUNT = 3;
    public static final String DEFAULT_DATABASE_URL = "jdbc:mysql://localhost:3306/app";
    public static final double PI_VALUE = 3.14159;
}

// Enums: PascalCase for enum name, UPPER_CASE for values
public enum OrderStatus {
    PENDING,
    PROCESSING,
    SHIPPED,
    DELIVERED,
    CANCELLED
}
```

#### Packages
```java
// Packages: lowercase, reverse domain notation
package com.company.project.module;
package org.apache.commons.lang3;
package java.util.concurrent;
```

### Keywords and Reserved Words

Java has 50+ reserved keywords that cannot be used as identifiers:

```java
// Access modifiers
public class AccessModifiers {
    public String publicField;      // Accessible everywhere
    protected String protectedField; // Accessible in package and subclasses
    private String privateField;    // Accessible only in this class
    String packageField;           // Default: accessible in package
}

// Type-related keywords
abstract class AbstractExample { }
final class FinalExample { }
static class StaticNestedClass { }

// Control flow keywords
public void controlFlowExample(int value) {
    if (value > 0) {
        // if-else logic
    } else if (value < 0) {
        // else-if logic
    } else {
        // else logic
    }

    switch (value) {
        case 1:
            break;
        case 2:
            continue;
        default:
            return;
    }

    for (int i = 0; i < 10; i++) {
        // for loop
    }

    while (value > 0) {
        value--;
    }

    do {
        value++;
    } while (value < 5);
}

// Exception handling keywords
public void exceptionExample() {
    try {
        // risky code
    } catch (Exception e) {
        // error handling
    } finally {
        // cleanup code
    }

    throw new IllegalArgumentException("Invalid argument");
}
```

### Identifiers and Naming Rules

#### Valid Identifier Rules
```java
public class IdentifierExamples {
    // Valid identifiers
    String name;           // Simple name
    String _privateVar;    // Starting with underscore (discouraged)
    String $specialVar;    // Starting with dollar sign (discouraged)
    String name2;          // Contains digits
    String camelCaseVar;   // Camel case (preferred)
    String 中文变量;        // Unicode characters (valid but not recommended)

    // Invalid identifiers (compilation errors)
    // String 2name;       // Cannot start with digit
    // String class;       // Cannot use reserved keywords
    // String my-var;      // Hyphens not allowed
    // String my var;      // Spaces not allowed
}
```

### Literals

Java supports various types of literals for different data types:

#### Numeric Literals
```java
public class NumericLiterals {
    public void examples() {
        // Integer literals
        int decimal = 42;              // Decimal
        int hex = 0x2A;               // Hexadecimal (42 in decimal)
        int binary = 0b101010;        // Binary (42 in decimal)
        int octal = 052;              // Octal (42 in decimal)

        // Long literals (suffix with L)
        long bigNumber = 1234567890L;
        long hexLong = 0x1234ABCDL;

        // Floating-point literals
        double pi = 3.14159;          // Double (default)
        float piFloat = 3.14159f;     // Float (suffix with f)
        double scientific = 1.23e-4;  // Scientific notation
        double hexFloat = 0x1.fp3;    // Hexadecimal floating-point

        // Underscore separators (Java 7+)
        int million = 1_000_000;
        long creditCard = 1234_5678_9012_3456L;
        double precise = 3.141_592_653_589_793;
    }
}
```

#### Character and String Literals
```java
public class CharacterStringLiterals {
    public void examples() {
        // Character literals
        char letter = 'A';
        char digit = '9';
        char unicode = '\u0041';      // Unicode 'A'
        char newline = '\n';          // Escape sequence
        char tab = '\t';
        char backslash = '\\';
        char singleQuote = '\'';

        // String literals
        String greeting = "Hello, World!";
        String multiline = "First line\nSecond line";
        String withQuotes = "She said \"Hello!\"";
        String filePath = "C:\\Users\\Name\\Documents";

        // Text blocks (Java 13+)
        String json = """
                {
                    "name": "John Doe",
                    "age": 30,
                    "city": "New York"
                }
                """;

        String sql = """
                SELECT customer_id, customer_name
                FROM customers
                WHERE age > 21
                ORDER BY customer_name;
                """;
    }
}
```

#### Boolean and Null Literals
```java
public class BooleanNullLiterals {
    public void examples() {
        // Boolean literals
        boolean isTrue = true;
        boolean isFalse = false;

        // Null literal
        String nullString = null;
        List<String> nullList = null;

        // Common null checks
        if (nullString == null) {
            System.out.println("String is null");
        }

        // Modern null handling with Optional (Java 8+)
        Optional<String> optional = Optional.ofNullable(nullString);
        optional.ifPresent(System.out::println);
    }
}
```

### Code Organization and Structure

#### File Structure
```java
// 1. Package declaration (if any)
package com.example.project;

// 2. Import statements (organized)
import java.util.List;
import java.util.ArrayList;
import java.util.Collections;
import java.io.*;
import java.time.LocalDateTime;

// 3. Class-level documentation
/**
 * Demonstrates proper Java file structure and organization.
 *
 * @author Developer Name
 * @version 1.0
 * @since Java 21
 */

// 4. Class declaration
public class WellOrganizedClass {

    // 5. Class constants (static final fields)
    public static final String VERSION = "1.0";
    private static final int MAX_ITEMS = 100;

    // 6. Instance fields
    private String name;
    private int id;
    private List<String> items;

    // 7. Constructors
    public WellOrganizedClass() {
        this("Default", 0);
    }

    public WellOrganizedClass(String name, int id) {
        this.name = name;
        this.id = id;
        this.items = new ArrayList<>();
    }

    // 8. Public methods
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    // 9. Private/helper methods
    private void validateInput(String input) {
        if (input == null || input.trim().isEmpty()) {
            throw new IllegalArgumentException("Input cannot be null or empty");
        }
    }

    // 10. Nested classes (if needed)
    public static class Builder {
        private String name;
        private int id;

        public Builder setName(String name) {
            this.name = name;
            return this;
        }

        public Builder setId(int id) {
            this.id = id;
            return this;
        }

        public WellOrganizedClass build() {
            return new WellOrganizedClass(name, id);
        }
    }
}
```

### Comments and Documentation

#### Comment Types
```java
public class CommentExamples {

    // Single-line comment
    // This explains what the next line does
    private String name;

    /*
     * Multi-line comment
     * Can span multiple lines
     * Useful for longer explanations
     */
    private int age;

    /**
     * JavaDoc comment for documentation generation
     * Describes the purpose and behavior of this method
     *
     * @param name the user's name (must not be null)
     * @param age the user's age (must be positive)
     * @return formatted string representation
     * @throws IllegalArgumentException if parameters are invalid
     * @since 1.0
     * @author Developer Name
     */
    public String formatUser(String name, int age) {
        if (name == null || name.trim().isEmpty()) {
            throw new IllegalArgumentException("Name cannot be null or empty");
        }
        if (age < 0) {
            throw new IllegalArgumentException("Age cannot be negative");
        }

        return String.format("User: %s, Age: %d", name, age);
    }
}
```

### Code Formatting Standards

#### Indentation and Spacing
```java
public class FormattingExample {

    // Use 4 spaces for indentation (or tabs consistently)
    public void properFormatting() {
        if (condition) {
            doSomething();
            doAnotherThing();
        } else {
            doAlternative();
        }

        // Space around operators
        int result = a + b * c;
        boolean isValid = (x > 0) && (y < 100);

        // Method calls with proper spacing
        String formatted = String.format("Value: %d", result);

        // Array initialization
        int[] numbers = {1, 2, 3, 4, 5};
        String[] names = {
            "Alice",
            "Bob",
            "Charlie"
        };
    }
}
```

### ⚠️ Common Pitfalls
- **Inconsistent naming**: Mixing camelCase with snake_case
- **Overuse of underscores**: Starting identifiers with _ (discouraged)
- **Poor commenting**: Over-commenting obvious code or under-commenting complex logic
- **Keyword confusion**: Trying to use reserved words as identifiers
- **Case sensitivity**: Forgetting Java is case-sensitive (String vs string)

### ✅ Best Practices
- Follow standard Java naming conventions consistently
- Use meaningful, descriptive names for classes, methods, and variables
- Keep line length under 120 characters for readability
- Use JavaDoc for public APIs and complex methods
- Organize imports and remove unused ones
- Use consistent indentation (4 spaces is standard)

### 🏋️ Exercise 5: Code Organization Challenge
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 20 minutes

Refactor a poorly organized class to follow Java conventions and best practices.

<details>
<summary>💡 Click to see hints</summary>

- Fix naming conventions for classes, methods, and variables
- Reorganize code structure (fields, constructors, methods)
- Add proper comments and documentation
- Follow formatting standards

</details>

<details>
<summary>✅ Click to see solution</summary>

**Before (poorly organized):**
```java
package badexample;
import java.util.*;
public class user_manager{
String user_name;
public int AGE;
private static String DEFAULT_name="Unknown";
public user_manager(String n,int a){user_name=n;AGE=a;}
public void setname(String n){user_name=n;}
public String getname(){return user_name;}
public void print(){System.out.println("Name: "+user_name+" Age: "+AGE);}
}
```

**After (properly organized):**
```java
package com.example.users;

import java.util.Objects;

/**
 * Manages user information including name and age.
 * Provides basic CRUD operations for user data.
 *
 * @author Developer Name
 * @version 1.0
 * @since Java 21
 */
public class UserManager {

    // Class constants
    private static final String DEFAULT_NAME = "Unknown";
    private static final int MIN_AGE = 0;
    private static final int MAX_AGE = 150;

    // Instance fields
    private String userName;
    private int age;

    // Constructors
    /**
     * Creates a new UserManager with default values.
     */
    public UserManager() {
        this(DEFAULT_NAME, 0);
    }

    /**
     * Creates a new UserManager with specified name and age.
     *
     * @param userName the user's name (cannot be null or empty)
     * @param age the user's age (must be between 0 and 150)
     * @throws IllegalArgumentException if parameters are invalid
     */
    public UserManager(String userName, int age) {
        setUserName(userName);
        setAge(age);
    }

    // Public methods
    /**
     * Gets the user's name.
     *
     * @return the user's name
     */
    public String getUserName() {
        return userName;
    }

    /**
     * Sets the user's name.
     *
     * @param userName the user's name (cannot be null or empty)
     * @throws IllegalArgumentException if name is null or empty
     */
    public void setUserName(String userName) {
        if (userName == null || userName.trim().isEmpty()) {
            throw new IllegalArgumentException("User name cannot be null or empty");
        }
        this.userName = userName.trim();
    }

    /**
     * Gets the user's age.
     *
     * @return the user's age
     */
    public int getAge() {
        return age;
    }

    /**
     * Sets the user's age.
     *
     * @param age the user's age (must be between 0 and 150)
     * @throws IllegalArgumentException if age is invalid
     */
    public void setAge(int age) {
        if (age < MIN_AGE || age > MAX_AGE) {
            throw new IllegalArgumentException(
                String.format("Age must be between %d and %d", MIN_AGE, MAX_AGE)
            );
        }
        this.age = age;
    }

    /**
     * Prints the user information to standard output.
     */
    public void printUserInfo() {
        System.out.printf("User: %s, Age: %d%n", userName, age);
    }

    // Object methods
    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;

        UserManager that = (UserManager) obj;
        return age == that.age && Objects.equals(userName, that.userName);
    }

    @Override
    public int hashCode() {
        return Objects.hash(userName, age);
    }

    @Override
    public String toString() {
        return String.format("UserManager{userName='%s', age=%d}", userName, age);
    }
}
```

**Explanation of improvements:**
- **Package naming**: Used proper reverse domain notation
- **Class naming**: Changed from `user_manager` to `UserManager` (PascalCase)
- **Field naming**: Changed from `user_name` and `AGE` to `userName` and `age` (camelCase)
- **Method naming**: Changed from `setname`/`getname` to `setUserName`/`getUserName`
- **Code organization**: Proper order of constants, fields, constructors, methods
- **Documentation**: Added comprehensive JavaDoc comments
- **Validation**: Added proper input validation with meaningful error messages
- **Formatting**: Consistent indentation and spacing
- **Best practices**: Implemented equals(), hashCode(), and toString() methods

</details>

[↑ Back to Top](#-table-of-contents)

---

## 5. Data Types & Variables

📊 **Chapter 5 of 35**

🎯 **Learning Objectives:**
- Master Java's primitive and reference data types
- Understand variable declaration, initialization, and scope
- Learn about type conversion and casting
- Explore wrapper classes and autoboxing/unboxing

⏱️ **Estimated Reading Time:** 25 minutes
📋 **Prerequisites:** Understanding of Java syntax basics

### Primitive Data Types

Java has 8 primitive data types that store values directly in memory:

#### Integral Types
```java
public class IntegralTypes {
    public static void main(String[] args) {
        // byte: 8-bit signed integer (-128 to 127)
        byte smallNumber = 100;
        byte maxByte = 127;
        byte minByte = -128;

        // short: 16-bit signed integer (-32,768 to 32,767)
        short mediumNumber = 1000;
        short maxShort = 32_767;
        short minShort = -32_768;

        // int: 32-bit signed integer (-2^31 to 2^31-1)
        int regularNumber = 42;
        int maxInt = 2_147_483_647;
        int minInt = -2_147_483_648;

        // long: 64-bit signed integer (-2^63 to 2^63-1)
        long bigNumber = 1234567890L;
        long maxLong = 9_223_372_036_854_775_807L;
        long minLong = -9_223_372_036_854_775_808L;

        System.out.println("Byte range: " + minByte + " to " + maxByte);
        System.out.println("Short range: " + minShort + " to " + maxShort);
        System.out.println("Int range: " + minInt + " to " + maxInt);
        System.out.println("Long range: " + minLong + " to " + maxLong);
    }
}
```

#### Floating-Point Types
```java
public class FloatingPointTypes {
    public static void main(String[] args) {
        // float: 32-bit IEEE 754 floating point
        float temperature = 98.6f;
        float pi = 3.14159f;
        float scientific = 1.23e-4f;

        // double: 64-bit IEEE 754 floating point (default for decimals)
        double precision = 3.141592653589793;
        double large = 1.23456789012345;
        double scientificDouble = 1.23e-10;

        // Special floating-point values
        float positiveInfinity = Float.POSITIVE_INFINITY;
        float negativeInfinity = Float.NEGATIVE_INFINITY;
        float notANumber = Float.NaN;

        double doubleInfinity = Double.POSITIVE_INFINITY;
        double doubleNaN = Double.NaN;

        // Precision comparison
        System.out.println("Float precision: " + temperature);
        System.out.println("Double precision: " + precision);

        // Check for special values
        System.out.println("Is NaN: " + Float.isNaN(notANumber));
        System.out.println("Is Infinite: " + Float.isInfinite(positiveInfinity));
    }
}
```

#### Character Type
```java
public class CharacterType {
    public static void main(String[] args) {
        // char: 16-bit Unicode character (0 to 65,535)
        char letter = 'A';
        char digit = '9';
        char symbol = '@';
        char unicode = '\u0041';  // Unicode for 'A'
        char chinese = '中';
        char emoji = '😊';

        // Escape sequences
        char newline = '\n';
        char tab = '\t';
        char backslash = '\\';
        char singleQuote = '\'';
        char carriageReturn = '\r';

        // Character arithmetic (chars are numeric)
        char nextLetter = (char) (letter + 1);  // 'B'

        System.out.println("Letter: " + letter);
        System.out.println("Unicode value: " + (int) letter);
        System.out.println("Next letter: " + nextLetter);
        System.out.println("Chinese character: " + chinese);
        System.out.println("Emoji: " + emoji);

        // Character utility methods
        System.out.println("Is letter digit? " + Character.isDigit(letter));
        System.out.println("Is digit letter? " + Character.isLetter(digit));
        System.out.println("Uppercase: " + Character.toUpperCase('a'));
    }
}
```

#### Boolean Type
```java
public class BooleanType {
    public static void main(String[] args) {
        // boolean: true or false only
        boolean isJavaFun = true;
        boolean isComplicated = false;

        // Boolean expressions
        boolean result1 = (5 > 3);          // true
        boolean result2 = (10 == 5);        // false
        boolean result3 = isJavaFun && !isComplicated;  // true

        // Boolean operations
        boolean a = true;
        boolean b = false;

        System.out.println("AND: " + (a && b));    // false
        System.out.println("OR: " + (a || b));     // true
        System.out.println("XOR: " + (a ^ b));     // true
        System.out.println("NOT a: " + !a);        // false

        // Short-circuit evaluation
        boolean shortCircuit = false && expensiveOperation();
        System.out.println("Short circuit result: " + shortCircuit);
    }

    private static boolean expensiveOperation() {
        System.out.println("This won't be printed due to short-circuit");
        return true;
    }
}
```

### Reference Data Types

Reference types store references (addresses) to objects in memory:

#### Strings
```java
public class StringExamples {
    public static void main(String[] args) {
        // String creation methods
        String literal = "Hello World";           // String literal (interned)
        String object = new String("Hello World"); // New String object
        String empty = "";                        // Empty string
        String nullString = null;                 // Null reference

        // String immutability
        String original = "Java";
        String modified = original.concat(" Programming");
        System.out.println("Original: " + original);   // Still "Java"
        System.out.println("Modified: " + modified);   // "Java Programming"

        // String comparison
        String str1 = "Hello";
        String str2 = "Hello";
        String str3 = new String("Hello");

        System.out.println("str1 == str2: " + (str1 == str2));         // true (same reference)
        System.out.println("str1 == str3: " + (str1 == str3));         // false (different objects)
        System.out.println("str1.equals(str3): " + str1.equals(str3)); // true (same content)

        // String methods
        String text = "  Java Programming  ";
        System.out.println("Length: " + text.length());
        System.out.println("Trimmed: '" + text.trim() + "'");
        System.out.println("Upper: " + text.toUpperCase());
        System.out.println("Lower: " + text.toLowerCase());
        System.out.println("Contains 'Java': " + text.contains("Java"));
        System.out.println("Starts with '  Java': " + text.startsWith("  Java"));
        System.out.println("Substring: " + text.substring(2, 6));

        // String building for efficiency
        StringBuilder builder = new StringBuilder();
        for (int i = 0; i < 5; i++) {
            builder.append("Item ").append(i).append(" ");
        }
        String result = builder.toString();
        System.out.println("Built string: " + result);
    }
}
```

#### Arrays
```java
public class ArrayExamples {
    public static void main(String[] args) {
        // Array declaration and initialization
        int[] numbers = new int[5];                    // Array of 5 integers
        String[] names = {"Alice", "Bob", "Charlie"};  // Array literal
        double[] grades = new double[]{95.5, 87.2, 92.1, 88.9};

        // Array access and modification
        numbers[0] = 10;
        numbers[1] = 20;
        numbers[4] = 50;

        System.out.println("Array length: " + numbers.length);
        System.out.println("First element: " + numbers[0]);
        System.out.println("Last element: " + numbers[numbers.length - 1]);

        // Array iteration
        System.out.println("For loop:");
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("numbers[" + i + "] = " + numbers[i]);
        }

        System.out.println("Enhanced for loop:");
        for (String name : names) {
            System.out.println("Name: " + name);
        }

        // Multi-dimensional arrays
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        System.out.println("Matrix:");
        for (int[] row : matrix) {
            for (int value : row) {
                System.out.print(value + " ");
            }
            System.out.println();
        }

        // Array utility methods
        int[] unsorted = {5, 2, 8, 1, 9};
        System.out.println("Original: " + java.util.Arrays.toString(unsorted));

        java.util.Arrays.sort(unsorted);
        System.out.println("Sorted: " + java.util.Arrays.toString(unsorted));

        int index = java.util.Arrays.binarySearch(unsorted, 8);
        System.out.println("Index of 8: " + index);
    }
}
```

### Variable Declaration and Initialization

```java
public class VariableDeclaration {

    // Class-level variables (fields)
    private static int classVariable = 100;    // Static variable
    private String instanceVariable;           // Instance variable

    public void demonstrateVariables() {
        // Local variable declaration and initialization
        int number;                    // Declaration only
        number = 42;                   // Initialization

        int initialized = 10;          // Declaration with initialization

        // Multiple declarations
        int a, b, c;                   // Multiple variables of same type
        int x = 1, y = 2, z = 3;       // Multiple with initialization

        // Type inference with var (Java 10+)
        var autoString = "Hello";      // Inferred as String
        var autoNumber = 42;           // Inferred as int
        var autoList = new java.util.ArrayList<String>(); // Inferred as ArrayList<String>

        // Final variables (constants)
        final int CONSTANT = 100;      // Local constant
        final String MESSAGE;          // Can be initialized later
        MESSAGE = "Initialized later";

        // Demonstration of usage
        System.out.println("Local number: " + number);
        System.out.println("Initialized: " + initialized);
        System.out.println("Multiple vars: " + x + ", " + y + ", " + z);
        System.out.println("Auto string: " + autoString);
        System.out.println("Auto number: " + autoNumber);
        System.out.println("Constant: " + CONSTANT);
        System.out.println("Message: " + MESSAGE);
    }

    // Constructor to initialize instance variable
    public VariableDeclaration(String value) {
        this.instanceVariable = value;
    }

    public static void main(String[] args) {
        VariableDeclaration demo = new VariableDeclaration("Instance Value");
        demo.demonstrateVariables();

        System.out.println("Class variable: " + classVariable);
        System.out.println("Instance variable: " + demo.instanceVariable);
    }
}
```

### Variable Scope

```java
public class VariableScope {

    // Class scope - accessible throughout the class
    private static String classField = "Class level";
    private String instanceField = "Instance level";

    public void demonstrateScope() {
        // Method scope - accessible within this method
        String methodVariable = "Method level";

        System.out.println("In method:");
        System.out.println("- Class field: " + classField);
        System.out.println("- Instance field: " + instanceField);
        System.out.println("- Method variable: " + methodVariable);

        // Block scope
        if (true) {
            String blockVariable = "Block level";  // Only accessible in this block
            String anotherMethod = methodVariable; // Can access method variable

            System.out.println("In block:");
            System.out.println("- Block variable: " + blockVariable);
            System.out.println("- Method from block: " + anotherMethod);
        }

        // blockVariable is not accessible here
        // System.out.println(blockVariable); // Compilation error

        // Loop scope
        for (int i = 0; i < 3; i++) { // 'i' is scoped to the loop
            String loopVariable = "Loop iteration " + i;
            System.out.println("Loop: " + loopVariable);
        }

        // 'i' and loopVariable are not accessible here
        // System.out.println(i); // Compilation error
    }

    public void shadowingExample() {
        String message = "Method level message";

        if (true) {
            String message = "Block level message"; // Shadows method variable
            System.out.println("In block: " + message); // Prints block level
        }

        System.out.println("In method: " + message); // Prints method level
    }

    public static void main(String[] args) {
        VariableScope scope = new VariableScope();
        scope.demonstrateScope();
        System.out.println();
        scope.shadowingExample();
    }
}
```

### Type Conversion and Casting

```java
public class TypeConversion {
    public static void main(String[] args) {
        demonstrateImplicitConversion();
        demonstrateExplicitCasting();
        demonstrateStringConversion();
        demonstrateWrapperConversion();
    }

    private static void demonstrateImplicitConversion() {
        System.out.println("=== Implicit Conversion (Widening) ===");

        // Automatic widening conversions (no data loss)
        byte b = 10;
        short s = b;        // byte to short
        int i = s;          // short to int
        long l = i;         // int to long
        float f = l;        // long to float
        double d = f;       // float to double

        System.out.println("byte: " + b);
        System.out.println("short: " + s);
        System.out.println("int: " + i);
        System.out.println("long: " + l);
        System.out.println("float: " + f);
        System.out.println("double: " + d);

        // Character to numeric
        char ch = 'A';
        int ascii = ch;     // char to int (gets ASCII value)
        System.out.println("Character 'A' as int: " + ascii);
    }

    private static void demonstrateExplicitCasting() {
        System.out.println("\n=== Explicit Casting (Narrowing) ===");

        // Explicit narrowing (potential data loss)
        double largeDouble = 123.456;
        float smallerFloat = (float) largeDouble;
        long longValue = (long) largeDouble;
        int intValue = (int) largeDouble;
        short shortValue = (short) intValue;
        byte byteValue = (byte) shortValue;

        System.out.println("Original double: " + largeDouble);
        System.out.println("Cast to float: " + smallerFloat);
        System.out.println("Cast to long: " + longValue);
        System.out.println("Cast to int: " + intValue);
        System.out.println("Cast to short: " + shortValue);
        System.out.println("Cast to byte: " + byteValue);

        // Demonstration of data loss
        int bigInt = 300;
        byte smallByte = (byte) bigInt;  // Data loss occurs
        System.out.println("300 as byte: " + smallByte + " (data loss!)");

        // Numeric to character
        int asciiValue = 65;
        char character = (char) asciiValue;
        System.out.println("65 as char: " + character);
    }

    private static void demonstrateStringConversion() {
        System.out.println("\n=== String Conversion ===");

        // Primitives to String
        int number = 42;
        double decimal = 3.14;
        boolean flag = true;

        String strFromInt = String.valueOf(number);
        String strFromDouble = String.valueOf(decimal);
        String strFromBoolean = String.valueOf(flag);

        System.out.println("Int to String: " + strFromInt);
        System.out.println("Double to String: " + strFromDouble);
        System.out.println("Boolean to String: " + strFromBoolean);

        // String to primitives
        String numberStr = "123";
        String decimalStr = "45.67";
        String booleanStr = "true";

        int parsedInt = Integer.parseInt(numberStr);
        double parsedDouble = Double.parseDouble(decimalStr);
        boolean parsedBoolean = Boolean.parseBoolean(booleanStr);

        System.out.println("String to int: " + parsedInt);
        System.out.println("String to double: " + parsedDouble);
        System.out.println("String to boolean: " + parsedBoolean);

        // Error handling for parsing
        try {
            int invalidParse = Integer.parseInt("not a number");
        } catch (NumberFormatException e) {
            System.out.println("Parse error: " + e.getMessage());
        }
    }

    private static void demonstrateWrapperConversion() {
        System.out.println("\n=== Wrapper Class Conversion ===");

        // Boxing (primitive to wrapper)
        Integer boxedInt = 42;              // Auto-boxing
        Double boxedDouble = 3.14;          // Auto-boxing
        Boolean boxedBoolean = true;        // Auto-boxing

        // Unboxing (wrapper to primitive)
        int unboxedInt = boxedInt;          // Auto-unboxing
        double unboxedDouble = boxedDouble; // Auto-unboxing
        boolean unboxedBoolean = boxedBoolean; // Auto-unboxing

        System.out.println("Boxed int: " + boxedInt);
        System.out.println("Unboxed int: " + unboxedInt);

        // Manual boxing/unboxing
        Integer manualBoxed = Integer.valueOf(100);
        int manualUnboxed = manualBoxed.intValue();

        System.out.println("Manual boxed: " + manualBoxed);
        System.out.println("Manual unboxed: " + manualUnboxed);

        // Null pointer risk with auto-unboxing
        Integer nullInteger = null;
        try {
            int risk = nullInteger; // NullPointerException
        } catch (NullPointerException e) {
            System.out.println("Null unboxing error: " + e.getClass().getSimpleName());
        }
    }
}
```

### Wrapper Classes

```java
public class WrapperClasses {
    public static void main(String[] args) {
        demonstrateWrapperBasics();
        demonstrateWrapperMethods();
        demonstrateComparison();
    }

    private static void demonstrateWrapperBasics() {
        System.out.println("=== Wrapper Class Basics ===");

        // All primitive wrapper classes
        Byte byteWrapper = 10;
        Short shortWrapper = 1000;
        Integer intWrapper = 42;
        Long longWrapper = 1234567890L;
        Float floatWrapper = 3.14f;
        Double doubleWrapper = 2.718;
        Character charWrapper = 'A';
        Boolean booleanWrapper = true;

        System.out.println("Byte wrapper: " + byteWrapper);
        System.out.println("Short wrapper: " + shortWrapper);
        System.out.println("Integer wrapper: " + intWrapper);
        System.out.println("Long wrapper: " + longWrapper);
        System.out.println("Float wrapper: " + floatWrapper);
        System.out.println("Double wrapper: " + doubleWrapper);
        System.out.println("Character wrapper: " + charWrapper);
        System.out.println("Boolean wrapper: " + booleanWrapper);
    }

    private static void demonstrateWrapperMethods() {
        System.out.println("\n=== Wrapper Class Methods ===");

        // Integer methods
        Integer num = 42;
        System.out.println("Integer value: " + num.intValue());
        System.out.println("As double: " + num.doubleValue());
        System.out.println("As string: " + num.toString());
        System.out.println("Hash code: " + num.hashCode());

        // Static utility methods
        System.out.println("Max int: " + Integer.MAX_VALUE);
        System.out.println("Min int: " + Integer.MIN_VALUE);
        System.out.println("Parse string: " + Integer.parseInt("123"));
        System.out.println("Binary string: " + Integer.toBinaryString(42));
        System.out.println("Hex string: " + Integer.toHexString(255));

        // Character methods
        Character ch = 'A';
        System.out.println("Is letter: " + Character.isLetter(ch));
        System.out.println("Is digit: " + Character.isDigit(ch));
        System.out.println("To lowercase: " + Character.toLowerCase(ch));
        System.out.println("Numeric value: " + Character.getNumericValue(ch));

        // Double methods
        Double d = 3.14159;
        System.out.println("Is infinite: " + Double.isInfinite(d));
        System.out.println("Is NaN: " + Double.isNaN(d));
        System.out.println("Compare to 3.0: " + d.compareTo(3.0));
    }

    private static void demonstrateComparison() {
        System.out.println("\n=== Wrapper Comparison ===");

        // Integer cache (-128 to 127)
        Integer a = 100;
        Integer b = 100;
        Integer c = new Integer(100); // Deprecated in Java 9+
        Integer d = 200;
        Integer e = 200;

        System.out.println("a == b (100): " + (a == b));         // true (cached)
        System.out.println("a == c (100): " + (a == c));         // false (different objects)
        System.out.println("d == e (200): " + (d == e));         // false (not cached)
        System.out.println("a.equals(c): " + a.equals(c));       // true (same value)
        System.out.println("d.equals(e): " + d.equals(e));       // true (same value)

        // Safe comparison
        Integer x = null;
        Integer y = 42;

        // Always use equals() for wrapper comparison
        System.out.println("Safe equals: " + Objects.equals(x, y));

        // Comparison with compareTo
        Integer num1 = 10;
        Integer num2 = 20;
        System.out.println("Compare result: " + num1.compareTo(num2)); // -1 (less than)
    }
}
```

### ⚠️ Common Pitfalls
- **Integer overflow**: No automatic detection of overflow in Java
- **Floating-point precision**: Avoid using == for floating-point comparison
- **Wrapper comparison**: Using == instead of equals() for wrapper objects
- **Null unboxing**: Auto-unboxing null wrapper objects causes NullPointerException
- **String mutability confusion**: Forgetting that Strings are immutable

### ✅ Best Practices
- Use appropriate data types for the range and precision needed
- Always use equals() to compare wrapper objects
- Handle NumberFormatException when parsing strings
- Use BigDecimal for precise decimal calculations
- Initialize variables before use
- Use final for constants and immutable variables

### 🏋️ Exercise 6: Data Type Converter
**Difficulty:** 🟡 Intermediate
**Estimated Time:** 30 minutes

Create a comprehensive data type converter that handles various conversions with proper error handling.

<details>
<summary>💡 Click to see hints</summary>

- Support conversion between all primitive types
- Handle string to number parsing with error handling
- Implement wrapper class operations
- Include input validation
- Use proper exception handling

</details>

<details>
<summary>✅ Click to see solution</summary>

```java
import java.math.BigDecimal;
import java.math.RoundingMode;
import java.util.Scanner;

/**
 * Comprehensive data type converter demonstrating type conversions,
 * wrapper classes, and error handling.
 */
public class DataTypeConverter {

    private final Scanner scanner;

    public DataTypeConverter() {
        this.scanner = new Scanner(System.in);
    }

    public static void main(String[] args) {
        DataTypeConverter converter = new DataTypeConverter();
        converter.runConverter();
    }

    public void runConverter() {
        System.out.println("🔄 Java Data Type Converter");
        System.out.println("==========================");

        boolean continueConverting = true;

        while (continueConverting) {
            try {
                displayMenu();
                int choice = getChoice();

                switch (choice) {
                    case 1 -> convertNumbers();
                    case 2 -> convertStrings();
                    case 3 -> demonstrateWrappers();
                    case 4 -> performArithmetic();
                    case 5 -> continueConverting = false;
                    default -> System.out.println("Invalid choice! Please try again.");
                }

                if (continueConverting) {
                    System.out.println("\nPress Enter to continue...");
                    scanner.nextLine();
                }

            } catch (Exception e) {
                System.err.println("Error: " + e.getMessage());
                scanner.nextLine(); // Clear invalid input
            }
        }

        scanner.close();
        System.out.println("Thank you for using the converter!");
    }

    private void displayMenu() {
        System.out.println("""

                Choose conversion type:
                1. Numeric Conversions
                2. String Conversions
                3. Wrapper Class Operations
                4. Arithmetic with Type Conversion
                5. Exit

                Enter your choice (1-5):""");
    }

    private int getChoice() {
        while (true) {
            try {
                String input = scanner.nextLine().trim();
                return Integer.parseInt(input);
            } catch (NumberFormatException e) {
                System.out.print("Please enter a valid number (1-5): ");
            }
        }
    }

    private void convertNumbers() {
        System.out.println("\n📊 Numeric Conversions");
        System.out.println("Enter a decimal number: ");

        try {
            String input = scanner.nextLine().trim();
            double originalValue = Double.parseDouble(input);

            System.out.println("\nOriginal value: " + originalValue);
            System.out.println("Conversions:");
            System.out.println("- byte: " + (byte) originalValue +
                             (originalValue > Byte.MAX_VALUE || originalValue < Byte.MIN_VALUE ?
                              " (overflow occurred)" : ""));
            System.out.println("- short: " + (short) originalValue +
                             (originalValue > Short.MAX_VALUE || originalValue < Short.MIN_VALUE ?
                              " (overflow occurred)" : ""));
            System.out.println("- int: " + (int) originalValue +
                             (originalValue > Integer.MAX_VALUE || originalValue < Integer.MIN_VALUE ?
                              " (overflow occurred)" : ""));
            System.out.println("- long: " + (long) originalValue);
            System.out.println("- float: " + (float) originalValue);
            System.out.println("- char: " + (originalValue >= 0 && originalValue <= 65535 ?
                              (char) originalValue : "Cannot convert to char"));

            // Binary and hex representations
            if (originalValue == (int) originalValue && originalValue >= Integer.MIN_VALUE &&
                originalValue <= Integer.MAX_VALUE) {
                int intValue = (int) originalValue;
                System.out.println("- binary: " + Integer.toBinaryString(intValue));
                System.out.println("- hex: 0x" + Integer.toHexString(intValue).toUpperCase());
            }

        } catch (NumberFormatException e) {
            System.err.println("Invalid number format: " + e.getMessage());
        }
    }

    private void convertStrings() {
        System.out.println("\n📝 String Conversions");
        System.out.println("Enter a value to convert from string: ");

        String input = scanner.nextLine().trim();
        System.out.println("\nOriginal string: \"" + input + "\"");
        System.out.println("Attempted conversions:");

        // Try different numeric conversions
        tryParseInteger(input);
        tryParseDouble(input);
        tryParseBoolean(input);

        // Character operations
        if (input.length() == 1) {
            char ch = input.charAt(0);
            System.out.println("- As character: '" + ch + "' (ASCII: " + (int) ch + ")");
            System.out.println("- Is letter: " + Character.isLetter(ch));
            System.out.println("- Is digit: " + Character.isDigit(ch));
        }

        // String analysis
        System.out.println("String analysis:");
        System.out.println("- Length: " + input.length());
        System.out.println("- Empty: " + input.isEmpty());
        System.out.println("- Blank: " + input.isBlank());
        System.out.println("- Uppercase: " + input.toUpperCase());
        System.out.println("- Lowercase: " + input.toLowerCase());
    }

    private void tryParseInteger(String input) {
        try {
            Integer parsed = Integer.valueOf(input);
            System.out.println("- As Integer: " + parsed + " ✓");
        } catch (NumberFormatException e) {
            System.out.println("- As Integer: Cannot parse ✗");
        }
    }

    private void tryParseDouble(String input) {
        try {
            Double parsed = Double.valueOf(input);
            System.out.println("- As Double: " + parsed + " ✓");
        } catch (NumberFormatException e) {
            System.out.println("- As Double: Cannot parse ✗");
        }
    }

    private void tryParseBoolean(String input) {
        Boolean parsed = Boolean.valueOf(input);
        System.out.println("- As Boolean: " + parsed + " (" +
                          (input.equalsIgnoreCase("true") ? "true parse" : "default false") + ")");
    }

    private void demonstrateWrappers() {
        System.out.println("\n📦 Wrapper Class Operations");
        System.out.println("Enter two integers: ");

        try {
            System.out.print("First number: ");
            Integer num1 = Integer.valueOf(scanner.nextLine().trim());

            System.out.print("Second number: ");
            Integer num2 = Integer.valueOf(scanner.nextLine().trim());

            System.out.println("\nWrapper operations:");
            System.out.println("- num1.equals(num2): " + num1.equals(num2));
            System.out.println("- num1.compareTo(num2): " + num1.compareTo(num2));
            System.out.println("- Reference equality (==): " + (num1 == num2));
            System.out.println("- num1.toString(): \"" + num1.toString() + "\"");
            System.out.println("- Integer.max(num1, num2): " + Integer.max(num1, num2));
            System.out.println("- Integer.min(num1, num2): " + Integer.min(num1, num2));

            // Auto-boxing/unboxing demonstration
            int primitive1 = num1; // Auto-unboxing
            Integer wrapper1 = primitive1 + 10; // Auto-boxing
            System.out.println("- Auto-unboxing + boxing result: " + wrapper1);

        } catch (NumberFormatException e) {
            System.err.println("Invalid integer input: " + e.getMessage());
        }
    }

    private void performArithmetic() {
        System.out.println("\n🔢 Arithmetic with Type Conversion");
        System.out.println("Enter two numbers for arithmetic operations: ");

        try {
            System.out.print("First number (can be decimal): ");
            String input1 = scanner.nextLine().trim();

            System.out.print("Second number (can be decimal): ");
            String input2 = scanner.nextLine().trim();

            // Try to determine best numeric type
            Number num1 = parseNumber(input1);
            Number num2 = parseNumber(input2);

            System.out.println("\nParsed as:");
            System.out.println("- First: " + num1 + " (" + num1.getClass().getSimpleName() + ")");
            System.out.println("- Second: " + num2 + " (" + num2.getClass().getSimpleName() + ")");

            // Perform operations using BigDecimal for precision
            BigDecimal bd1 = new BigDecimal(num1.toString());
            BigDecimal bd2 = new BigDecimal(num2.toString());

            System.out.println("\nArithmetic results (using BigDecimal for precision):");
            System.out.println("- Addition: " + bd1.add(bd2));
            System.out.println("- Subtraction: " + bd1.subtract(bd2));
            System.out.println("- Multiplication: " + bd1.multiply(bd2));

            if (bd2.compareTo(BigDecimal.ZERO) != 0) {
                System.out.println("- Division: " + bd1.divide(bd2, 4, RoundingMode.HALF_UP));
            } else {
                System.out.println("- Division: Cannot divide by zero");
            }

        } catch (Exception e) {
            System.err.println("Arithmetic error: " + e.getMessage());
        }
    }

    private Number parseNumber(String input) {
        // Try Integer first
        try {
            return Integer.valueOf(input);
        } catch (NumberFormatException ignored) {}

        // Try Long
        try {
            return Long.valueOf(input);
        } catch (NumberFormatException ignored) {}

        // Try Double
        try {
            return Double.valueOf(input);
        } catch (NumberFormatException ignored) {}

        throw new NumberFormatException("Cannot parse as number: " + input);
    }
}
```

**Explanation:**
- **Comprehensive Conversion**: Handles multiple data type conversions with proper error handling
- **User Interaction**: Menu-driven interface for different conversion types
- **Error Handling**: Graceful handling of invalid input with specific error messages
- **Type Safety**: Proper use of wrapper classes and type checking
- **Precision Handling**: Uses BigDecimal for accurate decimal arithmetic
- **Educational Value**: Demonstrates key concepts like auto-boxing, wrapper methods, and type conversion

</details>

[↑ Back to Top](#-table-of-contents)

---

## 6. Operators & Expressions

📊 **Chapter 6 of 35**

🎯 **Learning Objectives:**
- Master all Java operators: arithmetic, relational, logical, bitwise
- Understand operator precedence and associativity
- Learn about assignment operators and compound assignments
- Practice creating complex expressions and evaluations

⏱️ **Estimated Reading Time:** 22 minutes
📋 **Prerequisites:** Understanding of Java data types and variables

### Arithmetic Operators

Java provides standard arithmetic operators for mathematical computations:

```java
public class ArithmeticOperators {
    public static void main(String[] args) {
        demonstrateBasicArithmetic();
        demonstrateIntegerDivision();
        demonstrateModulusOperator();
        demonstrateIncrementDecrement();
    }

    private static void demonstrateBasicArithmetic() {
        System.out.println("=== Basic Arithmetic Operations ===");

        int a = 15, b = 4;
        double x = 15.0, y = 4.0;

        // Addition
        System.out.println(a + " + " + b + " = " + (a + b));
        System.out.println(x + " + " + y + " = " + (x + y));

        // Subtraction
        System.out.println(a + " - " + b + " = " + (a - b));
        System.out.println(x + " - " + y + " = " + (x - y));

        // Multiplication
        System.out.println(a + " * " + b + " = " + (a * b));
        System.out.println(x + " * " + y + " = " + (x * y));

        // Division
        System.out.println(a + " / " + b + " = " + (a / b));       // Integer division
        System.out.println(x + " / " + y + " = " + (x / y));       // Floating-point division

        // Modulus (remainder)
        System.out.println(a + " % " + b + " = " + (a % b));
        System.out.println(x + " % " + y + " = " + (x % y));
    }

    private static void demonstrateIntegerDivision() {
        System.out.println("\n=== Integer Division Behavior ===");

        int dividend = 17;
        int divisor = 5;

        int quotient = dividend / divisor;           // 3 (truncated)
        int remainder = dividend % divisor;          // 2
        double exactResult = (double) dividend / divisor; // 3.4

        System.out.println("Integer division: " + dividend + " / " + divisor + " = " + quotient);
        System.out.println("Remainder: " + dividend + " % " + divisor + " = " + remainder);
        System.out.println("Exact division: " + dividend + " / " + divisor + " = " + exactResult);

        // Verification: dividend = quotient * divisor + remainder
        System.out.println("Verification: " + quotient + " * " + divisor + " + " + remainder +
                          " = " + (quotient * divisor + remainder));
    }

    private static void demonstrateModulusOperator() {
        System.out.println("\n=== Modulus Operator Applications ===");

        // Check if number is even or odd
        int[] numbers = {10, 11, 0, -4, -7};
        for (int num : numbers) {
            String parity = (num % 2 == 0) ? "even" : "odd";
            System.out.println(num + " is " + parity);
        }

        // Circular array indexing
        int[] array = {10, 20, 30, 40, 50};
        int arrayLength = array.length;

        System.out.println("\nCircular array access:");
        for (int i = 0; i < 10; i++) {
            int index = i % arrayLength;
            System.out.println("i=" + i + ", index=" + index + ", value=" + array[index]);
        }

        // Time calculations
        int totalMinutes = 150;
        int hours = totalMinutes / 60;
        int minutes = totalMinutes % 60;
        System.out.println("\n" + totalMinutes + " minutes = " + hours + " hours and " +
                          minutes + " minutes");
    }

    private static void demonstrateIncrementDecrement() {
        System.out.println("\n=== Increment and Decrement Operators ===");

        int a = 5;
        int b = 5;

        // Pre-increment and post-increment
        System.out.println("Original: a = " + a + ", b = " + b);

        int preIncResult = ++a;   // Increment first, then use
        int postIncResult = b++;  // Use first, then increment

        System.out.println("After ++a: a = " + a + ", result = " + preIncResult);
        System.out.println("After b++: b = " + b + ", result = " + postIncResult);

        // Pre-decrement and post-decrement
        int c = 10;
        int d = 10;

        int preDecResult = --c;   // Decrement first, then use
        int postDecResult = d--;  // Use first, then decrement

        System.out.println("After --c: c = " + c + ", result = " + preDecResult);
        System.out.println("After d--: d = " + d + ", result = " + postDecResult);

        // Common mistake demonstration
        int x = 5;
        int result = x++ + ++x + x--;
        System.out.println("Complex expression result: " + result + ", final x = " + x);
        // Breakdown: 5 + 7 + 7 = 19, x becomes 6
    }
}
```

### Relational and Equality Operators

```java
public class RelationalOperators {
    public static void main(String[] args) {
        demonstrateComparison();
        demonstrateStringComparison();
        demonstrateObjectComparison();
    }

    private static void demonstrateComparison() {
        System.out.println("=== Relational Operators ===");

        int a = 10, b = 5, c = 10;

        System.out.println("a = " + a + ", b = " + b + ", c = " + c);
        System.out.println("a > b: " + (a > b));    // true
        System.out.println("a < b: " + (a < b));    // false
        System.out.println("a >= c: " + (a >= c));  // true
        System.out.println("a <= c: " + (a <= c));  // true
        System.out.println("a == c: " + (a == c));  // true
        System.out.println("a != b: " + (a != b));  // true

        // Chaining comparisons (common mistake)
        // System.out.println(a < b < c);  // Compilation error
        System.out.println("Correct chaining: " + (a > b && b < c));

        // Floating-point comparison caution
        double x = 0.1 + 0.2;
        double y = 0.3;
        System.out.println("0.1 + 0.2 = " + x);
        System.out.println("0.3 = " + y);
        System.out.println("x == y: " + (x == y));  // false due to precision
        System.out.println("Math.abs(x - y) < 1e-10: " + (Math.abs(x - y) < 1e-10)); // true
    }

    private static void demonstrateStringComparison() {
        System.out.println("\n=== String Comparison ===");

        String str1 = "Hello";
        String str2 = "Hello";
        String str3 = new String("Hello");
        String str4 = "hello";

        System.out.println("str1 == str2: " + (str1 == str2));           // true (same reference)
        System.out.println("str1 == str3: " + (str1 == str3));           // false (different objects)
        System.out.println("str1.equals(str3): " + str1.equals(str3));   // true (same content)
        System.out.println("str1.equals(str4): " + str1.equals(str4));   // false (case sensitive)
        System.out.println("str1.equalsIgnoreCase(str4): " + str1.equalsIgnoreCase(str4)); // true

        // String comparison methods
        String apple = "apple";
        String banana = "banana";

        System.out.println("apple.compareTo(banana): " + apple.compareTo(banana));     // negative
        System.out.println("banana.compareTo(apple): " + banana.compareTo(apple));     // positive
        System.out.println("apple.compareTo(apple): " + apple.compareTo(apple));       // zero
    }

    private static void demonstrateObjectComparison() {
        System.out.println("\n=== Object Comparison ===");

        Integer int1 = 127;
        Integer int2 = 127;
        Integer int3 = new Integer(127); // Deprecated but for demonstration
        Integer int4 = 128;
        Integer int5 = 128;

        System.out.println("Integer cache behavior:");
        System.out.println("int1 == int2 (127): " + (int1 == int2));     // true (cached)
        System.out.println("int1 == int3 (127): " + (int1 == int3));     // false (new object)
        System.out.println("int4 == int5 (128): " + (int4 == int5));     // false (not cached)

        System.out.println("int1.equals(int3): " + int1.equals(int3));   // true (same value)
        System.out.println("int4.equals(int5): " + int4.equals(int5));   // true (same value)

        // Null comparison
        String nullStr = null;
        String nonNullStr = "Hello";

        System.out.println("null == null: " + (nullStr == null));
        System.out.println("Objects.equals(null, null): " + java.util.Objects.equals(nullStr, nullStr));
        System.out.println("Objects.equals(null, \"Hello\"): " + java.util.Objects.equals(nullStr, nonNullStr));
    }
}
```

### Logical Operators

```java
public class LogicalOperators {
    public static void main(String[] args) {
        demonstrateLogicalOperators();
        demonstrateShortCircuitEvaluation();
        demonstrateTruthTables();
    }

    private static void demonstrateLogicalOperators() {
        System.out.println("=== Logical Operators ===");

        boolean a = true;
        boolean b = false;
        boolean c = true;

        System.out.println("a = " + a + ", b = " + b + ", c = " + c);

        // AND operator
        System.out.println("a && b: " + (a && b));           // false
        System.out.println("a && c: " + (a && c));           // true

        // OR operator
        System.out.println("a || b: " + (a || b));           // true
        System.out.println("b || false: " + (b || false));   // false

        // NOT operator
        System.out.println("!a: " + (!a));                   // false
        System.out.println("!b: " + (!b));                   // true

        // XOR operator
        System.out.println("a ^ b: " + (a ^ b));             // true
        System.out.println("a ^ c: " + (a ^ c));             // false

        // Complex expressions
        boolean complex1 = (a && b) || (c && !b);
        boolean complex2 = !(a || b) && c;

        System.out.println("(a && b) || (c && !b): " + complex1);
        System.out.println("!(a || b) && c: " + complex2);
    }

    private static void demonstrateShortCircuitEvaluation() {
        System.out.println("\n=== Short-Circuit Evaluation ===");

        // AND short-circuit
        System.out.println("Testing AND short-circuit:");
        boolean result1 = false && expensiveOperation("AND");
        System.out.println("Result: " + result1);

        boolean result2 = true && expensiveOperation("AND");
        System.out.println("Result: " + result2);

        // OR short-circuit
        System.out.println("\nTesting OR short-circuit:");
        boolean result3 = true || expensiveOperation("OR");
        System.out.println("Result: " + result3);

        boolean result4 = false || expensiveOperation("OR");
        System.out.println("Result: " + result4);

        // Practical example: null check
        String str = null;
        if (str != null && str.length() > 0) {
            System.out.println("String is not empty");
        } else {
            System.out.println("String is null or empty");
        }

        // Without short-circuit, this would cause NullPointerException
    }

    private static boolean expensiveOperation(String context) {
        System.out.println("  Expensive operation executed in " + context + " context");
        return true;
    }

    private static void demonstrateTruthTables() {
        System.out.println("\n=== Truth Tables ===");

        System.out.println("AND Truth Table:");
        System.out.println("A     B     A && B");
        System.out.println("true  true  " + (true && true));
        System.out.println("true  false " + (true && false));
        System.out.println("false true  " + (false && true));
        System.out.println("false false " + (false && false));

        System.out.println("\nOR Truth Table:");
        System.out.println("A     B     A || B");
        System.out.println("true  true  " + (true || true));
        System.out.println("true  false " + (true || false));
        System.out.println("false true  " + (false || true));
        System.out.println("false false " + (false || false));

        System.out.println("\nXOR Truth Table:");
        System.out.println("A     B     A ^ B");
        System.out.println("true  true  " + (true ^ true));
        System.out.println("true  false " + (true ^ false));
        System.out.println("false true  " + (false ^ true));
        System.out.println("false false " + (false ^ false));
    }
}
```

### Assignment Operators

```java
public class AssignmentOperators {
    public static void main(String[] args) {
        demonstrateBasicAssignment();
        demonstrateCompoundAssignment();
        demonstrateMultipleAssignment();
    }

    private static void demonstrateBasicAssignment() {
        System.out.println("=== Basic Assignment ===");

        // Simple assignment
        int a = 10;
        double b = 3.14;
        String c = "Hello";
        boolean d = true;

        System.out.println("a = " + a);
        System.out.println("b = " + b);
        System.out.println("c = " + c);
        System.out.println("d = " + d);

        // Assignment returns the assigned value
        int x, y, z;
        z = (y = (x = 5));  // All get the value 5
        System.out.println("x = " + x + ", y = " + y + ", z = " + z);
    }

    private static void demonstrateCompoundAssignment() {
        System.out.println("\n=== Compound Assignment Operators ===");

        int num = 10;
        System.out.println("Initial value: " + num);

        // Arithmetic compound assignments
        num += 5;   // equivalent to: num = num + 5
        System.out.println("After += 5: " + num);

        num -= 3;   // equivalent to: num = num - 3
        System.out.println("After -= 3: " + num);

        num *= 2;   // equivalent to: num = num * 2
        System.out.println("After *= 2: " + num);

        num /= 4;   // equivalent to: num = num / 4
        System.out.println("After /= 4: " + num);

        num %= 3;   // equivalent to: num = num % 3
        System.out.println("After %= 3: " + num);

        // Bitwise compound assignments
        int bits = 12;  // 1100 in binary
        System.out.println("\nBitwise operations on " + bits + " (" +
                          Integer.toBinaryString(bits) + " binary):");

        bits &= 10; // 1100 & 1010 = 1000
        System.out.println("After &= 10: " + bits + " (" + Integer.toBinaryString(bits) + ")");

        bits |= 5;  // 1000 | 0101 = 1101
        System.out.println("After |= 5: " + bits + " (" + Integer.toBinaryString(bits) + ")");

        bits ^= 7;  // 1101 ^ 0111 = 1010
        System.out.println("After ^= 7: " + bits + " (" + Integer.toBinaryString(bits) + ")");

        bits <<= 2; // Left shift by 2
        System.out.println("After <<= 2: " + bits + " (" + Integer.toBinaryString(bits) + ")");

        bits >>= 1; // Right shift by 1
        System.out.println("After >>= 1: " + bits + " (" + Integer.toBinaryString(bits) + ")");

        // String compound assignment
        String message = "Hello";
        message += " World";  // String concatenation
        message += "!";
        System.out.println("String result: " + message);
    }

    private static void demonstrateMultipleAssignment() {
        System.out.println("\n=== Multiple Assignment ===");

        // Multiple assignment (right to left evaluation)
        int x, y, z;
        x = y = z = 100;  // All variables get the value 100
        System.out.println("x = " + x + ", y = " + y + ", z = " + z);

        // Assignment in expressions
        int a = 5;
        int b = (a = 10) + 5;  // a is assigned 10, then b gets 15
        System.out.println("a = " + a + ", b = " + b);

        // Array element assignment
        int[] array = new int[3];
        array[0] = array[1] = array[2] = 42;
        System.out.println("Array: " + java.util.Arrays.toString(array));
    }
}
```

### Bitwise Operators

```java
public class BitwiseOperators {
    public static void main(String[] args) {
        demonstrateBitwiseOperations();
        demonstrateShiftOperators();
        demonstratePracticalApplications();
    }

    private static void demonstrateBitwiseOperations() {
        System.out.println("=== Bitwise Operations ===");

        int a = 12;  // 1100 in binary
        int b = 10;  // 1010 in binary

        System.out.println("a = " + a + " (" + Integer.toBinaryString(a) + " binary)");
        System.out.println("b = " + b + " (" + Integer.toBinaryString(b) + " binary)");

        // Bitwise AND
        int and = a & b;  // 1100 & 1010 = 1000 (8)
        System.out.println("a & b = " + and + " (" + Integer.toBinaryString(and) + " binary)");

        // Bitwise OR
        int or = a | b;   // 1100 | 1010 = 1110 (14)
        System.out.println("a | b = " + or + " (" + Integer.toBinaryString(or) + " binary)");

        // Bitwise XOR
        int xor = a ^ b;  // 1100 ^ 1010 = 0110 (6)
        System.out.println("a ^ b = " + xor + " (" + Integer.toBinaryString(xor) + " binary)");

        // Bitwise complement (NOT)
        int notA = ~a;    // Inverts all bits
        System.out.println("~a = " + notA + " (" + Integer.toBinaryString(notA) + " binary)");
    }

    private static void demonstrateShiftOperators() {
        System.out.println("\n=== Shift Operators ===");

        int value = 8;  // 1000 in binary
        System.out.println("Original: " + value + " (" + Integer.toBinaryString(value) + " binary)");

        // Left shift (multiply by 2^n)
        int leftShift = value << 2;  // 1000 << 2 = 100000 (32)
        System.out.println("value << 2 = " + leftShift + " (" + Integer.toBinaryString(leftShift) + " binary)");

        // Right shift (divide by 2^n, sign-extended)
        int rightShift = value >> 1;  // 1000 >> 1 = 0100 (4)
        System.out.println("value >> 1 = " + rightShift + " (" + Integer.toBinaryString(rightShift) + " binary)");

        // Unsigned right shift (zero-fill)
        int negativeValue = -8;
        System.out.println("Negative value: " + negativeValue + " (" + Integer.toBinaryString(negativeValue) + " binary)");

        int signedRightShift = negativeValue >> 1;
        int unsignedRightShift = negativeValue >>> 1;

        System.out.println("negativeValue >> 1 = " + signedRightShift + " (sign-extended)");
        System.out.println("negativeValue >>> 1 = " + unsignedRightShift + " (zero-fill)");
    }

    private static void demonstratePracticalApplications() {
        System.out.println("\n=== Practical Applications ===");

        // Check if number is even or odd using bitwise AND
        int[] numbers = {4, 7, 12, 15, 20};
        System.out.println("Even/Odd check using bitwise AND:");
        for (int num : numbers) {
            String parity = ((num & 1) == 0) ? "even" : "odd";
            System.out.println(num + " is " + parity);
        }

        // Power of 2 check
        System.out.println("\nPower of 2 check:");
        for (int num : new int[]{1, 2, 3, 4, 8, 15, 16, 32}) {
            boolean isPowerOfTwo = (num > 0) && ((num & (num - 1)) == 0);
            System.out.println(num + " is " + (isPowerOfTwo ? "" : "not ") + "a power of 2");
        }

        // Fast multiplication and division by powers of 2
        int number = 10;
        System.out.println("\nFast arithmetic with powers of 2:");
        System.out.println(number + " * 4 = " + (number << 2));  // Multiply by 4
        System.out.println(number + " * 8 = " + (number << 3));  // Multiply by 8
        System.out.println(number + " / 2 = " + (number >> 1));  // Divide by 2
        System.out.println(number + " / 4 = " + (number >> 2));  // Divide by 4

        // Bit manipulation for flags
        demonstrateBitFlags();
    }

    private static void demonstrateBitFlags() {
        System.out.println("\nBit flags example:");

        // Define flags as powers of 2
        final int READ = 1;     // 001
        final int WRITE = 2;    // 010
        final int EXECUTE = 4;  // 100

        // Set permissions
        int permissions = 0;
        permissions |= READ;    // Add read permission
        permissions |= WRITE;   // Add write permission

        System.out.println("Permissions: " + Integer.toBinaryString(permissions));
        System.out.println("Has READ: " + ((permissions & READ) != 0));
        System.out.println("Has WRITE: " + ((permissions & WRITE) != 0));
        System.out.println("Has EXECUTE: " + ((permissions & EXECUTE) != 0));

        // Remove write permission
        permissions &= ~WRITE;
        System.out.println("After removing WRITE: " + Integer.toBinaryString(permissions));
        System.out.println("Has WRITE: " + ((permissions & WRITE) != 0));
    }
}
```

### Operator Precedence and Associativity

```java
public class OperatorPrecedence {
    public static void main(String[] args) {
        demonstratePrecedence();
        demonstrateAssociativity();
        demonstrateComplexExpressions();
    }

    private static void demonstratePrecedence() {
        System.out.println("=== Operator Precedence ===");

        // Arithmetic vs. relational
        int a = 5, b = 3, c = 2;

        boolean result1 = a + b > c * 2;  // (a + b) > (c * 2) = 8 > 4 = true
        System.out.println("a + b > c * 2: " + result1);

        // Logical AND vs. OR
        boolean result2 = true || false && false;  // true || (false && false) = true
        System.out.println("true || false && false: " + result2);

        // Assignment vs. arithmetic
        int x = 5;
        int y = x += 3 * 2;  // x += (3 * 2), then y = x
        System.out.println("x = " + x + ", y = " + y);

        // Increment/decrement vs. arithmetic
        int i = 5;
        int result3 = ++i * 2;  // (++i) * 2 = 6 * 2 = 12
        System.out.println("++i * 2 = " + result3 + ", i = " + i);

        int j = 5;
        int result4 = j++ * 2;  // (j++) * 2 = 5 * 2 = 10
        System.out.println("j++ * 2 = " + result4 + ", j = " + j);
    }

    private static void demonstrateAssociativity() {
        System.out.println("\n=== Operator Associativity ===");

        // Left-to-right associativity
        int result1 = 100 / 5 / 2;  // (100 / 5) / 2 = 20 / 2 = 10
        System.out.println("100 / 5 / 2 = " + result1);

        // Right-to-left associativity (assignment)
        int a, b, c;
        a = b = c = 10;  // c = 10, then b = c, then a = b
        System.out.println("a = b = c = 10: a=" + a + ", b=" + b + ", c=" + c);

        // Ternary operator associativity
        String result2 = true ? "first" : false ? "second" : "third";
        // Equivalent to: true ? "first" : (false ? "second" : "third")
        System.out.println("Ternary result: " + result2);

        // Power calculation (Java doesn't have ** operator)
        double base = 2;
        double result3 = base * base * base;  // Left-to-right: ((2 * 2) * 2) = 8
        System.out.println("2 * 2 * 2 = " + result3);
    }

    private static void demonstrateComplexExpressions() {
        System.out.println("\n=== Complex Expressions ===");

        int x = 5, y = 10, z = 15;

        // Complex arithmetic expression
        int result1 = x + y * z - x * y / z;
        // Step by step: 5 + (10 * 15) - ((5 * 10) / 15)
        // = 5 + 150 - (50 / 15)
        // = 5 + 150 - 3 = 152
        System.out.println("x + y * z - x * y / z = " + result1);

        // Complex logical expression
        boolean result2 = x > 0 && y < 20 || z == 15 && x != y;
        // Step by step: (x > 0 && y < 20) || (z == 15 && x != y)
        // = (true && true) || (true && true)
        // = true || true = true
        System.out.println("Complex logical expression: " + result2);

        // Expression with side effects
        int a = 5;
        int result3 = ++a + a++ + a;
        // Step by step: ++a makes a = 6, then 6 + (a++ uses 6, makes a = 7) + 7
        // = 6 + 6 + 7 = 19
        System.out.println("++a + a++ + a = " + result3 + ", final a = " + a);

        // Using parentheses for clarity
        int b = 10, c = 5, d = 2;
        int result4 = (b + c) * d;        // 15 * 2 = 30
        int result5 = b + (c * d);        // 10 + 10 = 20
        System.out.println("(b + c) * d = " + result4);
        System.out.println("b + (c * d) = " + result5);
    }
}
```

### Conditional (Ternary) Operator

```java
public class TernaryOperator {
    public static void main(String[] args) {
        demonstrateBasicTernary();
        demonstrateNestedTernary();
        demonstratePracticalExamples();
    }

    private static void demonstrateBasicTernary() {
        System.out.println("=== Basic Ternary Operator ===");

        int age = 18;
        String status = (age >= 18) ? "Adult" : "Minor";
        System.out.println("Age " + age + " is " + status);

        // Compare with if-else
        String statusIfElse;
        if (age >= 18) {
            statusIfElse = "Adult";
        } else {
            statusIfElse = "Minor";
        }
        System.out.println("Using if-else: " + statusIfElse);

        // Numeric example
        int a = 10, b = 5;
        int max = (a > b) ? a : b;
        System.out.println("Max of " + a + " and " + b + " is " + max);

        // Boolean expression
        boolean isPositive = (5 > 0) ? true : false;  // Redundant, but for demonstration
        System.out.println("Is 5 positive? " + isPositive);

        // More practical boolean use
        boolean hasPermission = true;
        String message = hasPermission ? "Access granted" : "Access denied";
        System.out.println("Message: " + message);
    }

    private static void demonstrateNestedTernary() {
        System.out.println("\n=== Nested Ternary Operators ===");

        int score = 85;
        String grade = (score >= 90) ? "A" :
                      (score >= 80) ? "B" :
                      (score >= 70) ? "C" :
                      (score >= 60) ? "D" : "F";
        System.out.println("Score " + score + " gets grade " + grade);

        // Temperature classification
        int temperature = 25;
        String weather = (temperature > 30) ? "Hot" :
                        (temperature > 20) ? "Warm" :
                        (temperature > 10) ? "Cool" : "Cold";
        System.out.println("Temperature " + temperature + "°C is " + weather);

        // Multiple conditions
        int x = 0;
        String sign = (x > 0) ? "Positive" : (x < 0) ? "Negative" : "Zero";
        System.out.println("Number " + x + " is " + sign);

        // Complex nested example (not recommended for readability)
        int num = 15;
        String description = (num % 2 == 0) ?
                            ((num % 4 == 0) ? "Divisible by 4" : "Even but not by 4") :
                            ((num % 3 == 0) ? "Odd and divisible by 3" : "Odd");
        System.out.println("Number " + num + " is " + description);
    }

    private static void demonstratePracticalExamples() {
        System.out.println("\n=== Practical Examples ===");

        // Null checking
        String name = null;
        String displayName = (name != null) ? name : "Unknown";
        System.out.println("Display name: " + displayName);

        // Array bounds checking
        int[] array = {1, 2, 3, 4, 5};
        int index = 10;
        int value = (index >= 0 && index < array.length) ? array[index] : -1;
        System.out.println("Value at index " + index + ": " + value);

        // Method selection based on condition
        boolean useComplexAlgorithm = false;
        String result = useComplexAlgorithm ? complexCalculation() : simpleCalculation();
        System.out.println("Calculation result: " + result);

        // Format selection
        double price = 19.99;
        boolean showCents = true;
        String formattedPrice = showCents ?
                               String.format("$%.2f", price) :
                               String.format("$%.0f", price);
        System.out.println("Formatted price: " + formattedPrice);

        // Collection size check
        java.util.List<String> list = java.util.Arrays.asList("apple", "banana");
        String sizeMessage = (list.size() == 1) ? "1 item" : list.size() + " items";
        System.out.println("List contains " + sizeMessage);
    }

    private static String complexCalculation() {
        return "Complex result";
    }

    private static String simpleCalculation() {
        return "Simple result";
    }
}
```

### ⚠️ Common Pitfalls
- **Integer division**: Forgetting that division of integers truncates decimal part
- **Floating-point comparison**: Using == instead of checking difference within epsilon
- **Operator precedence**: Not using parentheses for complex expressions
- **Side effects in expressions**: Using increment/decrement in complex expressions
- **Short-circuit evaluation**: Relying on side effects in logical expressions

### ✅ Best Practices
- Use parentheses to make operator precedence explicit
- Avoid complex expressions with multiple side effects
- Use appropriate data types for the operations you need
- Always use equals() for object comparison, not ==
- Keep ternary operators simple and readable
- Use compound assignment operators for cleaner code

### 🏋️ Exercise 7: Expression Evaluator
**Difficulty:** 🔴 Advanced
**Estimated Time:** 45 minutes

Create a program that evaluates mathematical expressions with proper operator precedence and error handling.

<details>
<summary>💡 Click to see hints</summary>

- Implement a simple expression parser using recursion
- Handle operator precedence correctly
- Support parentheses for grouping
- Include error handling for invalid expressions
- Support basic arithmetic operators

</details>

<details>
<summary>✅ Click to see solution</summary>

```java
import java.util.*;
import java.util.regex.*;

/**
 * Simple mathematical expression evaluator that demonstrates
 * operator precedence, parsing, and expression evaluation.
 */
public class ExpressionEvaluator {

    private static final Pattern NUMBER_PATTERN = Pattern.compile("-?\\d+(\\.\\d+)?");
    private static final Pattern OPERATOR_PATTERN = Pattern.compile("[+\\-*/()]");

    public static void main(String[] args) {
        ExpressionEvaluator evaluator = new ExpressionEvaluator();
        Scanner scanner = new Scanner(System.in);

        System.out.println("🧮 Mathematical Expression Evaluator");
        System.out.println("Supports: +, -, *, /, parentheses");
        System.out.println("Enter 'quit' to exit\n");

        while (true) {
            System.out.print("Enter expression: ");
            String input = scanner.nextLine().trim();

            if (input.equalsIgnoreCase("quit")) {
                break;
            }

            if (input.isEmpty()) {
                continue;
            }

            try {
                double result = evaluator.evaluate(input);
                System.out.println("Result: " + result);
            } catch (Exception e) {
                System.err.println("Error: " + e.getMessage());
            }
            System.out.println();
        }

        scanner.close();
        System.out.println("Thank you for using the evaluator!");
    }

    public double evaluate(String expression) throws IllegalArgumentException {
        List<String> tokens = tokenize(expression);
        if (tokens.isEmpty()) {
            throw new IllegalArgumentException("Empty expression");
        }

        return evaluateExpression(tokens, 0).value;
    }

    private List<String> tokenize(String expression) {
        List<String> tokens = new ArrayList<>();
        Matcher matcher = Pattern.compile("-?\\d+(\\.\\d+)?|[+\\-*/()]").matcher(expression.replaceAll("\\s+", ""));

        while (matcher.find()) {
            tokens.add(matcher.group());
        }

        return tokens;
    }

    private Result evaluateExpression(List<String> tokens, int startIndex) {
        return evaluateAddSubtract(tokens, startIndex);
    }

    private Result evaluateAddSubtract(List<String> tokens, int startIndex) {
        Result left = evaluateMultiplyDivide(tokens, startIndex);
        int index = left.nextIndex;

        while (index < tokens.size()) {
            String operator = tokens.get(index);
            if (!operator.equals("+") && !operator.equals("-")) {
                break;
            }

            Result right = evaluateMultiplyDivide(tokens, index + 1);

            if (operator.equals("+")) {
                left = new Result(left.value + right.value, right.nextIndex);
            } else {
                left = new Result(left.value - right.value, right.nextIndex);
            }

            index = left.nextIndex;
        }

        return left;
    }

    private Result evaluateMultiplyDivide(List<String> tokens, int startIndex) {
        Result left = evaluateUnary(tokens, startIndex);
        int index = left.nextIndex;

        while (index < tokens.size()) {
            String operator = tokens.get(index);
            if (!operator.equals("*") && !operator.equals("/")) {
                break;
            }

            Result right = evaluateUnary(tokens, index + 1);

            if (operator.equals("*")) {
                left = new Result(left.value * right.value, right.nextIndex);
            } else {
                if (right.value == 0) {
                    throw new IllegalArgumentException("Division by zero");
                }
                left = new Result(left.value / right.value, right.nextIndex);
            }

            index = left.nextIndex;
        }

        return left;
    }

    private Result evaluateUnary(List<String> tokens, int startIndex) {
        if (startIndex >= tokens.size()) {
            throw new IllegalArgumentException("Unexpected end of expression");
        }

        String token = tokens.get(startIndex);

        // Handle unary minus
        if (token.equals("-")) {
            Result result = evaluateUnary(tokens, startIndex + 1);
            return new Result(-result.value, result.nextIndex);
        }

        // Handle unary plus
        if (token.equals("+")) {
            return evaluateUnary(tokens, startIndex + 1);
        }

        return evaluateFactor(tokens, startIndex);
    }

    private Result evaluateFactor(List<String> tokens, int startIndex) {
        if (startIndex >= tokens.size()) {
            throw new IllegalArgumentException("Unexpected end of expression");
        }

        String token = tokens.get(startIndex);

        // Handle parentheses
        if (token.equals("(")) {
            Result result = evaluateExpression(tokens, startIndex + 1);
            int closeParenIndex = result.nextIndex;

            if (closeParenIndex >= tokens.size() || !tokens.get(closeParenIndex).equals(")")) {
                throw new IllegalArgumentException("Missing closing parenthesis");
            }

            return new Result(result.value, closeParenIndex + 1);
        }

        // Handle numbers
        if (NUMBER_PATTERN.matcher(token).matches()) {
            try {
                double value = Double.parseDouble(token);
                return new Result(value, startIndex + 1);
            } catch (NumberFormatException e) {
                throw new IllegalArgumentException("Invalid number: " + token);
            }
        }

        throw new IllegalArgumentException("Unexpected token: " + token);
    }

    private static class Result {
        final double value;
        final int nextIndex;

        Result(double value, int nextIndex) {
            this.value = value;
            this.nextIndex = nextIndex;
        }
    }
}
```

**Additional test cases:**
```java
public class ExpressionEvaluatorTest {
    public static void main(String[] args) {
        ExpressionEvaluator evaluator = new ExpressionEvaluator();

        // Test basic operations
        testExpression(evaluator, "2 + 3", 5.0);
        testExpression(evaluator, "10 - 4", 6.0);
        testExpression(evaluator, "3 * 4", 12.0);
        testExpression(evaluator, "15 / 3", 5.0);

        // Test operator precedence
        testExpression(evaluator, "2 + 3 * 4", 14.0);
        testExpression(evaluator, "2 * 3 + 4", 10.0);
        testExpression(evaluator, "10 - 4 / 2", 8.0);

        // Test parentheses
        testExpression(evaluator, "(2 + 3) * 4", 20.0);
        testExpression(evaluator, "2 * (3 + 4)", 14.0);
        testExpression(evaluator, "(10 - 4) / 2", 3.0);

        // Test complex expressions
        testExpression(evaluator, "2 + 3 * (4 - 1)", 11.0);
        testExpression(evaluator, "(2 + 3) * (4 - 1)", 15.0);
        testExpression(evaluator, "10 / (2 + 3) - 1", 1.0);

        // Test negative numbers
        testExpression(evaluator, "-5 + 3", -2.0);
        testExpression(evaluator, "(-5) + 3", -2.0);
        testExpression(evaluator, "2 * -3", -6.0);

        // Test decimals
        testExpression(evaluator, "3.5 + 2.5", 6.0);
        testExpression(evaluator, "10.5 / 2.5", 4.2);

        System.out.println("All tests completed!");
    }

    private static void testExpression(ExpressionEvaluator evaluator, String expression, double expected) {
        try {
            double result = evaluator.evaluate(expression);
            if (Math.abs(result - expected) < 1e-10) {
                System.out.println("✓ " + expression + " = " + result);
            } else {
                System.out.println("✗ " + expression + " = " + result + " (expected " + expected + ")");
            }
        } catch (Exception e) {
            System.out.println("✗ " + expression + " threw exception: " + e.getMessage());
        }
    }
}
```

**Explanation:**
- **Recursive Descent Parser**: Implements operator precedence using recursive method calls
- **Proper Precedence**: Multiplication and division evaluated before addition and subtraction
- **Parentheses Support**: Handles nested parentheses correctly
- **Error Handling**: Comprehensive error checking for invalid expressions
- **Unary Operators**: Supports unary plus and minus
- **Token-based Parsing**: Breaks expression into tokens for easier processing
- **Test Suite**: Comprehensive tests to verify correctness

</details>

[↑ Back to Top](#-table-of-contents)

---

## 7. Control Flow Statements

📊 **Chapter 7 of 35**

🎯 **Learning Objectives:**
- Master conditional statements: if, else-if, switch
- Learn about loop constructs: for, while, do-while, enhanced for
- Understand break, continue, and return statements
- Practice nested control structures and loop control

⏱️ **Estimated Reading Time:** 30 minutes
📋 **Prerequisites:** Understanding of Java operators and expressions

### Conditional Statements

#### if, else-if, and else Statements

```java
public class ConditionalStatements {
    public static void main(String[] args) {
        demonstrateBasicIf();
        demonstrateIfElse();
        demonstrateIfElseIf();
        demonstrateNestedIf();
        demonstratePracticalExamples();
    }

    private static void demonstrateBasicIf() {
        System.out.println("=== Basic if Statement ===");

        int temperature = 25;

        // Simple if statement
        if (temperature > 30) {
            System.out.println("It's hot outside!");
        }

        if (temperature > 20) {
            System.out.println("It's warm outside!");
        }

        if (temperature < 10) {
            System.out.println("It's cold outside!");
        }

        // Multiple statements in if block
        int score = 95;
        if (score >= 90) {
            System.out.println("Excellent score!");
            System.out.println("You got an A grade.");
            System.out.println("Congratulations!");
        }

        // Single statement without braces (not recommended)
        if (score > 80)
            System.out.println("Good job!");  // Only this line is in the if
        System.out.println("This line always executes");
    }

    private static void demonstrateIfElse() {
        System.out.println("\n=== if-else Statement ===");

        int age = 17;

        if (age >= 18) {
            System.out.println("You are an adult.");
            System.out.println("You can vote.");
        } else {
            System.out.println("You are a minor.");
            System.out.println("You cannot vote yet.");
        }

        // Ternary operator equivalent
        String status = (age >= 18) ? "Adult" : "Minor";
        System.out.println("Status using ternary: " + status);

        // Boolean conditions
        boolean hasLicense = true;
        boolean hasInsurance = false;

        if (hasLicense && hasInsurance) {
            System.out.println("You can drive legally.");
        } else {
            System.out.println("You cannot drive legally.");
            if (!hasLicense) {
                System.out.println("  - You need a license.");
            }
            if (!hasInsurance) {
                System.out.println("  - You need insurance.");
            }
        }
    }

    private static void demonstrateIfElseIf() {
        System.out.println("\n=== if-else-if Chain ===");

        int score = 85;
        char grade;
        String description;

        if (score >= 90) {
            grade = 'A';
            description = "Excellent";
        } else if (score >= 80) {
            grade = 'B';
            description = "Good";
        } else if (score >= 70) {
            grade = 'C';
            description = "Average";
        } else if (score >= 60) {
            grade = 'D';
            description = "Below Average";
        } else {
            grade = 'F';
            description = "Failing";
        }

        System.out.println("Score: " + score);
        System.out.println("Grade: " + grade + " (" + description + ")");

        // Weather classification
        int temperature = 22;
        String weather;

        if (temperature > 35) {
            weather = "Extremely Hot";
        } else if (temperature > 25) {
            weather = "Hot";
        } else if (temperature > 15) {
            weather = "Mild";
        } else if (temperature > 5) {
            weather = "Cool";
        } else {
            weather = "Cold";
        }

        System.out.println("Temperature: " + temperature + "°C - " + weather);
    }

    private static void demonstrateNestedIf() {
        System.out.println("\n=== Nested if Statements ===");

        boolean isWeekend = true;
        boolean isSunny = true;
        boolean hasTime = false;

        if (isWeekend) {
            System.out.println("It's the weekend!");

            if (isSunny) {
                System.out.println("The weather is nice!");

                if (hasTime) {
                    System.out.println("Perfect day for outdoor activities!");
                } else {
                    System.out.println("Unfortunately, no time for outdoor fun.");
                }
            } else {
                System.out.println("It's cloudy, maybe a good day to stay indoors.");
            }
        } else {
            System.out.println("It's a weekday - time to work!");
        }
    }

    private static void demonstratePracticalExamples() {
        System.out.println("\n=== Practical Examples ===");

        // User authentication simulation
        String username = "admin";
        String password = "secret123";
        boolean isLoggedIn = false;

        if (username.equals("admin") && password.equals("secret123")) {
            isLoggedIn = true;
            System.out.println("Login successful! Welcome, " + username);
        } else {
            System.out.println("Login failed! Invalid credentials.");
        }

        // Input validation
        int userAge = 25;
        if (userAge >= 0 && userAge <= 150) {
            if (userAge < 13) {
                System.out.println("Child");
            } else if (userAge < 20) {
                System.out.println("Teenager");
            } else if (userAge < 60) {
                System.out.println("Adult");
            } else {
                System.out.println("Senior");
            }
        } else {
            System.out.println("Invalid age: " + userAge);
        }
    }
}
```

### Switch Statements

#### Traditional Switch Statement

```java
public class SwitchStatements {
    public static void main(String[] args) {
        demonstrateBasicSwitch();
        demonstrateSwitchWithBreak();
        demonstrateSwitchFallthrough();
        demonstrateSwitchExpressions();
    }

    private static void demonstrateBasicSwitch() {
        System.out.println("=== Basic Switch Statement ===");

        int dayOfWeek = 3;
        String dayName;

        switch (dayOfWeek) {
            case 1:
                dayName = "Monday";
                break;
            case 2:
                dayName = "Tuesday";
                break;
            case 3:
                dayName = "Wednesday";
                break;
            case 4:
                dayName = "Thursday";
                break;
            case 5:
                dayName = "Friday";
                break;
            case 6:
                dayName = "Saturday";
                break;
            case 7:
                dayName = "Sunday";
                break;
            default:
                dayName = "Invalid day";
                break;
        }

        System.out.println("Day " + dayOfWeek + " is " + dayName);

        // Switch with char
        char grade = 'B';
        switch (grade) {
            case 'A':
                System.out.println("Excellent!");
                break;
            case 'B':
                System.out.println("Good job!");
                break;
            case 'C':
                System.out.println("Average");
                break;
            case 'D':
                System.out.println("Below average");
                break;
            case 'F':
                System.out.println("Failed");
                break;
            default:
                System.out.println("Invalid grade");
        }
    }

    private static void demonstrateSwitchWithBreak() {
        System.out.println("\n=== Switch with Break Statements ===");

        String month = "March";
        int days;

        switch (month) {
            case "January":
            case "March":
            case "May":
            case "July":
            case "August":
            case "October":
            case "December":
                days = 31;
                break;
            case "April":
            case "June":
            case "September":
            case "November":
                days = 30;
                break;
            case "February":
                days = 28; // Not considering leap years
                break;
            default:
                days = -1;
                System.out.println("Invalid month: " + month);
        }

        if (days > 0) {
            System.out.println(month + " has " + days + " days");
        }
    }

    private static void demonstrateSwitchFallthrough() {
        System.out.println("\n=== Switch Fall-through Behavior ===");

        int number = 2;
        System.out.println("Number: " + number);
        System.out.print("Output: ");

        switch (number) {
            case 1:
                System.out.print("One ");
                // Fall through - no break
            case 2:
                System.out.print("Two ");
                // Fall through - no break
            case 3:
                System.out.print("Three ");
                // Fall through - no break
            case 4:
                System.out.print("Four ");
                break; // Stops here
            case 5:
                System.out.print("Five ");
                break;
            default:
                System.out.print("Other ");
        }
        System.out.println();

        // Intentional fall-through for grouping
        String season = "Summer";
        switch (season) {
            case "December":
            case "January":
            case "February":
                System.out.println(season + " is in Winter");
                break;
            case "March":
            case "April":
            case "May":
                System.out.println(season + " is in Spring");
                break;
            case "June":
            case "July":
            case "August":
                System.out.println(season + " is in Summer");
                break;
            case "September":
            case "October":
            case "November":
                System.out.println(season + " is in Fall");
                break;
            default:
                System.out.println("Invalid season");
        }
    }

    private static void demonstrateSwitchExpressions() {
        System.out.println("\n=== Modern Switch Expressions (Java 14+) ===");

        int dayNumber = 5;

        // Switch expression (returns value)
        String dayType = switch (dayNumber) {
            case 1, 2, 3, 4, 5 -> "Weekday";
            case 6, 7 -> "Weekend";
            default -> "Invalid day";
        };

        System.out.println("Day " + dayNumber + " is a " + dayType);

        // Switch expression with yield
        String grade = "B";
        String performance = switch (grade) {
            case "A" -> {
                System.out.println("Calculating bonus for A grade...");
                yield "Outstanding";
            }
            case "B" -> {
                System.out.println("Calculating bonus for B grade...");
                yield "Good";
            }
            case "C" -> "Average";
            case "D" -> "Below Average";
            case "F" -> "Poor";
            default -> {
                System.out.println("Unknown grade: " + grade);
                yield "Invalid";
            }
        };

        System.out.println("Performance: " + performance);

        // Pattern matching with switch (Java 21+)
        Object obj = "Hello World";
        String result = switch (obj) {
            case String s when s.length() > 5 -> "Long string: " + s;
            case String s -> "Short string: " + s;
            case Integer i -> "Integer: " + i;
            case null -> "Null value";
            default -> "Unknown type: " + obj.getClass().getSimpleName();
        };

        System.out.println("Pattern matching result: " + result);
    }
}
```

### Loop Statements

#### For Loops

```java
public class ForLoops {
    public static void main(String[] args) {
        demonstrateBasicFor();
        demonstrateEnhancedFor();
        demonstrateNestedFor();
        demonstrateForVariants();
    }

    private static void demonstrateBasicFor() {
        System.out.println("=== Basic For Loop ===");

        // Standard for loop
        System.out.print("Counting up: ");
        for (int i = 1; i <= 5; i++) {
            System.out.print(i + " ");
        }
        System.out.println();

        // Counting down
        System.out.print("Counting down: ");
        for (int i = 5; i >= 1; i--) {
            System.out.print(i + " ");
        }
        System.out.println();

        // Step by 2
        System.out.print("Even numbers: ");
        for (int i = 2; i <= 10; i += 2) {
            System.out.print(i + " ");
        }
        System.out.println();

        // Multiple variables
        System.out.print("Multiple variables: ");
        for (int i = 0, j = 10; i < 5; i++, j--) {
            System.out.print("(" + i + "," + j + ") ");
        }
        System.out.println();
    }

    private static void demonstrateEnhancedFor() {
        System.out.println("\n=== Enhanced For Loop (for-each) ===");

        // Array iteration
        int[] numbers = {10, 20, 30, 40, 50};
        System.out.print("Array elements: ");
        for (int number : numbers) {
            System.out.print(number + " ");
        }
        System.out.println();

        // String array
        String[] fruits = {"apple", "banana", "orange", "grape"};
        System.out.println("Fruits:");
        for (String fruit : fruits) {
            System.out.println("- " + fruit);
        }

        // Collection iteration
        java.util.List<String> cities = java.util.Arrays.asList("New York", "London", "Tokyo");
        System.out.println("Cities:");
        for (String city : cities) {
            System.out.println("- " + city);
        }

        // 2D array iteration
        int[][] matrix = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
        System.out.println("Matrix:");
        for (int[] row : matrix) {
            for (int element : row) {
                System.out.print(element + " ");
            }
            System.out.println();
        }
    }

    private static void demonstrateNestedFor() {
        System.out.println("\n=== Nested For Loops ===");

        // Multiplication table
        System.out.println("Multiplication table (5x5):");
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= 5; j++) {
                System.out.printf("%2d ", i * j);
            }
            System.out.println();
        }

        // Pattern printing
        System.out.println("\nTriangle pattern:");
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }

        // Number pyramid
        System.out.println("\nNumber pyramid:");
        for (int i = 1; i <= 5; i++) {
            // Print spaces
            for (int j = 1; j <= 5 - i; j++) {
                System.out.print(" ");
            }
            // Print numbers
            for (int j = 1; j <= i; j++) {
                System.out.print(j + " ");
            }
            System.out.println();
        }
    }

    private static void demonstrateForVariants() {
        System.out.println("\n=== For Loop Variants ===");

        // Infinite loop (careful!)
        System.out.println("Controlled infinite loop:");
        int counter = 0;
        for (;;) {
            System.out.println("Iteration: " + counter);
            counter++;
            if (counter >= 3) break;
        }

        // Empty body
        System.out.print("Finding first space in string: ");
        String text = "Hello World";
        int index;
        for (index = 0; index < text.length() && text.charAt(index) != ' '; index++) {
            // Empty body - all work done in condition
        }
        System.out.println("Found at index " + index);

        // Complex condition
        System.out.println("Complex condition example:");
        int[] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        int sum = 0;
        for (int i = 0; i < arr.length && sum < 20; i++) {
            sum += arr[i];
            System.out.println("Added " + arr[i] + ", sum = " + sum);
        }
    }
}
```

## 8. Classes & Objects

📊 **Chapter 8 of 35**

🎯 **Learning Objectives:**
- Understand the fundamental concepts of classes and objects
- Learn to define classes with fields, methods, and constructors
- Master object creation and initialization
- Explore instance vs static members
- Practice encapsulation with access modifiers

⏱️ **Estimated Reading Time:** 45 minutes
📋 **Prerequisites:** Understanding of Java syntax and control flow

### What are Classes and Objects?

Classes are blueprints or templates that define the structure and behavior of objects. Objects are instances of classes that contain actual data and can perform actions defined by their class.

```java
// Class definition
public class Car {
    // Fields (attributes/properties)
    private String brand;
    private String model;
    private int year;
    private double price;
    private boolean isRunning;

    // Constructor
    public Car(String brand, String model, int year, double price) {
        this.brand = brand;
        this.model = model;
        this.year = year;
        this.price = price;
        this.isRunning = false;
    }

    // Methods (behaviors)
    public void startEngine() {
        if (!isRunning) {
            isRunning = true;
            System.out.println(brand + " " + model + " engine started!");
        } else {
            System.out.println("Engine is already running.");
        }
    }

    public void stopEngine() {
        if (isRunning) {
            isRunning = false;
            System.out.println(brand + " " + model + " engine stopped.");
        } else {
            System.out.println("Engine is already off.");
        }
    }

    public void displayInfo() {
        System.out.println("=== Car Information ===");
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
        System.out.println("Price: $" + String.format("%.2f", price));
        System.out.println("Running: " + (isRunning ? "Yes" : "No"));
    }

    // Getter methods
    public String getBrand() { return brand; }
    public String getModel() { return model; }
    public int getYear() { return year; }
    public double getPrice() { return price; }
    public boolean isRunning() { return isRunning; }

    // Setter methods
    public void setPrice(double price) {
        if (price >= 0) {
            this.price = price;
        } else {
            System.out.println("Price cannot be negative!");
        }
    }
}
```

### Creating and Using Objects

```java
public class CarDemo {
    public static void main(String[] args) {
        // Creating objects (instances of Car class)
        Car car1 = new Car("Toyota", "Camry", 2022, 25000.0);
        Car car2 = new Car("Honda", "Civic", 2023, 23000.0);
        Car car3 = new Car("BMW", "X5", 2024, 65000.0);

        System.out.println("=== Working with Car Objects ===\n");

        // Using object methods
        car1.displayInfo();
        System.out.println();

        car1.startEngine();
        car1.startEngine(); // Try to start again
        car1.stopEngine();
        System.out.println();

        // Working with multiple objects
        Car[] cars = {car1, car2, car3};
        double totalValue = 0;

        System.out.println("=== Car Inventory ===");
        for (Car car : cars) {
            System.out.println(car.getBrand() + " " + car.getModel() + 
                             " (" + car.getYear() + ") - $" + 
                             String.format("%.2f", car.getPrice()));
            totalValue += car.getPrice();
        }
        System.out.println("Total Inventory Value: $" + String.format("%.2f", totalValue));

        // Modifying object state
        System.out.println("\n=== Price Updates ===");
        car2.setPrice(22000.0);
        System.out.println(car2.getBrand() + " " + car2.getModel() + 
                          " new price: $" + String.format("%.2f", car2.getPrice()));
    }
}
```

### Constructors

Constructors are special methods used to initialize objects when they are created.

```java
public class Student {
    private String name;
    private int age;
    private String studentId;
    private double gpa;
    private String major;

    // Default constructor
    public Student() {
        this.name = "Unknown";
        this.age = 18;
        this.studentId = generateStudentId();
        this.gpa = 0.0;
        this.major = "Undeclared";
    }

    // Parameterized constructor
    public Student(String name, int age, String major) {
        this.name = name;
        this.age = age;
        this.major = major;
        this.studentId = generateStudentId();
        this.gpa = 0.0;
    }

    // Full constructor
    public Student(String name, int age, String studentId, double gpa, String major) {
        this.name = name;
        this.age = age;
        this.studentId = studentId;
        this.gpa = gpa;
        this.major = major;
    }

    // Copy constructor
    public Student(Student other) {
        this.name = other.name;
        this.age = other.age;
        this.studentId = generateStudentId(); // Generate new ID
        this.gpa = other.gpa;
        this.major = other.major;
    }

    private String generateStudentId() {
        return "STU" + System.currentTimeMillis() % 100000;
    }

    public void study(String subject) {
        System.out.println(name + " is studying " + subject);
    }

    public void takeExam(String course, double score) {
        System.out.println(name + " took " + course + " exam and scored " + score);
        updateGPA(score);
    }

    private void updateGPA(double newScore) {
        // Simplified GPA calculation
        gpa = (gpa + (newScore / 25.0)) / 2.0; // Rough conversion and averaging
        if (gpa > 4.0) gpa = 4.0;
        if (gpa < 0.0) gpa = 0.0;
    }

    public void displayStudentInfo() {
        System.out.println("=== Student Information ===");
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Student ID: " + studentId);
        System.out.println("GPA: " + String.format("%.2f", gpa));
        System.out.println("Major: " + major);
    }

    // Getters and setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    
    public int getAge() { return age; }
    public void setAge(int age) { 
        if (age >= 16 && age <= 100) {
            this.age = age; 
        }
    }
    
    public String getStudentId() { return studentId; }
    public double getGpa() { return gpa; }
    public String getMajor() { return major; }
    public void setMajor(String major) { this.major = major; }
}

// Demonstration class
public class StudentDemo {
    public static void main(String[] args) {
        System.out.println("=== Constructor Examples ===\n");

        // Using different constructors
        Student student1 = new Student(); // Default constructor
        student1.displayStudentInfo();
        System.out.println();

        Student student2 = new Student("Alice Johnson", 20, "Computer Science");
        student2.displayStudentInfo();
        System.out.println();

        Student student3 = new Student("Bob Smith", 22, "STU12345", 3.5, "Mathematics");
        student3.displayStudentInfo();
        System.out.println();

        Student student4 = new Student(student2); // Copy constructor
        student4.setName("Alice Copy");
        student4.displayStudentInfo();
        System.out.println();

        // Using object methods
        System.out.println("=== Student Activities ===");
        student2.study("Data Structures");
        student2.takeExam("Programming 101", 85.0);
        student2.takeExam("Mathematics", 92.0);
        System.out.println();
        student2.displayStudentInfo();
    }
}
```

### Static vs Instance Members

```java
public class BankAccount {
    // Static members (belong to the class)
    private static int totalAccounts = 0;
    private static double totalBalance = 0.0;
    private static final double INTEREST_RATE = 0.03;
    
    // Instance members (belong to individual objects)
    private String accountNumber;
    private String accountHolder;
    private double balance;
    private String accountType;

    public BankAccount(String accountHolder, String accountType, double initialBalance) {
        this.accountNumber = generateAccountNumber();
        this.accountHolder = accountHolder;
        this.accountType = accountType;
        this.balance = initialBalance;
        
        // Update static variables
        totalAccounts++;
        totalBalance += initialBalance;
    }

    // Static method
    public static String generateAccountNumber() {
        return "ACC" + (totalAccounts + 1) + System.currentTimeMillis() % 10000;
    }

    // Static methods
    public static int getTotalAccounts() {
        return totalAccounts;
    }

    public static double getTotalBalance() {
        return totalBalance;
    }

    public static double getInterestRate() {
        return INTEREST_RATE;
    }

    public static void displayBankStatistics() {
        System.out.println("=== Bank Statistics ===");
        System.out.println("Total Accounts: " + totalAccounts);
        System.out.println("Total Balance: $" + String.format("%.2f", totalBalance));
        System.out.println("Interest Rate: " + (INTEREST_RATE * 100) + "%");
    }

    // Instance methods
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            totalBalance += amount;
            System.out.println("Deposited $" + String.format("%.2f", amount) + 
                             " to account " + accountNumber);
            System.out.println("New balance: $" + String.format("%.2f", balance));
        } else {
            System.out.println("Deposit amount must be positive!");
        }
    }

    public boolean withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            totalBalance -= amount;
            System.out.println("Withdrew $" + String.format("%.2f", amount) + 
                             " from account " + accountNumber);
            System.out.println("New balance: $" + String.format("%.2f", balance));
            return true;
        } else {
            System.out.println("Invalid withdrawal amount or insufficient funds!");
            return false;
        }
    }

    public void addInterest() {
        double interest = balance * INTEREST_RATE;
        deposit(interest);
        System.out.println("Interest added: $" + String.format("%.2f", interest));
    }

    public void displayAccountInfo() {
        System.out.println("=== Account Information ===");
        System.out.println("Account Number: " + accountNumber);
        System.out.println("Account Holder: " + accountHolder);
        System.out.println("Account Type: " + accountType);
        System.out.println("Balance: $" + String.format("%.2f", balance));
    }

    // Getters
    public String getAccountNumber() { return accountNumber; }
    public String getAccountHolder() { return accountHolder; }
    public double getBalance() { return balance; }
    public String getAccountType() { return accountType; }
}

// Demonstration class
public class BankDemo {
    public static void main(String[] args) {
        System.out.println("=== Static vs Instance Members Demo ===\n");

        // Display initial bank statistics
        BankAccount.displayBankStatistics();
        System.out.println();

        // Create bank accounts
        BankAccount account1 = new BankAccount("John Doe", "Checking", 1000.0);
        BankAccount account2 = new BankAccount("Jane Smith", "Savings", 2500.0);
        BankAccount account3 = new BankAccount("Bob Johnson", "Checking", 500.0);

        System.out.println("After creating accounts:");
        BankAccount.displayBankStatistics();
        System.out.println();

        // Perform transactions
        System.out.println("=== Transactions ===");
        account1.deposit(200.0);
        account1.withdraw(150.0);
        System.out.println();

        account2.addInterest();
        System.out.println();

        account3.withdraw(600.0); // This should fail
        account3.deposit(100.0);
        System.out.println();

        // Display individual account info
        account1.displayAccountInfo();
        System.out.println();
        account2.displayAccountInfo();
        System.out.println();
        account3.displayAccountInfo();
        System.out.println();

        // Final bank statistics
        System.out.println("Final bank statistics:");
        BankAccount.displayBankStatistics();

        // Accessing static method without object
        System.out.println("\nCurrent interest rate: " + 
                          (BankAccount.getInterestRate() * 100) + "%");
    }
}
```

### Method Overloading

Method overloading allows multiple methods with the same name but different parameters.

```java
public class Calculator {
    // Method overloading with different parameter types
    public int add(int a, int b) {
        System.out.println("Adding two integers: " + a + " + " + b);
        return a + b;
    }

    public double add(double a, double b) {
        System.out.println("Adding two doubles: " + a + " + " + b);
        return a + b;
    }

    public String add(String a, String b) {
        System.out.println("Concatenating two strings: \"" + a + "\" + \"" + b + "\"");
        return a + b;
    }

    // Method overloading with different number of parameters
    public int add(int a, int b, int c) {
        System.out.println("Adding three integers: " + a + " + " + b + " + " + c);
        return a + b + c;
    }

    public double add(double a, double b, double c, double d) {
        System.out.println("Adding four doubles");
        return a + b + c + d;
    }

    // Variable arguments (varargs)
    public int add(int... numbers) {
        System.out.print("Adding variable number of integers: ");
        int sum = 0;
        for (int num : numbers) {
            System.out.print(num + " ");
            sum += num;
        }
        System.out.println("= " + sum);
        return sum;
    }

    public double multiply(double a, double b) {
        return a * b;
    }

    public double multiply(double a, double b, double c) {
        return a * b * c;
    }

    // Method with different parameter order (not recommended)
    public void printDetails(String name, int age) {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public void printDetails(int age, String name) {
        System.out.println("Age: " + age + ", Name: " + name);
    }

    public static void main(String[] args) {
        Calculator calc = new Calculator();

        System.out.println("=== Method Overloading Demo ===\n");

        // Different parameter types
        System.out.println("Result: " + calc.add(5, 3));
        System.out.println("Result: " + calc.add(5.5, 3.2));
        System.out.println("Result: " + calc.add("Hello", "World"));
        System.out.println();

        // Different number of parameters
        System.out.println("Result: " + calc.add(1, 2, 3));
        System.out.println("Result: " + calc.add(1.1, 2.2, 3.3, 4.4));
        System.out.println();

        // Variable arguments
        System.out.println("Result: " + calc.add(1, 2, 3, 4, 5));
        System.out.println("Result: " + calc.add(10, 20));
        System.out.println();

        // Method overloading with different parameter order
        calc.printDetails("Alice", 25);
        calc.printDetails(30, "Bob");
    }
}
```

### Object Relationships and Composition

```java
// Composition example
class Address {
    private String street;
    private String city;
    private String state;
    private String zipCode;
    private String country;

    public Address(String street, String city, String state, String zipCode, String country) {
        this.street = street;
        this.city = city;
        this.state = state;
        this.zipCode = zipCode;
        this.country = country;
    }

    public void displayAddress() {
        System.out.println(street);
        System.out.println(city + ", " + state + " " + zipCode);
        System.out.println(country);
    }

    // Getters and setters
    public String getStreet() { return street; }
    public void setStreet(String street) { this.street = street; }
    public String getCity() { return city; }
    public void setCity(String city) { this.city = city; }
    public String getState() { return state; }
    public void setState(String state) { this.state = state; }
    public String getZipCode() { return zipCode; }
    public void setZipCode(String zipCode) { this.zipCode = zipCode; }
    public String getCountry() { return country; }
    public void setCountry(String country) { this.country = country; }

    @Override
    public String toString() {
        return street + ", " + city + ", " + state + " " + zipCode + ", " + country;
    }
}

class Person {
    private String name;
    private int age;
    private String email;
    private Address address; // Composition - Person HAS an Address

    public Person(String name, int age, String email, Address address) {
        this.name = name;
        this.age = age;
        this.email = email;
        this.address = address;
    }

    public void displayPersonInfo() {
        System.out.println("=== Person Information ===");
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Email: " + email);
        System.out.println("Address:");
        address.displayAddress();
    }

    public void relocate(Address newAddress) {
        System.out.println(name + " is moving from:");
        address.displayAddress();
        System.out.println("To:");
        this.address = newAddress;
        newAddress.displayAddress();
    }

    // Getters and setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
    public String getEmail() { return email; }
    public void setEmail(String email) { this.email = email; }
    public Address getAddress() { return address; }
    public void setAddress(Address address) { this.address = address; }
}

public class CompositionDemo {
    public static void main(String[] args) {
        System.out.println("=== Object Composition Demo ===\n");

        // Create address objects
        Address homeAddress = new Address(
            "123 Main Street",
            "Springfield",
            "IL",
            "62701",
            "USA"
        );

        Address workAddress = new Address(
            "456 Business Ave",
            "Springfield",
            "IL",
            "62702",
            "USA"
        );

        // Create person with address
        Person person = new Person("John Doe", 30, "john.doe@email.com", homeAddress);
        person.displayPersonInfo();
        System.out.println();

        // Relocate person
        person.relocate(workAddress);
        System.out.println();

        // Show updated info
        person.displayPersonInfo();
    }
}
```

### ⚠️ Common Pitfalls

1. **Forgetting to initialize objects**: Always use `new` keyword to create objects
2. **Null pointer exceptions**: Check for null before calling methods
3. **Static context confusion**: Cannot access instance members from static methods
4. **Constructor chaining**: Be careful with constructor calls and initialization order

### ✅ Best Practices

1. **Use meaningful class and variable names**
2. **Keep classes focused on a single responsibility**
3. **Encapsulate data with private fields and public methods**
4. **Provide constructors for proper object initialization**
5. **Override toString() method for better object representation**
6. **Use static members judiciously - only when they truly belong to the class**

### 🏋️ Exercise 8: Library Management System

Create a comprehensive library management system with the following classes:

```java
// Book class
public class Book {
    private String isbn;
    private String title;
    private String author;
    private String category;
    private boolean isAvailable;
    private int publicationYear;

    // Implement constructors, getters, setters, and methods
    // checkOut(), returnBook(), displayInfo()
}

// Library class  
public class Library {
    private String libraryName;
    private List<Book> books;
    private static int totalLibraries = 0;

    // Implement methods:
    // addBook(), removeBook(), searchByTitle(), searchByAuthor()
    // displayAvailableBooks(), displayLibraryStats()
}

// LibraryMember class
public class LibraryMember {
    private String memberId;
    private String name;
    private String email;
    private List<Book> borrowedBooks;
    private int borrowLimit;

    // Implement methods:
    // borrowBook(), returnBook(), displayBorrowedBooks()
}
```

[↑ Back to Top](#-table-of-contents)

---

## 9. Inheritance & Polymorphism

📊 **Chapter 9 of 35**

🎯 **Learning Objectives:**
- Master inheritance concepts and class hierarchies
- Understand method overriding and the @Override annotation
- Learn about polymorphism and dynamic method dispatch
- Explore the Object class and its methods
- Practice abstract classes and method implementations

⏱️ **Estimated Reading Time:** 50 minutes
📋 **Prerequisites:** Understanding of classes and objects

### Understanding Inheritance

Inheritance is a mechanism that allows a class to inherit properties and methods from another class. The class that inherits is called a subclass or child class, and the class being inherited from is called a superclass or parent class.

```java
// Base class (superclass)
class Animal {
    protected String name;
    protected int age;
    protected String species;

    public Animal(String name, int age, String species) {
        this.name = name;
        this.age = age;
        this.species = species;
        System.out.println("Animal constructor called for " + name);
    }

    public void eat() {
        System.out.println(name + " is eating.");
    }

    public void sleep() {
        System.out.println(name + " is sleeping.");
    }

    public void makeSound() {
        System.out.println(name + " makes a generic animal sound.");
    }

    public void displayInfo() {
        System.out.println("=== Animal Information ===");
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Species: " + species);
    }

    // Getters and setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
    public String getSpecies() { return species; }
    public void setSpecies(String species) { this.species = species; }
}

// Derived class (subclass)
class Dog extends Animal {
    private String breed;
    private boolean isGoodBoy;

    public Dog(String name, int age, String breed) {
        super(name, age, "Canine"); // Call parent constructor
        this.breed = breed;
        this.isGoodBoy = true;
        System.out.println("Dog constructor called for " + name);
    }

    // Method overriding
    @Override
    public void makeSound() {
        System.out.println(name + " barks: Woof! Woof!");
    }

    @Override
    public void eat() {
        System.out.println(name + " is eating dog food with enthusiasm!");
    }

    // Additional methods specific to Dog
    public void fetch() {
        System.out.println(name + " is fetching the ball!");
    }

    public void wagTail() {
        System.out.println(name + " is wagging tail happily!");
    }

    @Override
    public void displayInfo() {
        super.displayInfo(); // Call parent method
        System.out.println("Breed: " + breed);
        System.out.println("Good boy: " + (isGoodBoy ? "Yes" : "No"));
    }

    // Getters and setters
    public String getBreed() { return breed; }
    public void setBreed(String breed) { this.breed = breed; }
    public boolean isGoodBoy() { return isGoodBoy; }
    public void setGoodBoy(boolean goodBoy) { isGoodBoy = goodBoy; }
}

class Cat extends Animal {
    private boolean isIndoor;
    private int livesRemaining;

    public Cat(String name, int age, boolean isIndoor) {
        super(name, age, "Feline");
        this.isIndoor = isIndoor;
        this.livesRemaining = 9;
        System.out.println("Cat constructor called for " + name);
    }

    @Override
    public void makeSound() {
        System.out.println(name + " meows: Meow! Purr!");
    }

    @Override
    public void sleep() {
        System.out.println(name + " is sleeping 16 hours a day like a proper cat.");
    }

    public void climb() {
        System.out.println(name + " is climbing to high places!");
    }

    public void scratch() {
        System.out.println(name + " is scratching the furniture!");
    }

    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Indoor cat: " + (isIndoor ? "Yes" : "No"));
        System.out.println("Lives remaining: " + livesRemaining);
    }

    public boolean isIndoor() { return isIndoor; }
    public void setIndoor(boolean indoor) { isIndoor = indoor; }
    public int getLivesRemaining() { return livesRemaining; }
    public void setLivesRemaining(int livesRemaining) { this.livesRemaining = livesRemaining; }
}

class Bird extends Animal {
    private boolean canFly;
    private double wingspan;

    public Bird(String name, int age, boolean canFly, double wingspan) {
        super(name, age, "Avian");
        this.canFly = canFly;
        this.wingspan = wingspan;
        System.out.println("Bird constructor called for " + name);
    }

    @Override
    public void makeSound() {
        System.out.println(name + " chirps: Tweet! Tweet!");
    }

    public void fly() {
        if (canFly) {
            System.out.println(name + " is soaring through the sky!");
        } else {
            System.out.println(name + " cannot fly but is trying to flap wings!");
        }
    }

    public void buildNest() {
        System.out.println(name + " is building a cozy nest.");
    }

    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Can fly: " + (canFly ? "Yes" : "No"));
        System.out.println("Wingspan: " + wingspan + " inches");
    }

    public boolean isCanFly() { return canFly; }
    public void setCanFly(boolean canFly) { this.canFly = canFly; }
    public double getWingspan() { return wingspan; }
    public void setWingspan(double wingspan) { this.wingspan = wingspan; }
}
```

### Polymorphism in Action

Polymorphism allows objects of different classes to be treated as objects of a common base class while still maintaining their specific behaviors.

```java
public class PolymorphismDemo {
    public static void main(String[] args) {
        System.out.println("=== Inheritance and Polymorphism Demo ===\n");

        // Create different animals
        Animal[] animals = {
            new Dog("Buddy", 3, "Golden Retriever"),
            new Cat("Whiskers", 5, true),
            new Bird("Tweety", 1, true, 8.5),
            new Dog("Rex", 7, "German Shepherd"),
            new Cat("Shadow", 2, false)
        };

        System.out.println("\n=== Polymorphic Method Calls ===");
        for (Animal animal : animals) {
            System.out.println("\n--- " + animal.getName() + " ---");
            animal.displayInfo();
            animal.makeSound();
            animal.eat();
            animal.sleep();
            
            // Demonstrate runtime type checking
            if (animal instanceof Dog) {
                Dog dog = (Dog) animal; // Downcasting
                dog.fetch();
                dog.wagTail();
            } else if (animal instanceof Cat) {
                Cat cat = (Cat) animal;
                cat.climb();
                cat.scratch();
            } else if (animal instanceof Bird) {
                Bird bird = (Bird) animal;
                bird.fly();
                bird.buildNest();
            }
        }

        System.out.println("\n=== Method Overriding Examples ===");
        demonstrateMethodOverriding();
    }

    private static void demonstrateMethodOverriding() {
        Animal genericAnimal = new Animal("Generic", 1, "Unknown");
        Dog specificDog = new Dog("Max", 4, "Labrador");
        
        // Same method call, different implementations
        System.out.println("Generic animal sound:");
        genericAnimal.makeSound();
        
        System.out.println("\nSpecific dog sound:");
        specificDog.makeSound();

        // Polymorphic assignment
        Animal polymorphicAnimal = new Dog("Polymorphic Dog", 2, "Beagle");
        System.out.println("\nPolymorphic animal (actually a dog):");
        polymorphicAnimal.makeSound(); // Calls Dog's version
        
        // Cannot call Dog-specific methods without casting
        // polymorphicAnimal.fetch(); // This would cause compile error
        
        if (polymorphicAnimal instanceof Dog) {
            ((Dog) polymorphicAnimal).fetch(); // Casting required
        }
    }
}
```

### Advanced Inheritance Concepts

```java
// Multilevel inheritance example
class Vehicle {
    protected String make;
    protected String model;
    protected int year;
    protected double price;

    public Vehicle(String make, String model, int year, double price) {
        this.make = make;
        this.model = model;
        this.year = year;
        this.price = price;
        System.out.println("Vehicle constructor: " + make + " " + model);
    }

    public void start() {
        System.out.println(make + " " + model + " is starting...");
    }

    public void stop() {
        System.out.println(make + " " + model + " has stopped.");
    }

    public void displayVehicleInfo() {
        System.out.println("Make: " + make);
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
        System.out.println("Price: $" + String.format("%.2f", price));
    }

    public String getMake() { return make; }
    public String getModel() { return model; }
    public int getYear() { return year; }
    public double getPrice() { return price; }
}

class Car extends Vehicle {
    protected int doors;
    protected String fuelType;

    public Car(String make, String model, int year, double price, int doors, String fuelType) {
        super(make, model, year, price);
        this.doors = doors;
        this.fuelType = fuelType;
        System.out.println("Car constructor: " + doors + "-door " + fuelType + " car");
    }

    @Override
    public void start() {
        System.out.println("Car ignition: Turn key, engine starts with " + fuelType);
    }

    public void honk() {
        System.out.println("Car horn: Beep! Beep!");
    }

    @Override
    public void displayVehicleInfo() {
        super.displayVehicleInfo();
        System.out.println("Doors: " + doors);
        System.out.println("Fuel Type: " + fuelType);
    }

    public int getDoors() { return doors; }
    public String getFuelType() { return fuelType; }
}

class ElectricCar extends Car {
    private double batteryCapacity;
    private int range;
    private boolean isCharging;

    public ElectricCar(String make, String model, int year, double price, int doors, 
                      double batteryCapacity, int range) {
        super(make, model, year, price, doors, "Electric");
        this.batteryCapacity = batteryCapacity;
        this.range = range;
        this.isCharging = false;
        System.out.println("ElectricCar constructor: " + batteryCapacity + "kWh battery, " + range + " mile range");
    }

    @Override
    public void start() {
        System.out.println("Electric car: Silent start, ready to drive!");
    }

    public void charge() {
        if (!isCharging) {
            isCharging = true;
            System.out.println(make + " " + model + " is now charging...");
        } else {
            System.out.println(make + " " + model + " is already charging.");
        }
    }

    public void stopCharging() {
        if (isCharging) {
            isCharging = false;
            System.out.println(make + " " + model + " finished charging.");
        } else {
            System.out.println(make + " " + model + " is not charging.");
        }
    }

    @Override
    public void displayVehicleInfo() {
        super.displayVehicleInfo();
        System.out.println("Battery Capacity: " + batteryCapacity + " kWh");
        System.out.println("Range: " + range + " miles");
        System.out.println("Charging: " + (isCharging ? "Yes" : "No"));
    }

    public double getBatteryCapacity() { return batteryCapacity; }
    public int getRange() { return range; }
    public boolean isCharging() { return isCharging; }
}

public class MultilevelInheritanceDemo {
    public static void main(String[] args) {
        System.out.println("=== Multilevel Inheritance Demo ===\n");

        // Create instances at different levels
        Vehicle vehicle = new Vehicle("Generic", "Vehicle", 2023, 20000);
        Car car = new Car("Toyota", "Camry", 2024, 28000, 4, "Gasoline");
        ElectricCar eCar = new ElectricCar("Tesla", "Model 3", 2024, 45000, 4, 75.0, 300);

        System.out.println("\n=== Vehicle Operations ===");
        
        Vehicle[] vehicles = {vehicle, car, eCar};
        
        for (Vehicle v : vehicles) {
            System.out.println("\n--- " + v.getClass().getSimpleName() + ": " + v.getMake() + " " + v.getModel() + " ---");
            v.displayVehicleInfo();
            v.start();
            v.stop();
            
            // Specific operations based on type
            if (v instanceof ElectricCar) {
                ElectricCar ec = (ElectricCar) v;
                ec.charge();
                ec.honk();
                ec.stopCharging();
            } else if (v instanceof Car) {
                Car c = (Car) v;
                c.honk();
            }
        }
    }
}
```

### The Object Class and Method Overriding

Every class in Java implicitly extends the Object class. Understanding and overriding Object methods is crucial.

```java
class Product {
    private String name;
    private double price;
    private String category;
    private String id;

    public Product(String name, double price, String category, String id) {
        this.name = name;
        this.price = price;
        this.category = category;
        this.id = id;
    }

    // Override toString() - called when object is converted to string
    @Override
    public String toString() {
        return String.format("Product{id='%s', name='%s', price=%.2f, category='%s'}", 
                           id, name, price, category);
    }

    // Override equals() - defines when two objects are considered equal
    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true; // Same reference
        if (obj == null || getClass() != obj.getClass()) return false; // Null or different class
        
        Product product = (Product) obj;
        return Double.compare(product.price, price) == 0 &&
               java.util.Objects.equals(name, product.name) &&
               java.util.Objects.equals(category, product.category) &&
               java.util.Objects.equals(id, product.id);
    }

    // Override hashCode() - should always be overridden when equals() is overridden
    @Override
    public int hashCode() {
        return java.util.Objects.hash(name, price, category, id);
    }

    // Getters and setters
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public double getPrice() { return price; }
    public void setPrice(double price) { this.price = price; }
    public String getCategory() { return category; }
    public void setCategory(String category) { this.category = category; }
    public String getId() { return id; }
    public void setId(String id) { this.id = id; }
}

class Book extends Product {
    private String author;
    private String isbn;
    private int pages;

    public Book(String name, double price, String author, String isbn, int pages) {
        super(name, price, "Books", isbn); // Use ISBN as ID
        this.author = author;
        this.isbn = isbn;
        this.pages = pages;
    }

    @Override
    public String toString() {
        return String.format("Book{isbn='%s', title='%s', author='%s', price=%.2f, pages=%d}", 
                           isbn, getName(), author, getPrice(), pages);
    }

    @Override
    public boolean equals(Object obj) {
        if (!super.equals(obj)) return false;
        if (!(obj instanceof Book)) return false;
        
        Book book = (Book) obj;
        return pages == book.pages &&
               java.util.Objects.equals(author, book.author) &&
               java.util.Objects.equals(isbn, book.isbn);
    }

    @Override
    public int hashCode() {
        return java.util.Objects.hash(super.hashCode(), author, isbn, pages);
    }

    // Getters and setters
    public String getAuthor() { return author; }
    public void setAuthor(String author) { this.author = author; }
    public String getIsbn() { return isbn; }
    public void setIsbn(String isbn) { this.isbn = isbn; }
    public int getPages() { return pages; }
    public void setPages(int pages) { this.pages = pages; }
}

public class ObjectMethodsDemo {
    public static void main(String[] args) {
        System.out.println("=== Object Methods Demo ===\n");

        // Create some products and books
        Product laptop = new Product("Gaming Laptop", 1299.99, "Electronics", "ELEC001");
        Product phone = new Product("Smartphone", 899.99, "Electronics", "ELEC002");
        Product laptop2 = new Product("Gaming Laptop", 1299.99, "Electronics", "ELEC001");

        Book book1 = new Book("Clean Code", 45.99, "Robert C. Martin", "978-0132350884", 464);
        Book book2 = new Book("Java: The Complete Reference", 59.99, "Herbert Schildt", "978-1260440232", 1248);
        Book book1Copy = new Book("Clean Code", 45.99, "Robert C. Martin", "978-0132350884", 464);

        System.out.println("=== toString() Method ===");
        System.out.println("Laptop: " + laptop);
        System.out.println("Phone: " + phone);
        System.out.println("Book1: " + book1);
        System.out.println("Book2: " + book2);

        System.out.println("\n=== equals() Method ===");
        System.out.println("laptop.equals(laptop2): " + laptop.equals(laptop2)); // Should be true
        System.out.println("laptop.equals(phone): " + laptop.equals(phone)); // Should be false
        System.out.println("book1.equals(book1Copy): " + book1.equals(book1Copy)); // Should be true
        System.out.println("book1.equals(book2): " + book1.equals(book2)); // Should be false

        System.out.println("\n=== hashCode() Method ===");
        System.out.println("laptop hashCode: " + laptop.hashCode());
        System.out.println("laptop2 hashCode: " + laptop2.hashCode());
        System.out.println("Same hashCode for equal objects: " + (laptop.hashCode() == laptop2.hashCode()));

        System.out.println("\n=== Object Identity vs Equality ===");
        System.out.println("laptop == laptop2 (reference equality): " + (laptop == laptop2));
        System.out.println("laptop.equals(laptop2) (content equality): " + laptop.equals(laptop2));

        // Demonstrate polymorphism with Object references
        System.out.println("\n=== Polymorphism with Object Class ===");
        Object[] objects = {laptop, phone, book1, book2};
        
        for (Object obj : objects) {
            System.out.println("Object: " + obj); // Calls toString()
            System.out.println("Class: " + obj.getClass().getSimpleName());
            
            if (obj instanceof Book) {
                Book book = (Book) obj;
                System.out.println("  Author: " + book.getAuthor());
            } else if (obj instanceof Product) {
                Product product = (Product) obj;
                System.out.println("  Category: " + product.getCategory());
            }
            System.out.println();
        }
    }
}
```

### ⚠️ Common Pitfalls

1. **Forgetting to use @Override annotation**: Always use it for method overriding
2. **Breaking the equals() contract**: If you override equals(), you must override hashCode()
3. **Improper use of super keyword**: Remember to call super() in constructors when needed
4. **Downcasting without instanceof check**: Always check type before casting
5. **Confusing overriding with overloading**: They are different concepts

### ✅ Best Practices

1. **Use the @Override annotation** consistently for overridden methods
2. **Call super() appropriately** in constructors and overridden methods
3. **Override toString(), equals(), and hashCode()** in data classes
4. **Use instanceof before downcasting** to avoid ClassCastException
5. **Keep inheritance hierarchies shallow** to avoid complexity
6. **Favor composition over inheritance** when appropriate

### 🏋️ Exercise 9: Employee Management System

Create an employee management system demonstrating inheritance and polymorphism:

```java
// Base Employee class
abstract class Employee {
    protected String employeeId;
    protected String name;
    protected String department;
    protected double baseSalary;

    // Implement constructors and common methods
    // Abstract method: calculatePay()
}

// Derived classes
class FullTimeEmployee extends Employee {
    private double bonus;
    private int vacationDays;
    
    // Override calculatePay() to include bonus
}

class PartTimeEmployee extends Employee {
    private int hoursWorked;
    private double hourlyRate;
    
    // Override calculatePay() based on hours
}

class ContractEmployee extends Employee {
    private double contractAmount;
    private Date contractEndDate;
    
    // Override calculatePay() with contract terms
}

// Manager class (multilevel inheritance)
class Manager extends FullTimeEmployee {
    private List<Employee> subordinates;
    private double managementBonus;
    
    // Additional methods for team management
}

// Test with polymorphic array of employees
```

[↑ Back to Top](#-table-of-contents)

---

## 10. Encapsulation & Access Modifiers

📊 **Chapter 10 of 35**

🎯 **Learning Objectives:**
- Master encapsulation principles and data hiding
- Understand all Java access modifiers (private, protected, public, package-private)
- Learn to design secure and maintainable class interfaces
- Practice getter and setter methods with validation
- Explore immutable classes and defensive programming

⏱️ **Estimated Reading Time:** 40 minutes
📋 **Prerequisites:** Understanding of classes, objects, and inheritance

### Understanding Encapsulation

Encapsulation is one of the fundamental principles of object-oriented programming. It involves bundling data and methods that operate on that data within a single unit (class) and restricting direct access to some components.

```java
// Bad example - no encapsulation
class BadBankAccount {
    public String accountNumber;
    public double balance;
    public String ownerName;
    
    // Anyone can directly modify these fields!
}

// Good example - proper encapsulation
class GoodBankAccount {
    private String accountNumber;
    private double balance;
    private String ownerName;
    private boolean isActive;
    private java.util.List<String> transactionHistory;
    
    public GoodBankAccount(String accountNumber, String ownerName, double initialBalance) {
        this.accountNumber = accountNumber;
        this.ownerName = ownerName;
        this.balance = initialBalance >= 0 ? initialBalance : 0;
        this.isActive = true;
        this.transactionHistory = new java.util.ArrayList<>();
        addTransaction("Account opened with balance: $" + initialBalance);
    }
    
    // Controlled access through methods
    public boolean deposit(double amount) {
        if (amount > 0 && isActive) {
            balance += amount;
            addTransaction("Deposited: $" + amount + ", New balance: $" + balance);
            return true;
        }
        return false;
    }
    
    public boolean withdraw(double amount) {
        if (amount > 0 && amount <= balance && isActive) {
            balance -= amount;
            addTransaction("Withdrew: $" + amount + ", New balance: $" + balance);
            return true;
        }
        return false;
    }
    
    private void addTransaction(String transaction) {
        transactionHistory.add(java.time.LocalDateTime.now() + ": " + transaction);
    }
    
    // Safe getters
    public double getBalance() {
        return balance;
    }
    
    public String getAccountNumber() {
        return accountNumber;
    }
    
    public String getOwnerName() {
        return ownerName;
    }
    
    public boolean isActive() {
        return isActive;
    }
    
    // Defensive copy for mutable objects
    public java.util.List<String> getTransactionHistory() {
        return new java.util.ArrayList<>(transactionHistory);
    }
    
    public void closeAccount() {
        if (balance == 0) {
            isActive = false;
            addTransaction("Account closed");
        } else {
            System.out.println("Cannot close account with non-zero balance: $" + balance);
        }
    }
}
```

### Access Modifiers in Detail

Java provides four levels of access control through access modifiers:

```java
// Demonstration of all access modifiers
public class AccessModifierDemo {
    
    // PUBLIC - accessible from anywhere
    public String publicField = "Everyone can see this";
    
    // PROTECTED - accessible within package and by subclasses
    protected String protectedField = "Subclasses and same package can see this";
    
    // PACKAGE-PRIVATE (default) - accessible within the same package only
    String packagePrivateField = "Only same package can see this";
    
    // PRIVATE - accessible only within the same class
    private String privateField = "Only this class can see this";
    
    // Constructor
    public AccessModifierDemo(String value) {
        this.privateField = value;
    }
    
    // PUBLIC method - can be called from anywhere
    public void publicMethod() {
        System.out.println("This is a public method");
        // Can access all fields within the same class
        System.out.println("Accessing private field: " + privateField);
    }
    
    // PROTECTED method - accessible to subclasses and same package
    protected void protectedMethod() {
        System.out.println("This is a protected method");
    }
    
    // PACKAGE-PRIVATE method - accessible within same package
    void packagePrivateMethod() {
        System.out.println("This is a package-private method");
    }
    
    // PRIVATE method - only accessible within this class
    private void privateMethod() {
        System.out.println("This is a private method");
    }
    
    // Public method that uses private method
    public void doSomething() {
        privateMethod(); // OK - same class
        validateData();  // OK - same class
    }
    
    private boolean validateData() {
        // Private helper method for internal use
        return privateField != null && !privateField.isEmpty();
    }
}

// Subclass to demonstrate protected access
class SubAccessDemo extends AccessModifierDemo {
    
    public SubAccessDemo() {
        super("Subclass instance");
    }
    
    public void demonstrateAccess() {
        System.out.println("=== Access from Subclass ===");
        
        // Can access public members
        System.out.println("Public field: " + publicField);
        publicMethod();
        
        // Can access protected members
        System.out.println("Protected field: " + protectedField);
        protectedMethod();
        
        // Can access package-private if in same package
        System.out.println("Package-private field: " + packagePrivateField);
        packagePrivateMethod();
        
        // CANNOT access private members
        // System.out.println(privateField); // Compile error!
        // privateMethod(); // Compile error!
    }
}
```

### Proper Getter and Setter Design

```java
class Person {
    private String name;
    private int age;
    private String email;
    private String phoneNumber;
    private java.util.Date birthDate;
    private java.util.List<String> hobbies;
    
    public Person(String name, int age, String email) {
        setName(name);    // Use setters for validation
        setAge(age);
        setEmail(email);
        this.hobbies = new java.util.ArrayList<>();
    }
    
    // Getter with validation
    public String getName() {
        return name;
    }
    
    // Setter with validation
    public void setName(String name) {
        if (name == null || name.trim().isEmpty()) {
            throw new IllegalArgumentException("Name cannot be null or empty");
        }
        if (name.length() > 50) {
            throw new IllegalArgumentException("Name cannot exceed 50 characters");
        }
        this.name = name.trim();
    }
    
    public int getAge() {
        return age;
    }
    
    public void setAge(int age) {
        if (age < 0 || age > 150) {
            throw new IllegalArgumentException("Age must be between 0 and 150");
        }
        this.age = age;
    }
    
    public String getEmail() {
        return email;
    }
    
    public void setEmail(String email) {
        if (email == null || !isValidEmail(email)) {
            throw new IllegalArgumentException("Invalid email format");
        }
        this.email = email.toLowerCase();
    }
    
    private boolean isValidEmail(String email) {
        // Simple email validation
        return email.contains("@") && email.contains(".") && email.length() > 5;
    }
    
    public String getPhoneNumber() {
        return phoneNumber;
    }
    
    public void setPhoneNumber(String phoneNumber) {
        if (phoneNumber != null) {
            // Remove all non-digits
            String cleaned = phoneNumber.replaceAll("[^0-9]", "");
            if (cleaned.length() == 10) {
                this.phoneNumber = cleaned;
            } else {
                throw new IllegalArgumentException("Phone number must be 10 digits");
            }
        }
    }
    
    // Defensive copying for mutable objects
    public java.util.Date getBirthDate() {
        return birthDate != null ? new java.util.Date(birthDate.getTime()) : null;
    }
    
    public void setBirthDate(java.util.Date birthDate) {
        this.birthDate = birthDate != null ? new java.util.Date(birthDate.getTime()) : null;
    }
    
    // Safe access to collections
    public java.util.List<String> getHobbies() {
        return new java.util.ArrayList<>(hobbies); // Return defensive copy
    }
    
    public void addHobby(String hobby) {
        if (hobby != null && !hobby.trim().isEmpty()) {
            String trimmedHobby = hobby.trim();
            if (!hobbies.contains(trimmedHobby)) {
                hobbies.add(trimmedHobby);
            }
        }
    }
    
    public boolean removeHobby(String hobby) {
        return hobbies.remove(hobby);
    }
    
    public void clearHobbies() {
        hobbies.clear();
    }
    
    @Override
    public String toString() {
        return String.format("Person{name='%s', age=%d, email='%s', hobbies=%s}", 
                           name, age, email, hobbies);
    }
}
```

### Immutable Classes

Immutable classes are classes whose instances cannot be modified after creation. They provide thread safety and simplicity.

```java
// Immutable class example
public final class ImmutableStudent {
    private final String studentId;
    private final String name;
    private final int age;
    private final java.util.List<String> courses;
    private final java.util.Map<String, Double> grades;
    
    // Builder pattern for immutable classes with many fields
    public static class Builder {
        private String studentId;
        private String name;
        private int age;
        private java.util.List<String> courses = new java.util.ArrayList<>();
        private java.util.Map<String, Double> grades = new java.util.HashMap<>();
        
        public Builder setStudentId(String studentId) {
            this.studentId = studentId;
            return this;
        }
        
        public Builder setName(String name) {
            this.name = name;
            return this;
        }
        
        public Builder setAge(int age) {
            this.age = age;
            return this;
        }
        
        public Builder addCourse(String course) {
            this.courses.add(course);
            return this;
        }
        
        public Builder addGrade(String course, Double grade) {
            this.grades.put(course, grade);
            return this;
        }
        
        public ImmutableStudent build() {
            return new ImmutableStudent(this);
        }
    }
    
    private ImmutableStudent(Builder builder) {
        this.studentId = builder.studentId;
        this.name = builder.name;
        this.age = builder.age;
        // Create defensive copies of mutable objects
        this.courses = java.util.Collections.unmodifiableList(
            new java.util.ArrayList<>(builder.courses)
        );
        this.grades = java.util.Collections.unmodifiableMap(
            new java.util.HashMap<>(builder.grades)
        );
    }
    
    // Only getters, no setters
    public String getStudentId() {
        return studentId;
    }
    
    public String getName() {
        return name;
    }
    
    public int getAge() {
        return age;
    }
    
    // Return unmodifiable collections
    public java.util.List<String> getCourses() {
        return courses; // Already unmodifiable
    }
    
    public java.util.Map<String, Double> getGrades() {
        return grades; // Already unmodifiable
    }
    
    // Methods that return new instances for "modifications"
    public ImmutableStudent withAge(int newAge) {
        return new Builder()
            .setStudentId(this.studentId)
            .setName(this.name)
            .setAge(newAge)
            .build();
    }
    
    public ImmutableStudent withAddedCourse(String course) {
        Builder builder = new Builder()
            .setStudentId(this.studentId)
            .setName(this.name)
            .setAge(this.age);
        
        // Add existing courses
        for (String existingCourse : this.courses) {
            builder.addCourse(existingCourse);
        }
        builder.addCourse(course);
        
        // Add existing grades
        for (java.util.Map.Entry<String, Double> entry : this.grades.entrySet()) {
            builder.addGrade(entry.getKey(), entry.getValue());
        }
        
        return builder.build();
    }
    
    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;
        
        ImmutableStudent that = (ImmutableStudent) obj;
        return age == that.age &&
               java.util.Objects.equals(studentId, that.studentId) &&
               java.util.Objects.equals(name, that.name) &&
               java.util.Objects.equals(courses, that.courses) &&
               java.util.Objects.equals(grades, that.grades);
    }
    
    @Override
    public int hashCode() {
        return java.util.Objects.hash(studentId, name, age, courses, grades);
    }
    
    @Override
    public String toString() {
        return String.format("ImmutableStudent{id='%s', name='%s', age=%d, courses=%s, grades=%s}",
                           studentId, name, age, courses, grades);
    }
}
```

### Package Organization and Access Control

```java
// File: com/company/model/User.java
package com.company.model;

public class User {
    private String username;
    private String hashedPassword;
    protected String email; // Accessible to subclasses
    
    // Package-private field - accessible within com.company.model package
    String lastLoginTime;
    
    public User(String username, String email) {
        this.username = username;
        this.email = email;
    }
    
    // Public interface
    public String getUsername() {
        return username;
    }
    
    public String getEmail() {
        return email;
    }
    
    // Package-private method for internal use
    void updateLastLogin() {
        lastLoginTime = java.time.LocalDateTime.now().toString();
    }
    
    // Protected method for subclasses
    protected boolean verifyPassword(String password) {
        return hashedPassword != null && hashedPassword.equals(hashPassword(password));
    }
    
    private String hashPassword(String password) {
        // Simple hash for demonstration
        return "hashed_" + password;
    }
}

// File: com/company/model/AdminUser.java
package com.company.model;

public class AdminUser extends User {
    private java.util.Set<String> permissions;
    
    public AdminUser(String username, String email) {
        super(username, email);
        this.permissions = new java.util.HashSet<>();
    }
    
    public void addPermission(String permission) {
        permissions.add(permission);
    }
    
    public boolean hasPermission(String permission) {
        return permissions.contains(permission);
    }
    
    // Can access protected methods from superclass
    public boolean authenticateAdmin(String password) {
        return verifyPassword(password) && hasPermission("ADMIN");
    }
    
    // Can access package-private fields and methods
    public String getLastLogin() {
        return lastLoginTime; // Package-private field accessible
    }
}
```

### Real-World Example: Security System

```java
class SecuritySystem {
    private boolean isArmed;
    private String securityCode;
    private java.util.List<String> authorizedUsers;
    private java.util.List<String> securityLog;
    private int failedAttempts;
    private static final int MAX_FAILED_ATTEMPTS = 3;
    
    public SecuritySystem(String initialCode) {
        setSecurityCode(initialCode);
        this.isArmed = false;
        this.authorizedUsers = new java.util.ArrayList<>();
        this.securityLog = new java.util.ArrayList<>();
        this.failedAttempts = 0;
        logEvent("Security system initialized");
    }
    
    public boolean armSystem(String code, String user) {
        if (authenticate(code, user)) {
            isArmed = true;
            logEvent("System armed by " + user);
            return true;
        }
        return false;
    }
    
    public boolean disarmSystem(String code, String user) {
        if (authenticate(code, user)) {
            isArmed = false;
            failedAttempts = 0; // Reset on successful disarm
            logEvent("System disarmed by " + user);
            return true;
        }
        return false;
    }
    
    private boolean authenticate(String code, String user) {
        if (securityCode.equals(code) && isAuthorizedUser(user)) {
            failedAttempts = 0;
            logEvent("Successful authentication by " + user);
            return true;
        } else {
            failedAttempts++;
            logEvent("Failed authentication attempt by " + user + " (Attempt " + failedAttempts + ")");
            
            if (failedAttempts >= MAX_FAILED_ATTEMPTS) {
                triggerAlarm();
            }
            return false;
        }
    }
    
    private void triggerAlarm() {
        logEvent("ALARM TRIGGERED - Too many failed attempts!");
        // In real system, this would activate alarms, notify security, etc.
        System.out.println("🚨 SECURITY ALARM ACTIVATED! 🚨");
    }
    
    public void addAuthorizedUser(String adminCode, String user) {
        if (securityCode.equals(adminCode)) {
            authorizedUsers.add(user);
            logEvent("User " + user + " added to authorized users");
        } else {
            logEvent("Unauthorized attempt to add user " + user);
        }
    }
    
    private boolean isAuthorizedUser(String user) {
        return authorizedUsers.contains(user);
    }
    
    private void setSecurityCode(String code) {
        if (code == null || code.length() < 4) {
            throw new IllegalArgumentException("Security code must be at least 4 characters");
        }
        this.securityCode = code;
        logEvent("Security code updated");
    }
    
    public boolean changeSecurityCode(String oldCode, String newCode, String user) {
        if (authenticate(oldCode, user)) {
            setSecurityCode(newCode);
            logEvent("Security code changed by " + user);
            return true;
        }
        return false;
    }
    
    private void logEvent(String event) {
        String timestamp = java.time.LocalDateTime.now().toString();
        securityLog.add(timestamp + ": " + event);
    }
    
    // Safe public methods
    public boolean isSystemArmed() {
        return isArmed;
    }
    
    public int getFailedAttempts() {
        return failedAttempts;
    }
    
    public java.util.List<String> getSecurityLog(String adminCode) {
        if (securityCode.equals(adminCode)) {
            return new java.util.ArrayList<>(securityLog); // Defensive copy
        }
        logEvent("Unauthorized attempt to access security log");
        return java.util.Collections.emptyList();
    }
    
    public java.util.List<String> getAuthorizedUsers(String adminCode) {
        if (securityCode.equals(adminCode)) {
            return new java.util.ArrayList<>(authorizedUsers); // Defensive copy
        }
        return java.util.Collections.emptyList();
    }
}

// Demo class
public class EncapsulationDemo {
    public static void main(String[] args) {
        System.out.println("=== Encapsulation and Security Demo ===\n");
        
        // Initialize security system
        SecuritySystem security = new SecuritySystem("admin123");
        
        // Add authorized users
        security.addAuthorizedUser("admin123", "Alice");
        security.addAuthorizedUser("admin123", "Bob");
        
        System.out.println("System armed: " + security.isSystemArmed());
        
        // Arm system
        boolean armed = security.armSystem("admin123", "Alice");
        System.out.println("Arm successful: " + armed);
        System.out.println("System armed: " + security.isSystemArmed());
        
        // Failed disarm attempts
        security.disarmSystem("wrong", "Alice");
        security.disarmSystem("wrong", "Charlie");
        security.disarmSystem("wrong", "Alice");
        security.disarmSystem("wrong", "Alice"); // This should trigger alarm
        
        // Successful disarm
        security.disarmSystem("admin123", "Alice");
        
        // Display security log
        System.out.println("\n=== Security Log ===");
        java.util.List<String> log = security.getSecurityLog("admin123");
        for (String entry : log) {
            System.out.println(entry);
        }
        
        // Demonstrate immutable class
        System.out.println("\n=== Immutable Student Demo ===");
        ImmutableStudent student = new ImmutableStudent.Builder()
            .setStudentId("STU001")
            .setName("John Doe")
            .setAge(20)
            .addCourse("Math")
            .addCourse("Physics")
            .addGrade("Math", 95.0)
            .build();
        
        System.out.println("Original: " + student);
        
        // "Modify" by creating new instance
        ImmutableStudent olderStudent = student.withAge(21);
        System.out.println("Older version: " + olderStudent);
        System.out.println("Original unchanged: " + student);
    }
}
```

### ⚠️ Common Pitfalls

1. **Making fields public unnecessarily**: Always use private fields with controlled access
2. **Forgetting defensive copying**: Return copies of mutable objects, not references
3. **Not validating input in setters**: Always validate data before setting
4. **Overusing getters and setters**: Don't create them automatically for every field
5. **Breaking encapsulation with return references**: Be careful with collections and mutable objects

### ✅ Best Practices

1. **Make fields private by default** and provide controlled access through methods
2. **Use the most restrictive access modifier** that still allows proper functionality
3. **Validate input data** in constructors and setter methods
4. **Return defensive copies** of mutable objects when necessary
5. **Use immutable classes** when objects shouldn't change after creation
6. **Group related functionality** in packages and use package-private access appropriately

### 🏋️ Exercise 10: Bank Account System

Create a comprehensive bank account system demonstrating proper encapsulation:

```java
// Create these classes with proper encapsulation:

abstract class Account {
    // Protected fields for subclasses
    // Private methods for internal operations
    // Public interface for external access
}

class CheckingAccount extends Account {
    // Overdraft protection features
    // Transaction limits
}

class SavingsAccount extends Account {
    // Interest calculation
    // Withdrawal restrictions
}

class Bank {
    // Manage multiple accounts
    // Account creation and deletion
    // Security and audit logging
}

// Implement proper:
// - Access control
// - Input validation  
// - Defensive programming
// - Immutable transaction records
```

[↑ Back to Top](#-table-of-contents)

---

## 11. Abstract Classes & Interfaces

📊 **Chapter 11 of 35**

🎯 **Learning Objectives:**
- Understand the difference between abstract classes and interfaces
- Master abstract method implementation and concrete method inheritance
- Learn interface contracts and multiple inheritance through interfaces
- Explore default and static methods in interfaces (Java 8+)
- Practice designing flexible and extensible systems

⏱️ **Estimated Reading Time:** 45 minutes
📋 **Prerequisites:** Understanding of inheritance and polymorphism

### Abstract Classes

Abstract classes cannot be instantiated directly and are designed to be subclassed. They can contain both abstract methods (without implementation) and concrete methods (with implementation).

```java
// Abstract base class for shapes
abstract class Shape {
    protected String name;
    protected String color;
    
    public Shape(String name, String color) {
        this.name = name;
        this.color = color;
    }
    
    // Abstract methods - must be implemented by subclasses
    public abstract double calculateArea();
    public abstract double calculatePerimeter();
    public abstract void draw();
    
    // Concrete methods - inherited by subclasses
    public void displayInfo() {
        System.out.println("Shape: " + name);
        System.out.println("Color: " + color);
        System.out.println("Area: " + String.format("%.2f", calculateArea()));
        System.out.println("Perimeter: " + String.format("%.2f", calculatePerimeter()));
    }
    
    public String getName() {
        return name;
    }
    
    public String getColor() {
        return color;
    }
    
    public void setColor(String color) {
        this.color = color;
    }
    
    // Template method pattern - defines algorithm structure
    public final void processShape() {
        System.out.println("Processing " + name + "...");
        validateShape();
        calculateProperties();
        draw();
        System.out.println("Shape processing complete.\n");
    }
    
    private void validateShape() {
        System.out.println("Validating " + name + " properties...");
    }
    
    private void calculateProperties() {
        System.out.println("Calculating area: " + calculateArea());
        System.out.println("Calculating perimeter: " + calculatePerimeter());
    }
}

// Concrete implementation of Circle
class Circle extends Shape {
    private double radius;
    
    public Circle(String color, double radius) {
        super("Circle", color);
        this.radius = radius;
    }
    
    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
    
    @Override
    public double calculatePerimeter() {
        return 2 * Math.PI * radius;
    }
    
    @Override
    public void draw() {
        System.out.println("Drawing a " + color + " circle with radius " + radius);
    }
    
    public double getRadius() {
        return radius;
    }
    
    public void setRadius(double radius) {
        if (radius > 0) {
            this.radius = radius;
        }
    }
}

// Concrete implementation of Rectangle
class Rectangle extends Shape {
    private double width;
    private double height;
    
    public Rectangle(String color, double width, double height) {
        super("Rectangle", color);
        this.width = width;
        this.height = height;
    }
    
    @Override
    public double calculateArea() {
        return width * height;
    }
    
    @Override
    public double calculatePerimeter() {
        return 2 * (width + height);
    }
    
    @Override
    public void draw() {
        System.out.println("Drawing a " + color + " rectangle (" + width + "x" + height + ")");
    }
    
    public double getWidth() {
        return width;
    }
    
    public double getHeight() {
        return height;
    }
    
    public void setWidth(double width) {
        if (width > 0) {
            this.width = width;
        }
    }
    
    public void setHeight(double height) {
        if (height > 0) {
            this.height = height;
        }
    }
}

// Concrete implementation of Triangle
class Triangle extends Shape {
    private double side1, side2, side3;
    
    public Triangle(String color, double side1, double side2, double side3) {
        super("Triangle", color);
        if (isValidTriangle(side1, side2, side3)) {
            this.side1 = side1;
            this.side2 = side2;
            this.side3 = side3;
        } else {
            throw new IllegalArgumentException("Invalid triangle sides");
        }
    }
    
    private boolean isValidTriangle(double a, double b, double c) {
        return (a + b > c) && (a + c > b) && (b + c > a);
    }
    
    @Override
    public double calculateArea() {
        // Using Heron's formula
        double s = calculatePerimeter() / 2;
        return Math.sqrt(s * (s - side1) * (s - side2) * (s - side3));
    }
    
    @Override
    public double calculatePerimeter() {
        return side1 + side2 + side3;
    }
    
    @Override
    public void draw() {
        System.out.println("Drawing a " + color + " triangle with sides " + 
                         side1 + ", " + side2 + ", " + side3);
    }
    
    public double getSide1() { return side1; }
    public double getSide2() { return side2; }
    public double getSide3() { return side3; }
}
```

### Interfaces

Interfaces define contracts that implementing classes must follow. They can contain method signatures, default methods, static methods, and constants.

```java
// Basic interface for drawable objects
interface Drawable {
    // Interface constants (implicitly public, static, final)
    String DEFAULT_COLOR = "BLACK";
    int MAX_SIZE = 1000;
    
    // Abstract methods (implicitly public and abstract)
    void draw();
    void resize(double factor);
    
    // Default method (Java 8+)
    default void highlight() {
        System.out.println("Highlighting the drawable object");
    }
    
    // Static method (Java 8+)
    static void printInfo() {
        System.out.println("This is a Drawable interface");
    }
}

// Interface for objects that can be moved
interface Movable {
    void move(double deltaX, double deltaY);
    void moveTo(double x, double y);
    
    // Default method
    default void moveUp(double distance) {
        move(0, distance);
    }
    
    default void moveDown(double distance) {
        move(0, -distance);
    }
    
    default void moveLeft(double distance) {
        move(-distance, 0);
    }
    
    default void moveRight(double distance) {
        move(distance, 0);
    }
}

// Interface for rotatable objects
interface Rotatable {
    void rotate(double angle);
    double getRotation();
    
    default void rotateClockwise(double angle) {
        rotate(angle);
    }
    
    default void rotateCounterClockwise(double angle) {
        rotate(-angle);
    }
}

// Class implementing multiple interfaces
class GraphicsCircle implements Drawable, Movable, Rotatable {
    private double x, y;
    private double radius;
    private String color;
    private double rotation;
    
    public GraphicsCircle(double x, double y, double radius, String color) {
        this.x = x;
        this.y = y;
        this.radius = radius;
        this.color = color != null ? color : DEFAULT_COLOR;
        this.rotation = 0;
    }
    
    // Implementing Drawable interface
    @Override
    public void draw() {
        System.out.println("Drawing " + color + " circle at (" + x + "," + y + 
                         ") with radius " + radius + " and rotation " + rotation + "°");
    }
    
    @Override
    public void resize(double factor) {
        if (factor > 0) {
            radius *= factor;
            System.out.println("Resized circle by factor " + factor + 
                             ", new radius: " + radius);
        }
    }
    
    // Implementing Movable interface
    @Override
    public void move(double deltaX, double deltaY) {
        x += deltaX;
        y += deltaY;
        System.out.println("Moved circle by (" + deltaX + "," + deltaY + 
                         "), new position: (" + x + "," + y + ")");
    }
    
    @Override
    public void moveTo(double x, double y) {
        this.x = x;
        this.y = y;
        System.out.println("Moved circle to position: (" + x + "," + y + ")");
    }
    
    // Implementing Rotatable interface
    @Override
    public void rotate(double angle) {
        rotation = (rotation + angle) % 360;
        if (rotation < 0) rotation += 360;
        System.out.println("Rotated circle by " + angle + "°, current rotation: " + rotation + "°");
    }
    
    @Override
    public double getRotation() {
        return rotation;
    }
    
    // Getters and setters
    public double getX() { return x; }
    public double getY() { return y; }
    public double getRadius() { return radius; }
    public String getColor() { return color; }
    
    public void setColor(String color) {
        this.color = color != null ? color : DEFAULT_COLOR;
    }
}

// Another class implementing the same interfaces
class GraphicsRectangle implements Drawable, Movable, Rotatable {
    private double x, y;
    private double width, height;
    private String color;
    private double rotation;
    
    public GraphicsRectangle(double x, double y, double width, double height, String color) {
        this.x = x;
        this.y = y;
        this.width = width;
        this.height = height;
        this.color = color != null ? color : DEFAULT_COLOR;
        this.rotation = 0;
    }
    
    @Override
    public void draw() {
        System.out.println("Drawing " + color + " rectangle at (" + x + "," + y + 
                         ") with size " + width + "x" + height + 
                         " and rotation " + rotation + "°");
    }
    
    @Override
    public void resize(double factor) {
        if (factor > 0) {
            width *= factor;
            height *= factor;
            System.out.println("Resized rectangle by factor " + factor + 
                             ", new size: " + width + "x" + height);
        }
    }
    
    @Override
    public void move(double deltaX, double deltaY) {
        x += deltaX;
        y += deltaY;
        System.out.println("Moved rectangle by (" + deltaX + "," + deltaY + 
                         "), new position: (" + x + "," + y + ")");
    }
    
    @Override
    public void moveTo(double x, double y) {
        this.x = x;
        this.y = y;
        System.out.println("Moved rectangle to position: (" + x + "," + y + ")");
    }
    
    @Override
    public void rotate(double angle) {
        rotation = (rotation + angle) % 360;
        if (rotation < 0) rotation += 360;
        System.out.println("Rotated rectangle by " + angle + "°, current rotation: " + rotation + "°");
    }
    
    @Override
    public double getRotation() {
        return rotation;
    }
}
```

### Advanced Interface Features (Java 8+)

```java
// Interface with default and static methods
interface PaymentProcessor {
    // Abstract method
    boolean processPayment(double amount, String currency);
    
    // Default method - can be overridden
    default boolean validateAmount(double amount) {
        return amount > 0 && amount <= getMaxTransactionLimit();
    }
    
    // Default method using other interface methods
    default String formatAmount(double amount, String currency) {
        return String.format("%.2f %s", amount, currency);
    }
    
    // Static method - cannot be overridden
    static double convertCurrency(double amount, String fromCurrency, String toCurrency) {
        // Simplified conversion (in reality, you'd use real exchange rates)
        java.util.Map<String, Double> rates = new java.util.HashMap<>();
        rates.put("USD", 1.0);
        rates.put("EUR", 0.85);
        rates.put("GBP", 0.73);
        rates.put("JPY", 110.0);
        
        Double fromRate = rates.get(fromCurrency);
        Double toRate = rates.get(toCurrency);
        
        if (fromRate != null && toRate != null) {
            return (amount / fromRate) * toRate;
        }
        
        throw new IllegalArgumentException("Unsupported currency conversion");
    }
    
    // Static utility method
    static boolean isValidCurrency(String currency) {
        return java.util.Arrays.asList("USD", "EUR", "GBP", "JPY").contains(currency);
    }
    
    // Abstract method for implementation-specific limits
    double getMaxTransactionLimit();
}

// Credit card processor implementation
class CreditCardProcessor implements PaymentProcessor {
    private String processorName;
    private double transactionFee;
    
    public CreditCardProcessor(String processorName, double transactionFee) {
        this.processorName = processorName;
        this.transactionFee = transactionFee;
    }
    
    @Override
    public boolean processPayment(double amount, String currency) {
        if (!validateAmount(amount) || !PaymentProcessor.isValidCurrency(currency)) {
            System.out.println("Invalid payment parameters");
            return false;
        }
        
        double fee = amount * transactionFee;
        double total = amount + fee;
        
        System.out.println(processorName + " processing payment:");
        System.out.println("Amount: " + formatAmount(amount, currency));
        System.out.println("Fee: " + formatAmount(fee, currency));
        System.out.println("Total: " + formatAmount(total, currency));
        
        // Simulate payment processing
        return Math.random() > 0.1; // 90% success rate
    }
    
    @Override
    public double getMaxTransactionLimit() {
        return 10000.0; // Credit card limit
    }
    
    // Override default method for custom validation
    @Override
    public boolean validateAmount(double amount) {
        // Additional validation for credit cards
        return PaymentProcessor.super.validateAmount(amount) && amount >= 1.0;
    }
}

// PayPal processor implementation
class PayPalProcessor implements PaymentProcessor {
    private String accountEmail;
    
    public PayPalProcessor(String accountEmail) {
        this.accountEmail = accountEmail;
    }
    
    @Override
    public boolean processPayment(double amount, String currency) {
        if (!validateAmount(amount)) {
            return false;
        }
        
        System.out.println("PayPal processing payment for " + accountEmail + ":");
        System.out.println("Amount: " + formatAmount(amount, currency));
        
        // Simulate PayPal processing
        return Math.random() > 0.05; // 95% success rate
    }
    
    @Override
    public double getMaxTransactionLimit() {
        return 25000.0; // PayPal limit
    }
}
```

### Functional Interfaces and Lambdas

```java
// Functional interface - has exactly one abstract method
@FunctionalInterface
interface Calculator {
    double calculate(double a, double b);
    
    // Default methods don't count toward the single abstract method requirement
    default void printResult(double a, double b) {
        System.out.println("Result: " + calculate(a, b));
    }
    
    // Static methods don't count either
    static Calculator getAddition() {
        return (a, b) -> a + b;
    }
    
    static Calculator getMultiplication() {
        return (a, b) -> a * b;
    }
}

// Another functional interface
@FunctionalInterface
interface StringProcessor {
    String process(String input);
    
    default StringProcessor andThen(StringProcessor after) {
        return input -> after.process(this.process(input));
    }
    
    static StringProcessor identity() {
        return input -> input;
    }
}

public class FunctionalInterfaceDemo {
    public static void main(String[] args) {
        System.out.println("=== Functional Interface Demo ===\n");
        
        // Using lambda expressions with functional interfaces
        Calculator addition = (a, b) -> a + b;
        Calculator subtraction = (a, b) -> a - b;
        Calculator multiplication = Calculator.getMultiplication();
        Calculator division = (a, b) -> b != 0 ? a / b : 0;
        
        double x = 10, y = 3;
        
        System.out.println("Operations on " + x + " and " + y + ":");
        System.out.println("Addition: " + addition.calculate(x, y));
        System.out.println("Subtraction: " + subtraction.calculate(x, y));
        System.out.println("Multiplication: " + multiplication.calculate(x, y));
        System.out.println("Division: " + division.calculate(x, y));
        
        // Using default method
        addition.printResult(x, y);
        
        // StringProcessor examples
        StringProcessor uppercase = String::toUpperCase;
        StringProcessor addPrefix = s -> "PREFIX_" + s;
        StringProcessor addSuffix = s -> s + "_SUFFIX";
        
        String input = "hello world";
        System.out.println("\nString processing:");
        System.out.println("Original: " + input);
        System.out.println("Uppercase: " + uppercase.process(input));
        System.out.println("With prefix: " + addPrefix.process(input));
        
        // Chain processors using andThen
        StringProcessor chain = addPrefix.andThen(uppercase).andThen(addSuffix);
        System.out.println("Chained: " + chain.process(input));
    }
}
```

### Interface vs Abstract Class Comparison

```java
// When to use abstract class: IS-A relationship with shared implementation
abstract class Vehicle {
    protected String make, model;
    protected int year;
    
    public Vehicle(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }
    
    // Concrete method - common to all vehicles
    public String getInfo() {
        return year + " " + make + " " + model;
    }
    
    // Abstract method - varies by vehicle type
    public abstract void start();
    public abstract double getFuelEfficiency();
}

// When to use interface: CAN-DO relationship, multiple inheritance
interface Flyable {
    void takeOff();
    void land();
    double getAltitude();
    
    default void fly() {
        takeOff();
        System.out.println("Flying at altitude: " + getAltitude());
        land();
    }
}

interface Swimmable {
    void dive();
    void surface();
    double getDepth();
}

// Car extends Vehicle (IS-A relationship)
class Car extends Vehicle {
    public Car(String make, String model, int year) {
        super(make, model, year);
    }
    
    @Override
    public void start() {
        System.out.println(getInfo() + " engine started");
    }
    
    @Override
    public double getFuelEfficiency() {
        return 25.0; // MPG
    }
}

// Airplane extends Vehicle and implements Flyable (IS-A Vehicle, CAN Fly)
class Airplane extends Vehicle implements Flyable {
    private double altitude;
    
    public Airplane(String make, String model, int year) {
        super(make, model, year);
        this.altitude = 0;
    }
    
    @Override
    public void start() {
        System.out.println(getInfo() + " aircraft engines started");
    }
    
    @Override
    public double getFuelEfficiency() {
        return 5.2; // Miles per gallon
    }
    
    @Override
    public void takeOff() {
        altitude = 35000;
        System.out.println(getInfo() + " taking off to " + altitude + " feet");
    }
    
    @Override
    public void land() {
        altitude = 0;
        System.out.println(getInfo() + " landing");
    }
    
    @Override
    public double getAltitude() {
        return altitude;
    }
}

// Duck implements both Flyable and Swimmable (CAN Fly and CAN Swim)
class Duck implements Flyable, Swimmable {
    private String name;
    private double altitude;
    private double depth;
    
    public Duck(String name) {
        this.name = name;
        this.altitude = 0;
        this.depth = 0;
    }
    
    @Override
    public void takeOff() {
        altitude = 100;
        System.out.println(name + " the duck is flying at " + altitude + " feet");
    }
    
    @Override
    public void land() {
        altitude = 0;
        System.out.println(name + " the duck has landed");
    }
    
    @Override
    public double getAltitude() {
        return altitude;
    }
    
    @Override
    public void dive() {
        depth = 10;
        System.out.println(name + " the duck is diving to " + depth + " feet deep");
    }
    
    @Override
    public void surface() {
        depth = 0;
        System.out.println(name + " the duck has surfaced");
    }
    
    @Override
    public double getDepth() {
        return depth;
    }
}
```

### Real-World Example: Plugin System

```java
// Plugin interface
interface Plugin {
    String getName();
    String getVersion();
    void initialize();
    void execute();
    void shutdown();
    
    default String getInfo() {
        return getName() + " v" + getVersion();
    }
    
    default boolean isCompatible(String systemVersion) {
        return true; // Default compatibility
    }
}

// Abstract base plugin with common functionality
abstract class BasePlugin implements Plugin {
    protected String name;
    protected String version;
    protected boolean initialized;
    protected java.util.List<String> logs;
    
    public BasePlugin(String name, String version) {
        this.name = name;
        this.version = version;
        this.initialized = false;
        this.logs = new java.util.ArrayList<>();
    }
    
    @Override
    public String getName() {
        return name;
    }
    
    @Override
    public String getVersion() {
        return version;
    }
    
    @Override
    public void initialize() {
        if (!initialized) {
            log("Initializing " + getInfo());
            doInitialize();
            initialized = true;
            log("Initialization complete");
        }
    }
    
    @Override
    public void shutdown() {
        if (initialized) {
            log("Shutting down " + getInfo());
            doShutdown();
            initialized = false;
            log("Shutdown complete");
        }
    }
    
    protected void log(String message) {
        String timestamp = java.time.LocalDateTime.now().toString();
        logs.add(timestamp + ": " + message);
        System.out.println("[" + name + "] " + message);
    }
    
    public java.util.List<String> getLogs() {
        return new java.util.ArrayList<>(logs);
    }
    
    // Template methods for subclasses
    protected abstract void doInitialize();
    protected abstract void doShutdown();
}

// Concrete plugin implementations
class DatabasePlugin extends BasePlugin {
    private String connectionString;
    
    public DatabasePlugin(String connectionString) {
        super("Database Connector", "1.0.0");
        this.connectionString = connectionString;
    }
    
    @Override
    protected void doInitialize() {
        log("Connecting to database: " + connectionString);
        // Simulate database connection
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            Thread.currentThread().interrupt();
        }
    }
    
    @Override
    protected void doShutdown() {
        log("Closing database connections");
    }
    
    @Override
    public void execute() {
        if (initialized) {
            log("Executing database operations");
            // Simulate database work
        } else {
            log("Plugin not initialized!");
        }
    }
}

class SecurityPlugin extends BasePlugin {
    private int securityLevel;
    
    public SecurityPlugin(int securityLevel) {
        super("Security Manager", "2.1.0");
        this.securityLevel = securityLevel;
    }
    
    @Override
    protected void doInitialize() {
        log("Initializing security level " + securityLevel);
    }
    
    @Override
    protected void doShutdown() {
        log("Clearing security contexts");
    }
    
    @Override
    public void execute() {
        if (initialized) {
            log("Running security checks");
            // Simulate security operations
        } else {
            log("Security plugin not initialized!");
        }
    }
    
    @Override
    public boolean isCompatible(String systemVersion) {
        // More restrictive compatibility check
        return systemVersion.compareTo("2.0") >= 0;
    }
}

// Plugin manager
class PluginManager {
    private java.util.List<Plugin> plugins;
    private String systemVersion;
    
    public PluginManager(String systemVersion) {
        this.systemVersion = systemVersion;
        this.plugins = new java.util.ArrayList<>();
    }
    
    public void registerPlugin(Plugin plugin) {
        if (plugin.isCompatible(systemVersion)) {
            plugins.add(plugin);
            System.out.println("Registered plugin: " + plugin.getInfo());
        } else {
            System.out.println("Plugin " + plugin.getInfo() + 
                             " is not compatible with system version " + systemVersion);
        }
    }
    
    public void initializeAll() {
        System.out.println("Initializing all plugins...");
        for (Plugin plugin : plugins) {
            plugin.initialize();
        }
    }
    
    public void executeAll() {
        System.out.println("Executing all plugins...");
        for (Plugin plugin : plugins) {
            plugin.execute();
        }
    }
    
    public void shutdownAll() {
        System.out.println("Shutting down all plugins...");
        for (Plugin plugin : plugins) {
            plugin.shutdown();
        }
    }
    
    public void listPlugins() {
        System.out.println("Registered plugins:");
        for (Plugin plugin : plugins) {
            System.out.println("- " + plugin.getInfo());
        }
    }
}

// Demo
public class AbstractInterfaceDemo {
    public static void main(String[] args) {
        System.out.println("=== Abstract Classes and Interfaces Demo ===\n");
        
        // Abstract class demo
        System.out.println("=== Abstract Class Demo ===");
        Shape[] shapes = {
            new Circle("Red", 5.0),
            new Rectangle("Blue", 4.0, 6.0),
            new Triangle("Green", 3.0, 4.0, 5.0)
        };
        
        for (Shape shape : shapes) {
            shape.processShape();
        }
        
        // Interface demo
        System.out.println("=== Interface Demo ===");
        GraphicsCircle gCircle = new GraphicsCircle(0, 0, 3.0, "Purple");
        gCircle.draw();
        gCircle.move(5, 10);
        gCircle.rotate(45);
        gCircle.highlight();
        
        // Payment processor demo
        System.out.println("\n=== Payment Processor Demo ===");
        PaymentProcessor creditCard = new CreditCardProcessor("Visa", 0.03);
        PaymentProcessor paypal = new PayPalProcessor("user@example.com");
        
        creditCard.processPayment(100.0, "USD");
        paypal.processPayment(75.0, "EUR");
        
        // Plugin system demo
        System.out.println("\n=== Plugin System Demo ===");
        PluginManager manager = new PluginManager("2.0.1");
        
        manager.registerPlugin(new DatabasePlugin("jdbc:mysql://localhost:3306/mydb"));
        manager.registerPlugin(new SecurityPlugin(5));
        
        manager.listPlugins();
        manager.initializeAll();
        manager.executeAll();
        manager.shutdownAll();
    }
}
```

### ⚠️ Common Pitfalls

1. **Confusing abstract classes with interfaces**: Use abstract classes for IS-A relationships, interfaces for CAN-DO capabilities
2. **Not implementing all abstract methods**: Concrete subclasses must implement all abstract methods
3. **Overusing inheritance**: Sometimes composition is better than inheritance
4. **Forgetting @Override annotation**: Always use it when implementing interface methods
5. **Interface pollution**: Don't put too many methods in a single interface

### ✅ Best Practices

1. **Use interfaces to define contracts** and abstract classes for shared implementation
2. **Keep interfaces small and focused** (Interface Segregation Principle)
3. **Use default methods** to evolve interfaces without breaking existing implementations
4. **Prefer composition over inheritance** when possible
5. **Use @FunctionalInterface** for single-method interfaces intended for lambdas
6. **Document interface contracts** clearly for implementers

### 🏋️ Exercise 11: Media Player System

Create a flexible media player system using abstract classes and interfaces:

```java
// Design and implement:

abstract class MediaFile {
    // Common properties: filename, size, duration
    // Abstract methods: play(), pause(), stop()
    // Concrete methods: getInfo(), isPlaying()
}

interface Playable {
    void play();
    void pause();
    void stop();
    boolean isPlaying();
}

interface Downloadable {
    void download(String url);
    double getDownloadProgress();
    boolean isDownloaded();
}

interface Streamable {
    void startStream(String streamUrl);
    void stopStream();
    int getBufferLevel();
}

// Implement concrete classes:
// - AudioFile (extends MediaFile, implements Playable, Downloadable)
// - VideoFile (extends MediaFile, implements Playable, Downloadable, Streamable)
// - StreamingAudio (implements Playable, Streamable)

// Create a MediaPlayer that can handle any Playable content
// Demonstrate polymorphism with different media types
```

[↑ Back to Top](#-table-of-contents)

---

## 12. Exception Handling

📊 **Chapter 12 of 35**

🎯 **Learning Objectives:**
- Master try-catch-finally blocks and exception propagation
- Understand checked vs unchecked exceptions
- Learn to create custom exceptions
- Practice try-with-resources for automatic resource management
- Explore best practices for exception handling and error recovery

⏱️ **Estimated Reading Time:** 40 minutes
📋 **Prerequisites:** Understanding of classes, inheritance, and method calls

### Understanding Exceptions

Exceptions are events that disrupt the normal flow of program execution. Java provides a robust exception handling mechanism to deal with runtime errors gracefully.

```java
// Exception hierarchy demonstration
public class ExceptionBasics {
    public static void main(String[] args) {
        demonstrateBasicExceptions();
        demonstrateExceptionTypes();
        demonstrateExceptionPropagation();
    }
    
    private static void demonstrateBasicExceptions() {
        System.out.println("=== Basic Exception Handling ===");
        
        // Example 1: Division by zero
        try {
            int result = 10 / 0;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero: " + e.getMessage());
        }
        
        // Example 2: Array index out of bounds
        try {
            int[] numbers = {1, 2, 3};
            System.out.println("Number at index 5: " + numbers[5]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index out of bounds: " + e.getMessage());
        }
        
        // Example 3: Null pointer exception
        try {
            String text = null;
            int length = text.length();
            System.out.println("Text length: " + length);
        } catch (NullPointerException e) {
            System.out.println("Null pointer exception: " + e.getMessage());
        }
        
        System.out.println("Program continues after exceptions...\n");
    }
    
    private static void demonstrateExceptionTypes() {
        System.out.println("=== Exception Types ===");
        
        // Checked exception - must be handled
        try {
            java.io.FileReader file = new java.io.FileReader("nonexistent.txt");
        } catch (java.io.FileNotFoundException e) {
            System.out.println("File not found (checked exception): " + e.getMessage());
        }
        
        // Unchecked exception - runtime exception
        try {
            String number = "abc";
            int parsed = Integer.parseInt(number);
        } catch (NumberFormatException e) {
            System.out.println("Number format error (unchecked): " + e.getMessage());
        }
        
        // Error - serious problems, usually not caught
        try {
            // This would cause OutOfMemoryError in real scenario
            // int[] hugArray = new int[Integer.MAX_VALUE];
            System.out.println("Simulating error handling...");
        } catch (OutOfMemoryError e) {
            System.out.println("Out of memory error: " + e.getMessage());
        }
        
        System.out.println();
    }
    
    private static void demonstrateExceptionPropagation() {
        System.out.println("=== Exception Propagation ===");
        
        try {
            method1();
        } catch (Exception e) {
            System.out.println("Caught in main: " + e.getClass().getSimpleName() + 
                             " - " + e.getMessage());
            
            // Print stack trace
            System.out.println("Stack trace:");
            e.printStackTrace();
        }
    }
    
    private static void method1() throws Exception {
        System.out.println("In method1");
        method2();
    }
    
    private static void method2() throws Exception {
        System.out.println("In method2");
        method3();
    }
    
    private static void method3() throws Exception {
        System.out.println("In method3");
        throw new Exception("Exception from method3");
    }
}
```

### Try-Catch-Finally Blocks

```java
public class TryCatchFinally {
    public static void main(String[] args) {
        demonstrateBasicTryCatch();
        demonstrateMultipleCatch();
        demonstrateFinallyBlock();
        demonstrateTryWithResources();
    }
    
    private static void demonstrateBasicTryCatch() {
        System.out.println("=== Basic Try-Catch ===");
        
        // Simple try-catch
        try {
            int[] numbers = {1, 2, 3};
            System.out.println("Accessing valid index: " + numbers[1]);
            System.out.println("Accessing invalid index: " + numbers[10]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
        
        System.out.println("Execution continues...\n");
    }
    
    private static void demonstrateMultipleCatch() {
        System.out.println("=== Multiple Catch Blocks ===");
        
        String[] testCases = {"123", "abc", null};
        
        for (int i = 0; i < testCases.length + 1; i++) {
            try {
                String value = testCases[i]; // May throw ArrayIndexOutOfBoundsException
                int number = Integer.parseInt(value); // May throw NumberFormatException or NullPointerException
                int result = 100 / number; // May throw ArithmeticException
                System.out.println("Result for '" + value + "': " + result);
                
            } catch (ArrayIndexOutOfBoundsException e) {
                System.out.println("Array index out of bounds: " + e.getMessage());
            } catch (NumberFormatException e) {
                System.out.println("Invalid number format: " + e.getMessage());
            } catch (NullPointerException e) {
                System.out.println("Null value encountered");
            } catch (ArithmeticException e) {
                System.out.println("Arithmetic error: " + e.getMessage());
            } catch (Exception e) {
                // Generic catch - should be last
                System.out.println("Unexpected exception: " + e.getClass().getSimpleName());
            }
        }
        
        System.out.println();
    }
    
    private static void demonstrateFinallyBlock() {
        System.out.println("=== Finally Block ===");
        
        // Finally block always executes
        try {
            System.out.println("In try block");
            int result = 10 / 2;
            System.out.println("Result: " + result);
        } catch (Exception e) {
            System.out.println("In catch block");
        } finally {
            System.out.println("In finally block - always executes");
        }
        
        // Finally executes even with exception
        try {
            System.out.println("In try block with exception");
            int result = 10 / 0;
            System.out.println("This won't execute");
        } catch (ArithmeticException e) {
            System.out.println("In catch block: " + e.getMessage());
        } finally {
            System.out.println("Finally executes even with exception");
        }
        
        // Finally executes even with return
        System.out.println("Return value: " + methodWithFinally());
        
        System.out.println();
    }
    
    private static int methodWithFinally() {
        try {
            System.out.println("In try - about to return");
            return 1;
        } finally {
            System.out.println("Finally executes even before return");
            // Note: Don't return from finally - it overrides try/catch returns
        }
    }
    
    private static void demonstrateTryWithResources() {
        System.out.println("=== Try-With-Resources ===");
        
        // Traditional approach (verbose)
        java.io.BufferedReader reader = null;
        try {
            reader = new java.io.BufferedReader(new java.io.StringReader("Hello\nWorld"));
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println("Read: " + line);
            }
        } catch (java.io.IOException e) {
            System.out.println("IO Error: " + e.getMessage());
        } finally {
            if (reader != null) {
                try {
                    reader.close();
                } catch (java.io.IOException e) {
                    System.out.println("Error closing reader: " + e.getMessage());
                }
            }
        }
        
        // Try-with-resources (automatic resource management)
        try (java.io.BufferedReader autoReader = new java.io.BufferedReader(
                new java.io.StringReader("Auto\nManaged\nResource"))) {
            
            String line;
            while ((line = autoReader.readLine()) != null) {
                System.out.println("Auto-read: " + line);
            }
        } catch (java.io.IOException e) {
            System.out.println("IO Error: " + e.getMessage());
        }
        // Resource automatically closed here
        
        System.out.println();
    }
}
```

### Custom Exceptions

```java
// Custom checked exception
class InsufficientFundsException extends Exception {
    private double balance;
    private double requestedAmount;
    
    public InsufficientFundsException(double balance, double requestedAmount) {
        super(String.format("Insufficient funds: Balance %.2f, Requested %.2f", 
                          balance, requestedAmount));
        this.balance = balance;
        this.requestedAmount = requestedAmount;
    }
    
    public double getBalance() { return balance; }
    public double getRequestedAmount() { return requestedAmount; }
    public double getShortfall() { return requestedAmount - balance; }
}

// Custom unchecked exception
class InvalidAccountException extends RuntimeException {
    private String accountNumber;
    
    public InvalidAccountException(String accountNumber) {
        super("Invalid account number: " + accountNumber);
        this.accountNumber = accountNumber;
    }
    
    public InvalidAccountException(String accountNumber, String message) {
        super(message);
        this.accountNumber = accountNumber;
    }
    
    public String getAccountNumber() { return accountNumber; }
}

// Custom exception with nested cause
class AccountOperationException extends Exception {
    public AccountOperationException(String message) {
        super(message);
    }
    
    public AccountOperationException(String message, Throwable cause) {
        super(message, cause);
    }
}

// Bank account class demonstrating custom exceptions
class BankAccount {
    private String accountNumber;
    private String ownerName;
    private double balance;
    private boolean isActive;
    
    public BankAccount(String accountNumber, String ownerName, double initialBalance) {
        if (accountNumber == null || accountNumber.trim().isEmpty()) {
            throw new InvalidAccountException(accountNumber, "Account number cannot be null or empty");
        }
        
        this.accountNumber = accountNumber;
        this.ownerName = ownerName;
        this.balance = Math.max(0, initialBalance);
        this.isActive = true;
    }
    
    public void deposit(double amount) throws AccountOperationException {
        if (!isActive) {
            throw new AccountOperationException("Cannot deposit to inactive account: " + accountNumber);
        }
        
        if (amount <= 0) {
            throw new IllegalArgumentException("Deposit amount must be positive: " + amount);
        }
        
        try {
            // Simulate potential system error
            if (Math.random() < 0.1) { // 10% chance of system error
                throw new RuntimeException("Database connection failed");
            }
            
            balance += amount;
            System.out.println(String.format("Deposited %.2f to account %s. New balance: %.2f", 
                             amount, accountNumber, balance));
            
        } catch (RuntimeException e) {
            throw new AccountOperationException("Deposit failed for account " + accountNumber, e);
        }
    }
    
    public void withdraw(double amount) throws InsufficientFundsException, AccountOperationException {
        if (!isActive) {
            throw new AccountOperationException("Cannot withdraw from inactive account: " + accountNumber);
        }
        
        if (amount <= 0) {
            throw new IllegalArgumentException("Withdrawal amount must be positive: " + amount);
        }
        
        if (amount > balance) {
            throw new InsufficientFundsException(balance, amount);
        }
        
        try {
            // Simulate potential system error
            if (Math.random() < 0.05) { // 5% chance of system error
                throw new RuntimeException("Network timeout");
            }
            
            balance -= amount;
            System.out.println(String.format("Withdrew %.2f from account %s. New balance: %.2f", 
                             amount, accountNumber, balance));
            
        } catch (RuntimeException e) {
            throw new AccountOperationException("Withdrawal failed for account " + accountNumber, e);
        }
    }
    
    public double getBalance() { return balance; }
    public String getAccountNumber() { return accountNumber; }
    public String getOwnerName() { return ownerName; }
    public boolean isActive() { return isActive; }
    
    public void closeAccount() throws AccountOperationException {
        if (balance != 0) {
            throw new AccountOperationException(
                "Cannot close account with non-zero balance: " + balance);
        }
        isActive = false;
        System.out.println("Account " + accountNumber + " closed successfully");
    }
}

// Demo class
public class CustomExceptionsDemo {
    public static void main(String[] args) {
        System.out.println("=== Custom Exceptions Demo ===\n");
        
        try {
            BankAccount account = new BankAccount("ACC123", "John Doe", 1000.0);
            
            // Successful operations
            account.deposit(500.0);
            account.withdraw(200.0);
            
            // This will cause InsufficientFundsException
            try {
                account.withdraw(2000.0);
            } catch (InsufficientFundsException e) {
                System.out.println("Withdrawal failed: " + e.getMessage());
                System.out.println("Shortfall: $" + String.format("%.2f", e.getShortfall()));
                System.out.println("Current balance: $" + String.format("%.2f", e.getBalance()));
            }
            
            // Multiple attempts to trigger system errors
            for (int i = 0; i < 5; i++) {
                try {
                    account.deposit(100.0);
                } catch (AccountOperationException e) {
                    System.out.println("System error during deposit: " + e.getMessage());
                    if (e.getCause() != null) {
                        System.out.println("Caused by: " + e.getCause().getMessage());
                    }
                    break;
                }
            }
            
        } catch (InvalidAccountException e) {
            System.out.println("Invalid account: " + e.getMessage());
            System.out.println("Account number: " + e.getAccountNumber());
        } catch (AccountOperationException e) {
            System.out.println("Account operation failed: " + e.getMessage());
        }
        
        // Test invalid account creation
        try {
            BankAccount invalidAccount = new BankAccount("", "Invalid User", 100.0);
        } catch (InvalidAccountException e) {
            System.out.println("Failed to create account: " + e.getMessage());
        }
    }
}
```

### Exception Handling Best Practices

```java
public class ExceptionBestPractices {
    
    // Good: Specific exception handling
    public static void goodExceptionHandling() {
        System.out.println("=== Good Exception Handling ===");
        
        try {
            processUserInput("invalid_number");
        } catch (NumberFormatException e) {
            System.out.println("Invalid number format. Please enter a valid number.");
            // Log the technical details
            logError("NumberFormatException in processUserInput", e);
        } catch (IllegalArgumentException e) {
            System.out.println("Invalid input: " + e.getMessage());
            logError("IllegalArgumentException in processUserInput", e);
        }
    }
    
    // Bad: Generic exception handling
    public static void badExceptionHandling() {
        System.out.println("=== Bad Exception Handling ===");
        
        try {
            processUserInput("invalid_number");
        } catch (Exception e) {
            // Too generic - loses specific error information
            System.out.println("Something went wrong: " + e.getMessage());
        }
    }
    
    private static void processUserInput(String input) {
        if (input == null) {
            throw new IllegalArgumentException("Input cannot be null");
        }
        
        int number = Integer.parseInt(input); // May throw NumberFormatException
        
        if (number < 0) {
            throw new IllegalArgumentException("Number must be positive");
        }
    }
    
    // Good: Resource management with try-with-resources
    public static void goodResourceManagement() {
        System.out.println("=== Good Resource Management ===");
        
        try (java.io.BufferedWriter writer = java.nio.file.Files.newBufferedWriter(
                java.nio.file.Paths.get("output.txt"))) {
            
            writer.write("Hello, World!");
            writer.newLine();
            writer.write("Automatic resource management");
            
        } catch (java.io.IOException e) {
            System.out.println("File operation failed: " + e.getMessage());
            logError("IOException in file writing", e);
        }
        // Writer is automatically closed here
    }
    
    // Method that properly declares exceptions
    public static java.util.List<String> readFile(String filename) 
            throws java.io.IOException, SecurityException {
        
        java.util.List<String> lines = new java.util.ArrayList<>();
        
        try (java.io.BufferedReader reader = java.nio.file.Files.newBufferedReader(
                java.nio.file.Paths.get(filename))) {
            
            String line;
            while ((line = reader.readLine()) != null) {
                lines.add(line);
            }
            
        } catch (java.io.IOException e) {
            // Add context to the exception
            throw new java.io.IOException("Failed to read file: " + filename, e);
        }
        
        return lines;
    }
    
    // Exception translation - converting low-level to high-level exceptions
    public static void saveUserData(String userId, String data) throws DataProcessingException {
        try {
            // Low-level file operations
            java.nio.file.Path userFile = java.nio.file.Paths.get("users", userId + ".dat");
            java.nio.file.Files.createDirectories(userFile.getParent());
            java.nio.file.Files.write(userFile, data.getBytes());
            
        } catch (java.io.IOException e) {
            // Translate to business-level exception
            throw new DataProcessingException("Failed to save user data for: " + userId, e);
        } catch (SecurityException e) {
            throw new DataProcessingException("Access denied while saving user data: " + userId, e);
        }
    }
    
    // Defensive programming with validation
    public static double calculatePercentage(double part, double whole) {
        // Validate inputs
        if (Double.isNaN(part) || Double.isNaN(whole)) {
            throw new IllegalArgumentException("Arguments cannot be NaN");
        }
        
        if (Double.isInfinite(part) || Double.isInfinite(whole)) {
            throw new IllegalArgumentException("Arguments cannot be infinite");
        }
        
        if (whole == 0) {
            throw new IllegalArgumentException("Whole cannot be zero");
        }
        
        if (part < 0 || whole < 0) {
            throw new IllegalArgumentException("Arguments must be non-negative");
        }
        
        return (part / whole) * 100;
    }
    
    private static void logError(String message, Throwable throwable) {
        // In real application, use proper logging framework
        System.err.println("ERROR: " + message);
        System.err.println("Exception: " + throwable.getClass().getSimpleName() + 
                          " - " + throwable.getMessage());
        // throwable.printStackTrace(); // For debugging
    }
    
    public static void main(String[] args) {
        goodExceptionHandling();
        badExceptionHandling();
        goodResourceManagement();
        
        // Demonstrate percentage calculation with validation
        try {
            double percentage = calculatePercentage(25, 100);
            System.out.println("Percentage: " + percentage + "%");
            
            // This will throw exception
            calculatePercentage(50, 0);
        } catch (IllegalArgumentException e) {
            System.out.println("Calculation error: " + e.getMessage());
        }
        
        // Demonstrate exception translation
        try {
            saveUserData("user123", "Important user data");
            System.out.println("User data saved successfully");
        } catch (DataProcessingException e) {
            System.out.println("Business error: " + e.getMessage());
            if (e.getCause() != null) {
                System.out.println("Technical cause: " + e.getCause().getClass().getSimpleName());
            }
        }
    }
}

// Custom business exception
class DataProcessingException extends Exception {
    public DataProcessingException(String message) {
        super(message);
    }
    
    public DataProcessingException(String message, Throwable cause) {
        super(message, cause);
    }
}
```

### Real-World Example: Configuration Manager

```java
import java.io.*;
import java.util.*;
import java.util.concurrent.ConcurrentHashMap;

// Custom exceptions for configuration management
class ConfigurationException extends Exception {
    public ConfigurationException(String message) { super(message); }
    public ConfigurationException(String message, Throwable cause) { super(message, cause); }
}

class ConfigurationNotFoundException extends ConfigurationException {
    public ConfigurationNotFoundException(String configName) {
        super("Configuration not found: " + configName);
    }
}

class InvalidConfigurationFormatException extends ConfigurationException {
    private int lineNumber;
    
    public InvalidConfigurationFormatException(String message, int lineNumber) {
        super(message + " at line " + lineNumber);
        this.lineNumber = lineNumber;
    }
    
    public int getLineNumber() { return lineNumber; }
}

// Configuration manager with comprehensive exception handling
class ConfigurationManager {
    private Map<String, String> properties;
    private String configFile;
    private long lastModified;
    
    public ConfigurationManager(String configFile) throws ConfigurationException {
        this.configFile = configFile;
        this.properties = new ConcurrentHashMap<>();
        loadConfiguration();
    }
    
    private void loadConfiguration() throws ConfigurationException {
        File file = new File(configFile);
        
        if (!file.exists()) {
            throw new ConfigurationNotFoundException(configFile);
        }
        
        if (!file.canRead()) {
            throw new ConfigurationException("Cannot read configuration file: " + configFile);
        }
        
        try (BufferedReader reader = new BufferedReader(new FileReader(file))) {
            properties.clear();
            String line;
            int lineNumber = 0;
            
            while ((line = reader.readLine()) != null) {
                lineNumber++;
                
                // Skip empty lines and comments
                line = line.trim();
                if (line.isEmpty() || line.startsWith("#")) {
                    continue;
                }
                
                // Parse key=value format
                int equalsIndex = line.indexOf('=');
                if (equalsIndex == -1) {
                    throw new InvalidConfigurationFormatException(
                        "Missing '=' in configuration line: " + line, lineNumber);
                }
                
                if (equalsIndex == 0) {
                    throw new InvalidConfigurationFormatException(
                        "Missing key in configuration line: " + line, lineNumber);
                }
                
                String key = line.substring(0, equalsIndex).trim();
                String value = line.substring(equalsIndex + 1).trim();
                
                if (key.isEmpty()) {
                    throw new InvalidConfigurationFormatException(
                        "Empty key in configuration line: " + line, lineNumber);
                }
                
                properties.put(key, value);
            }
            
            lastModified = file.lastModified();
            System.out.println("Configuration loaded successfully from: " + configFile);
            System.out.println("Properties loaded: " + properties.size());
            
        } catch (IOException e) {
            throw new ConfigurationException("Failed to read configuration file: " + configFile, e);
        }
    }
    
    public String getProperty(String key) throws ConfigurationException {
        if (key == null || key.trim().isEmpty()) {
            throw new IllegalArgumentException("Property key cannot be null or empty");
        }
        
        checkForConfigurationUpdates();
        
        String value = properties.get(key);
        if (value == null) {
            throw new ConfigurationException("Property not found: " + key);
        }
        
        return value;
    }
    
    public String getProperty(String key, String defaultValue) {
        try {
            return getProperty(key);
        } catch (ConfigurationException e) {
            return defaultValue;
        }
    }
    
    public int getIntProperty(String key) throws ConfigurationException {
        String value = getProperty(key);
        try {
            return Integer.parseInt(value);
        } catch (NumberFormatException e) {
            throw new ConfigurationException(
                "Property '" + key + "' is not a valid integer: " + value, e);
        }
    }
    
    public boolean getBooleanProperty(String key) throws ConfigurationException {
        String value = getProperty(key).toLowerCase();
        if ("true".equals(value) || "yes".equals(value) || "1".equals(value)) {
            return true;
        } else if ("false".equals(value) || "no".equals(value) || "0".equals(value)) {
            return false;
        } else {
            throw new ConfigurationException(
                "Property '" + key + "' is not a valid boolean: " + value);
        }
    }
    
    private void checkForConfigurationUpdates() throws ConfigurationException {
        File file = new File(configFile);
        if (file.exists() && file.lastModified() > lastModified) {
            System.out.println("Configuration file updated, reloading...");
            loadConfiguration();
        }
    }
    
    public void setProperty(String key, String value) throws ConfigurationException {
        if (key == null || key.trim().isEmpty()) {
            throw new IllegalArgumentException("Property key cannot be null or empty");
        }
        
        properties.put(key, value != null ? value : "");
        saveConfiguration();
    }
    
    private void saveConfiguration() throws ConfigurationException {
        File backupFile = new File(configFile + ".backup");
        File originalFile = new File(configFile);
        
        try {
            // Create backup
            if (originalFile.exists()) {
                Files.copy(originalFile.toPath(), backupFile.toPath(), 
                          java.nio.file.StandardCopyOption.REPLACE_EXISTING);
            }
            
            // Write new configuration
            try (PrintWriter writer = new PrintWriter(new FileWriter(originalFile))) {
                writer.println("# Configuration file");
                writer.println("# Generated on: " + new Date());
                writer.println();
                
                // Sort properties for consistent output
                properties.entrySet().stream()
                    .sorted(Map.Entry.comparingByKey())
                    .forEach(entry -> writer.println(entry.getKey() + "=" + entry.getValue()));
            }
            
            lastModified = originalFile.lastModified();
            System.out.println("Configuration saved successfully");
            
        } catch (IOException e) {
            // Restore backup if save failed
            if (backupFile.exists()) {
                try {
                    Files.copy(backupFile.toPath(), originalFile.toPath(),
                              java.nio.file.StandardCopyOption.REPLACE_EXISTING);
                } catch (IOException restoreError) {
                    e.addSuppressed(restoreError);
                }
            }
            throw new ConfigurationException("Failed to save configuration", e);
        }
    }
    
    public Set<String> getPropertyNames() {
        return new HashSet<>(properties.keySet());
    }
    
    public void printConfiguration() {
        System.out.println("=== Current Configuration ===");
        properties.entrySet().stream()
            .sorted(Map.Entry.comparingByKey())
            .forEach(entry -> System.out.println(entry.getKey() + " = " + entry.getValue()));
    }
}

// Demo application
public class ConfigurationDemo {
    public static void main(String[] args) {
        System.out.println("=== Configuration Manager Demo ===\n");
        
        // Create a sample configuration file
        createSampleConfigFile();
        
        try {
            ConfigurationManager config = new ConfigurationManager("app.properties");
            
            // Read various property types
            System.out.println("App Name: " + config.getProperty("app.name"));
            System.out.println("Version: " + config.getProperty("app.version"));
            System.out.println("Port: " + config.getIntProperty("server.port"));
            System.out.println("Debug Mode: " + config.getBooleanProperty("debug.enabled"));
            
            // Use default values
            String theme = config.getProperty("ui.theme", "default");
            System.out.println("UI Theme: " + theme);
            
            // Modify configuration
            config.setProperty("last.run", new Date().toString());
            
            config.printConfiguration();
            
        } catch (ConfigurationNotFoundException e) {
            System.err.println("Configuration file not found: " + e.getMessage());
        } catch (InvalidConfigurationFormatException e) {
            System.err.println("Invalid configuration format: " + e.getMessage());
            System.err.println("Line number: " + e.getLineNumber());
        } catch (ConfigurationException e) {
            System.err.println("Configuration error: " + e.getMessage());
            if (e.getCause() != null) {
                System.err.println("Caused by: " + e.getCause().getMessage());
            }
        }
        
        // Demonstrate error handling with invalid file
        try {
            ConfigurationManager badConfig = new ConfigurationManager("nonexistent.properties");
        } catch (ConfigurationException e) {
            System.err.println("Expected error: " + e.getMessage());
        }
    }
    
    private static void createSampleConfigFile() {
        try (PrintWriter writer = new PrintWriter(new FileWriter("app.properties"))) {
            writer.println("# Sample application configuration");
            writer.println("app.name=My Java Application");
            writer.println("app.version=1.0.0");
            writer.println("server.port=8080");
            writer.println("debug.enabled=true");
            writer.println("database.url=jdbc:mysql://localhost:3306/mydb");
            writer.println("");
            writer.println("# UI Settings");
            writer.println("ui.title=Application Dashboard");
        } catch (IOException e) {
            System.err.println("Failed to create sample config file: " + e.getMessage());
        }
    }
}
```

### ⚠️ Common Pitfalls

1. **Catching Exception instead of specific exceptions**: Be specific with exception handling
2. **Ignoring exceptions**: Never use empty catch blocks
3. **Not using try-with-resources**: Always use it for resource management
4. **Returning in finally blocks**: This overrides return values from try/catch
5. **Not preserving original exceptions**: Use chained exceptions to maintain error context

### ✅ Best Practices

1. **Catch specific exceptions** rather than generic Exception class
2. **Use try-with-resources** for automatic resource management
3. **Create meaningful custom exceptions** with context information
4. **Log exceptions properly** with appropriate detail levels
5. **Fail fast** - validate inputs early and throw exceptions immediately
6. **Use exception chaining** to preserve original error context

### 🏋️ Exercise 12: File Processing System

Create a robust file processing system with comprehensive exception handling:

```java
// Design and implement:

class FileProcessor {
    // Methods that demonstrate different exception handling patterns:
    // - processTextFile(String filename) throws FileProcessingException
    // - validateFileFormat(File file) throws InvalidFileFormatException
    // - backupFile(File original) throws BackupException
    // - processInBatches(List<File> files) // Handle partial failures
}

// Custom exceptions:
// - FileProcessingException (checked)
// - InvalidFileFormatException (checked)
// - BackupException (checked)
// - ProcessingInterruptedException (unchecked)

// Requirements:
// - Use try-with-resources for file operations
// - Implement proper exception chaining
// - Create detailed error messages with context
// - Handle both individual file errors and batch processing failures
// - Include recovery mechanisms where appropriate
```

[↑ Back to Top](#-table-of-contents)

---

## Remaining Sections Overview

The following sections complete the comprehensive Java documentation. Due to space constraints, here's an overview of the remaining essential topics:

### 13. Generics
- Generic classes and methods
- Type parameters and wildcards
- Bounded type parameters
- Generic inheritance and erasure

### 14. Collections Framework
- List, Set, Map interfaces and implementations
- Collection utilities and algorithms
- Comparators and sorting
- Concurrent collections

### 15. Lambda Expressions & Functional Programming
- Functional interfaces and method references
- Stream operations and pipelines
- Optional class for null safety
- Functional programming patterns

### 16. Streams API
- Stream creation and intermediate operations
- Terminal operations and collectors
- Parallel streams and performance
- Custom collectors and stream patterns

### 17-20. Concurrency & Multithreading
- Thread fundamentals and synchronization
- Executor framework and thread pools
- CompletableFuture and async programming
- Thread safety and concurrent data structures

### 21-24. Enterprise Features
- Annotations and reflection
- Module system (JPMS)
- Records and pattern matching
- Virtual threads (Project Loom)

### 25-27. I/O & Networking
- File I/O and NIO.2
- Network programming and HTTP client
- Serialization and data persistence

### 28-32. Real-World Applications & Best Practices
- REST API development
- Database integration with JDBC
- Unit testing with JUnit 5
- Performance optimization techniques
- Design patterns and architectural best practices

Each section follows the same comprehensive format with:
- Learning objectives and prerequisites
- Detailed explanations with examples
- Real-world applications and demos
- Common pitfalls and best practices
- Hands-on exercises

This documentation provides a complete learning path from Java fundamentals to advanced enterprise development.

**Abstract Class**: A class that cannot be instantiated and may contain abstract methods that must be implemented by subclasses.

**Annotation**: Metadata that provides information about code elements, used by the compiler, runtime, or development tools.

**API (Application Programming Interface)**: A set of classes, interfaces, and methods that provide functionality for building applications.

**Autoboxing**: Automatic conversion of primitive types to their corresponding wrapper classes.

**Bytecode**: Platform-independent intermediate code that Java source code compiles to, executed by the JVM.

**Class**: A blueprint or template for creating objects, defining their attributes and behaviors.

**ClassPath**: The path that tells the JVM where to find class files and libraries.

**Constructor**: A special method used to initialize objects when they are created.

**Encapsulation**: The bundling of data and methods that operate on that data within a single unit (class).

**Exception**: An event that disrupts normal program flow, handled using try-catch blocks.

**Garbage Collection**: Automatic memory management that reclaims memory used by objects no longer referenced.

**Generics**: A feature that allows classes and methods to operate on objects of various types while providing compile-time type safety.

**Inheritance**: A mechanism where one class acquires properties and methods of another class.

**Interface**: A contract that defines method signatures that implementing classes must provide.

**JDK (Java Development Kit)**: The complete development environment including compiler, debugger, and other tools.

**JRE (Java Runtime Environment)**: The runtime environment containing JVM and standard libraries needed to run Java applications.

**JVM (Java Virtual Machine)**: The runtime engine that executes Java bytecode on specific platforms.

**Lambda Expression**: Anonymous functions that provide a concise way to represent functional interfaces.

**Method Overloading**: Having multiple methods with the same name but different parameters.

**Method Overriding**: Providing a specific implementation of a method in a subclass that is already defined in its parent class.

**Object**: An instance of a class containing data and methods defined by the class.

**Package**: A namespace that organizes related classes and interfaces.

**Polymorphism**: The ability of objects to take multiple forms, allowing the same interface to be used for different underlying data types.

**Record**: A special class type for immutable data carriers (Java 14+).

**Reflection**: The ability to examine and modify program structure and behavior at runtime.

**Serialization**: The process of converting objects into a byte stream for storage or transmission.

**Static**: Keyword indicating that a method or variable belongs to the class rather than instances.

**Stream**: A sequence of elements supporting sequential and parallel aggregate operations (Java 8+).

**Thread**: A lightweight subprocess that allows concurrent execution of code.

**Unboxing**: Automatic conversion of wrapper classes to their corresponding primitive types.

**Variable**: A memory location with a name that stores data.

**Virtual Thread**: Lightweight threads introduced in Java 21 for improved concurrency performance.

## 34. Quick Reference Card

### 📋 **Data Types**
```java
// Primitives
byte b = 127;           // 8-bit signed integer
short s = 32767;        // 16-bit signed integer
int i = 2147483647;     // 32-bit signed integer
long l = 9223372036854775807L; // 64-bit signed integer
float f = 3.14f;        // 32-bit floating point
double d = 3.14159;     // 64-bit floating point
char c = 'A';           // 16-bit Unicode character
boolean flag = true;    // true or false

// Reference types
String str = "Hello";
int[] array = {1, 2, 3};
List<String> list = new ArrayList<>();
```

### 🔧 **Operators**
```java
// Arithmetic: +, -, *, /, %
// Relational: <, >, <=, >=, ==, !=
// Logical: &&, ||, !
// Bitwise: &, |, ^, ~, <<, >>, >>>
// Assignment: =, +=, -=, *=, /=, %=
// Unary: ++, --, +, -
// Ternary: condition ? value1 : value2
```

### 🎯 **Control Flow**
```java
// if statement
if (condition) {
    // code
} else if (condition2) {
    // code
} else {
    // code
}

// switch statement
switch (variable) {
    case value1 -> action1;
    case value2 -> action2;
    default -> defaultAction;
}

// for loop
for (int i = 0; i < 10; i++) {
    // code
}

// enhanced for loop
for (Type item : collection) {
    // code
}

// while loop
while (condition) {
    // code
}

// do-while loop
do {
    // code
} while (condition);
```

### 🏗️ **Class Structure**
```java
public class ClassName {
    // Fields
    private int field;
    public static final String CONSTANT = "value";

    // Constructor
    public ClassName(int field) {
        this.field = field;
    }

    // Methods
    public int getField() {
        return field;
    }

    public void setField(int field) {
        this.field = field;
    }

    // Static method
    public static void staticMethod() {
        // code
    }
}
```

### 🚨 **Exception Handling**
```java
try {
    // risky code
} catch (SpecificException e) {
    // handle specific exception
} catch (Exception e) {
    // handle general exception
} finally {
    // cleanup code
}

// Try-with-resources
try (Resource resource = new Resource()) {
    // use resource
} catch (Exception e) {
    // handle exception
}
```

### 📚 **Collections Framework**
```java
// List
List<String> list = new ArrayList<>();
list.add("item");
list.get(0);

// Set
Set<String> set = new HashSet<>();
set.add("unique");

// Map
Map<String, Integer> map = new HashMap<>();
map.put("key", 42);
map.get("key");

// Iteration
for (String item : collection) { }
collection.forEach(item -> System.out.println(item));
```

### 🧮 **Lambda Expressions**
```java
// Basic lambda
(parameters) -> expression
(parameters) -> { statements; }

// Examples
list.forEach(item -> System.out.println(item));
list.stream().filter(s -> s.length() > 3).collect(Collectors.toList());
Runnable task = () -> System.out.println("Running");
```

### 🌊 **Streams API**
```java
List<String> result = list.stream()
    .filter(s -> s.startsWith("A"))
    .map(String::toUpperCase)
    .sorted()
    .collect(Collectors.toList());
```

## 35. Further Reading

### 📖 **Official Documentation**
- [Oracle Java Documentation](https://docs.oracle.com/en/java/)
- [Java Language Specification](https://docs.oracle.com/javase/specs/)
- [Java API Documentation](https://docs.oracle.com/en/java/javase/21/docs/api/)

### 🎓 **Learning Resources**
- [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/)
- [OpenJDK Website](https://openjdk.org/)
- [Java Code Geeks](https://www.javacodegeeks.com/)
- [Baeldung Java Tutorials](https://www.baeldung.com/)

### 📚 **Recommended Books**
- "Effective Java" by Joshua Bloch
- "Java: The Complete Reference" by Herbert Schildt
- "Clean Code" by Robert Martin
- "Java Concurrency in Practice" by Brian Goetz

### 🛠️ **Development Tools**
- [IntelliJ IDEA](https://www.jetbrains.com/idea/)
- [Eclipse IDE](https://www.eclipse.org/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Maven](https://maven.apache.org/)
- [Gradle](https://gradle.org/)

### 🌐 **Community Resources**
- [Stack Overflow Java Tag](https://stackoverflow.com/questions/tagged/java)
- [Reddit r/Java](https://www.reddit.com/r/java/)
- [Java Weekly Newsletter](https://www.baeldung.com/java-weekly-briefing)
- [Oracle Java Community](https://www.oracle.com/java/technologies/community/)

### 🚀 **Advanced Topics**
- Spring Framework
- Hibernate ORM
- Apache Kafka
- Microservices with Spring Boot
- Reactive Programming with Project Reactor

---

*This documentation provides a comprehensive introduction to Java programming. Continue exploring, practicing, and building projects to master the language. Happy coding! ☕*

[↑ Back to Top](#-table-of-contents)
