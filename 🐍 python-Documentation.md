# 🐍 Python Documentation
*Version: 3.12 | Last Updated: January 2024*

Python is a high-level, interpreted programming language known for its simplicity, readability, and versatility. It's widely used for web development, data science, artificial intelligence, automation, and scientific computing.

---

## 📚 Table of Contents

### 🚀 **Part I: Getting Started**
- [Chapter 1: Introduction to Python](#-chapter-1-introduction-to-python)
- [Chapter 2: Installation & Setup](#-chapter-2-installation--setup)
- [Chapter 3: Your First Python Program](#-chapter-3-your-first-python-program)
- [Chapter 4: Python Development Environment](#-chapter-4-python-development-environment)

### 🧱 **Part II: Core Fundamentals**
- [Chapter 5: Basic Syntax & Structure](#-chapter-5-basic-syntax--structure)
- [Chapter 6: Variables & Data Types](#-chapter-6-variables--data-types)
- [Chapter 7: Operators & Expressions](#-chapter-7-operators--expressions)
- [Chapter 8: Input & Output Operations](#-chapter-8-input--output-operations)

### 🔄 **Part III: Control Flow**
- [Chapter 9: Conditional Statements](#-chapter-9-conditional-statements)
- [Chapter 10: Loops & Iteration](#-chapter-10-loops--iteration)
- [Chapter 11: Exception Handling](#-chapter-11-exception-handling)

### 📦 **Part IV: Data Structures**
- [Chapter 12: Lists & Tuples](#-chapter-12-lists--tuples)
- [Chapter 13: Dictionaries & Sets](#-chapter-13-dictionaries--sets)
- [Chapter 14: Strings & Text Processing](#-chapter-14-strings--text-processing)

### ⚡ **Part V: Functions & Modules**
- [Chapter 15: Functions](#-chapter-15-functions)
- [Chapter 16: Lambda Functions & Functional Programming](#-chapter-16-lambda-functions--functional-programming)
- [Chapter 17: Modules & Packages](#-chapter-17-modules--packages)
- [Chapter 18: Standard Library](#-chapter-18-standard-library)

### 🎯 **Part VI: Object-Oriented Programming**
- [Chapter 19: Classes & Objects](#-chapter-19-classes--objects)
- [Chapter 20: Inheritance & Polymorphism](#-chapter-20-inheritance--polymorphism)
- [Chapter 21: Special Methods & Magic Functions](#-chapter-21-special-methods--magic-functions)

### 🚀 **Part VII: Advanced Python**
- [Chapter 22: File I/O & Working with Files](#-chapter-22-file-io--working-with-files)
- [Chapter 23: Regular Expressions](#-chapter-23-regular-expressions)
- [Chapter 24: Decorators & Context Managers](#-chapter-24-decorators--context-managers)
- [Chapter 25: Generators & Iterators](#-chapter-25-generators--iterators)
- [Chapter 26: Concurrency & Parallelism](#-chapter-26-concurrency--parallelism)

### 🌐 **Part VIII: Real-World Applications**
- [Chapter 27: Web Development with Python](#-chapter-27-web-development-with-python)
- [Chapter 28: Data Science & Analytics](#-chapter-28-data-science--analytics)
- [Chapter 29: Database Programming](#-chapter-29-database-programming)
- [Chapter 30: Testing & Debugging](#-chapter-30-testing--debugging)

### 🚀 **Part IX: Projects & Practice**
- [Project 1: Personal Task Manager](#-project-1-personal-task-manager)
- [Project 2: Web Scraper & Data Analyzer](#-project-2-web-scraper--data-analyzer)
- [Project 3: RESTful API with Flask](#-project-3-restful-api-with-flask)

### 📖 **Appendices**
- [Glossary](#-glossary)
- [Quick Reference Card](#-quick-reference-card)
- [Further Reading](#-further-reading)
- [Community Resources](#-community-resources)
- [Contributing Guidelines](#-contributing-guidelines)

---

## 🚀 Chapter 1: Introduction to Python
📊 **Progress:** Chapter 1 of 30  
🎯 **Learning Objectives:** Understand Python's history, philosophy, and use cases  
⏱️ **Estimated Reading Time:** 15 minutes  
📋 **Prerequisites:** None

### What is Python?

Python is a high-level, interpreted programming language created by Guido van Rossum and first released in 1991. Named after the British comedy group Monty Python, Python emphasizes code readability and simplicity, making it an excellent choice for both beginners and experienced developers.

### The Zen of Python

Python's design philosophy is captured in "The Zen of Python" by Tim Peters:

```python
import this
```

Key principles include:
- **Beautiful is better than ugly**
- **Explicit is better than implicit**
- **Simple is better than complex**
- **Readability counts**
- **There should be one obvious way to do it**

### Why Choose Python?

#### 🔥 **Advantages**

1. **Easy to Learn**: Python's syntax closely resembles English, making it accessible to newcomers
2. **Versatile**: Used in web development, data science, AI, automation, and more
3. **Large Community**: Extensive documentation, tutorials, and third-party packages
4. **Cross-platform**: Runs on Windows, macOS, Linux, and many other platforms
5. **Rich Ecosystem**: Over 400,000 packages available on PyPI (Python Package Index)

#### ⚠️ **Limitations**

1. **Slower Execution**: Being interpreted, Python is generally slower than compiled languages
2. **Memory Usage**: Can consume more memory than languages like C or C++
3. **Mobile Development**: Limited options for mobile app development
4. **Runtime Errors**: Some errors only surface during execution

### Python Use Cases

#### 🌐 **Web Development**
- Django and Flask for backend development
- FastAPI for modern API development
- Web scraping with BeautifulSoup and Scrapy

#### 📊 **Data Science & Analytics**
- NumPy for numerical computing
- Pandas for data manipulation
- Matplotlib and Plotly for visualization
- Scikit-learn for machine learning

#### 🤖 **Artificial Intelligence**
- TensorFlow and PyTorch for deep learning
- OpenAI GPT integration
- Computer vision with OpenCV
- Natural language processing with NLTK and spaCy

#### 🔧 **Automation & Scripting**
- System administration tasks
- File processing and organization
- API integration and testing
- DevOps automation

### Python Versions

Python has two major versions:
- **Python 2.x**: Legacy version (deprecated as of January 1, 2020)
- **Python 3.x**: Current version with active development

**Python 3.12** (our focus) introduces several improvements:
- Enhanced error messages
- Improved performance
- New syntax features
- Better type hints support

### 💡 Code Example: Python Philosophy in Action

```python
# Python's emphasis on readability
def calculate_compound_interest(principal, rate, time, compounds_per_year):
    """
    Calculate compound interest using the standard formula.
    
    Args:
        principal: Initial investment amount
        rate: Annual interest rate (as decimal)
        time: Investment period in years
        compounds_per_year: Number of times interest is compounded per year
    
    Returns:
        Final amount after compound interest
    """
    amount = principal * (1 + rate / compounds_per_year) ** (compounds_per_year * time)
    return round(amount, 2)

# Usage example
initial_investment = 1000
annual_rate = 0.05  # 5%
years = 10
compounding_frequency = 12  # Monthly

final_amount = calculate_compound_interest(
    initial_investment, 
    annual_rate, 
    years, 
    compounding_frequency
)

print(f"Initial investment: ${initial_investment:,.2f}")
print(f"After {years} years: ${final_amount:,.2f}")
print(f"Total gain: ${final_amount - initial_investment:,.2f}")
```

### ⚠️ Common Pitfalls

1. **Indentation Matters**: Python uses indentation to define code blocks
2. **Case Sensitivity**: `Variable` and `variable` are different
3. **Version Confusion**: Ensure you're using Python 3.x, not Python 2.x

### ✅ Best Practices

1. **Follow PEP 8**: Python's style guide for readable code
2. **Use Meaningful Names**: Choose descriptive variable and function names
3. **Write Documentation**: Use docstrings to document your functions
4. **Handle Exceptions**: Anticipate and handle potential errors gracefully

### 🏋️ Exercise 1: Getting Familiar with Python
**Difficulty:** 🟢 Beginner  
**Estimated Time:** 10 minutes

Write a Python program that demonstrates Python's readability by creating a simple program that:
1. Asks for the user's name
2. Asks for their favorite number
3. Calculates and displays the square of their favorite number
4. Provides an encouraging message

<details>
<summary>💡 Click to see hints</summary>

- Use the `input()` function to get user input
- Use `int()` to convert string input to integer
- Use f-strings for formatting output
- Remember that `input()` always returns a string

</details>

<details>
<summary>✅ Click to see solution</summary>

```python
# Simple interactive program demonstrating Python's readability
def main():
    """Main function that runs our interactive program."""
    
    # Get user information
    name = input("What's your name? ")
    
    # Get favorite number and convert to integer
    favorite_number_str = input(f"Hi {name}! What's your favorite number? ")
    favorite_number = int(favorite_number_str)
    
    # Calculate the square
    squared_number = favorite_number ** 2
    
    # Display results with encouraging message
    print(f"\nHello {name}!")
    print(f"Your favorite number is {favorite_number}")
    print(f"The square of {favorite_number} is {squared_number}")
    print(f"That's a great number choice, {name}! 🎉")

# Run the program
if __name__ == "__main__":
    main()
```

**Explanation:**
- **Why this approach works**: The code is self-documenting and follows Python's philosophy of readability
- **Key concepts demonstrated**: Functions, user input, string formatting, type conversion
- **Alternative solutions**: Could use single lines instead of variables, but this is more readable
- **Python philosophy**: Notice how the code reads almost like English sentences

</details>

[🔝 Back to Top](#-python-documentation)

---

## 🛠️ Chapter 2: Installation & Setup
📊 **Progress:** Chapter 2 of 30  
🎯 **Learning Objectives:** Install Python 3.12 and set up a development environment  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Basic computer literacy

### Installing Python 3.12

#### 🪟 **Windows Installation**

1. **Download Python 3.12**
   - Visit [python.org/downloads](https://python.org/downloads)
   - Download the latest Python 3.12.x installer
   - Choose the appropriate version (32-bit or 64-bit)

2. **Installation Process**
   ```
   ✅ Add Python 3.12 to PATH (Important!)
   ✅ Install for all users
   ✅ Install pip (Python package manager)
   ```

3. **Verify Installation**
   ```cmd
   python --version
   # Should output: Python 3.12.x
   
   pip --version
   # Should show pip version
   ```

#### 🍎 **macOS Installation**

**Option 1: Official Installer**
1. Download from [python.org](https://python.org/downloads)
2. Run the `.pkg` installer
3. Follow installation wizard

**Option 2: Homebrew (Recommended)**
```bash
# Install Homebrew if not already installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Python 3.12
brew install python@3.12

# Verify installation
python3.12 --version
```

#### 🐧 **Linux Installation**

**Ubuntu/Debian:**
```bash
# Update package list
sudo apt update

# Install Python 3.12
sudo apt install python3.12 python3.12-pip python3.12-venv

# Verify installation
python3.12 --version
```

**CentOS/RHEL/Fedora:**
```bash
# Install Python 3.12
sudo dnf install python3.12 python3.12-pip

# Or for older systems
sudo yum install python3.12 python3.12-pip
```

**Arch Linux:**
```bash
# Python 3.12 is usually in the official repositories
sudo pacman -S python python-pip
```

### Virtual Environments

Virtual environments are crucial for Python development. They allow you to:
- Isolate project dependencies
- Avoid conflicts between different projects
- Maintain clean system Python installation

#### Creating Virtual Environments

```bash
# Create a virtual environment
python -m venv myproject_env

# Activate the environment
# Windows:
myproject_env\Scripts\activate

# macOS/Linux:
source myproject_env/bin/activate

# Verify activation (should show virtual environment name)
which python

# Install packages in virtual environment
pip install requests numpy pandas

# Deactivate when done
deactivate
```

### Package Management with pip

pip is Python's package installer and manager.

#### Essential pip Commands

```bash
# Install a package
pip install package_name

# Install specific version
pip install package_name==1.2.3

# Install from requirements file
pip install -r requirements.txt

# List installed packages
pip list

# Show package information
pip show package_name

# Upgrade a package
pip install --upgrade package_name

# Uninstall a package
pip uninstall package_name

# Create requirements file
pip freeze > requirements.txt
```

### 💡 Code Example: Environment Setup Verification

```python
#!/usr/bin/env python3
"""
Python Environment Verification Script
This script checks your Python installation and environment setup.
"""

import sys
import os
import platform
from pathlib import Path

def check_python_version():
    """Check if Python version is 3.12 or higher."""
    version = sys.version_info
    print(f"🐍 Python Version: {version.major}.{version.minor}.{version.micro}")
    
    if version.major == 3 and version.minor >= 12:
        print("✅ Python version is compatible!")
        return True
    else:
        print("❌ Please upgrade to Python 3.12 or higher")
        return False

def check_virtual_environment():
    """Check if running in a virtual environment."""
    in_venv = hasattr(sys, 'real_prefix') or (
        hasattr(sys, 'base_prefix') and sys.base_prefix != sys.prefix
    )
    
    if in_venv:
        print("✅ Running in virtual environment")
        print(f"   Virtual env path: {sys.prefix}")
    else:
        print("⚠️  Not in virtual environment (recommended for projects)")
    
    return in_venv

def check_pip_installation():
    """Check if pip is available and working."""
    try:
        import subprocess
        result = subprocess.run([sys.executable, '-m', 'pip', '--version'], 
                              capture_output=True, text=True, check=True)
        print(f"✅ pip is available: {result.stdout.strip()}")
        return True
    except (subprocess.CalledProcessError, FileNotFoundError):
        print("❌ pip is not available or not working")
        return False

def display_system_info():
    """Display system information."""
    print("\n🖥️  System Information:")
    print(f"   Operating System: {platform.system()} {platform.release()}")
    print(f"   Architecture: {platform.architecture()[0]}")
    print(f"   Python Executable: {sys.executable}")
    print(f"   Current Working Directory: {Path.cwd()}")

def main():
    """Main function to run all checks."""
    print("🔍 Python Environment Check")
    print("=" * 50)
    
    # Run all checks
    python_ok = check_python_version()
    venv_status = check_virtual_environment()
    pip_ok = check_pip_installation()
    
    display_system_info()
    
    print("\n📋 Summary:")
    if python_ok and pip_ok:
        print("✅ Your Python environment is ready for development!")
        if not venv_status:
            print("💡 Consider using virtual environments for your projects")
    else:
        print("❌ Please fix the issues above before continuing")

if __name__ == "__main__":
    main()
```

### Python Path and Environment Variables

Understanding how Python finds modules and packages:

```python
import sys
import os

# Display Python path
print("Python Module Search Path:")
for i, path in enumerate(sys.path, 1):
    print(f"{i:2d}. {path}")

# Display important environment variables
important_vars = ['PYTHONPATH', 'PYTHONHOME', 'VIRTUAL_ENV']
print("\nImportant Environment Variables:")
for var in important_vars:
    value = os.environ.get(var, 'Not set')
    print(f"{var}: {value}")
```

### ⚠️ Common Pitfalls

1. **PATH Issues**: Forgetting to add Python to system PATH
2. **Multiple Python Versions**: Confusion between `python`, `python3`, and `python3.12`
3. **Pip vs Pip3**: Using wrong pip version
4. **Permission Errors**: Installing packages system-wide without proper permissions
5. **Virtual Environment Activation**: Forgetting to activate virtual environment

### ✅ Best Practices

1. **Always Use Virtual Environments**: Isolate project dependencies
2. **Pin Package Versions**: Use `requirements.txt` with specific versions
3. **Regular Updates**: Keep Python and packages updated for security
4. **System vs User Installation**: Use virtual environments instead of system-wide installs
5. **Documentation**: Document your environment setup in README files

### 🏋️ Exercise 2: Environment Setup
**Difficulty:** 🟢 Beginner  
**Estimated Time:** 15 minutes

Set up a complete Python development environment:
1. Create a new virtual environment named `python_learning`
2. Activate the virtual environment
3. Install the following packages: `requests`, `numpy`, `matplotlib`
4. Create a `requirements.txt` file
5. Write a simple script that imports all three packages and prints their versions

<details>
<summary>💡 Click to see hints</summary>

- Use `python -m venv python_learning` to create the environment
- Don't forget to activate before installing packages
- Use `pip freeze > requirements.txt` to create the requirements file
- You can get package versions using `package.__version__`

</details>

<details>
<summary>✅ Click to see solution</summary>

**Step 1: Create and activate virtual environment**
```bash
# Create virtual environment
python -m venv python_learning

# Activate (Windows)
python_learning\Scripts\activate

# Activate (macOS/Linux)
source python_learning/bin/activate
```

**Step 2: Install packages**
```bash
pip install requests numpy matplotlib
```

**Step 3: Create requirements.txt**
```bash
pip freeze > requirements.txt
```

**Step 4: Version checking script**
```python
#!/usr/bin/env python3
"""
Package Version Checker
Displays versions of installed packages in our environment.
"""

import sys

def check_package_version(package_name):
    """Check and display the version of a package."""
    try:
        # Import the package dynamically
        package = __import__(package_name)
        version = getattr(package, '__version__', 'Version not available')
        print(f"✅ {package_name}: {version}")
        return True
    except ImportError:
        print(f"❌ {package_name}: Not installed")
        return False

def main():
    """Main function to check all packages."""
    print("📦 Package Version Check")
    print("=" * 30)
    print(f"🐍 Python: {sys.version.split()[0]}")
    print()
    
    # List of packages to check
    packages = ['requests', 'numpy', 'matplotlib']
    
    print("📋 Installed Packages:")
    all_installed = True
    for package in packages:
        if not check_package_version(package):
            all_installed = False
    
    print()
    if all_installed:
        print("✅ All required packages are installed!")
        print("💡 Your environment is ready for Python development!")
    else:
        print("❌ Some packages are missing. Please install them using:")
        print("pip install requests numpy matplotlib")

if __name__ == "__main__":
    main()
```

**Step 5: Requirements.txt content (example)**
```txt
matplotlib==3.8.2
numpy==1.26.2
requests==2.31.0
```

**Explanation:**
- **Virtual environment isolation**: Keeps project dependencies separate from system Python
- **Requirements file**: Enables reproducible installations across different machines
- **Dynamic imports**: Shows how to programmatically check package availability
- **Error handling**: Gracefully handles missing packages with try-except blocks

</details>

[🔝 Back to Top](#-python-documentation)

---

## 👋 Chapter 3: Your First Python Program
📊 **Progress:** Chapter 3 of 30  
🎯 **Learning Objectives:** Write, run, and understand your first Python programs  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Python 3.12 installed and working

### The Traditional "Hello, World!"

Every programming journey begins with "Hello, World!" - a simple program that displays a greeting message.

```python
# hello_world.py
print("Hello, World!")
```

### Running Python Programs

#### 🖥️ **Interactive Mode (REPL)**

The Python REPL (Read-Eval-Print Loop) allows you to test code interactively:

```bash
$ python
Python 3.12.0 (main, Oct  2 2023, 15:46:18)
>>> print("Hello, World!")
Hello, World!
>>> 2 + 2
4
>>> exit()
```

#### 📄 **Script Mode**

Save your code in a `.py` file and run it:

```bash
# Create file
echo 'print("Hello, World!")' > hello_world.py

# Run the script
python hello_world.py
```

#### 🔧 **IDE Integration**

Most IDEs provide "Run" buttons or keyboard shortcuts:
- **VS Code**: F5 or Ctrl+F5
- **PyCharm**: Shift+F10
- **IDLE**: F5

### Understanding Program Structure

```python
#!/usr/bin/env python3
"""
My First Python Program
This program demonstrates basic Python concepts.
"""

# This is a single-line comment

def main():
    """
    Main function - the entry point of our program.
    This is a docstring that explains what the function does.
    """
    # Variable assignment
    name = "Python"
    version = 3.12
    
    # Output with f-string formatting
    print(f"Hello from {name} {version}!")
    
    # Simple calculation
    result = 10 * 3 + 2
    print(f"10 * 3 + 2 = {result}")

# This ensures main() runs only when script is executed directly
if __name__ == "__main__":
    main()
```

### 💡 Code Examples: Building Complexity Gradually

#### Example 1: Interactive Greeting Program

```python
"""
Interactive Greeting Program
Demonstrates user input, string manipulation, and conditional logic.
"""

def get_user_name():
    """Get and validate user's name."""
    while True:
        name = input("What's your name? ").strip()
        if name:  # Check if name is not empty
            return name
        print("Please enter a valid name.")

def get_age():
    """Get and validate user's age."""
    while True:
        try:
            age = int(input("How old are you? "))
            if age < 0:
                print("Age cannot be negative!")
                continue
            if age > 150:
                print("That seems unlikely! Please enter your real age.")
                continue
            return age
        except ValueError:
            print("Please enter a valid number.")

def generate_greeting(name, age):
    """Generate personalized greeting based on age."""
    if age < 13:
        return f"Hey there, {name}! You're just a kid!"
    elif age < 20:
        return f"Hello, {name}! Teen years are exciting!"
    elif age < 60:
        return f"Hello, {name}! You're in your prime!"
    else:
        return f"Greetings, {name}! Wisdom comes with age!"

def main():
    """Main program function."""
    print("🎉 Welcome to the Interactive Greeting Program!")
    print("-" * 50)
    
    # Get user information
    name = get_user_name()
    age = get_age()
    
    # Generate and display personalized greeting
    greeting = generate_greeting(name, age)
    print(f"\n{greeting}")
    
    # Fun fact based on age
    if age >= 18:
        print(f"🗳️  You can vote in most countries!")
    if age >= 21:
        print("🍺 You can drink legally in the US!")
    
    print(f"\n📊 Fun fact: You've been alive for approximately {age * 365} days!")
    print("Thanks for using our program! 👋")

if __name__ == "__main__":
    main()
```

#### Example 2: Simple Calculator

```python
"""
Simple Calculator Program
Demonstrates functions, error handling, and basic arithmetic operations.
"""

def add(x, y):
    """Add two numbers."""
    return x + y

def subtract(x, y):
    """Subtract second number from first."""
    return x - y

def multiply(x, y):
    """Multiply two numbers."""
    return x * y

def divide(x, y):
    """Divide first number by second."""
    if y == 0:
        raise ValueError("Cannot divide by zero!")
    return x / y

def get_number(prompt):
    """Get a valid number from user input."""
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Invalid input! Please enter a number.")

def get_operation():
    """Get valid operation from user."""
    operations = {
        '1': ('Addition', add),
        '2': ('Subtraction', subtract),
        '3': ('Multiplication', multiply),
        '4': ('Division', divide)
    }
    
    print("\nSelect operation:")
    for key, (name, _) in operations.items():
        print(f"{key}. {name}")
    
    while True:
        choice = input("Enter choice (1-4): ").strip()
        if choice in operations:
            return operations[choice]
        print("Invalid choice! Please select 1-4.")

def main():
    """Main calculator function."""
    print("🔢 Simple Python Calculator")
    print("=" * 30)
    
    while True:
        try:
            # Get numbers
            num1 = get_number("Enter first number: ")
            num2 = get_number("Enter second number: ")
            
            # Get operation
            operation_name, operation_func = get_operation()
            
            # Perform calculation
            result = operation_func(num1, num2)
            
            # Display result
            print(f"\n📊 Result:")
            print(f"{num1} {operation_name.lower()} {num2} = {result}")
            
            # Ask if user wants to continue
            if input("\nPerform another calculation? (y/n): ").lower() != 'y':
                break
                
        except ValueError as e:
            print(f"❌ Error: {e}")
        except KeyboardInterrupt:
            print("\n👋 Goodbye!")
            break
    
    print("Thanks for using the calculator!")

if __name__ == "__main__":
    main()
```

### Python Execution Model

Understanding how Python executes your code:

1. **Source Code**: Your `.py` files
2. **Bytecode Compilation**: Python compiles to `.pyc` files
3. **Python Virtual Machine**: Executes the bytecode
4. **Output**: Results displayed to user

```python
import dis

def simple_function(x):
    return x * 2 + 1

# View the bytecode
print("Bytecode for simple_function:")
dis.dis(simple_function)
```

### Debugging Your First Programs

#### Using Print Statements

```python
def debug_example():
    """Demonstrate debugging with print statements."""
    numbers = [1, 2, 3, 4, 5]
    total = 0
    
    print(f"Starting with numbers: {numbers}")  # Debug output
    
    for i, num in enumerate(numbers):
        total += num
        print(f"Step {i+1}: Added {num}, total is now {total}")  # Debug output
    
    print(f"Final total: {total}")
    return total

debug_example()
```

#### Using the Python Debugger (pdb)

```python
import pdb

def problematic_function():
    """Function that might need debugging."""
    x = 10
    y = 0
    
    pdb.set_trace()  # Debugger will stop here
    
    result = x / y  # This will cause an error
    return result

# To debug: run the function and use pdb commands
# n (next), s (step), c (continue), p <variable> (print), q (quit)
```

### File Organization and Project Structure

```
my_first_project/
├── main.py              # Main program entry point
├── helpers.py           # Helper functions
├── requirements.txt     # Package dependencies
└── README.md           # Project documentation
```

**main.py:**
```python
"""
Main program file.
"""
from helpers import greet_user, calculate_age_in_days

def main():
    name = input("Your name: ")
    age = int(input("Your age: "))
    
    greet_user(name)
    days = calculate_age_in_days(age)
    print(f"You've lived approximately {days:,} days!")

if __name__ == "__main__":
    main()
```

**helpers.py:**
```python
"""
Helper functions for the main program.
"""

def greet_user(name):
    """Greet the user with their name."""
    print(f"Hello, {name}! Welcome to Python!")

def calculate_age_in_days(age):
    """Calculate approximate days lived based on age."""
    return age * 365
```

### ⚠️ Common Pitfalls

1. **Indentation Errors**: Python uses indentation to define code blocks
   ```python
   # Wrong
   if True:
   print("This will cause an IndentationError")
   
   # Correct
   if True:
       print("This is properly indented")
   ```

2. **Forgetting Parentheses**: Function calls need parentheses
   ```python
   # Wrong
   print "Hello"  # Python 2 syntax
   
   # Correct
   print("Hello")  # Python 3 syntax
   ```

3. **String vs Number Confusion**: Input always returns strings
   ```python
   # Problematic
   age = input("Age: ")
   next_year = age + 1  # Will cause TypeError
   
   # Correct
   age = int(input("Age: "))
   next_year = age + 1
   ```

### ✅ Best Practices

1. **Use Meaningful Names**: Choose descriptive variable and function names
2. **Add Documentation**: Use docstrings for functions and modules
3. **Handle Errors**: Anticipate and handle potential exceptions
4. **Follow PEP 8**: Maintain consistent coding style
5. **Test Your Code**: Run your programs with different inputs
6. **Use Version Control**: Start using git early in your journey

### 🏋️ Exercise 3: Build Your First Interactive Program
**Difficulty:** 🟢 Beginner  
**Estimated Time:** 20 minutes

Create a program called "Personal Info Collector" that:
1. Asks for user's name, age, and favorite hobby
2. Calculates how many days they've been alive
3. Calculates how many hours they might have spent on their hobby (assume 2 hours per week since age 10)
4. Displays all information in a nicely formatted summary
5. Saves the information to a text file named after the user

<details>
<summary>💡 Click to see hints</summary>

- Use `input()` for getting user information
- Use `int()` to convert age to number for calculations
- Use f-strings for nice formatting
- Create filename by replacing spaces with underscores: `name.replace(" ", "_")`
- Use `open()` with `'w'` mode to write to file

</details>

<details>
<summary>✅ Click to see solution</summary>

```python
#!/usr/bin/env python3
"""
Personal Info Collector
Collects user information and saves it to a file.
"""

import os
from datetime import datetime

def get_user_info():
    """Collect user information interactively."""
    print("📝 Personal Info Collector")
    print("=" * 30)
    
    name = input("What's your name? ").strip()
    
    while True:
        try:
            age = int(input("How old are you? "))
            if age < 0 or age > 150:
                print("Please enter a realistic age (0-150)")
                continue
            break
        except ValueError:
            print("Please enter a valid number for age")
    
    hobby = input("What's your favorite hobby? ").strip()
    
    return name, age, hobby

def calculate_statistics(age):
    """Calculate various statistics based on age."""
    days_alive = age * 365
    hours_alive = days_alive * 24
    
    # Assume hobby started at age 10, 2 hours per week
    hobby_years = max(0, age - 10)
    hobby_hours = hobby_years * 52 * 2  # 52 weeks per year, 2 hours per week
    
    return {
        'days_alive': days_alive,
        'hours_alive': hours_alive,
        'hobby_hours': hobby_hours
    }

def create_summary(name, age, hobby, stats):
    """Create a formatted summary of user information."""
    summary = f"""
🎉 Personal Summary for {name}
{"=" * (25 + len(name))}

📊 Basic Information:
   Name: {name}
   Age: {age} years old
   Favorite Hobby: {hobby}

📈 Life Statistics:
   Days alive: {stats['days_alive']:,} days
   Hours alive: {stats['hours_alive']:,} hours
   
🎯 Hobby Statistics:
   Estimated hours spent on {hobby}: {stats['hobby_hours']:,} hours
   That's {stats['hobby_hours'] / 24:.1f} days of pure {hobby}!

📅 Report generated on: {datetime.now().strftime("%Y-%m-%d at %H:%M:%S")}
"""
    return summary

def save_to_file(name, summary):
    """Save summary to a file named after the user."""
    filename = f"{name.replace(' ', '_').lower()}_summary.txt"
    
    try:
        with open(filename, 'w', encoding='utf-8') as file:
            file.write(summary)
        return filename
    except IOError as e:
        print(f"Error saving file: {e}")
        return None

def main():
    """Main program function."""
    try:
        # Get user information
        name, age, hobby = get_user_info()
        
        # Calculate statistics
        stats = calculate_statistics(age)
        
        # Create summary
        summary = create_summary(name, age, hobby, stats)
        
        # Display summary
        print(summary)
        
        # Save to file
        filename = save_to_file(name, summary)
        if filename:
            print(f"💾 Summary saved to: {filename}")
            print(f"📁 File location: {os.path.abspath(filename)}")
        
        print("\n🎊 Thanks for using Personal Info Collector!")
        
    except KeyboardInterrupt:
        print("\n\n👋 Program cancelled by user. Goodbye!")
    except Exception as e:
        print(f"\n❌ An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()
```

**Explanation:**
- **Modular design**: Functions handle specific tasks (collecting info, calculating, formatting)
- **Input validation**: Ensures age is a valid number within reasonable range
- **Error handling**: Handles file I/O errors and user interruption gracefully
- **File operations**: Creates and writes to a text file with user's information
- **String formatting**: Uses f-strings for clean, readable output
- **Statistics calculation**: Demonstrates arithmetic operations and logical thinking

</details>

[🔝 Back to Top](#-python-documentation)

---

## 💻 Chapter 4: Python Development Environment
📊 **Progress:** Chapter 4 of 30  
🎯 **Learning Objectives:** Set up professional development tools and IDE  
⏱️ **Estimated Reading Time:** 30 minutes  
📋 **Prerequisites:** Python 3.12 installed

### Choosing Your IDE

#### 🌟 **Visual Studio Code (Recommended)**

VS Code is free, lightweight, and has excellent Python support.

**Installation & Setup:**
1. Download from [code.visualstudio.com](https://code.visualstudio.com)
2. Install the Python extension by Microsoft
3. Configure Python interpreter

**Essential Extensions:**
```
- Python (Microsoft)
- Pylance (Microsoft) 
- Python Docstring Generator
- autoDocstring
- GitLens
- Bracket Pair Colorizer 2
- Code Runner
```

**Configuration (settings.json):**
```json
{
    "python.defaultInterpreterPath": "python",
    "python.linting.enabled": true,
    "python.linting.pylintEnabled": true,
    "python.formatting.provider": "black",
    "python.formatting.blackArgs": ["--line-length=88"],
    "editor.formatOnSave": true,
    "python.testing.pytestEnabled": true,
    "python.testing.unittestEnabled": false,
    "editor.rulers": [79, 88],
    "files.autoSave": "afterDelay"
}
```

#### 🚀 **PyCharm (Professional)**

JetBrains PyCharm offers powerful features for serious development.

**Features:**
- Advanced debugging
- Integrated version control
- Database tools
- Web development support
- Code analysis and refactoring

**Setup Tips:**
- Use Community Edition for learning
- Configure virtual environment interpreter
- Enable PEP 8 code style warnings
- Set up code formatter

#### 🐍 **IDLE (Built-in)**

Python's built-in IDE, perfect for beginners.

**Pros:**
- Comes with Python installation
- Simple and lightweight
- Good for learning basics

**Cons:**
- Limited features
- No advanced debugging
- Basic project management

### Code Formatting and Style

#### PEP 8 - Python Style Guide

Python Enhancement Proposal 8 defines coding standards:

```python
# Good: PEP 8 compliant
def calculate_compound_interest(principal, rate, time):
    """
    Calculate compound interest.
    
    Args:
        principal (float): Initial amount
        rate (float): Interest rate as decimal
        time (int): Time period in years
    
    Returns:
        float: Final amount after interest
    """
    return principal * (1 + rate) ** time


# Bad: Not PEP 8 compliant
def calculateCompoundInterest(p,r,t):
    return p*(1+r)**t
```

#### Black - Code Formatter

Black is an opinionated code formatter:

```bash
# Install Black
pip install black

# Format a file
black my_script.py

# Format entire project
black .

# Check what would be changed without modifying
black --check .
```

#### Flake8 - Style Guide Enforcement

```bash
# Install flake8
pip install flake8

# Check code style
flake8 my_script.py

# Configuration in setup.cfg
[flake8]
max-line-length = 88
extend-ignore = E203, W503
```

### Version Control with Git

#### Setting Up Git Repository

```bash
# Initialize repository
git init

# Create .gitignore for Python
echo "*.pyc
__pycache__/
*.pyo
*.pyd
.Python
env/
venv/
.venv/
pip-log.txt
pip-delete-this-directory.txt
.tox/
.coverage
.pytest_cache/
htmlcov/
.DS_Store" > .gitignore

# Add and commit files
git add .
git commit -m "Initial commit"
```

#### Essential Git Commands for Python Development

```bash
# Check status
git status

# Add files
git add filename.py
git add .  # Add all files

# Commit changes
git commit -m "Add new feature"

# View history
git log --oneline

# Create and switch to new branch
git checkout -b feature-name

# Merge branch
git checkout main
git merge feature-name

# Push to remote repository
git remote add origin https://github.com/username/repo.git
git push -u origin main
```

### 💡 Code Example: Development Environment Tester

```python
#!/usr/bin/env python3
"""
Development Environment Tester
Tests various aspects of your Python development setup.
"""

import sys
import os
import subprocess
import importlib
from pathlib import Path

def test_python_version():
    """Test Python version compatibility."""
    version = sys.version_info
    print(f"🐍 Python Version: {version.major}.{version.minor}.{version.micro}")
    
    if version.major == 3 and version.minor >= 8:
        print("✅ Python version is compatible with modern development")
        return True
    else:
        print("❌ Please upgrade to Python 3.8 or higher")
        return False

def test_package_availability():
    """Test availability of common development packages."""
    packages = {
        'pip': 'Package installer',
        'black': 'Code formatter',
        'flake8': 'Style checker',
        'pytest': 'Testing framework',
        'requests': 'HTTP library'
    }
    
    print("\n📦 Package Availability:")
    available_packages = []
    
    for package, description in packages.items():
        try:
            if package == 'pip':
                # Special case for pip
                subprocess.check_call([sys.executable, '-m', 'pip', '--version'], 
                                    stdout=subprocess.DEVNULL, 
                                    stderr=subprocess.DEVNULL)
            else:
                importlib.import_module(package)
            print(f"✅ {package:10} - {description}")
            available_packages.append(package)
        except (ImportError, subprocess.CalledProcessError):
            print(f"❌ {package:10} - {description} (Not installed)")
    
    return available_packages

def test_git_availability():
    """Test if Git is available and configured."""
    print("\n📄 Git Configuration:")
    
    try:
        # Check if git is available
        subprocess.check_call(['git', '--version'], 
                            stdout=subprocess.DEVNULL, 
                            stderr=subprocess.DEVNULL)
        print("✅ Git is available")
        
        # Check git configuration
        try:
            name = subprocess.check_output(['git', 'config', 'user.name'], 
                                         stderr=subprocess.DEVNULL, 
                                         text=True).strip()
            email = subprocess.check_output(['git', 'config', 'user.email'], 
                                          stderr=subprocess.DEVNULL, 
                                          text=True).strip()
            print(f"✅ Git user: {name} <{email}>")
            return True
        except subprocess.CalledProcessError:
            print("⚠️  Git is available but not configured")
            print("   Run: git config --global user.name 'Your Name'")
            print("   Run: git config --global user.email 'your.email@example.com'")
            return False
            
    except (subprocess.CalledProcessError, FileNotFoundError):
        print("❌ Git is not available")
        print("   Install Git from: https://git-scm.com/")
        return False

def test_project_structure():
    """Test basic project structure setup."""
    print("\n📁 Project Structure:")
    
    current_dir = Path.cwd()
    important_files = {
        'README.md': 'Project documentation',
        '.gitignore': 'Git ignore file',
        'requirements.txt': 'Package dependencies',
        'setup.py': 'Package setup (optional)'
    }
    
    existing_files = []
    for filename, description in important_files.items():
        file_path = current_dir / filename
        if file_path.exists():
            print(f"✅ {filename:15} - {description}")
            existing_files.append(filename)
        else:
            print(f"⚠️  {filename:15} - {description} (Missing)")
    
    return existing_files

def test_code_quality_tools():
    """Test code quality and formatting tools."""
    print("\n🔧 Code Quality Tools:")
    
    # Test Black formatter
    try:
        result = subprocess.run([sys.executable, '-m', 'black', '--version'], 
                              capture_output=True, text=True, check=True)
        print(f"✅ Black formatter: {result.stdout.strip()}")
    except (subprocess.CalledProcessError, FileNotFoundError):
        print("❌ Black formatter not available")
        print("   Install with: pip install black")
    
    # Test Flake8 linter
    try:
        result = subprocess.run([sys.executable, '-m', 'flake8', '--version'], 
                              capture_output=True, text=True, check=True)
        version_line = result.stdout.split('\n')[0]
        print(f"✅ Flake8 linter: {version_line}")
    except (subprocess.CalledProcessError, FileNotFoundError):
        print("❌ Flake8 linter not available")
        print("   Install with: pip install flake8")

def generate_setup_recommendations():
    """Generate recommendations for improving development setup."""
    print("\n💡 Setup Recommendations:")
    
    recommendations = [
        "Install VS Code with Python extension for better development experience",
        "Set up virtual environment for project isolation",
        "Install Black and Flake8 for code quality",
        "Configure Git with your name and email",
        "Create .gitignore file for Python projects",
        "Use requirements.txt to track dependencies",
        "Set up automated testing with pytest",
        "Consider using pre-commit hooks for code quality"
    ]
    
    for i, recommendation in enumerate(recommendations, 1):
        print(f"{i:2d}. {recommendation}")

def main():
    """Main function to run all development environment tests."""
    print("🔍 Python Development Environment Check")
    print("=" * 50)
    
    # Run all tests
    python_ok = test_python_version()
    available_packages = test_package_availability()
    git_ok = test_git_availability()
    existing_files = test_project_structure()
    test_code_quality_tools()
    
    # Summary
    print("\n📋 Summary:")
    if python_ok:
        print("✅ Python environment is ready")
    else:
        print("❌ Python needs to be updated")
    
    if len(available_packages) >= 3:
        print("✅ Good package availability")
    else:
        print("⚠️  Consider installing more development packages")
    
    if git_ok:
        print("✅ Git is properly configured")
    else:
        print("⚠️  Git needs setup or configuration")
    
    if len(existing_files) >= 2:
        print("✅ Project structure looks good")
    else:
        print("⚠️  Consider adding project structure files")
    
    generate_setup_recommendations()

if __name__ == "__main__":
    main()
```

### Virtual Environment Best Practices

#### Creating Project-Specific Environments

```bash
# Create virtual environment for each project
mkdir my_python_project
cd my_python_project
python -m venv venv

# Activation scripts by platform
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install project dependencies
pip install -r requirements.txt

# Save current environment
pip freeze > requirements.txt
```

#### Managing Multiple Python Versions with pyenv

```bash
# Install pyenv (macOS with Homebrew)
brew install pyenv

# List available Python versions
pyenv install --list

# Install specific Python version
pyenv install 3.12.0

# Set global Python version
pyenv global 3.12.0

# Set local Python version for project
pyenv local 3.12.0
```

### Debugging Tools

#### Using the Built-in Debugger (pdb)

```python
import pdb

def problematic_function(numbers):
    """Function that might need debugging."""
    result = []
    for num in numbers:
        # Set breakpoint here
        pdb.set_trace()
        
        if num > 0:
            result.append(num * 2)
        else:
            result.append(num)
    
    return result

# Test the function
test_numbers = [1, -2, 3, 0, -5]
output = problematic_function(test_numbers)
print(output)
```

#### Using logging for debugging

```python
import logging

# Configure logging
logging.basicConfig(
    level=logging.DEBUG,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    handlers=[
        logging.FileHandler('debug.log'),
        logging.StreamHandler()
    ]
)

logger = logging.getLogger(__name__)

def calculate_average(numbers):
    """Calculate average with logging."""
    logger.debug(f"Input numbers: {numbers}")
    
    if not numbers:
        logger.warning("Empty list provided")
        return 0
    
    total = sum(numbers)
    count = len(numbers)
    average = total / count
    
    logger.info(f"Calculated average: {average}")
    return average

# Usage
test_data = [1, 2, 3, 4, 5]
result = calculate_average(test_data)
print(f"Average: {result}")
```

### Testing Setup

#### Setting Up pytest

```bash
# Install pytest
pip install pytest pytest-cov

# Create test file structure
mkdir tests
touch tests/__init__.py
touch tests/test_main.py
```

**tests/test_main.py:**
```python
import pytest
from main import calculate_average

def test_calculate_average():
    """Test average calculation."""
    assert calculate_average([1, 2, 3, 4, 5]) == 3.0
    assert calculate_average([10, 20]) == 15.0
    assert calculate_average([]) == 0
    
def test_calculate_average_single_number():
    """Test average with single number."""
    assert calculate_average([42]) == 42.0
    
def test_calculate_average_negative_numbers():
    """Test average with negative numbers."""
    assert calculate_average([-1, -2, -3]) == -2.0

def test_calculate_average_mixed_numbers():
    """Test average with mixed positive and negative numbers."""
    assert calculate_average([-1, 1, -2, 2]) == 0.0
```

#### Running Tests

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=main

# Run specific test file
pytest tests/test_main.py

# Run with verbose output
pytest -v

# Run and stop on first failure
pytest -x
```

### ⚠️ Common Development Environment Issues

1. **Python Path Problems**: Multiple Python installations causing confusion
2. **Virtual Environment Not Activated**: Installing packages globally instead of in venv
3. **IDE Not Recognizing Python**: Wrong interpreter selected in IDE settings
4. **Import Errors**: Module not found due to incorrect PYTHONPATH
5. **Package Version Conflicts**: Different projects requiring different versions

### ✅ Development Environment Best Practices

1. **One Virtual Environment Per Project**: Avoid dependency conflicts
2. **Requirements File**: Always maintain `requirements.txt`
3. **Version Control Everything**: Except virtual environments and cache files
4. **Consistent Code Style**: Use Black and Flake8
5. **Automated Testing**: Set up pytest from the beginning
6. **Documentation**: Write docstrings and README files
7. **IDE Configuration**: Customize for productivity

### 🏋️ Exercise 4: Complete Development Setup
**Difficulty:** 🟡 Intermediate  
**Estimated Time:** 30 minutes

Set up a complete Python development environment:
1. Create a new project directory with proper structure
2. Set up virtual environment and install development tools
3. Configure Git repository with appropriate .gitignore
4. Write a simple module with functions
5. Create corresponding tests
6. Set up code formatting and linting

<details>
<summary>💡 Click to see hints</summary>

- Use `mkdir` to create project directory structure
- Install `black`, `flake8`, and `pytest` in virtual environment
- Python .gitignore templates available on GitHub
- Write simple functions that are easy to test
- Use pytest naming convention: `test_*.py`

</details>

<details>
<summary>✅ Click to see solution</summary>

**Step 1: Create project structure**
```bash
mkdir python_dev_project
cd python_dev_project

# Create directory structure
mkdir src tests docs
touch README.md requirements.txt setup.py
touch src/__init__.py src/calculator.py
touch tests/__init__.py tests/test_calculator.py
```

**Step 2: Set up virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install development tools
pip install black flake8 pytest pytest-cov
pip freeze > requirements.txt
```

**Step 3: Create .gitignore**
```bash
cat > .gitignore << EOF
# Python
*.pyc
__pycache__/
*.pyo
*.pyd
.Python
venv/
env/
.env
.venv

# Testing
.pytest_cache/
.coverage
htmlcov/

# IDE
.vscode/
.idea/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db
EOF
```

**Step 4: Initialize Git**
```bash
git init
git add .
git commit -m "Initial project setup"
```

**Step 5: Write calculator module (src/calculator.py)**
```python
"""
Simple calculator module for demonstration.
"""

def add(a, b):
    """Add two numbers."""
    return a + b

def subtract(a, b):
    """Subtract second number from first."""
    return a - b

def multiply(a, b):
    """Multiply two numbers."""
    return a * b

def divide(a, b):
    """Divide first number by second."""
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b

def power(base, exponent):
    """Calculate base raised to exponent power."""
    return base ** exponent

def square_root(number):
    """Calculate square root of a number."""
    if number < 0:
        raise ValueError("Cannot calculate square root of negative number")
    return number ** 0.5
```

**Step 6: Write tests (tests/test_calculator.py)**
```python
"""
Tests for calculator module.
"""

import pytest
import sys
from pathlib import Path

# Add src directory to Python path
sys.path.insert(0, str(Path(__file__).parent.parent / "src"))

from calculator import add, subtract, multiply, divide, power, square_root

class TestBasicOperations:
    """Test basic arithmetic operations."""
    
    def test_add(self):
        """Test addition function."""
        assert add(2, 3) == 5
        assert add(-1, 1) == 0
        assert add(0, 0) == 0
        assert add(-5, -5) == -10
    
    def test_subtract(self):
        """Test subtraction function."""
        assert subtract(5, 3) == 2
        assert subtract(0, 5) == -5
        assert subtract(-1, -1) == 0
        assert subtract(10, 15) == -5
    
    def test_multiply(self):
        """Test multiplication function."""
        assert multiply(3, 4) == 12
        assert multiply(-2, 5) == -10
        assert multiply(0, 100) == 0
        assert multiply(-3, -3) == 9

class TestAdvancedOperations:
    """Test advanced operations."""
    
    def test_divide(self):
        """Test division function."""
        assert divide(10, 2) == 5
        assert divide(9, 3) == 3
        assert divide(-8, 2) == -4
        assert divide(7, 2) == 3.5
    
    def test_divide_by_zero(self):
        """Test division by zero raises exception."""
        with pytest.raises(ValueError, match="Cannot divide by zero"):
            divide(10, 0)
    
    def test_power(self):
        """Test power function."""
        assert power(2, 3) == 8
        assert power(5, 0) == 1
        assert power(10, 1) == 10
        assert power(-2, 2) == 4
    
    def test_square_root(self):
        """Test square root function."""
        assert square_root(4) == 2
        assert square_root(9) == 3
        assert square_root(0) == 0
        assert abs(square_root(2) - 1.4142135623730951) < 1e-15
    
    def test_square_root_negative(self):
        """Test square root of negative number raises exception."""
        with pytest.raises(ValueError, match="Cannot calculate square root of negative number"):
            square_root(-1)
```

**Step 7: Create setup.py**
```python
from setuptools import setup, find_packages

setup(
    name="python-dev-project",
    version="0.1.0",
    packages=find_packages(where="src"),
    package_dir={"": "src"},
    python_requires=">=3.8",
    author="Your Name",
    author_email="your.email@example.com",
    description="A sample Python project with proper development setup",
    long_description=open("README.md").read(),
    long_description_content_type="text/markdown",
    classifiers=[
        "Development Status :: 3 - Alpha",
        "Intended Audience :: Developers",
        "License :: OSI Approved :: MIT License",
        "Programming Language :: Python :: 3",
        "Programming Language :: Python :: 3.8",
        "Programming Language :: Python :: 3.9",
        "Programming Language :: Python :: 3.10",
        "Programming Language :: Python :: 3.11",
        "Programming Language :: Python :: 3.12",
    ],
)
```

**Step 8: Create README.md**
```markdown
# Python Development Project

A sample Python project demonstrating proper development environment setup.

## Features

- Simple calculator module
- Comprehensive test suite
- Code formatting with Black
- Linting with Flake8
- Virtual environment setup

## Installation

1. Clone the repository
2. Create virtual environment: `python -m venv venv`
3. Activate virtual environment: `source venv/bin/activate`
4. Install dependencies: `pip install -r requirements.txt`

## Usage

```python
from src.calculator import add, subtract, multiply, divide

result = add(5, 3)
print(f"5 + 3 = {result}")
```

## Testing

Run tests with pytest:
```bash
pytest
pytest --cov=src  # With coverage
```

## Code Quality

Format code with Black:
```bash
black src/ tests/
```

Check code style with Flake8:
```bash
flake8 src/ tests/
```

## Development

This project follows PEP 8 style guidelines and includes:
- Type hints (when applicable)
- Comprehensive docstrings
- Unit tests for all functions
- Continuous integration ready
```

**Step 9: Run quality checks**
```bash
# Format code
black src/ tests/

# Check style
flake8 src/ tests/

# Run tests
pytest --cov=src

# Final commit
git add .
git commit -m "Add calculator module with tests and documentation"
```

**Explanation:**
- **Project structure**: Follows Python packaging standards with separate src and tests directories
- **Virtual environment**: Isolates project dependencies from system Python
- **Testing framework**: pytest provides powerful testing capabilities with fixtures and parametrization
- **Code quality tools**: Black ensures consistent formatting, Flake8 catches style issues
- **Version control**: Git tracks all changes while ignoring generated files
- **Documentation**: README provides clear instructions for setup and usage

</details>

[🔝 Back to Top](#-python-documentation)

---

## 📝 Chapter 5: Basic Syntax & Structure
📊 **Progress:** Chapter 5 of 30  
🎯 **Learning Objectives:** Master Python's fundamental syntax rules and code structure  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Python development environment setup

### Python Syntax Fundamentals

Python's syntax is designed to be readable and intuitive. Unlike many programming languages that use braces `{}` or other symbols to define code blocks, Python uses **indentation**.

#### Indentation Rules

```python
# Correct indentation
if True:
    print("This is indented correctly")
    if True:
        print("This is nested indentation")
    print("Back to first level")

# Incorrect indentation - will cause IndentationError
if True:
print("This will cause an error")  # Missing indentation

# Mixed indentation - will cause IndentationError  
if True:
    print("Using 4 spaces")
	print("Using tab character")  # Don't mix tabs and spaces!
```

> 💡 **Tip:** Use 4 spaces for indentation (PEP 8 standard). Configure your editor to show whitespace characters.

#### Comments and Documentation

```python
# This is a single-line comment

"""
This is a multi-line comment
or docstring when used at the beginning
of modules, classes, or functions.
"""

def greet(name):
    """
    This is a docstring - it documents what the function does.
    
    Args:
        name (str): The name to greet
    
    Returns:
        str: A greeting message
    """
    return f"Hello, {name}!"

# Inline comments should be used sparingly
x = 5  # This assigns 5 to variable x
```

### Statement Structure

#### Simple Statements

```python
# Variable assignment
name = "Python"
age = 30
is_active = True

# Multiple assignments
x, y, z = 1, 2, 3
a = b = c = 0

# Augmented assignments
count = 10
count += 5  # Same as: count = count + 5
count *= 2  # Same as: count = count * 2
```

#### Line Continuation

```python
# Explicit line continuation with backslash
total = 1 + 2 + 3 + \
        4 + 5 + 6

# Implicit line continuation (preferred)
total = (1 + 2 + 3 +
         4 + 5 + 6)

# For function calls
result = some_very_long_function_name(
    parameter1,
    parameter2,
    parameter3
)

# For lists, dictionaries, etc.
shopping_list = [
    "apples",
    "bananas",
    "oranges",
    "milk"
]

# Dictionary formatting
person = {
    "name": "Alice",
    "age": 30,
    "city": "New York"
}
```

### Code Blocks and Compound Statements

#### Conditional Blocks

```python
# if-elif-else structure
temperature = 75

if temperature > 80:
    print("It's hot outside")
    recommendation = "Stay hydrated"
elif temperature > 60:
    print("Nice weather")
    recommendation = "Perfect for a walk"
else:
    print("It's cold")
    recommendation = "Wear a jacket"

print(f"Recommendation: {recommendation}")
```

#### Loop Blocks

```python
# for loop
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(f"I like {fruit}")
    if fruit == "banana":
        print("Bananas are my favorite!")

# while loop with proper indentation
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1
    if count == 3:
        print("Halfway there!")
```

#### Function and Class Blocks

```python
# Function definition
def calculate_circle_area(radius):
    """Calculate the area of a circle."""
    import math
    if radius < 0:
        raise ValueError("Radius cannot be negative")
    
    area = math.pi * radius ** 2
    return round(area, 2)

# Class definition
class Rectangle:
    """A simple rectangle class."""
    
    def __init__(self, width, height):
        """Initialize rectangle with width and height."""
        self.width = width
        self.height = height
    
    def area(self):
        """Calculate area of rectangle."""
        return self.width * self.height
    
    def perimeter(self):
        """Calculate perimeter of rectangle."""
        return 2 * (self.width + self.height)
```

### 💡 Code Example: Python Syntax Showcase

```python
#!/usr/bin/env python3
"""
Python Syntax Showcase
Demonstrates various Python syntax features and best practices.
"""

import math
from datetime import datetime


def analyze_numbers(numbers):
    """
    Analyze a list of numbers and return statistics.
    
    Args:
        numbers (list): List of numeric values
    
    Returns:
        dict: Dictionary containing various statistics
    """
    # Input validation
    if not numbers:
        return {"error": "Empty list provided"}
    
    if not all(isinstance(n, (int, float)) for n in numbers):
        return {"error": "All items must be numbers"}
    
    # Calculate statistics
    total = sum(numbers)
    count = len(numbers)
    average = total / count
    
    # Find min and max
    minimum = min(numbers)
    maximum = max(numbers)
    
    # Calculate standard deviation
    variance = sum((x - average) ** 2 for x in numbers) / count
    std_deviation = math.sqrt(variance)
    
    # Categorize numbers
    positive = [n for n in numbers if n > 0]
    negative = [n for n in numbers if n < 0]
    zeros = [n for n in numbers if n == 0]
    
    # Create result dictionary
    result = {
        "count": count,
        "sum": total,
        "average": round(average, 2),
        "min": minimum,
        "max": maximum,
        "std_deviation": round(std_deviation, 2),
        "positive_count": len(positive),
        "negative_count": len(negative),
        "zero_count": len(zeros),
        "analysis_time": datetime.now().isoformat()
    }
    
    return result


def demonstrate_syntax_features():
    """Demonstrate various Python syntax features."""
    
    # 1. Variable assignments and multiple assignments
    x, y, z = 10, 20, 30
    a = b = c = 0
    
    print("=== Variable Assignments ===")
    print(f"x={x}, y={y}, z={z}")
    print(f"a={a}, b={b}, c={c}")
    
    # 2. String formatting methods
    name = "Python"
    version = 3.12
    
    print("\n=== String Formatting ===")
    print("Old style: %s version %.1f" % (name, version))
    print("New style: {} version {:.1f}".format(name, version))
    print(f"F-string: {name} version {version:.1f}")
    
    # 3. List comprehensions vs traditional loops
    numbers = range(1, 11)
    
    print("\n=== List Comprehensions vs Loops ===")
    
    # Traditional loop
    squares_loop = []
    for num in numbers:
        if num % 2 == 0:
            squares_loop.append(num ** 2)
    
    # List comprehension (more Pythonic)
    squares_comprehension = [num ** 2 for num in numbers if num % 2 == 0]
    
    print(f"Traditional loop result: {squares_loop}")
    print(f"List comprehension result: {squares_comprehension}")
    print(f"Results are equal: {squares_loop == squares_comprehension}")
    
    # 4. Dictionary comprehensions
    print("\n=== Dictionary Comprehensions ===")
    word_lengths = {word: len(word) for word in ["Python", "is", "awesome"]}
    print(f"Word lengths: {word_lengths}")
    
    # 5. Conditional expressions (ternary operator)
    print("\n=== Conditional Expressions ===")
    for num in [-5, 0, 5, 10]:
        # Traditional if-else
        if num >= 0:
            result_traditional = "positive or zero"
        else:
            result_traditional = "negative"
        
        # Ternary operator (more concise)
        result_ternary = "positive or zero" if num >= 0 else "negative"
        
        print(f"Number {num:2d}: {result_traditional} (ternary: {result_ternary})")
    
    # 6. Exception handling
    print("\n=== Exception Handling ===")
    test_values = [10, 0, "invalid", -5]
    
    for value in test_values:
        try:
            # This might raise various exceptions
            if isinstance(value, str):
                raise ValueError(f"Cannot process string: {value}")
            
            result = 100 / value
            sqrt_result = math.sqrt(abs(value))
            
            print(f"✅ {value}: division=%.2f, sqrt=%.2f" % (result, sqrt_result))
            
        except ZeroDivisionError:
            print(f"❌ {value}: Cannot divide by zero")
        except ValueError as e:
            print(f"❌ {value}: {e}")
        except Exception as e:
            print(f"❌ {value}: Unexpected error: {e}")
    
    # 7. Working with functions and return values
    print("\n=== Function Analysis ===")
    test_data = [1, 2, 3, -1, 0, 5.5, -2.3]
    analysis = analyze_numbers(test_data)
    
    print("Analysis results:")
    for key, value in analysis.items():
        print(f"  {key}: {value}")


def main():
    """Main function demonstrating proper program structure."""
    print("🐍 Python Syntax Showcase")
    print("=" * 50)
    
    try:
        demonstrate_syntax_features()
        
        # Interactive section
        print("\n" + "=" * 50)
        print("Interactive Section")
        
        user_input = input("Enter numbers separated by spaces: ").strip()
        
        if user_input:
            try:
                # Parse user input
                user_numbers = [float(x) for x in user_input.split()]
                user_analysis = analyze_numbers(user_numbers)
                
                print("\nYour numbers analysis:")
                for key, value in user_analysis.items():
                    if key != "analysis_time":
                        print(f"  {key}: {value}")
                        
            except ValueError:
                print("❌ Please enter valid numbers only")
        else:
            print("No input provided, skipping analysis")
            
    except KeyboardInterrupt:
        print("\n\n👋 Program interrupted by user")
    except Exception as e:
        print(f"\n❌ An unexpected error occurred: {e}")
    
    print("\nThanks for exploring Python syntax! 🎉")


if __name__ == "__main__":
    main()
```

### Python Naming Conventions

Following PEP 8 naming conventions:

```python
# Variables and functions: snake_case
user_name = "Alice"
total_count = 100

def calculate_tax_amount(gross_income, tax_rate):
    """Calculate tax amount based on income and rate."""
    return gross_income * tax_rate

# Constants: UPPER_CASE
PI = 3.14159
MAX_RETRIES = 5
DEFAULT_TIMEOUT = 30

# Classes: PascalCase
class BankAccount:
    """Represents a bank account."""
    
    def __init__(self, account_number, initial_balance=0):
        self.account_number = account_number
        self._balance = initial_balance  # Protected attribute
        self.__pin = None  # Private attribute
    
    def deposit(self, amount):
        """Deposit money into account."""
        if amount > 0:
            self._balance += amount
            return True
        return False

# Modules and packages: lowercase
# mymodule.py, mypackage/

# Private methods: leading underscore
class Calculator:
    def calculate(self, expression):
        """Public method to calculate expression."""
        return self._parse_expression(expression)
    
    def _parse_expression(self, expr):
        """Private helper method."""
        # Implementation details
        pass
```

### Operators and Expressions

#### Arithmetic Operators

```python
# Basic arithmetic
a, b = 10, 3

print(f"Addition: {a} + {b} = {a + b}")        # 13
print(f"Subtraction: {a} - {b} = {a - b}")     # 7
print(f"Multiplication: {a} * {b} = {a * b}")  # 30
print(f"Division: {a} / {b} = {a / b}")        # 3.333...
print(f"Floor Division: {a} // {b} = {a // b}") # 3
print(f"Modulus: {a} % {b} = {a % b}")         # 1
print(f"Exponentiation: {a} ** {b} = {a ** b}") # 1000
```

#### Comparison Operators

```python
x, y = 5, 10

print(f"Equal: {x} == {y} is {x == y}")              # False
print(f"Not equal: {x} != {y} is {x != y}")          # True
print(f"Less than: {x} < {y} is {x < y}")            # True
print(f"Greater than: {x} > {y} is {x > y}")         # False
print(f"Less or equal: {x} <= {y} is {x <= y}")      # True
print(f"Greater or equal: {x} >= {y} is {x >= y}")   # False

# Chained comparisons (unique to Python)
age = 25
print(f"Adult: 18 <= {age} <= 65 is {18 <= age <= 65}")  # True
```

#### Logical Operators

```python
p, q = True, False

print(f"AND: {p} and {q} = {p and q}")        # False
print(f"OR: {p} or {q} = {p or q}")           # True
print(f"NOT: not {p} = {not p}")              # False

# Short-circuit evaluation
def expensive_function():
    print("This function is called")
    return True

print("Testing short-circuit:")
result1 = False and expensive_function()  # expensive_function not called
result2 = True or expensive_function()    # expensive_function not called
print(f"Results: {result1}, {result2}")
```

#### Identity and Membership Operators

```python
# Identity operators
a = [1, 2, 3]
b = a        # b refers to same object as a
c = [1, 2, 3]  # c is a new object with same content

print(f"a is b: {a is b}")        # True
print(f"a is c: {a is c}")        # False
print(f"a == c: {a == c}")        # True

# Membership operators
fruits = ["apple", "banana", "cherry"]
print(f"'apple' in fruits: {'apple' in fruits}")        # True
print(f"'grape' not in fruits: {'grape' not in fruits}") # True

text = "Hello, World!"
print(f"'World' in text: {'World' in text}")            # True
```

### ⚠️ Common Syntax Pitfalls

1. **Indentation Errors**
   ```python
   # Wrong
   if True:
   print("Missing indentation")
   
   # Correct
   if True:
       print("Proper indentation")
   ```

2. **Mixing Tabs and Spaces**
   ```python
   # Wrong - mixing tabs and spaces
   if True:
       print("Using spaces")
   	print("Using tab")  # This will cause IndentationError
   
   # Correct - consistent spacing
   if True:
       print("Using spaces")
       print("Using spaces consistently")
   ```

3. **Forgetting Colons**
   ```python
   # Wrong
   if x > 0
       print("Positive")
   
   # Correct
   if x > 0:
       print("Positive")
   ```

4. **Assignment vs Equality**
   ```python
   # Wrong - assignment in condition
   x = 5
   if x = 5:  # SyntaxError
       print("Equal to 5")
   
   # Correct - comparison
   x = 5
   if x == 5:
       print("Equal to 5")
   ```

### ✅ Best Practices for Python Syntax

1. **Consistent Indentation**: Use 4 spaces, not tabs
2. **Meaningful Names**: Choose descriptive variable and function names
3. **Line Length**: Keep lines under 79 characters (PEP 8)
4. **Blank Lines**: Use blank lines to separate logical sections
5. **Comments**: Write clear, helpful comments
6. **Docstrings**: Document functions, classes, and modules
7. **Error Handling**: Use try-except blocks appropriately

### 🏋️ Exercise 5: Syntax and Style Practice
**Difficulty:** 🟡 Intermediate  
**Estimated Time:** 25 minutes

Create a program that demonstrates proper Python syntax and style:
1. Write a class called `StudentGradeAnalyzer`
2. It should store student names and their grades
3. Include methods to add students, calculate averages, and find top performers
4. Follow all PEP 8 conventions
5. Include proper error handling and documentation
6. Add a main function that demonstrates the class usage

<details>
<summary>💡 Click to see hints</summary>

- Use snake_case for methods and variables
- Use PascalCase for class names  
- Include docstrings for class and methods
- Handle edge cases (empty data, invalid grades)
- Use list comprehensions where appropriate
- Follow proper indentation and spacing

</details>

<details>
<summary>✅ Click to see solution</summary>

```python
#!/usr/bin/env python3
"""
Student Grade Analyzer
A program demonstrating proper Python syntax and PEP 8 style guidelines.
"""

from typing import List, Dict, Optional, Tuple


class StudentGradeAnalyzer:
    """
    Analyzes student grades and provides statistical information.
    
    This class manages student data and provides methods for analyzing
    academic performance including averages, grade distributions, and
    identifying top performers.
    """
    
    def __init__(self):
        """Initialize the analyzer with empty student data."""
        self._students: Dict[str, List[float]] = {}
        self._grade_scale = {
            'A': (90, 100),
            'B': (80, 89),
            'C': (70, 79), 
            'D': (60, 69),
            'F': (0, 59)
        }
    
    def add_student(self, name: str, grades: Optional[List[float]] = None) -> bool:
        """
        Add a new student to the analyzer.
        
        Args:
            name (str): Student's name
            grades (List[float], optional): Initial grades for the student
        
        Returns:
            bool: True if student was added successfully, False otherwise
        
        Raises:
            ValueError: If name is empty or grades contain invalid values
        """
        # Validate input
        if not name or not isinstance(name, str):
            raise ValueError("Student name must be a non-empty string")
        
        name = name.strip()
        if not name:
            raise ValueError("Student name cannot be just whitespace")
        
        # Initialize grades list
        if grades is None:
            grades = []
        
        # Validate grades
        if not self._validate_grades(grades):
            raise ValueError("All grades must be numbers between 0 and 100")
        
        # Add student (update if already exists)
        self._students[name] = list(grades)  # Create a copy
        return True
    
    def add_grade(self, student_name: str, grade: float) -> bool:
        """
        Add a grade for an existing student.
        
        Args:
            student_name (str): Name of the student
            grade (float): Grade to add (0-100)
        
        Returns:
            bool: True if grade was added successfully
        
        Raises:
            ValueError: If student doesn't exist or grade is invalid
        """
        if student_name not in self._students:
            raise ValueError(f"Student '{student_name}' not found")
        
        if not self._validate_grades([grade]):
            raise ValueError("Grade must be a number between 0 and 100")
        
        self._students[student_name].append(grade)
        return True
    
    def get_student_average(self, student_name: str) -> float:
        """
        Calculate average grade for a specific student.
        
        Args:
            student_name (str): Name of the student
        
        Returns:
            float: Average grade rounded to 2 decimal places
        
        Raises:
            ValueError: If student doesn't exist or has no grades
        """
        if student_name not in self._students:
            raise ValueError(f"Student '{student_name}' not found")
        
        grades = self._students[student_name]
        if not grades:
            raise ValueError(f"No grades recorded for '{student_name}'")
        
        return round(sum(grades) / len(grades), 2)
    
    def get_class_average(self) -> float:
        """
        Calculate the overall class average.
        
        Returns:
            float: Class average rounded to 2 decimal places
        
        Raises:
            ValueError: If no students or no grades recorded
        """
        all_grades = []
        for grades in self._students.values():
            all_grades.extend(grades)
        
        if not all_grades:
            raise ValueError("No grades recorded for any student")
        
        return round(sum(all_grades) / len(all_grades), 2)
    
    def get_top_performers(self, count: int = 3) -> List[Tuple[str, float]]:
        """
        Get top performing students based on average grades.
        
        Args:
            count (int): Number of top performers to return (default: 3)
        
        Returns:
            List[Tuple[str, float]]: List of (student_name, average) tuples
        
        Raises:
            ValueError: If count is not positive
        """
        if count <= 0:
            raise ValueError("Count must be a positive integer")
        
        # Calculate averages for students with grades
        student_averages = []
        for name, grades in self._students.items():
            if grades:  # Only include students with grades
                avg = sum(grades) / len(grades)
                student_averages.append((name, round(avg, 2)))
        
        if not student_averages:
            return []
        
        # Sort by average (descending) and return top performers
        student_averages.sort(key=lambda x: x[1], reverse=True)
        return student_averages[:count]
    
    def get_grade_distribution(self) -> Dict[str, int]:
        """
        Get distribution of letter grades across all students.
        
        Returns:
            Dict[str, int]: Dictionary mapping letter grades to counts
        """
        distribution = {grade: 0 for grade in self._grade_scale.keys()}
        
        for grades in self._students.values():
            for grade in grades:
                letter_grade = self._get_letter_grade(grade)
                distribution[letter_grade] += 1
        
        return distribution
    
    def get_student_summary(self) -> Dict[str, Dict]:
        """
        Get comprehensive summary for all students.
        
        Returns:
            Dict[str, Dict]: Dictionary with student summaries
        """
        summary = {}
        
        for name, grades in self._students.items():
            if grades:
                avg = round(sum(grades) / len(grades), 2)
                letter_grade = self._get_letter_grade(avg)
                summary[name] = {
                    'grades': grades,
                    'average': avg,
                    'letter_grade': letter_grade,
                    'grade_count': len(grades),
                    'highest': max(grades),
                    'lowest': min(grades)
                }
            else:
                summary[name] = {
                    'grades': [],
                    'average': None,
                    'letter_grade': None,
                    'grade_count': 0,
                    'highest': None,
                    'lowest': None
                }
        
        return summary
    
    def _validate_grades(self, grades: List[float]) -> bool:
        """
        Validate that all grades are valid numbers between 0 and 100.
        
        Args:
            grades (List[float]): List of grades to validate
        
        Returns:
            bool: True if all grades are valid
        """
        return all(
            isinstance(grade, (int, float)) and 0 <= grade <= 100 
            for grade in grades
        )
    
    def _get_letter_grade(self, numerical_grade: float) -> str:
        """
        Convert numerical grade to letter grade.
        
        Args:
            numerical_grade (float): Numerical grade (0-100)
        
        Returns:
            str: Corresponding letter grade
        """
        for letter, (min_grade, max_grade) in self._grade_scale.items():
            if min_grade <= numerical_grade <= max_grade:
                return letter
        return 'F'  # Fallback
    
    def __str__(self) -> str:
        """String representation of the analyzer."""
        return f"StudentGradeAnalyzer with {len(self._students)} students"
    
    def __len__(self) -> int:
        """Return number of students."""
        return len(self._students)


def demonstrate_analyzer():
    """Demonstrate the StudentGradeAnalyzer functionality."""
    print("🎓 Student Grade Analyzer Demo")
    print("=" * 40)
    
    # Create analyzer instance
    analyzer = StudentGradeAnalyzer()
    
    # Add students with initial grades
    students_data = [
        ("Alice Johnson", [85, 92, 88, 91]),
        ("Bob Smith", [78, 85, 82, 79]),
        ("Charlie Brown", [95, 98, 93, 97]),
        ("Diana Prince", [88, 85, 90, 87]),
        ("Eve Wilson", [72, 75, 78, 74])
    ]
    
    print("Adding students...")
    for name, grades in students_data:
        try:
            analyzer.add_student(name, grades)
            print(f"✅ Added {name} with {len(grades)} grades")
        except ValueError as e:
            print(f"❌ Error adding {name}: {e}")
    
    # Add additional grades
    print("\nAdding additional grades...")
    additional_grades = [
        ("Alice Johnson", 89),
        ("Bob Smith", 81),
        ("Charlie Brown", 96)
    ]
    
    for name, grade in additional_grades:
        try:
            analyzer.add_grade(name, grade)
            print(f"✅ Added grade {grade} for {name}")
        except ValueError as e:
            print(f"❌ Error adding grade for {name}: {e}")
    
    # Display class statistics
    print(f"\n📊 Class Statistics:")
    print(f"Total students: {len(analyzer)}")
    
    try:
        class_avg = analyzer.get_class_average()
        print(f"Class average: {class_avg:.2f}")
    except ValueError as e:
        print(f"Cannot calculate class average: {e}")
    
    # Show top performers
    print(f"\n🏆 Top Performers:")
    top_performers = analyzer.get_top_performers(3)
    for i, (name, avg) in enumerate(top_performers, 1):
        print(f"{i}. {name}: {avg:.2f}")
    
    # Grade distribution
    print(f"\n📈 Grade Distribution:")
    distribution = analyzer.get_grade_distribution()
    for letter, count in distribution.items():
        print(f"{letter}: {count} grades")
    
    # Individual student summaries
    print(f"\n👥 Student Summaries:")
    summaries = analyzer.get_student_summary()
    for name, data in summaries.items():
        if data['average'] is not None:
            print(f"{name}:")
            print(f"  Average: {data['average']:.2f} ({data['letter_grade']})")
            print(f"  Range: {data['lowest']:.0f} - {data['highest']:.0f}")
            print(f"  Total grades: {data['grade_count']}")
        else:
            print(f"{name}: No grades recorded")


def interactive_mode():
    """Interactive mode for user input."""
    print("\n" + "="*40)
    print("🔄 Interactive Mode")
    print("Add your own students and grades!")
    
    analyzer = StudentGradeAnalyzer()
    
    while True:
        print("\nOptions:")
        print("1. Add student")
        print("2. Add grade to existing student")
        print("3. Show class statistics")
        print("4. Exit")
        
        try:
            choice = input("\nEnter your choice (1-4): ").strip()
            
            if choice == '1':
                name = input("Enter student name: ").strip()
                grades_input = input("Enter grades separated by spaces (or press Enter for none): ").strip()
                
                grades = []
                if grades_input:
                    grades = [float(x) for x in grades_input.split()]
                
                analyzer.add_student(name, grades)
                print(f"✅ Added {name} successfully!")
                
            elif choice == '2':
                name = input("Enter student name: ").strip()
                grade = float(input("Enter grade: "))
                
                analyzer.add_grade(name, grade)
                print(f"✅ Added grade {grade} for {name}!")
                
            elif choice == '3':
                if len(analyzer) == 0:
                    print("No students added yet!")
                    continue
                
                print(f"\n📊 Statistics for {len(analyzer)} students:")
                
                try:
                    avg = analyzer.get_class_average()
                    print(f"Class average: {avg:.2f}")
                    
                    top = analyzer.get_top_performers(min(3, len(analyzer)))
                    print("\nTop performers:")
                    for i, (name, score) in enumerate(top, 1):
                        print(f"  {i}. {name}: {score:.2f}")
                        
                except ValueError as e:
                    print(f"Cannot show statistics: {e}")
                
            elif choice == '4':
                print("👋 Goodbye!")
                break
            else:
                print("Invalid choice! Please enter 1-4.")
                
        except ValueError as e:
            print(f"❌ Error: {e}")
        except KeyboardInterrupt:
            print("\n👋 Goodbye!")
            break
        except Exception as e:
            print(f"❌ Unexpected error: {e}")


def main():
    """Main function demonstrating the complete program."""
    try:
        # Run demonstration
        demonstrate_analyzer()
        
        # Ask user if they want interactive mode
        user_choice = input("\nWould you like to try interactive mode? (y/n): ").lower().strip()
        
        if user_choice == 'y':
            interactive_mode()
        
        print("\nThank you for using Student Grade Analyzer! 🎉")
        
    except KeyboardInterrupt:
        print("\n👋 Program interrupted. Goodbye!")
    except Exception as e:
        print(f"❌ An unexpected error occurred: {e}")


if __name__ == "__main__":
    main()
```

**Explanation:**
- **PEP 8 Compliance**: Uses snake_case for variables/functions, PascalCase for classes
- **Type Hints**: Includes type annotations for better code documentation
- **Error Handling**: Comprehensive validation and exception handling
- **Documentation**: Detailed docstrings for all public methods
- **Encapsulation**: Private methods indicated with leading underscore
- **Clean Structure**: Logical organization with proper separation of concerns
- **Interactive Features**: Demonstrates both programmatic and user-driven functionality

</details>

[🔝 Back to Top](#-python-documentation)

---

## 📊 Chapter 6: Variables & Data Types
📊 **Progress:** Chapter 6 of 30  
🎯 **Learning Objectives:** Master Python's data types and variable handling  
⏱️ **Estimated Reading Time:** 30 minutes  
📋 **Prerequisites:** Understanding of Python syntax

### Python's Dynamic Type System

Python is **dynamically typed**, meaning you don't need to declare variable types explicitly. The interpreter determines types at runtime based on the assigned values.

```python
# Dynamic typing in action
x = 42          # x is an integer
print(type(x))  # <class 'int'>

x = "Hello"     # Now x is a string
print(type(x))  # <class 'str'>

x = [1, 2, 3]   # Now x is a list
print(type(x))  # <class 'list'>
```

### Built-in Data Types

#### Numeric Types

**Integers (int)**
```python
# Integer literals
positive_num = 42
negative_num = -17
zero = 0

# Different number bases
binary = 0b1010      # Binary (10 in decimal)
octal = 0o12         # Octal (10 in decimal)
hexadecimal = 0xa    # Hexadecimal (10 in decimal)

# Large integers (unlimited precision)
big_number = 123456789012345678901234567890
print(f"Big number: {big_number}")

# Integer operations
a, b = 15, 4
print(f"Division: {a / b}")        # 3.75 (float)
print(f"Floor division: {a // b}") # 3 (integer)
print(f"Modulus: {a % b}")         # 3
print(f"Power: {a ** b}")          # 50625
```

**Floating Point Numbers (float)**
```python
# Float literals
pi = 3.14159
scientific = 1.23e-4  # Scientific notation (0.000123)
negative_float = -2.5

# Float precision and limitations
print(f"0.1 + 0.2 = {0.1 + 0.2}")  # 0.30000000000000004
print(f"Rounded: {round(0.1 + 0.2, 2)}")  # 0.3

# Float methods
num = 3.14159
print(f"As integer ratio: {num.as_integer_ratio()}")  # (884279719003555, 281474976710656)
print(f"Is integer: {num.is_integer()}")              # False
print((4.0).is_integer())                             # True
```

**Complex Numbers (complex)**
```python
# Complex number creation
z1 = 3 + 4j
z2 = complex(2, -1)  # 2 - 1j

print(f"z1: {z1}")
print(f"z2: {z2}")
print(f"z1.real: {z1.real}")      # 3.0
print(f"z1.imag: {z1.imag}")      # 4.0
print(f"Conjugate: {z1.conjugate()}")  # (3-4j)

# Complex operations
result = z1 * z2
print(f"z1 * z2 = {result}")
```

#### Text Type (str)

**String Creation and Basic Operations**
```python
# String creation methods
single_quotes = 'Hello, World!'
double_quotes = "Python Programming"
triple_quotes = """Multi-line
string with
line breaks"""

# String concatenation
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name
print(f"Full name: {full_name}")

# String multiplication
separator = "-" * 40
print(separator)

# String methods
text = "  Python Programming  "
print(f"Original: '{text}'")
print(f"Stripped: '{text.strip()}'")
print(f"Upper: {text.upper()}")
print(f"Lower: {text.lower()}")
print(f"Title: {text.title()}")
print(f"Replace: {text.replace('Python', 'Java')}")
```

**String Formatting**
```python
name = "Alice"
age = 30
balance = 1234.567

# Old-style formatting (avoid in new code)
old_style = "Name: %s, Age: %d, Balance: %.2f" % (name, age, balance)

# str.format() method
new_style = "Name: {}, Age: {}, Balance: {:.2f}".format(name, age, balance)
named_format = "Name: {n}, Age: {a}, Balance: {b:.2f}".format(n=name, a=age, b=balance)

# f-strings (recommended, Python 3.6+)
f_string = f"Name: {name}, Age: {age}, Balance: {balance:.2f}"

print("Formatting comparison:")
print(f"Old style: {old_style}")
print(f"New style: {new_style}")
print(f"Named: {named_format}")
print(f"F-string: {f_string}")

# Advanced f-string formatting
import datetime
now = datetime.datetime.now()
print(f"Current time: {now:%Y-%m-%d %H:%M:%S}")

# Expressions in f-strings
x, y = 10, 3
print(f"{x} + {y} = {x + y}")
print(f"Is {x} > {y}? {x > y}")
```

#### Boolean Type (bool)

```python
# Boolean literals
is_active = True
is_complete = False

# Boolean from other types
print(f"bool(1): {bool(1)}")        # True
print(f"bool(0): {bool(0)}")        # False
print(f"bool(''): {bool('')}")      # False
print(f"bool('text'): {bool('text')}") # True
print(f"bool([]): {bool([])}")      # False
print(f"bool([1]): {bool([1])}")    # True

# Falsy values in Python
falsy_values = [False, None, 0, 0.0, '', [], {}, set()]
for value in falsy_values:
    print(f"{repr(value):>10} is {'falsy' if not value else 'truthy'}")

# Boolean operations
a, b = True, False
print(f"a and b: {a and b}")        # False
print(f"a or b: {a or b}")          # True
print(f"not a: {not a}")            # False

# Short-circuit evaluation
def expensive_operation():
    print("Expensive operation called!")
    return True

print("Testing short-circuit:")
result1 = False and expensive_operation()  # expensive_operation not called
print(f"Result1: {result1}")

result2 = True or expensive_operation()    # expensive_operation not called
print(f"Result2: {result2}")
```

#### None Type

```python
# None represents absence of value
empty_value = None
print(f"Type of None: {type(empty_value)}")

# Common use cases for None
def get_user_age(user_id):
    """Return user age or None if user not found."""
    users = {1: 25, 2: 30, 3: 35}
    return users.get(user_id)  # Returns None if key not found

# Checking for None
user_age = get_user_age(999)
if user_age is None:
    print("User not found")
else:
    print(f"User age: {user_age}")

# None vs False vs 0 vs empty string
values = [None, False, 0, '', []]
for value in values:
    print(f"{repr(value):>10}: is None? {value is None}, is falsy? {not bool(value)}")
```

### 💡 Code Example: Data Type Explorer

```python
#!/usr/bin/env python3
"""
Python Data Type Explorer
Comprehensive demonstration of Python's built-in data types.
"""

import sys
from decimal import Decimal
from fractions import Fraction
import datetime


class DataTypeExplorer:
    """Explores and demonstrates Python data types."""
    
    def __init__(self):
        """Initialize the explorer with sample data."""
        self.sample_data = {
            'integers': [42, -17, 0, 999999999999999999999],
            'floats': [3.14, -2.5, 1.23e-4, float('inf'), float('-inf')],
            'strings': ['Hello', 'Python', '', '123', 'Multi\nline'],
            'booleans': [True, False],
            'complex_numbers': [3+4j, complex(2, -1), 1j],
            'none_value': [None]
        }
    
    def explore_numeric_types(self):
        """Demonstrate numeric types and operations."""
        print("🔢 Numeric Types Exploration")
        print("=" * 40)
        
        # Integer exploration
        print("\n📊 Integer Operations:")
        a, b = 17, 5
        operations = [
            ('+', a + b),
            ('-', a - b),
            ('*', a * b),
            ('/', a / b),
            ('//', a // b),
            ('%', a % b),
            ('**', a ** b),
            ('divmod', divmod(a, b))
        ]
        
        for op, result in operations:
            print(f"  {a} {op} {b} = {result}")
        
        # Float precision issues
        print("\n⚠️  Float Precision Issues:")
        calculations = [
            (0.1 + 0.2, "0.1 + 0.2"),
            (0.1 + 0.1 + 0.1, "0.1 + 0.1 + 0.1"),
            (1.0 - 0.9, "1.0 - 0.9")
        ]
        
        for result, expression in calculations:
            print(f"  {expression} = {result}")
            print(f"    Rounded to 10 decimals: {round(result, 10)}")
        
        # Better alternatives for precision
        print("\n✅ Precision Solutions:")
        from decimal import Decimal
        from fractions import Fraction
        
        # Using Decimal for exact decimal arithmetic
        d1, d2 = Decimal('0.1'), Decimal('0.2')
        print(f"  Decimal('0.1') + Decimal('0.2') = {d1 + d2}")
        
        # Using Fraction for exact rational arithmetic
        f1, f2 = Fraction(1, 3), Fraction(1, 6)
        print(f"  Fraction(1, 3) + Fraction(1, 6) = {f1 + f2}")
    
    def explore_string_features(self):
        """Demonstrate string features and methods."""
        print("\n📝 String Features Exploration")
        print("=" * 40)
        
        sample_text = "  Hello, Python World!  "
        print(f"Original text: '{sample_text}'")
        
        # String methods demonstration
        string_methods = [
            ('strip()', sample_text.strip()),
            ('upper()', sample_text.upper()),
            ('lower()', sample_text.lower()),
            ('title()', sample_text.title()),
            ('swapcase()', sample_text.swapcase()),
            ('replace("Python", "Amazing")', sample_text.replace("Python", "Amazing")),
            ('split()', sample_text.split()),
            ('split(",")', sample_text.split(',')),
            ('count("l")', sample_text.count('l')),
            ('find("Python")', sample_text.find('Python')),
            ('startswith("  Hello")', sample_text.startswith("  Hello")),
            ('endswith("!  ")', sample_text.endswith("!  "))
        ]
        
        print("\n🔧 String Methods:")
        for method_name, result in string_methods:
            print(f"  {method_name:<25} → {repr(result)}")
        
        # String formatting showcase
        print("\n🎨 String Formatting:")
        name, age, balance = "Alice", 30, 1234.567
        
        formatting_examples = [
            ('f-string', f"Name: {name}, Age: {age}, Balance: ${balance:.2f}"),
            ('format()', "Name: {}, Age: {}, Balance: ${:.2f}".format(name, age, balance)),
            ('% formatting', "Name: %s, Age: %d, Balance: $%.2f" % (name, age, balance))
        ]
        
        for method, result in formatting_examples:
            print(f"  {method:<12} → {result}")
        
        # Advanced f-string features
        print("\n🚀 Advanced F-string Features:")
        import math
        number = 42
        pi_value = math.pi
        now = datetime.datetime.now()
        
        advanced_examples = [
            f"Expression: {number} * 2 = {number * 2}",
            f"Conditional: {number} is {'even' if number % 2 == 0 else 'odd'}",
            f"Function call: sqrt({number}) = {math.sqrt(number):.2f}",
            f"Formatting: π = {pi_value:.6f}",
            f"Date formatting: {now:%Y-%m-%d %H:%M:%S}",
            f"Padding: '{name:>10}' '{name:<10}' '{name:^10}'",
            f"Number formatting: {1234567:,} or {1234567:.2e}"
        ]
        
        for example in advanced_examples:
            print(f"  {example}")
    
    def explore_type_conversion(self):
        """Demonstrate type conversion and casting."""
        print("\n🔄 Type Conversion Exploration")
        print("=" * 40)
        
        # Conversion examples
        original_values = [42, 3.14, "123", "45.67", True, False, [1, 2, 3], None]
        target_types = [int, float, str, bool, list]
        
        print("📋 Type Conversion Table:")
        print(f"{'Original':<15} {'Type':<10} → {'Target':<6} {'Result':<20} {'Success'}")
        print("-" * 70)
        
        for original in original_values:
            for target_type in target_types:
                try:
                    converted = target_type(original)
                    success = "✅"
                    result_str = repr(converted)
                    if len(result_str) > 18:
                        result_str = result_str[:15] + "..."
                except (ValueError, TypeError) as e:
                    success = "❌"
                    result_str = str(e)[:18] + "..." if len(str(e)) > 18 else str(e)
                
                print(f"{repr(original):<15} {type(original).__name__:<10} → {target_type.__name__:<6} {result_str:<20} {success}")
    
    def explore_type_checking(self):
        """Demonstrate type checking methods."""
        print("\n🔍 Type Checking Exploration")
        print("=" * 40)
        
        sample_values = [
            42, 3.14, "Hello", True, None, [1, 2], {"key": "value"}, 
            complex(1, 2), set([1, 2, 3]), lambda x: x
        ]
        
        print("📊 Type Information:")
        for value in sample_values:
            print(f"\nValue: {repr(value)}")
            print(f"  type(): {type(value)}")
            print(f"  type().__name__: {type(value).__name__}")
            print(f"  isinstance(int): {isinstance(value, int)}")
            print(f"  isinstance(str): {isinstance(value, str)}")
            print(f"  isinstance((int, float)): {isinstance(value, (int, float))}")
            
            # Check if it's callable
            if callable(value):
                print(f"  callable(): True (can be called like a function)")
            
            # Check if it has specific attributes
            if hasattr(value, '__len__'):
                try:
                    print(f"  len(): {len(value)}")
                except TypeError:
                    print(f"  len(): Not supported despite having __len__")
    
    def memory_and_identity_exploration(self):
        """Explore memory usage and object identity."""
        print("\n🧠 Memory and Identity Exploration")
        print("=" * 40)
        
        # Small integers are cached
        print("📋 Integer Caching (Small Integers):")
        a = 100
        b = 100
        print(f"a = 100, b = 100")
        print(f"id(a): {id(a)}, id(b): {id(b)}")
        print(f"a is b: {a is b} (same object)")
        
        # Large integers are not cached
        a = 1000
        b = 1000
        print(f"\na = 1000, b = 1000")
        print(f"id(a): {id(a)}, id(b): {id(b)}")
        print(f"a is b: {a is b} (different objects)")
        
        # String interning
        print(f"\n📝 String Behavior:")
        s1 = "hello"
        s2 = "hello"
        s3 = "hello world"
        s4 = "hello world"
        
        comparisons = [
            (s1, s2, "hello"),
            (s3, s4, "hello world")
        ]
        
        for str1, str2, desc in comparisons:
            print(f"{desc}: is comparison = {str1 is str2}, == comparison = {str1 == str2}")
        
        # Memory usage
        print(f"\n💾 Memory Usage:")
        import sys
        test_objects = [
            (42, "integer"),
            (3.14, "float"),
            ("Hello", "string"),
            ([1, 2, 3], "list"),
            ({"a": 1}, "dict"),
            ({1, 2, 3}, "set")
        ]
        
        for obj, desc in test_objects:
            size = sys.getsizeof(obj)
            print(f"  {desc:<10}: {size:>3} bytes - {repr(obj)}")
    
    def run_full_exploration(self):
        """Run complete data type exploration."""
        print("🐍 Python Data Type Explorer")
        print("=" * 50)
        
        try:
            self.explore_numeric_types()
            self.explore_string_features()
            self.explore_type_conversion()
            self.explore_type_checking()
            self.memory_and_identity_exploration()
            
            print(f"\n✅ Exploration completed successfully!")
            print("💡 Key takeaways:")
            print("   - Python is dynamically typed")
            print("   - Be careful with float precision")
            print("   - Use f-strings for formatting")
            print("   - Understand the difference between 'is' and '=='")
            print("   - Know when to use isinstance() vs type()")
            
        except Exception as e:
            print(f"❌ An error occurred during exploration: {e}")


def interactive_type_checker():
    """Interactive tool for checking variable types."""
    print("\n🔧 Interactive Type Checker")
    print("=" * 30)
    print("Enter Python expressions to see their types and values")
    print("Type 'quit' to exit")
    
    while True:
        try:
            user_input = input("\n>>> ").strip()
            
            if user_input.lower() in ['quit', 'exit', 'q']:
                break
            
            if not user_input:
                continue
            
            # Evaluate the expression safely
            try:
                result = eval(user_input)
                print(f"Result: {repr(result)}")
                print(f"Type: {type(result).__name__}")
                print(f"Type details: {type(result)}")
                
                # Additional information based on type
                if isinstance(result, (int, float)):
                    print(f"Numeric value: {result}")
                    if isinstance(result, float):
                        print(f"Is integer: {result.is_integer()}")
                elif isinstance(result, str):
                    print(f"Length: {len(result)} characters")
                    print(f"Is alphanumeric: {result.isalnum()}")
                elif hasattr(result, '__len__'):
                    print(f"Length: {len(result)} items")
                
            except Exception as e:
                print(f"❌ Error evaluating expression: {e}")
                
        except KeyboardInterrupt:
            break
        except EOFError:
            break
    
    print("\n👋 Type checker session ended")


def main():
    """Main function to run the data type exploration."""
    try:
        explorer = DataTypeExplorer()
        explorer.run_full_exploration()
        
        # Ask if user wants interactive mode
        choice = input("\nWould you like to try the interactive type checker? (y/n): ").lower().strip()
        if choice == 'y':
            interactive_type_checker()
        
        print("\n🎉 Thank you for exploring Python data types!")
        
    except KeyboardInterrupt:
        print("\n👋 Program interrupted. Goodbye!")
    except Exception as e:
        print(f"❌ An unexpected error occurred: {e}")


if __name__ == "__main__":
    main()
```

### Variable Assignment and Scoping

#### Variable Assignment Patterns

```python
# Single assignment
name = "Python"

# Multiple assignment (tuple unpacking)
x, y, z = 1, 2, 3

# Swapping variables
a, b = 10, 20
a, b = b, a  # Now a=20, b=10

# Chained assignment
x = y = z = 0

# Augmented assignment
count = 10
count += 5   # count = count + 5
count -= 2   # count = count - 2
count *= 3   # count = count * 3
count //= 2  # count = count // 2

# Unpacking with star operator
numbers = [1, 2, 3, 4, 5]
first, *middle, last = numbers
print(f"First: {first}, Middle: {middle}, Last: {last}")
```

#### Variable Scope

```python
# Global scope
global_var = "I'm global"

def outer_function():
    """Demonstrate different scopes."""
    outer_var = "I'm in outer function"
    
    def inner_function():
        """Inner function with its own scope."""
        inner_var = "I'm in inner function"
        
        # Access variables from different scopes
        print(f"Inner: {inner_var}")
        print(f"Outer: {outer_var}")      # Access outer scope
        print(f"Global: {global_var}")    # Access global scope
    
    inner_function()
    
    # This would cause an error:
    # print(inner_var)  # NameError: name 'inner_var' is not defined

outer_function()

# Global and nonlocal keywords
counter = 0  # Global variable

def increment_global():
    """Modify global variable."""
    global counter
    counter += 1

def create_counter():
    """Create a closure that modifies enclosing scope."""
    count = 0
    
    def increment():
        nonlocal count
        count += 1
        return count
    
    return increment

# Using the functions
print(f"Initial counter: {counter}")
increment_global()
print(f"After increment: {counter}")

my_counter = create_counter()
print(f"Counter 1: {my_counter()}")  # 1
print(f"Counter 2: {my_counter()}")  # 2
print(f"Counter 3: {my_counter()}")  # 3
```

### ⚠️ Common Pitfalls with Variables and Data Types

1. **Mutable Default Arguments**
   ```python
   # Wrong - mutable default argument
   def add_item(item, target_list=[]):
       target_list.append(item)
       return target_list
   
   list1 = add_item("first")     # ['first']
   list2 = add_item("second")    # ['first', 'second'] - Unexpected!
   
   # Correct approach
   def add_item_correct(item, target_list=None):
       if target_list is None:
           target_list = []
       target_list.append(item)
       return target_list
   ```

2. **Integer Division Confusion**
   ```python
   # Python 3 vs Python 2 behavior
   result1 = 5 / 2     # 2.5 (float division)
   result2 = 5 // 2    # 2 (floor division)
   
   # Be explicit about what you want
   print(f"Float division: {5 / 2}")
   print(f"Integer division: {5 // 2}")
   ```

3. **String Mutability Misunderstanding**
   ```python
   # Strings are immutable
   text = "Hello"
   # text[0] = 'h'  # This would cause TypeError
   
   # Correct way to modify strings
   text = text.lower()  # Creates new string
   text = text.replace('H', 'h')  # Creates new string
   ```

### ✅ Best Practices for Variables and Data Types

1. **Use Meaningful Variable Names**
   ```python
   # Bad
   d = 3.14159 * r * r
   
   # Good  
   pi = 3.14159
   area = pi * radius * radius
   ```

2. **Follow Naming Conventions**
   ```python
   # Constants
   PI = 3.14159
   MAX_ATTEMPTS = 3
   
   # Variables and functions
   user_name = "Alice"
   total_count = 100
   
   def calculate_area(radius):
       return PI * radius ** 2
   ```

3. **Use Type Hints (Python 3.5+)**
   ```python
   def calculate_compound_interest(
       principal: float, 
       rate: float, 
       time: int
   ) -> float:
       """Calculate compound interest with type hints."""
       return principal * (1 + rate) ** time
   ```

4. **Handle Type Conversions Safely**
   ```python
   def safe_int_conversion(value: str) -> tuple[bool, int]:
       """Safely convert string to integer."""
       try:
           return True, int(value)
       except (ValueError, TypeError):
           return False, 0
   
   # Usage
   success, number = safe_int_conversion("123")
   if success:
       print(f"Converted number: {number}")
   else:
       print("Conversion failed")
   ```

### 🏋️ Exercise 6: Data Type Manipulation
**Difficulty:** 🟡 Intermediate  
**Estimated Time:** 30 minutes

Create a comprehensive data type manipulation program that:
1. Creates a `DataProcessor` class that can handle different data types
2. Implements methods for type conversion with error handling  
3. Provides statistical analysis for numeric data
4. Includes string manipulation and formatting features
5. Demonstrates proper variable scoping and memory management

<details>
<summary>💡 Click to see hints</summary>

- Use isinstance() for type checking
- Handle conversion errors with try-except blocks
- Implement __str__ and __repr__ for your class
- Use property decorators for computed attributes
- Remember to validate input data types

</details>

<details>
<summary>✅ Click to see solution</summary>

```python
#!/usr/bin/env python3
"""
Data Type Manipulation Program
Comprehensive demonstration of Python data type handling.
"""

from typing import Any, List, Dict, Union, Optional, Tuple
import statistics
import sys
from decimal import Decimal, InvalidOperation
from fractions import Fraction


class DataProcessor:
    """
    A comprehensive data processor that handles various Python data types.
    
    This class provides methods for type conversion, validation, and analysis
    while demonstrating proper error handling and type safety.
    """
    
    def __init__(self):
        """Initialize the data processor with empty storage."""
        self._data_store: Dict[str, List[Any]] = {
            'integers': [],
            'floats': [],
            'strings': [],
            'booleans': [],
            'complex_numbers': [],
            'decimals': [],
            'fractions': [],
            'mixed': []
        }
        self._conversion_history: List[Dict[str, Any]] = []
    
    @property
    def data_summary(self) -> Dict[str, int]:
        """Get summary of stored data types."""
        return {category: len(data) for category, data in self._data_store.items()}
    
    @property
    def total_items(self) -> int:
        """Get total number of stored items."""
        return sum(len(data) for data in self._data_store.values())
    
    def add_data(self, value: Any, category: Optional[str] = None) -> bool:
        """
        Add data to the appropriate category.
        
        Args:
            value: The value to add
            category: Optional specific category, auto-detected if None
        
        Returns:
            bool: True if data was added successfully
        """
        if category is None:
            category = self._detect_category(value)
        
        if category in self._data_store:
            self._data_store[category].append(value)
            return True
        else:
            self._data_store['mixed'].append(value)
            return False
    
    def _detect_category(self, value: Any) -> str:
        """Detect the appropriate category for a value."""
        if isinstance(value, bool):  # Check bool before int (bool is subclass of int)
            return 'booleans'
        elif isinstance(value, int):
            return 'integers'
        elif isinstance(value, float):
            return 'floats'
        elif isinstance(value, str):
            return 'strings'
        elif isinstance(value, complex):
            return 'complex_numbers'
        elif isinstance(value, Decimal):
            return 'decimals'
        elif isinstance(value, Fraction):
            return 'fractions'
        else:
            return 'mixed'
    
    def safe_convert(self, value: Any, target_type: type) -> Tuple[bool, Any, str]:
        """
        Safely convert a value to target type with detailed error reporting.
        
        Args:
            value: Value to convert
            target_type: Target type to convert to
        
        Returns:
            Tuple of (success, converted_value, message)
        """
        original_type = type(value).__name__
        
        try:
            if target_type == bool:
                # Special handling for boolean conversion
                if isinstance(value, str):
                    if value.lower() in ['true', '1', 'yes', 'on']:
                        converted = True
                    elif value.lower() in ['false', '0', 'no', 'off', '']:
                        converted = False
                    else:
                        converted = bool(value)
                else:
                    converted = bool(value)
            elif target_type == complex:
                if isinstance(value, str):
                    # Handle string representations of complex numbers
                    converted = complex(value.replace(' ', ''))
                else:
                    converted = complex(value)
            elif target_type == Decimal:
                converted = Decimal(str(value))
            elif target_type == Fraction:
                converted = Fraction(value)
            else:
                converted = target_type(value)
            
            # Record successful conversion
            conversion_record = {
                'original_value': value,
                'original_type': original_type,
                'target_type': target_type.__name__,
                'converted_value': converted,
                'success': True
            }
            self._conversion_history.append(conversion_record)
            
            return True, converted, f"Successfully converted {original_type} to {target_type.__name__}"
            
        except (ValueError, TypeError, InvalidOperation) as e:
            # Record failed conversion
            conversion_record = {
                'original_value': value,
                'original_type': original_type,
                'target_type': target_type.__name__,
                'converted_value': None,
                'success': False,
                'error': str(e)
            }
            self._conversion_history.append(conversion_record)
            
            return False, None, f"Failed to convert {original_type} to {target_type.__name__}: {str(e)}"
    
    def analyze_numeric_data(self) -> Dict[str, Any]:
        """
        Analyze all numeric data and provide statistical summary.
        
        Returns:
            Dict containing statistical analysis
        """
        # Collect all numeric values
        numeric_values = []
        numeric_values.extend(self._data_store['integers'])
        numeric_values.extend(self._data_store['floats'])
        
        # Convert decimals and fractions to float for analysis
        numeric_values.extend([float(d) for d in self._data_store['decimals']])
        numeric_values.extend([float(f) for f in self._data_store['fractions']])
        
        if not numeric_values:
            return {"error": "No numeric data available"}
        
        try:
            analysis = {
                'count': len(numeric_values),
                'sum': sum(numeric_values),
                'mean': statistics.mean(numeric_values),
                'median': statistics.median(numeric_values),
                'min': min(numeric_values),
                'max': max(numeric_values),
                'range': max(numeric_values) - min(numeric_values)
            }
            
            # Add standard deviation if we have enough data points
            if len(numeric_values) > 1:
                analysis['std_dev'] = statistics.stdev(numeric_values)
                analysis['variance'] = statistics.variance(numeric_values)
            
            # Add mode if possible
            try:
                analysis['mode'] = statistics.mode(numeric_values)
            except statistics.StatisticsError:
                analysis['mode'] = "No unique mode"
            
            return analysis
            
        except Exception as e:
            return {"error": f"Analysis failed: {str(e)}"}
    
    def analyze_string_data(self) -> Dict[str, Any]:
        """
        Analyze string data and provide comprehensive summary.
        
        Returns:
            Dict containing string analysis
        """
        strings = self._data_store['strings']
        
        if not strings:
            return {"error": "No string data available"}
        
        # Calculate various string metrics
        lengths = [len(s) for s in strings]
        total_chars = sum(lengths)
        
        # Count different character types
        alpha_count = sum(1 for s in strings if s.isalpha())
        numeric_count = sum(1 for s in strings if s.isdigit())
        alphanumeric_count = sum(1 for s in strings if s.isalnum())
        
        # Find common characteristics
        empty_strings = sum(1 for s in strings if not s)
        whitespace_only = sum(1 for s in strings if s.isspace())
        
        analysis = {
            'total_strings': len(strings),
            'total_characters': total_chars,
            'average_length': total_chars / len(strings) if strings else 0,
            'shortest_length': min(lengths) if lengths else 0,
            'longest_length': max(lengths) if lengths else 0,
            'empty_strings': empty_strings,
            'whitespace_only': whitespace_only,
            'alphabetic_strings': alpha_count,
            'numeric_strings': numeric_count,
            'alphanumeric_strings': alphanumeric_count,
            'unique_strings': len(set(strings)),
            'most_common': max(set(strings), key=strings.count) if strings else None
        }
        
        return analysis
    
    def get_conversion_history(self) -> List[Dict[str, Any]]:
        """Get the history of all type conversions."""
        return self._conversion_history.copy()
    
    def clear_data(self, category: Optional[str] = None) -> bool:
        """
        Clear data from specified category or all categories.
        
        Args:
            category: Specific category to clear, or None for all
        
        Returns:
            bool: True if data was cleared
        """
        if category is None:
            for cat in self._data_store:
                self._data_store[cat].clear()
            self._conversion_history.clear()
            return True
        elif category in self._data_store:
            self._data_store[category].clear()
            return True
        else:
            return False
    
    def memory_usage_report(self) -> Dict[str, int]:
        """Get memory usage report for stored data."""
        report = {}
        for category, data in self._data_store.items():
            total_size = sum(sys.getsizeof(item) for item in data)
            report[category] = {
                'items': len(data),
                'total_bytes': total_size,
                'average_bytes': total_size / len(data) if data else 0
            }
        return report
    
    def __str__(self) -> str:
        """String representation of the processor."""
        return f"DataProcessor with {self.total_items} items across {len(self._data_store)} categories"
    
    def __repr__(self) -> str:
        """Developer-friendly representation."""
        return f"DataProcessor(total_items={self.total_items}, categories={list(self._data_store.keys())})"


def demonstrate_data_processor():
    """Demonstrate the DataProcessor functionality."""
    print("🔧 Data Processor Demonstration")
    print("=" * 40)
    
    processor = DataProcessor()
    
    # Sample data of various types
    sample_data = [
        42, 3.14, "Hello", True, 2+3j, "123", False, 
        -17, 2.718, "Python", 0, "", "42.5", None
    ]
    
    print("📥 Adding sample data...")
    for item in sample_data:
        success = processor.add_data(item)
        print(f"  Added {repr(item):>10} ({type(item).__name__}) - {'✅' if success else '❌'}")
    
    print(f"\n📊 Data Summary:")
    summary = processor.data_summary
    for category, count in summary.items():
        if count > 0:
            print(f"  {category}: {count} items")
    
    print(f"\n🔄 Testing Type Conversions:")
    conversion_tests = [
        ("123", int),
        ("45.67", float),
        ("True", bool),
        (42, str),
        ("3+4j", complex),
        (3.14159, Decimal),
        ("22/7", Fraction)
    ]
    
    for value, target_type in conversion_tests:
        success, converted, message = processor.safe_convert(value, target_type)
        status = "✅" if success else "❌"
        print(f"  {status} {repr(value)} → {target_type.__name__}: {message}")
        if success:
            print(f"      Result: {repr(converted)}")
    
    # Analyze numeric data
    print(f"\n📈 Numeric Data Analysis:")
    numeric_analysis = processor.analyze_numeric_data()
    if 'error' not in numeric_analysis:
        for key, value in numeric_analysis.items():
            if isinstance(value, float):
                print(f"  {key}: {value:.3f}")
            else:
                print(f"  {key}: {value}")
    else:
        print(f"  {numeric_analysis['error']}")
    
    # Analyze string data
    print(f"\n📝 String Data Analysis:")
    string_analysis = processor.analyze_string_data()
    if 'error' not in string_analysis:
        for key, value in string_analysis.items():
            if isinstance(value, float):
                print(f"  {key}: {value:.2f}")
            else:
                print(f"  {key}: {value}")
    else:
        print(f"  {string_analysis['error']}")
    
    # Memory usage report
    print(f"\n💾 Memory Usage Report:")
    memory_report = processor.memory_usage_report()
    for category, info in memory_report.items():
        if info['items'] > 0:
            print(f"  {category}: {info['items']} items, {info['total_bytes']} bytes total")


def interactive_data_processor():
    """Interactive data processor for user input."""
    print("\n🎮 Interactive Data Processor")
    print("=" * 30)
    
    processor = DataProcessor()
    
    while True:
        print("\nOptions:")
        print("1. Add data")
        print("2. Convert data type")
        print("3. View summary")
        print("4. Analyze numeric data")
        print("5. Analyze string data")
        print("6. View conversion history")
        print("7. Clear data")
        print("8. Exit")
        
        try:
            choice = input("\nEnter choice (1-8): ").strip()
            
            if choice == '1':
                value_input = input("Enter value: ").strip()
                
                # Try to determine the best type for the input
                try:
                    # Try integer first
                    if '.' not in value_input and 'e' not in value_input.lower():
                        value = int(value_input)
                    else:
                        value = float(value_input)
                except ValueError:
                    # Keep as string if not numeric
                    value = value_input
                
                processor.add_data(value)
                print(f"✅ Added {repr(value)} ({type(value).__name__})")
            
            elif choice == '2':
                value_input = input("Enter value to convert: ").strip()
                type_input = input("Enter target type (int/float/str/bool/complex): ").strip().lower()
                
                type_map = {
                    'int': int,
                    'float': float,
                    'str': str,
                    'bool': bool,
                    'complex': complex
                }
                
                if type_input in type_map:
                    success, converted, message = processor.safe_convert(value_input, type_map[type_input])
                    print(f"{'✅' if success else '❌'} {message}")
                    if success:
                        print(f"  Result: {repr(converted)}")
                else:
                    print("❌ Invalid type. Use: int, float, str, bool, or complex")
            
            elif choice == '3':
                print("\n📊 Data Summary:")
                summary = processor.data_summary
                print(f"  Total items: {processor.total_items}")
                for category, count in summary.items():
                    if count > 0:
                        print(f"  {category}: {count}")
            
            elif choice == '4':
                analysis = processor.analyze_numeric_data()
                print("\n📈 Numeric Analysis:")
                if 'error' in analysis:
                    print(f"  {analysis['error']}")
                else:
                    for key, value in analysis.items():
                        if isinstance(value, float):
                            print(f"  {key}: {value:.3f}")
                        else:
                            print(f"  {key}: {value}")
            
            elif choice == '5':
                analysis = processor.analyze_string_data()
                print("\n📝 String Analysis:")
                if 'error' in analysis:
                    print(f"  {analysis['error']}")
                else:
                    for key, value in analysis.items():
                        if isinstance(value, float):
                            print(f"  {key}: {value:.2f}")
                        else:
                            print(f"  {key}: {value}")
            
            elif choice == '6':
                history = processor.get_conversion_history()
                print(f"\n📋 Conversion History ({len(history)} conversions):")
                for i, record in enumerate(history[-10:], 1):  # Show last 10
                    status = "✅" if record['success'] else "❌"
                    print(f"  {i}. {status} {repr(record['original_value'])} "
                          f"({record['original_type']}) → {record['target_type']}")
                    if not record['success']:
                        print(f"     Error: {record.get('error', 'Unknown error')}")
            
            elif choice == '7':
                category = input("Enter category to clear (or 'all' for everything): ").strip()
                if category.lower() == 'all':
                    processor.clear_data()
                    print("✅ All data cleared")
                else:
                    success = processor.clear_data(category)
                    if success:
                        print(f"✅ Cleared {category} data")
                    else:
                        print(f"❌ Category '{category}' not found")
            
            elif choice == '8':
                print("👋 Goodbye!")
                break
            
            else:
                print("❌ Invalid choice. Please enter 1-8.")
        
        except KeyboardInterrupt:
            print("\n👋 Goodbye!")
            break
        except Exception as e:
            print(f"❌ Error: {e}")


def main():
    """Main function for the data type manipulation program."""
    try:
        demonstrate_data_processor()
        
        choice = input("\nWould you like to try interactive mode? (y/n): ").lower().strip()
        if choice == 'y':
            interactive_data_processor()
        
        print("\n🎉 Thanks for exploring Python data types!")
        
    except KeyboardInterrupt:
        print("\n👋 Program interrupted. Goodbye!")
    except Exception as e:
        print(f"❌ Unexpected error: {e}")


if __name__ == "__main__":
    main()
```

**Explanation:**
- **Comprehensive Type Handling**: The DataProcessor handles all major Python data types with automatic categorization
- **Safe Type Conversion**: Implements robust error handling for type conversions with detailed feedback
- **Statistical Analysis**: Provides meaningful statistical analysis for numeric data
- **String Analysis**: Analyzes string data for various characteristics and patterns
- **Memory Management**: Tracks memory usage and provides reporting capabilities
- **Conversion History**: Maintains a history of all type conversion attempts for debugging
- **Interactive Mode**: Allows users to experiment with data processing in real-time
- **Property Decorators**: Demonstrates use of @property for computed attributes
- **Type Hints**: Uses comprehensive type hints for better code documentation

</details>

[🔝 Back to Top](#-python-documentation)

---

## ⚡ Chapter 7: Operators & Expressions
📊 **Progress:** Chapter 7 of 30  
🎯 **Learning Objectives:** Master Python operators and expression evaluation  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of variables and data types

### Arithmetic Operators

Python provides a comprehensive set of arithmetic operators for mathematical operations:

```python
# Basic arithmetic operations
a, b = 15, 4

print(f"Addition: {a} + {b} = {a + b}")           # 19
print(f"Subtraction: {a} - {b} = {a - b}")        # 11  
print(f"Multiplication: {a} * {b} = {a * b}")     # 60
print(f"Division: {a} / {b} = {a / b}")           # 3.75
print(f"Floor Division: {a} // {b} = {a // b}")   # 3
print(f"Modulus: {a} % {b} = {a % b}")            # 3
print(f"Exponentiation: {a} ** {b} = {a ** b}")   # 50625

# Unary operators
positive = +a    # Unary plus (usually unnecessary)
negative = -a    # Unary minus (negation)
print(f"Unary plus: +{a} = {positive}")
print(f"Unary minus: -{a} = {negative}")
```

#### Special Cases and Edge Conditions

```python
# Division by zero
try:
    result = 10 / 0
except ZeroDivisionError as e:
    print(f"Division by zero error: {e}")

try:
    result = 10 // 0
except ZeroDivisionError as e:
    print(f"Floor division by zero error: {e}")

# Modulus with negative numbers
print(f"7 % 3 = {7 % 3}")        # 1
print(f"-7 % 3 = {-7 % 3}")      # 2 (sign follows divisor)
print(f"7 % -3 = {7 % -3}")      # -2
print(f"-7 % -3 = {-7 % -3}")    # -1

# Large number operations
big1 = 10**100
big2 = 3
print(f"Large number division: {big1} / {big2} = {big1 / big2}")
```

### Comparison Operators

```python
# Basic comparisons
x, y = 10, 20
print(f"Equal: {x} == {y} → {x == y}")                    # False
print(f"Not equal: {x} != {y} → {x != y}")                # True
print(f"Less than: {x} < {y} → {x < y}")                  # True
print(f"Less than or equal: {x} <= {y} → {x <= y}")       # True
print(f"Greater than: {x} > {y} → {x > y}")               # False
print(f"Greater than or equal: {x} >= {y} → {x >= y}")    # False

# Chained comparisons (unique to Python)
age = 25
adult = 18 <= age <= 65
print(f"Is adult (18 <= {age} <= 65): {adult}")           # True

# Multiple chaining
score = 85
grade_a = 90 <= score <= 100
grade_b = 80 <= score < 90
print(f"Grade A: {grade_a}, Grade B: {grade_b}")          # False, True

# String comparisons (lexicographic)
str1, str2 = "apple", "banana"
print(f"'{str1}' < '{str2}': {'apple' < 'banana'}")       # True
print(f"'Apple' < 'apple': {'Apple' < 'apple'}")          # True (uppercase comes first)
```

### Logical Operators

```python
# Boolean logic
p, q = True, False

print(f"AND: {p} and {q} = {p and q}")                    # False
print(f"OR: {p} or {q} = {p or q}")                       # True
print(f"NOT: not {p} = {not p}")                          # False

# Short-circuit evaluation
def expensive_function():
    print("Expensive function called!")
    return True

print("\nTesting short-circuit evaluation:")
result1 = False and expensive_function()  # expensive_function NOT called
result2 = True or expensive_function()    # expensive_function NOT called
print(f"Results: {result1}, {result2}")

# Truthiness testing
values = [0, 1, "", "text", [], [1], {}, {"key": "value"}, None, False, True]
print("\nTruthiness testing:")
for value in values:
    print(f"{repr(value):>15}: {'truthy' if value else 'falsy'}")
```

### Bitwise Operators

```python
# Bitwise operations on integers
a, b = 12, 10  # Binary: 1100, 1010

print(f"Binary representation:")
print(f"a = {a} = {bin(a)}")
print(f"b = {b} = {bin(b)}")

print(f"\nBitwise operations:")
print(f"AND: {a} & {b} = {a & b} = {bin(a & b)}")         # 8 = 1000
print(f"OR: {a} | {b} = {a | b} = {bin(a | b)}")          # 14 = 1110
print(f"XOR: {a} ^ {b} = {a ^ b} = {bin(a ^ b)}")         # 6 = 0110
print(f"NOT: ~{a} = {~a} = {bin(~a & 0xFF)}")             # Two's complement
print(f"Left shift: {a} << 2 = {a << 2} = {bin(a << 2)}")  # 48 = 110000
print(f"Right shift: {a} >> 2 = {a >> 2} = {bin(a >> 2)}") # 3 = 11

# Practical bitwise applications
def check_bit(number, position):
    """Check if bit at position is set."""
    return bool(number & (1 << position))

def set_bit(number, position):
    """Set bit at position."""
    return number | (1 << position)

def clear_bit(number, position):
    """Clear bit at position."""
    return number & ~(1 << position)

number = 42  # Binary: 101010
print(f"\nBit manipulation on {number} ({bin(number)}):")
print(f"Bit 1 is set: {check_bit(number, 1)}")
print(f"Set bit 0: {set_bit(number, 0)} = {bin(set_bit(number, 0))}")
print(f"Clear bit 3: {clear_bit(number, 3)} = {bin(clear_bit(number, 3))}")
```

### Assignment Operators

```python
# Basic assignment
x = 10
print(f"Initial value: {x}")

# Augmented assignment operators
x += 5    # x = x + 5
print(f"After += 5: {x}")

x -= 3    # x = x - 3
print(f"After -= 3: {x}")

x *= 2    # x = x * 2
print(f"After *= 2: {x}")

x //= 4   # x = x // 4
print(f"After //= 4: {x}")

x **= 2   # x = x ** 2
print(f"After **= 2: {x}")

# Augmented assignment with other types
text = "Hello"
text += " World"    # String concatenation
print(f"String concatenation: {text}")

numbers = [1, 2, 3]
numbers += [4, 5]   # List concatenation
print(f"List concatenation: {numbers}")

count = 0
count += 1          # Increment counter
print(f"Counter: {count}")
```

### Identity and Membership Operators

```python
# Identity operators (is, is not)
a = [1, 2, 3]
b = a           # b references same object as a
c = [1, 2, 3]   # c is a new object with same content

print(f"Identity testing:")
print(f"a is b: {a is b}")         # True (same object)
print(f"a is c: {a is c}")         # False (different objects)
print(f"a == c: {a == c}")         # True (same content)
print(f"a is not c: {a is not c}") # True

# Special case with small integers (cached)
x = 100
y = 100
print(f"x is y (100): {x is y}")   # True (cached)

x = 1000
y = 1000
print(f"x is y (1000): {x is y}")  # False (not cached)

# None testing
value = None
print(f"value is None: {value is None}")       # Correct way
print(f"value == None: {value == None}")       # Works but not recommended

# Membership operators (in, not in)
fruits = ["apple", "banana", "cherry"]
print(f"\nMembership testing:")
print(f"'apple' in fruits: {'apple' in fruits}")           # True
print(f"'grape' in fruits: {'grape' in fruits}")           # False
print(f"'grape' not in fruits: {'grape' not in fruits}")   # True

# String membership
text = "Hello, Python!"
print(f"'Python' in text: {'Python' in text}")             # True
print(f"'Java' not in text: {'Java' not in text}")         # True

# Dictionary membership (checks keys)
person = {"name": "Alice", "age": 30}
print(f"'name' in person: {'name' in person}")             # True
print(f"'Alice' in person: {'Alice' in person}")           # False (not a key)
print(f"'Alice' in person.values(): {'Alice' in person.values()}")  # True
```

### Operator Precedence and Associativity

```python
# Operator precedence demonstration
result1 = 2 + 3 * 4        # Multiplication first: 2 + 12 = 14
result2 = (2 + 3) * 4      # Parentheses change order: 5 * 4 = 20
print(f"2 + 3 * 4 = {result1}")
print(f"(2 + 3) * 4 = {result2}")

# Complex expression
result = 2 ** 3 ** 2       # Right associative: 2 ** (3 ** 2) = 2 ** 9 = 512
print(f"2 ** 3 ** 2 = {result}")

result = (2 ** 3) ** 2     # Left to right with parentheses: 8 ** 2 = 64
print(f"(2 ** 3) ** 2 = {result}")

# Boolean operator precedence
result = True or False and False   # 'and' has higher precedence
print(f"True or False and False = {result}")  # True

result = (True or False) and False # Explicit parentheses
print(f"(True or False) and False = {result}")  # False

# Comparison and logical combination
age = 25
is_adult = age >= 18 and age <= 65  # Comparison operators first
print(f"Is adult: {is_adult}")

# More complex example
x, y, z = 10, 20, 30
complex_result = x < y and y < z or x > z
print(f"Complex condition result: {complex_result}")  # True
```

### 💡 Code Example: Expression Evaluator

```python
#!/usr/bin/env python3
"""
Python Expression Evaluator
Demonstrates operator usage and expression evaluation.
"""

import operator
import math
from typing import Any, Dict, Callable


class ExpressionEvaluator:
    """
    A comprehensive expression evaluator that demonstrates 
    Python operators and expression evaluation.
    """
    
    def __init__(self):
        """Initialize the evaluator with operator mappings."""
        self.binary_operators: Dict[str, Callable] = {
            '+': operator.add,
            '-': operator.sub,
            '*': operator.mul,
            '/': operator.truediv,
            '//': operator.floordiv,
            '%': operator.mod,
            '**': operator.pow,
            '&': operator.and_,
            '|': operator.or_,
            '^': operator.xor,
            '<<': operator.lshift,
            '>>': operator.rshift,
            '==': operator.eq,
            '!=': operator.ne,
            '<': operator.lt,
            '<=': operator.le,
            '>': operator.gt,
            '>=': operator.ge,
        }
        
        self.unary_operators: Dict[str, Callable] = {
            '+': operator.pos,
            '-': operator.neg,
            '~': operator.invert,
            'not': operator.not_,
        }
    
    def evaluate_arithmetic(self, a: float, op: str, b: float) -> tuple[bool, Any, str]:
        """
        Evaluate arithmetic expression safely.
        
        Args:
            a: First operand
            op: Operator string  
            b: Second operand
            
        Returns:
            Tuple of (success, result, message)
        """
        try:
            if op not in self.binary_operators:
                return False, None, f"Unknown operator: {op}"
            
            result = self.binary_operators[op](a, b)
            return True, result, f"{a} {op} {b} = {result}"
            
        except ZeroDivisionError:
            return False, None, f"Division by zero: {a} {op} {b}"
        except Exception as e:
            return False, None, f"Error: {str(e)}"
    
    def demonstrate_precedence(self):
        """Demonstrate operator precedence rules."""
        print("🔢 Operator Precedence Demonstration")
        print("=" * 40)
        
        expressions = [
            "2 + 3 * 4",
            "(2 + 3) * 4", 
            "2 ** 3 ** 2",
            "(2 ** 3) ** 2",
            "True or False and False",
            "(True or False) and False",
            "10 - 4 - 2",
            "10 - (4 - 2)",
            "16 / 4 / 2",
            "16 / (4 / 2)",
            "not True or False",
            "not (True or False)"
        ]
        
        for expr in expressions:
            try:
                result = eval(expr)
                print(f"{expr:25} = {result}")
            except Exception as e:
                print(f"{expr:25} = ERROR: {e}")
    
    def demonstrate_short_circuit(self):
        """Demonstrate short-circuit evaluation."""
        print("\n⚡ Short-Circuit Evaluation")
        print("=" * 40)
        
        def side_effect(name: str, return_value: bool = True) -> bool:
            print(f"    Function {name} called!")
            return return_value
        
        print("Testing 'and' operator:")
        print("False and side_effect('A'):")
        result1 = False and side_effect('A')
        print(f"    Result: {result1}")
        
        print("\nTrue and side_effect('B'):")
        result2 = True and side_effect('B')
        print(f"    Result: {result2}")
        
        print("\nTesting 'or' operator:")
        print("True or side_effect('C'):")
        result3 = True or side_effect('C')
        print(f"    Result: {result3}")
        
        print("\nFalse or side_effect('D'):")
        result4 = False or side_effect('D')
        print(f"    Result: {result4}")
    
    def demonstrate_chained_comparisons(self):
        """Demonstrate Python's chained comparison operators."""
        print("\n🔗 Chained Comparison Operators")
        print("=" * 40)
        
        test_values = [5, 15, 25, 35]
        
        comparisons = [
            "0 <= x <= 10",
            "10 < x < 30", 
            "20 <= x <= 40",
            "x < 0 or x > 50"
        ]
        
        print("Value  | " + " | ".join(f"{comp:15}" for comp in comparisons))
        print("-" * 80)
        
        for value in test_values:
            results = []
            for comp in comparisons:
                try:
                    # Replace x with actual value
                    expr = comp.replace('x', str(value))
                    result = eval(expr)
                    results.append(f"{result:^15}")
                except:
                    results.append(f"{'ERROR':^15}")
            
            print(f"{value:5}  | " + " | ".join(results))
    
    def run_demonstration(self):
        """Run complete operator demonstration."""
        print("🐍 Python Operators & Expressions")
        print("=" * 50)
        
        self.demonstrate_precedence()
        self.demonstrate_short_circuit() 
        self.demonstrate_chained_comparisons()
        
        print("\n💡 Key Takeaways:")
        print("   - Parentheses override operator precedence")
        print("   - 'and' and 'or' use short-circuit evaluation")
        print("   - Python supports chained comparisons")
        print("   - Be careful with operator precedence in complex expressions")


def main():
    """Main function for operators demonstration."""
    evaluator = ExpressionEvaluator()
    evaluator.run_demonstration()


if __name__ == "__main__":
    main()
```

### ⚠️ Common Pitfalls with Operators

1. **Operator Precedence Confusion**
   ```python
   # Wrong assumption about precedence
   result = 5 + 3 * 2    # 11, not 16
   
   # Be explicit with parentheses
   result = (5 + 3) * 2  # 16
   ```

2. **Identity vs Equality**
   ```python
   # Wrong - using 'is' for value comparison
   if score is 100:      # Don't do this
       print("Perfect!")
   
   # Correct - using '==' for value comparison
   if score == 100:
       print("Perfect!")
   ```

3. **Division Operator Changes (Python 2 vs 3)**
   ```python
   # Python 3 behavior
   result = 5 / 2        # 2.5 (float division)
   result = 5 // 2       # 2 (floor division)
   ```

### ✅ Best Practices for Operators

1. **Use Parentheses for Clarity**
2. **Prefer 'is' for None Comparisons**
3. **Use Chained Comparisons When Appropriate**
4. **Be Aware of Short-Circuit Evaluation**
5. **Choose the Right Division Operator**

### 🏋️ Exercise 7: Advanced Calculator with Operators
**Difficulty:** 🟡 Intermediate  
**Estimated Time:** 25 minutes

Create an advanced calculator that demonstrates all Python operators:
1. Support arithmetic, bitwise, and logical operations
2. Handle operator precedence correctly
3. Provide detailed step-by-step evaluation
4. Include input validation and error handling
5. Support both binary and unary operations

<details>
<summary>💡 Click to see hints</summary>

- Use the `operator` module for function-based operations
- Implement operator precedence with proper parsing
- Handle edge cases like division by zero
- Use try-except blocks for error handling
- Consider using `eval()` carefully with input validation

</details>

<details>
<summary>✅ Click to see solution</summary>

```python
#!/usr/bin/env python3
"""
Advanced Calculator with Full Operator Support
Demonstrates Python operators with comprehensive functionality.
"""

import operator
import re
from typing import Any, Dict, List, Tuple, Union


class AdvancedCalculator:
    """
    Advanced calculator supporting all Python operators with 
    proper precedence and error handling.
    """
    
    def __init__(self):
        """Initialize calculator with operator definitions."""
        self.binary_ops = {
            '**': (operator.pow, 4, 'right'),
            '*': (operator.mul, 3, 'left'),
            '/': (operator.truediv, 3, 'left'),
            '//': (operator.floordiv, 3, 'left'),
            '%': (operator.mod, 3, 'left'),
            '+': (operator.add, 2, 'left'),
            '-': (operator.sub, 2, 'left'),
            '<<': (operator.lshift, 1, 'left'),
            '>>': (operator.rshift, 1, 'left'),
            '&': (operator.and_, 0, 'left'),
            '^': (operator.xor, 0, 'left'),
            '|': (operator.or_, 0, 'left'),
        }
        
        self.comparison_ops = {
            '==': operator.eq,
            '!=': operator.ne,
            '<': operator.lt,
            '<=': operator.le,
            '>': operator.gt,
            '>=': operator.ge,
        }
        
        self.unary_ops = {
            '+': operator.pos,
            '-': operator.neg,
            '~': operator.invert,
        }
    
    def evaluate_expression(self, expression: str) -> Tuple[bool, Any, str]:
        """
        Evaluate mathematical expression with full operator support.
        
        Args:
            expression: Mathematical expression string
            
        Returns:
            Tuple of (success, result, message)
        """
        try:
            # Clean and validate expression
            cleaned = self._clean_expression(expression)
            if not self._validate_expression(cleaned):
                return False, None, "Invalid expression format"
            
            # Use eval with restricted namespace for safety
            safe_dict = {
                '__builtins__': {},
                'abs': abs, 'round': round, 'min': min, 'max': max,
                'pow': pow, 'divmod': divmod
            }
            
            result = eval(cleaned, safe_dict)
            return True, result, f"Result: {result}"
            
        except ZeroDivisionError:
            return False, None, "Error: Division by zero"
        except SyntaxError:
            return False, None, "Error: Invalid syntax"
        except NameError as e:
            return False, None, f"Error: {str(e)}"
        except Exception as e:
            return False, None, f"Error: {str(e)}"
    
    def _clean_expression(self, expr: str) -> str:
        """Clean and standardize expression format."""
        # Remove spaces and convert to lowercase
        cleaned = re.sub(r'\s+', '', expr.strip())
        
        # Replace some common alternative formats
        replacements = {
            'x': '*',  # Allow 'x' as multiplication
            'mod': '%',  # Allow 'mod' as modulus
            'div': '//',  # Allow 'div' as floor division
        }
        
        for old, new in replacements.items():
            cleaned = cleaned.replace(old, new)
        
        return cleaned
    
    def _validate_expression(self, expr: str) -> bool:
        """Validate expression contains only allowed characters."""
        allowed = set('0123456789+-*/()%**//<<>>&|^~.= <>')
        return all(c in allowed for c in expr)
    
    def demonstrate_operators(self):
        """Demonstrate different operator categories."""
        print("🧮 Advanced Calculator - Operator Demonstration")
        print("=" * 55)
        
        # Arithmetic operators
        print("\n📊 Arithmetic Operators:")
        arithmetic_tests = [
            "15 + 4 * 3",
            "(15 + 4) * 3", 
            "17 / 4",
            "17 // 4",
            "17 % 4",
            "2 ** 3 ** 2",
            "abs(-42)",
            "divmod(17, 4)"
        ]
        
        for test in arithmetic_tests:
            success, result, message = self.evaluate_expression(test)
            status = "✅" if success else "❌"
            print(f"  {status} {test:<15} = {result if success else 'ERROR'}")
        
        # Bitwise operators
        print("\n🔢 Bitwise Operators:")
        bitwise_tests = [
            "12 & 10",   # AND
            "12 | 10",   # OR  
            "12 ^ 10",   # XOR
            "~12",       # NOT
            "12 << 2",   # Left shift
            "12 >> 1"    # Right shift
        ]
        
        for test in bitwise_tests:
            success, result, message = self.evaluate_expression(test)
            status = "✅" if success else "❌"
            if success and test != "~12":
                # Show binary representation
                print(f"  {status} {test:<10} = {result:2d} (binary: {bin(result)})")
            else:
                print(f"  {status} {test:<10} = {result if success else 'ERROR'}")
        
        # Comparison operators
        print("\n⚖️  Comparison Operators:")
        comparison_tests = [
            "10 == 10",
            "10 != 5",
            "10 < 20",
            "10 <= 10",
            "15 > 10",
            "15 >= 15"
        ]
        
        for test in comparison_tests:
            success, result, message = self.evaluate_expression(test)
            status = "✅" if success else "❌"
            print(f"  {status} {test:<10} = {result}")
    
    def interactive_mode(self):
        """Interactive calculator mode."""
        print("\n🎮 Interactive Calculator Mode")
        print("=" * 35)
        print("Enter mathematical expressions (type 'quit' to exit)")
        print("Supported: +, -, *, /, //, %, **, &, |, ^, <<, >>, ~")
        print("Functions: abs(), round(), min(), max(), pow(), divmod()")
        
        while True:
            try:
                user_input = input("\n>>> ").strip()
                
                if user_input.lower() in ['quit', 'exit', 'q']:
                    break
                
                if not user_input:
                    continue
                
                success, result, message = self.evaluate_expression(user_input)
                
                if success:
                    print(f"Result: {result}")
                    
                    # Show additional information for numbers
                    if isinstance(result, (int, float)):
                        print(f"Type: {type(result).__name__}")
                        if isinstance(result, int) and result >= 0:
                            print(f"Binary: {bin(result)}")
                            print(f"Hex: {hex(result)}")
                            print(f"Octal: {oct(result)}")
                else:
                    print(message)
                    
            except KeyboardInterrupt:
                break
            except EOFError:
                break
        
        print("\n👋 Calculator session ended")


def main():
    """Main function for advanced calculator."""
    try:
        calculator = AdvancedCalculator()
        calculator.demonstrate_operators()
        
        choice = input("\nWould you like to try interactive mode? (y/n): ").lower().strip()
        if choice == 'y':
            calculator.interactive_mode()
        
        print("\n🎉 Thank you for using the Advanced Calculator!")
        
    except KeyboardInterrupt:
        print("\n👋 Program interrupted. Goodbye!")
    except Exception as e:
        print(f"❌ Unexpected error: {e}")


if __name__ == "__main__":
    main()
```

**Explanation:**
- **Comprehensive Operator Support**: Handles arithmetic, bitwise, and comparison operators
- **Safe Expression Evaluation**: Uses restricted eval() with controlled namespace
- **Operator Precedence**: Properly handles complex expressions with correct precedence
- **Input Validation**: Cleans and validates user input before evaluation
- **Error Handling**: Provides detailed error messages for various failure cases
- **Interactive Mode**: Allows users to experiment with different expressions
- **Educational Output**: Shows binary, hex, and octal representations for integer results

</details>

[🔝 Back to Top](#-python-documentation)

---

## 📥 Chapter 8: Input & Output Operations
📊 **Progress:** Chapter 8 of 30  
🎯 **Learning Objectives:** Master Python's input/output capabilities  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Understanding of variables and data types

### Basic Input/Output

#### Getting User Input

```python
# Basic input
name = input("What's your name? ")
print(f"Hello, {name}!")

# Input always returns a string
age_str = input("How old are you? ")
age = int(age_str)  # Convert to integer
print(f"You are {age} years old")

# Input with type conversion and validation
def get_number(prompt):
    """Get a valid number from user."""
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Please enter a valid number!")

number = get_number("Enter a number: ")
print(f"You entered: {number}")
```

#### Formatted Output

```python
# Print function basics
print("Hello, World!")
print("Multiple", "arguments", "separated", "by", "spaces")
print("Custom", "separator", sep="-")
print("No newline", end="")
print(" continues on same line")

# Print to different destinations
import sys
print("Error message", file=sys.stderr)
print("Regular output", file=sys.stdout)

# String formatting methods
name, age, score = "Alice", 25, 95.5

# f-strings (Python 3.6+)
print(f"Name: {name}, Age: {age}, Score: {score:.1f}")

# str.format() method
print("Name: {}, Age: {}, Score: {:.1f}".format(name, age, score))
print("Name: {n}, Age: {a}, Score: {s:.1f}".format(n=name, a=age, s=score))

# % formatting (legacy)
print("Name: %s, Age: %d, Score: %.1f" % (name, age, score))
```

### Advanced Input/Output Techniques

#### Password Input
```python
import getpass

# Hide password input
password = getpass.getpass("Enter password: ")
print(f"Password length: {len(password)}")
```

#### Command Line Arguments
```python
import sys

# Access command line arguments
print(f"Script name: {sys.argv[0]}")
print(f"Arguments: {sys.argv[1:]}")

# Using argparse for better argument handling
import argparse

parser = argparse.ArgumentParser(description='Process some integers.')
parser.add_argument('integers', metavar='N', type=int, nargs='+',
                   help='an integer for the accumulator')
parser.add_argument('--sum', dest='accumulate', action='store_const',
                   const=sum, default=max,
                   help='sum the integers (default: find the max)')

args = parser.parse_args()
print(args.accumulate(args.integers))
```

[🔝 Back to Top](#-python-documentation)

---

## 🔀 Chapter 9: Conditional Statements
📊 **Progress:** Chapter 9 of 30  
🎯 **Learning Objectives:** Master Python's conditional logic and decision making  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Understanding of operators and expressions

### if, elif, and else Statements

```python
# Basic if statement
age = 18
if age >= 18:
    print("You are an adult")

# if-else statement
temperature = 75
if temperature > 80:
    print("It's hot outside")
else:
    print("It's not too hot")

# if-elif-else chain
score = 85
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"

print(f"Your grade is: {grade}")
```

### Conditional Expressions (Ternary Operator)

```python
# Ternary operator syntax: value_if_true if condition else value_if_false
age = 20
status = "adult" if age >= 18 else "minor"
print(f"Status: {status}")

# Nested ternary operators (use sparingly)
score = 85
grade = "A" if score >= 90 else "B" if score >= 80 else "C"
print(f"Grade: {grade}")
```

### Complex Conditions

```python
# Multiple conditions with logical operators
username = "admin"
password = "secret123"
is_active = True

if username == "admin" and password == "secret123" and is_active:
    print("Access granted")
else:
    print("Access denied")

# Using parentheses for clarity
age = 25
income = 50000
credit_score = 750

eligible = (age >= 21 and income >= 30000) or credit_score >= 700
if eligible:
    print("Loan approved")
else:
    print("Loan denied")
```

[🔝 Back to Top](#-python-documentation)

---

## 🔄 Chapter 10: Loops & Iteration
📊 **Progress:** Chapter 10 of 30  
🎯 **Learning Objectives:** Master Python's looping constructs and iteration patterns  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of conditional statements

### for Loops

```python
# Basic for loop with range
for i in range(5):
    print(f"Count: {i}")

# for loop with start, stop, step
for i in range(1, 11, 2):  # 1, 3, 5, 7, 9
    print(f"Odd number: {i}")

# Iterating over sequences
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(f"I like {fruit}")

# Iterating with index using enumerate
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")

# Iterating over dictionaries
person = {"name": "Alice", "age": 30, "city": "New York"}
for key, value in person.items():
    print(f"{key}: {value}")
```

### while Loops

```python
# Basic while loop
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1

# while loop with user input
while True:
    user_input = input("Enter 'quit' to exit: ")
    if user_input.lower() == 'quit':
        break
    print(f"You entered: {user_input}")
```

### Loop Control Statements

```python
# break statement
for i in range(10):
    if i == 5:
        break
    print(i)  # Prints 0, 1, 2, 3, 4

# continue statement
for i in range(10):
    if i % 2 == 0:
        continue  # Skip even numbers
    print(i)  # Prints 1, 3, 5, 7, 9

# else clause with loops
for i in range(5):
    if i == 10:  # This never happens
        break
else:
    print("Loop completed normally")  # This executes
```

### Nested Loops

```python
# Multiplication table
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} x {j} = {i * j}")
    print()  # Empty line after each row
```

[🔝 Back to Top](#-python-documentation)

---

## ⚠️ Chapter 11: Exception Handling
📊 **Progress:** Chapter 11 of 30  
🎯 **Learning Objectives:** Master Python's exception handling mechanisms  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Understanding of basic Python syntax

### Basic Exception Handling

```python
# Basic try-except
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print(f"Result: {result}")
except ValueError:
    print("Invalid input! Please enter a number.")
except ZeroDivisionError:
    print("Cannot divide by zero!")
```

### Multiple Exception Types

```python
# Handling multiple exceptions
def safe_divide(a, b):
    try:
        result = a / b
        return result
    except (TypeError, ValueError) as e:
        print(f"Input error: {e}")
        return None
    except ZeroDivisionError:
        print("Cannot divide by zero!")
        return None
    except Exception as e:
        print(f"Unexpected error: {e}")
        return None

# Usage
print(safe_divide(10, 2))    # 5.0
print(safe_divide(10, 0))    # Cannot divide by zero! None
print(safe_divide(10, "a"))  # Input error: ... None
```

### finally and else Clauses

```python
# Complete exception handling structure
def read_file(filename):
    try:
        file = open(filename, 'r')
        content = file.read()
        return content
    except FileNotFoundError:
        print(f"File {filename} not found")
        return None
    except PermissionError:
        print(f"Permission denied for {filename}")
        return None
    else:
        print("File read successfully")  # Executes if no exception
    finally:
        try:
            file.close()  # Always executes
            print("File closed")
        except:
            pass
```

### Custom Exceptions

```python
# Define custom exception
class CustomError(Exception):
    """Custom exception for specific error conditions."""
    def __init__(self, message, error_code=None):
        super().__init__(message)
        self.error_code = error_code

# Using custom exception
def validate_age(age):
    if not isinstance(age, int):
        raise CustomError("Age must be an integer", "TYPE_ERROR")
    if age < 0:
        raise CustomError("Age cannot be negative", "VALUE_ERROR")
    if age > 150:
        raise CustomError("Age seems unrealistic", "RANGE_ERROR")
    return True

# Usage
try:
    validate_age(-5)
except CustomError as e:
    print(f"Validation error: {e}")
    print(f"Error code: {e.error_code}")
```

[🔝 Back to Top](#-python-documentation)

---

## 📋 Chapter 12: Lists & Tuples
📊 **Progress:** Chapter 12 of 30  
🎯 **Learning Objectives:** Master Python's sequence data structures  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of basic data types

### Lists

```python
# Creating lists
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]
empty_list = []
list_from_range = list(range(5))  # [0, 1, 2, 3, 4]

# List methods
fruits = ["apple", "banana"]
fruits.append("cherry")           # Add to end
fruits.insert(1, "orange")       # Insert at index
fruits.extend(["grape", "kiwi"])  # Add multiple items
fruits.remove("banana")           # Remove first occurrence
popped = fruits.pop()             # Remove and return last item
index = fruits.index("apple")     # Find index of item
count = fruits.count("apple")     # Count occurrences

print(f"Fruits: {fruits}")
print(f"Popped: {popped}")
print(f"Apple index: {index}")
```

### List Slicing

```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# Basic slicing
print(numbers[2:5])      # [2, 3, 4]
print(numbers[:5])       # [0, 1, 2, 3, 4]
print(numbers[5:])       # [5, 6, 7, 8, 9]
print(numbers[:])        # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9] (copy)

# Step slicing
print(numbers[::2])      # [0, 2, 4, 6, 8] (every 2nd)
print(numbers[1::2])     # [1, 3, 5, 7, 9] (every 2nd starting at 1)
print(numbers[::-1])     # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0] (reverse)

# Negative indices
print(numbers[-1])       # 9 (last element)
print(numbers[-3:])      # [7, 8, 9] (last 3 elements)
```

### List Comprehensions

```python
# Basic list comprehension
squares = [x**2 for x in range(10)]
print(f"Squares: {squares}")

# List comprehension with condition
even_squares = [x**2 for x in range(10) if x % 2 == 0]
print(f"Even squares: {even_squares}")

# Complex list comprehension
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flattened = [item for row in matrix for item in row]
print(f"Flattened: {flattened}")
```

### Tuples

```python
# Creating tuples
coordinates = (10, 20)
colors = ("red", "green", "blue")
single_item = (42,)  # Note the comma for single-item tuple
empty_tuple = ()

# Tuple unpacking
x, y = coordinates
print(f"X: {x}, Y: {y}")

# Multiple assignment using tuples
a, b, c = 1, 2, 3  # Same as (1, 2, 3)

# Swapping variables using tuples
a, b = b, a

# Named tuples
from collections import namedtuple
Point = namedtuple('Point', ['x', 'y'])
p = Point(10, 20)
print(f"Point: {p.x}, {p.y}")
```

### Common Operations

```python
# Operations that work on both lists and tuples
sequence1 = [1, 2, 3]
sequence2 = (4, 5, 6)

# Length
print(f"List length: {len(sequence1)}")
print(f"Tuple length: {len(sequence2)}")

# Membership testing
print(f"2 in list: {2 in sequence1}")
print(f"7 not in tuple: {7 not in sequence2}")

# Concatenation
combined_list = sequence1 + [7, 8, 9]
combined_tuple = sequence2 + (7, 8, 9)

# Repetition
repeated_list = [0] * 5         # [0, 0, 0, 0, 0]
repeated_tuple = ("hi",) * 3    # ("hi", "hi", "hi")
```

[🔝 Back to Top](#-python-documentation)

---

## 📚 Chapter 13: Dictionaries & Sets
📊 **Progress:** Chapter 13 of 30  
🎯 **Learning Objectives:** Master Python's mapping and set data structures  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of lists and basic data types

### Dictionaries

Dictionaries are Python's implementation of associative arrays or hash maps.

```python
# Creating dictionaries
person = {
    "name": "Alice",
    "age": 30,
    "city": "New York"
}

# Alternative creation methods
person2 = dict(name="Bob", age=25, city="Boston")
person3 = dict([("name", "Charlie"), ("age", 35)])

# Dictionary methods
person["email"] = "alice@example.com"  # Add new key
age = person.get("age", 0)  # Get with default
removed_city = person.pop("city", "Unknown")  # Remove and return
last_item = person.popitem()  # Remove and return last item

# Dictionary comprehensions
squares = {x: x**2 for x in range(5)}
print(f"Squares: {squares}")

# Nested dictionaries
company = {
    "name": "TechCorp",
    "employees": {
        "alice": {"role": "developer", "salary": 80000},
        "bob": {"role": "manager", "salary": 90000}
    }
}

# Accessing nested values
alice_salary = company["employees"]["alice"]["salary"]
```

### Sets

Sets are unordered collections of unique elements.

```python
# Creating sets
fruits = {"apple", "banana", "cherry"}
numbers = set([1, 2, 3, 3, 4, 4, 5])  # Duplicates removed
empty_set = set()  # Note: {} creates empty dict, not set

# Set operations
fruits.add("orange")
fruits.discard("banana")  # Doesn't raise error if not found
fruits.remove("apple")    # Raises error if not found

# Set mathematics
set1 = {1, 2, 3, 4}
set2 = {3, 4, 5, 6}

union = set1 | set2           # {1, 2, 3, 4, 5, 6}
intersection = set1 & set2    # {3, 4}
difference = set1 - set2      # {1, 2}
symmetric_diff = set1 ^ set2  # {1, 2, 5, 6}

# Set comprehensions
even_squares = {x**2 for x in range(10) if x % 2 == 0}
```

---

## 🔤 Chapter 14: Strings & Text Processing
📊 **Progress:** Chapter 14 of 30  
🎯 **Learning Objectives:** Master Python's string manipulation capabilities  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Understanding of basic data types

### String Basics

```python
# String creation and basic operations
text = "Hello, Python!"
multiline = """This is a
multi-line
string"""

# String indexing and slicing
first_char = text[0]        # 'H'
last_char = text[-1]        # '!'
substring = text[7:13]      # 'Python'
reversed_text = text[::-1]  # '!nohtyP ,olleH'

# String methods
print(text.upper())         # HELLO, PYTHON!
print(text.lower())         # hello, python!
print(text.title())         # Hello, Python!
print(text.replace("Python", "World"))  # Hello, World!
print(text.split(","))      # ['Hello', ' Python!']
```

### Advanced String Operations

```python
# String formatting
name = "Alice"
age = 30
score = 95.67

# F-strings (Python 3.6+)
message = f"Name: {name}, Age: {age}, Score: {score:.2f}"

# Format specifications
number = 1234567.89
print(f"Comma separator: {number:,}")
print(f"Scientific: {number:.2e}")
print(f"Percentage: {0.85:.1%}")

# String validation methods
text = "Python123"
print(f"Is alphanumeric: {text.isalnum()}")
print(f"Is alpha: {text.isalpha()}")
print(f"Is digit: {text.isdigit()}")
print(f"Is title case: {'Python Programming'.istitle()}")
```

---

## ⚡ Chapter 15: Functions
📊 **Progress:** Chapter 15 of 30  
🎯 **Learning Objectives:** Master function definition, parameters, and scope  
⏱️ **Estimated Reading Time:** 30 minutes  
📋 **Prerequisites:** Understanding of basic Python syntax

### Function Basics

```python
# Basic function definition
def greet(name):
    """Greet a person by name."""
    return f"Hello, {name}!"

# Function with multiple parameters
def calculate_area(length, width):
    """Calculate area of rectangle."""
    area = length * width
    return area

# Function with default parameters
def greet_with_title(name, title="Mr./Ms."):
    """Greet person with optional title."""
    return f"Hello, {title} {name}!"

# Usage
print(greet("Alice"))
print(calculate_area(10, 5))
print(greet_with_title("Smith"))
print(greet_with_title("Johnson", "Dr."))
```

### Advanced Function Features

```python
# Variable-length arguments
def sum_numbers(*args):
    """Sum any number of arguments."""
    return sum(args)

def print_info(**kwargs):
    """Print keyword arguments."""
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# Usage
print(sum_numbers(1, 2, 3, 4, 5))  # 15
print_info(name="Alice", age=30, city="NYC")

# Lambda functions
square = lambda x: x**2
numbers = [1, 2, 3, 4, 5]
squared = list(map(square, numbers))
print(f"Squared: {squared}")

# Higher-order functions
def apply_operation(numbers, operation):
    """Apply operation to all numbers."""
    return [operation(x) for x in numbers]

result = apply_operation([1, 2, 3, 4], lambda x: x**2)
print(f"Applied operation: {result}")
```

---

## 📦 Chapter 16: Lambda Functions & Functional Programming
📊 **Progress:** Chapter 16 of 30  
🎯 **Learning Objectives:** Understand functional programming concepts in Python  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Understanding of functions

### Lambda Functions

```python
# Lambda syntax: lambda arguments: expression
add = lambda x, y: x + y
print(add(5, 3))  # 8

# Lambda with map, filter, reduce
numbers = [1, 2, 3, 4, 5]

# Map - apply function to all items
squared = list(map(lambda x: x**2, numbers))
print(f"Squared: {squared}")

# Filter - filter items based on condition
even = list(filter(lambda x: x % 2 == 0, numbers))
print(f"Even numbers: {even}")

# Reduce - reduce sequence to single value
from functools import reduce
sum_all = reduce(lambda x, y: x + y, numbers)
print(f"Sum: {sum_all}")
```

### Functional Programming Patterns

```python
# List comprehensions as functional alternatives
numbers = range(10)

# Instead of map
squared = [x**2 for x in numbers]

# Instead of filter
even = [x for x in numbers if x % 2 == 0]

# Generator expressions for memory efficiency
squared_gen = (x**2 for x in numbers)
print(f"Generator: {squared_gen}")
print(f"First few squares: {list(squared_gen)[:5]}")
```

---

## 📁 Chapter 17: Modules & Packages
📊 **Progress:** Chapter 17 of 30  
🎯 **Learning Objectives:** Understand Python's module system and code organization  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of functions

### Importing Modules

```python
# Different import styles
import math
from math import sqrt, pi
from math import *  # Not recommended
import math as m

# Using imported functions
print(math.sqrt(16))    # 4.0
print(sqrt(25))         # 5.0
print(pi)              # 3.141592653589793
print(m.cos(0))        # 1.0
```

### Creating Your Own Modules

```python
# File: my_math_utils.py
def factorial(n):
    """Calculate factorial of n."""
    if n <= 1:
        return 1
    return n * factorial(n - 1)

def fibonacci(n):
    """Generate fibonacci sequence up to n terms."""
    sequence = []
    a, b = 0, 1
    for _ in range(n):
        sequence.append(a)
        a, b = b, a + b
    return sequence

# Constants
GOLDEN_RATIO = 1.618033988749

# File: main.py
import my_math_utils

print(my_math_utils.factorial(5))
print(my_math_utils.fibonacci(10))
print(f"Golden ratio: {my_math_utils.GOLDEN_RATIO}")
```

### Package Structure

```
my_package/
    __init__.py
    math_utils.py
    string_utils.py
    data/
        __init__.py
        processors.py
```

---

## 📚 Chapter 18: Standard Library
📊 **Progress:** Chapter 18 of 30  
🎯 **Learning Objectives:** Explore Python's extensive standard library  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of modules

### Essential Standard Library Modules

```python
# datetime - Date and time operations
import datetime

now = datetime.datetime.now()
today = datetime.date.today()
time_delta = datetime.timedelta(days=7)
next_week = today + time_delta

print(f"Current time: {now}")
print(f"Next week: {next_week}")

# os - Operating system interface
import os

current_dir = os.getcwd()
files = os.listdir('.')
home_dir = os.path.expanduser('~')

print(f"Current directory: {current_dir}")
print(f"Files: {files[:5]}")  # First 5 files

# pathlib - Object-oriented filesystem paths
from pathlib import Path

path = Path('my_file.txt')
parent_dir = path.parent
file_exists = path.exists()
absolute_path = path.absolute()

# json - JSON encoder/decoder
import json

data = {'name': 'Alice', 'age': 30, 'skills': ['Python', 'SQL']}
json_string = json.dumps(data, indent=2)
parsed_data = json.loads(json_string)

print(f"JSON: {json_string}")

# random - Generate random numbers
import random

random_int = random.randint(1, 100)
random_choice = random.choice(['red', 'blue', 'green'])
random_sample = random.sample(range(100), 5)

print(f"Random int: {random_int}")
print(f"Random choice: {random_choice}")
print(f"Random sample: {random_sample}")
```

---

## 🎯 Chapter 19: Classes & Objects
📊 **Progress:** Chapter 19 of 30  
🎯 **Learning Objectives:** Master object-oriented programming in Python  
⏱️ **Estimated Reading Time:** 30 minutes  
📋 **Prerequisites:** Understanding of functions and data structures

### Basic Class Definition

```python
class BankAccount:
    """A simple bank account class."""
    
    # Class variable (shared by all instances)
    bank_name = "Python Bank"
    
    def __init__(self, account_holder, initial_balance=0):
        """Initialize a new bank account."""
        self.account_holder = account_holder
        self.balance = initial_balance
        self.transaction_history = []
    
    def deposit(self, amount):
        """Deposit money into the account."""
        if amount > 0:
            self.balance += amount
            self.transaction_history.append(f"Deposited ${amount}")
            return True
        return False
    
    def withdraw(self, amount):
        """Withdraw money from the account."""
        if 0 < amount <= self.balance:
            self.balance -= amount
            self.transaction_history.append(f"Withdrew ${amount}")
            return True
        return False
    
    def get_balance(self):
        """Get current balance."""
        return self.balance
    
    def __str__(self):
        """String representation of the account."""
        return f"Account({self.account_holder}): ${self.balance}"

# Using the class
account = BankAccount("Alice", 1000)
account.deposit(500)
account.withdraw(200)
print(account)  # Account(Alice): $1300
print(f"Balance: ${account.get_balance()}")
```

### Instance and Class Methods

```python
class Circle:
    """A circle class demonstrating different method types."""
    
    pi = 3.14159  # Class variable
    
    def __init__(self, radius):
        self.radius = radius
    
    # Instance method
    def area(self):
        """Calculate area of the circle."""
        return self.pi * self.radius ** 2
    
    def circumference(self):
        """Calculate circumference of the circle."""
        return 2 * self.pi * self.radius
    
    # Class method
    @classmethod
    def from_diameter(cls, diameter):
        """Create circle from diameter."""
        return cls(diameter / 2)
    
    # Static method
    @staticmethod
    def pi_approximation(precision=2):
        """Return pi approximation."""
        return round(3.14159265359, precision)
    
    def __repr__(self):
        return f"Circle(radius={self.radius})"

# Usage
circle1 = Circle(5)
circle2 = Circle.from_diameter(10)  # Class method
pi_approx = Circle.pi_approximation(4)  # Static method

print(f"Circle 1 area: {circle1.area()}")
print(f"Circle 2: {circle2}")
print(f"Pi approximation: {pi_approx}")
```

---

## 🔗 Chapter 20: Inheritance & Polymorphism
📊 **Progress:** Chapter 20 of 30  
🎯 **Learning Objectives:** Understand inheritance and polymorphism in Python  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of classes and objects

### Basic Inheritance

```python
# Base class
class Animal:
    """Base class for all animals."""
    
    def __init__(self, name, species):
        self.name = name
        self.species = species
    
    def make_sound(self):
        """Make a generic animal sound."""
        return "Some generic animal sound"
    
    def info(self):
        """Return basic animal information."""
        return f"{self.name} is a {self.species}"

# Derived classes
class Dog(Animal):
    """Dog class inheriting from Animal."""
    
    def __init__(self, name, breed):
        super().__init__(name, "Dog")
        self.breed = breed
    
    def make_sound(self):
        """Override the make_sound method."""
        return "Woof! Woof!"
    
    def fetch(self):
        """Dog-specific method."""
        return f"{self.name} is fetching the ball!"

class Cat(Animal):
    """Cat class inheriting from Animal."""
    
    def __init__(self, name, breed):
        super().__init__(name, "Cat")
        self.breed = breed
    
    def make_sound(self):
        """Override the make_sound method."""
        return "Meow!"
    
    def climb(self):
        """Cat-specific method."""
        return f"{self.name} is climbing a tree!"

# Polymorphism in action
animals = [
    Dog("Buddy", "Golden Retriever"),
    Cat("Whiskers", "Siamese"),
    Dog("Rex", "German Shepherd")
]

for animal in animals:
    print(f"{animal.info()}")
    print(f"Sound: {animal.make_sound()}")
    print()
```

### Multiple Inheritance

```python
class Flyable:
    """Mixin class for flying capability."""
    
    def fly(self):
        return "Flying through the air!"

class Swimmable:
    """Mixin class for swimming capability."""
    
    def swim(self):
        return "Swimming in water!"

class Duck(Animal, Flyable, Swimmable):
    """Duck class with multiple inheritance."""
    
    def __init__(self, name):
        super().__init__(name, "Duck")
    
    def make_sound(self):
        return "Quack!"

# Usage
duck = Duck("Donald")
print(duck.info())
print(duck.make_sound())
print(duck.fly())
print(duck.swim())
```

[🔝 Back to Top](#-python-documentation)

---

## 🎨 Chapter 21: Special Methods & Magic Functions
📊 **Progress:** Chapter 21 of 30  
🎯 **Learning Objectives:** Master Python's special methods and operator overloading  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Understanding of classes and objects

### Common Magic Methods

```python
class Vector:
    """A 2D vector class demonstrating magic methods."""
    
    def __init__(self, x, y):
        self.x = x
        self.y = y
    
    def __str__(self):
        """Human-readable string representation."""
        return f"Vector({self.x}, {self.y})"
    
    def __repr__(self):
        """Developer-friendly representation."""
        return f"Vector({self.x!r}, {self.y!r})"
    
    def __add__(self, other):
        """Vector addition."""
        if isinstance(other, Vector):
            return Vector(self.x + other.x, self.y + other.y)
        return NotImplemented
    
    def __mul__(self, scalar):
        """Scalar multiplication."""
        if isinstance(scalar, (int, float)):
            return Vector(self.x * scalar, self.y * scalar)
        return NotImplemented
    
    def __eq__(self, other):
        """Equality comparison."""
        if isinstance(other, Vector):
            return self.x == other.x and self.y == other.y
        return False
    
    def __len__(self):
        """Vector magnitude."""
        return int((self.x**2 + self.y**2)**0.5)
    
    def __getitem__(self, index):
        """Index access."""
        if index == 0:
            return self.x
        elif index == 1:
            return self.y
        else:
            raise IndexError("Vector index out of range")

# Usage
v1 = Vector(3, 4)
v2 = Vector(1, 2)
print(f"v1: {v1}")
print(f"v1 + v2: {v1 + v2}")
print(f"v1 * 2: {v1 * 2}")
print(f"Length of v1: {len(v1)}")
print(f"v1[0]: {v1[0]}")
```

---

## 📁 Chapter 22: File I/O & Working with Files
📊 **Progress:** Chapter 22 of 30  
🎯 **Learning Objectives:** Master file operations and data persistence  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of basic Python syntax

### Basic File Operations

```python
# Writing to a file
with open('example.txt', 'w') as file:
    file.write("Hello, World!\n")
    file.write("This is a test file.\n")

# Reading from a file
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)

# Reading line by line
with open('example.txt', 'r') as file:
    for line_num, line in enumerate(file, 1):
        print(f"Line {line_num}: {line.strip()}")

# Working with CSV files
import csv

data = [
    ['Name', 'Age', 'City'],
    ['Alice', 30, 'New York'],
    ['Bob', 25, 'Boston']
]

with open('people.csv', 'w', newline='') as file:
    writer = csv.writer(file)
    writer.writerows(data)

# Reading CSV
with open('people.csv', 'r') as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

### JSON File Operations

```python
import json

# Writing JSON
data = {
    'users': [
        {'name': 'Alice', 'age': 30, 'skills': ['Python', 'SQL']},
        {'name': 'Bob', 'age': 25, 'skills': ['JavaScript', 'React']}
    ]
}

with open('users.json', 'w') as file:
    json.dump(data, file, indent=2)

# Reading JSON
with open('users.json', 'r') as file:
    loaded_data = json.load(file)
    print(f"Loaded data: {loaded_data}")
```

---

## 📱 Chapter 23: Regular Expressions
📊 **Progress:** Chapter 23 of 30  
🎯 **Learning Objectives:** Master pattern matching with regular expressions  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Understanding of strings

### Basic Regular Expressions

```python
import re

# Basic pattern matching
text = "The phone number is 123-456-7890"
pattern = r'\d{3}-\d{3}-\d{4}'
match = re.search(pattern, text)

if match:
    print(f"Found phone number: {match.group()}")

# Common regex patterns
email_pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
phone_pattern = r'\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}'
url_pattern = r'https?://(?:[-\w.])+(?:\.[a-zA-Z]{2,4})+(?:/?(?:[\w/_.])*)?'

# Finding all matches
text_with_emails = "Contact us at info@example.com or support@test.org"
emails = re.findall(email_pattern, text_with_emails)
print(f"Found emails: {emails}")

# Substitution
censored_text = re.sub(r'\b\d{3}-\d{3}-\d{4}\b', '[REDACTED]', text)
print(f"Censored: {censored_text}")
```

---

## 🎭 Chapter 24: Decorators & Context Managers
📊 **Progress:** Chapter 24 of 30  
🎯 **Learning Objectives:** Understand advanced Python features for code enhancement  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of functions and classes

### Decorators

```python
import time
from functools import wraps

# Simple decorator
def timer(func):
    """Measure function execution time."""
    @wraps(func)
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"{func.__name__} took {end_time - start_time:.4f} seconds")
        return result
    return wrapper

@timer
def slow_function():
    """A function that takes some time."""
    time.sleep(1)
    return "Done!"

result = slow_function()

# Decorator with parameters
def retry(max_attempts=3, delay=1):
    """Retry decorator with configurable attempts and delay."""
    def decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            for attempt in range(max_attempts):
                try:
                    return func(*args, **kwargs)
                except Exception as e:
                    if attempt == max_attempts - 1:
                        raise e
                    print(f"Attempt {attempt + 1} failed: {e}")
                    time.sleep(delay)
        return wrapper
    return decorator

@retry(max_attempts=3, delay=0.5)
def unreliable_function():
    """Function that might fail."""
    import random
    if random.random() < 0.7:
        raise ValueError("Random failure!")
    return "Success!"
```

### Context Managers

```python
# Using with statement
with open('test.txt', 'w') as file:
    file.write("Hello, World!")
# File automatically closed

# Custom context manager class
class Timer:
    """Context manager for timing operations."""
    
    def __enter__(self):
        self.start_time = time.time()
        return self
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        self.end_time = time.time()
        print(f"Operation took {self.end_time - self.start_time:.4f} seconds")

# Usage
with Timer():
    time.sleep(0.5)

# Context manager using contextlib
from contextlib import contextmanager

@contextmanager
def temporary_file(filename):
    """Create and automatically clean up temporary file."""
    file = open(filename, 'w')
    try:
        yield file
    finally:
        file.close()
        import os
        if os.path.exists(filename):
            os.remove(filename)

with temporary_file('temp.txt') as f:
    f.write("Temporary content")
```

---

## 🔄 Chapter 25: Generators & Iterators
📊 **Progress:** Chapter 25 of 30  
🎯 **Learning Objectives:** Understand lazy evaluation and memory-efficient iteration  
⏱️ **Estimated Reading Time:** 20 minutes  
📋 **Prerequisites:** Understanding of functions and loops

### Generators

```python
# Generator function
def fibonacci(n):
    """Generate fibonacci sequence up to n terms."""
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# Using generator
fib_gen = fibonacci(10)
print("Fibonacci sequence:")
for num in fib_gen:
    print(num, end=" ")
print()

# Generator expression
squares = (x**2 for x in range(10))
print(f"First 5 squares: {list(squares)[:5]}")

# Infinite generator
def count_up(start=0):
    """Infinite counter starting from start."""
    num = start
    while True:
        yield num
        num += 1

counter = count_up(10)
print("First 5 numbers from counter:")
for _ in range(5):
    print(next(counter))
```

### Custom Iterators

```python
class CountDown:
    """Custom iterator for countdown."""
    
    def __init__(self, start):
        self.start = start
    
    def __iter__(self):
        return self
    
    def __next__(self):
        if self.start <= 0:
            raise StopIteration
        self.start -= 1
        return self.start + 1

# Usage
countdown = CountDown(5)
for num in countdown:
    print(f"Countdown: {num}")
```

---

## ⚡ Chapter 26: Concurrency & Parallelism
📊 **Progress:** Chapter 26 of 30  
🎯 **Learning Objectives:** Introduction to concurrent and parallel programming  
⏱️ **Estimated Reading Time:** 25 minutes  
📋 **Prerequisites:** Understanding of functions and basic programming concepts

### Threading

```python
import threading
import time

def worker(name, delay):
    """Worker function for threading."""
    print(f"Worker {name} starting")
    time.sleep(delay)
    print(f"Worker {name} finished")

# Creating and starting threads
threads = []
for i in range(3):
    thread = threading.Thread(target=worker, args=(f"Thread-{i}", i+1))
    threads.append(thread)
    thread.start()

# Wait for all threads to complete
for thread in threads:
    thread.join()

print("All threads completed")
```

### Asyncio (Python 3.7+)

```python
import asyncio

async def async_worker(name, delay):
    """Async worker function."""
    print(f"Async worker {name} starting")
    await asyncio.sleep(delay)
    print(f"Async worker {name} finished")

async def main():
    """Main async function."""
    tasks = []
    for i in range(3):
        task = asyncio.create_task(async_worker(f"Task-{i}", i+1))
        tasks.append(task)
    
    await asyncio.gather(*tasks)
    print("All async tasks completed")

# Run async code
asyncio.run(main())
```

---

## 🚀 Project 1: Personal Task Manager
📊 **Progress:** Project 1 of 3  
🎯 **Learning Objectives:** Apply Python concepts in a real-world application  
⏱️ **Estimated Time:** 45 minutes  
📋 **Prerequisites:** Understanding of classes, file I/O, and basic data structures

### Project Overview

Build a command-line task manager that can create, read, update, and delete tasks with persistence to JSON files.

```python
#!/usr/bin/env python3
"""
Personal Task Manager
A comprehensive task management system demonstrating Python concepts.
"""

import json
import datetime
from typing import List, Dict, Optional
from enum import Enum

class Priority(Enum):
    """Task priority levels."""
    LOW = "low"
    MEDIUM = "medium"
    HIGH = "high"
    URGENT = "urgent"

class Status(Enum):
    """Task status options."""
    TODO = "todo"
    IN_PROGRESS = "in_progress"
    COMPLETED = "completed"
    CANCELLED = "cancelled"

class Task:
    """Individual task representation."""
    
    def __init__(self, title: str, description: str = "", 
                 priority: Priority = Priority.MEDIUM):
        self.id = self._generate_id()
        self.title = title
        self.description = description
        self.priority = priority
        self.status = Status.TODO
        self.created_at = datetime.datetime.now().isoformat()
        self.updated_at = self.created_at
        self.completed_at = None
        self.due_date = None
    
    def _generate_id(self) -> str:
        """Generate unique task ID."""
        import uuid
        return str(uuid.uuid4())[:8]
    
    def mark_completed(self):
        """Mark task as completed."""
        self.status = Status.COMPLETED
        self.completed_at = datetime.datetime.now().isoformat()
        self.updated_at = self.completed_at
    
    def update(self, **kwargs):
        """Update task attributes."""
        for key, value in kwargs.items():
            if hasattr(self, key):
                setattr(self, key, value)
        self.updated_at = datetime.datetime.now().isoformat()
    
    def to_dict(self) -> Dict:
        """Convert task to dictionary."""
        return {
            'id': self.id,
            'title': self.title,
            'description': self.description,
            'priority': self.priority.value,
            'status': self.status.value,
            'created_at': self.created_at,
            'updated_at': self.updated_at,
            'completed_at': self.completed_at,
            'due_date': self.due_date
        }
    
    @classmethod
    def from_dict(cls, data: Dict) -> 'Task':
        """Create task from dictionary."""
        task = cls(data['title'], data.get('description', ''))
        task.id = data['id']
        task.priority = Priority(data['priority'])
        task.status = Status(data['status'])
        task.created_at = data['created_at']
        task.updated_at = data['updated_at']
        task.completed_at = data.get('completed_at')
        task.due_date = data.get('due_date')
        return task
    
    def __str__(self) -> str:
        status_symbol = {
            Status.TODO: "☐",
            Status.IN_PROGRESS: "◐",
            Status.COMPLETED: "☑",
            Status.CANCELLED: "☒"
        }
        priority_symbol = {
            Priority.LOW: "🔵",
            Priority.MEDIUM: "🟡",
            Priority.HIGH: "🟠",
            Priority.URGENT: "🔴"
        }
        
        return (f"{status_symbol[self.status]} {priority_symbol[self.priority]} "
                f"[{self.id}] {self.title}")

class TaskManager:
    """Task management system."""
    
    def __init__(self, data_file: str = "tasks.json"):
        self.data_file = data_file
        self.tasks: List[Task] = []
        self.load_tasks()
    
    def load_tasks(self):
        """Load tasks from JSON file."""
        try:
            with open(self.data_file, 'r') as file:
                data = json.load(file)
                self.tasks = [Task.from_dict(task_data) for task_data in data]
        except FileNotFoundError:
            self.tasks = []
        except json.JSONDecodeError:
            print("Warning: Could not parse tasks file. Starting with empty task list.")
            self.tasks = []
    
    def save_tasks(self):
        """Save tasks to JSON file."""
        try:
            with open(self.data_file, 'w') as file:
                json.dump([task.to_dict() for task in self.tasks], file, indent=2)
        except IOError as e:
            print(f"Error saving tasks: {e}")
    
    def add_task(self, title: str, description: str = "", 
                 priority: Priority = Priority.MEDIUM) -> Task:
        """Add new task."""
        task = Task(title, description, priority)
        self.tasks.append(task)
        self.save_tasks()
        return task
    
    def get_task(self, task_id: str) -> Optional[Task]:
        """Get task by ID."""
        for task in self.tasks:
            if task.id == task_id:
                return task
        return None
    
    def list_tasks(self, status_filter: Optional[Status] = None,
                   priority_filter: Optional[Priority] = None) -> List[Task]:
        """List tasks with optional filtering."""
        filtered_tasks = self.tasks
        
        if status_filter:
            filtered_tasks = [t for t in filtered_tasks if t.status == status_filter]
        
        if priority_filter:
            filtered_tasks = [t for t in filtered_tasks if t.priority == priority_filter]
        
        return sorted(filtered_tasks, key=lambda t: t.created_at, reverse=True)
    
    def update_task(self, task_id: str, **kwargs) -> bool:
        """Update task by ID."""
        task = self.get_task(task_id)
        if task:
            task.update(**kwargs)
            self.save_tasks()
            return True
        return False
    
    def delete_task(self, task_id: str) -> bool:
        """Delete task by ID."""
        task = self.get_task(task_id)
        if task:
            self.tasks.remove(task)
            self.save_tasks()
            return True
        return False
    
    def get_statistics(self) -> Dict:
        """Get task statistics."""
        stats = {
            'total': len(self.tasks),
            'todo': len([t for t in self.tasks if t.status == Status.TODO]),
            'in_progress': len([t for t in self.tasks if t.status == Status.IN_PROGRESS]),
            'completed': len([t for t in self.tasks if t.status == Status.COMPLETED]),
            'cancelled': len([t for t in self.tasks if t.status == Status.CANCELLED])
        }
        
        priority_stats = {
            'low': len([t for t in self.tasks if t.priority == Priority.LOW]),
            'medium': len([t for t in self.tasks if t.priority == Priority.MEDIUM]),
            'high': len([t for t in self.tasks if t.priority == Priority.HIGH]),
            'urgent': len([t for t in self.tasks if t.priority == Priority.URGENT])
        }
        
        stats['by_priority'] = priority_stats
        return stats

def main():
    """Main application interface."""
    manager = TaskManager()
    
    print("🎯 Personal Task Manager")
    print("=" * 30)
    
    while True:
        print("\nOptions:")
        print("1. Add Task")
        print("2. List Tasks")
        print("3. Update Task")
        print("4. Complete Task")
        print("5. Delete Task")
        print("6. Statistics")
        print("7. Exit")
        
        try:
            choice = input("\nEnter your choice (1-7): ").strip()
            
            if choice == '1':
                title = input("Task title: ").strip()
                if not title:
                    print("Title cannot be empty!")
                    continue
                
                description = input("Description (optional): ").strip()
                
                print("Priority levels: 1=Low, 2=Medium, 3=High, 4=Urgent")
                priority_map = {
                    '1': Priority.LOW,
                    '2': Priority.MEDIUM,
                    '3': Priority.HIGH,
                    '4': Priority.URGENT
                }
                
                priority_choice = input("Priority (1-4, default=2): ").strip() or '2'
                priority = priority_map.get(priority_choice, Priority.MEDIUM)
                
                task = manager.add_task(title, description, priority)
                print(f"✅ Task created: {task}")
            
            elif choice == '2':
                tasks = manager.list_tasks()
                if not tasks:
                    print("No tasks found.")
                else:
                    print(f"\n📋 Tasks ({len(tasks)} total):")
                    for task in tasks:
                        print(f"  {task}")
                        if task.description:
                            print(f"     📝 {task.description}")
            
            elif choice == '3':
                task_id = input("Enter task ID: ").strip()
                task = manager.get_task(task_id)
                
                if not task:
                    print("Task not found!")
                    continue
                
                print(f"Current task: {task}")
                new_title = input(f"New title (current: {task.title}): ").strip()
                new_description = input(f"New description (current: {task.description}): ").strip()
                
                updates = {}
                if new_title:
                    updates['title'] = new_title
                if new_description:
                    updates['description'] = new_description
                
                if updates:
                    manager.update_task(task_id, **updates)
                    print("✅ Task updated!")
                else:
                    print("No changes made.")
            
            elif choice == '4':
                task_id = input("Enter task ID to complete: ").strip()
                task = manager.get_task(task_id)
                
                if not task:
                    print("Task not found!")
                    continue
                
                task.mark_completed()
                manager.save_tasks()
                print(f"✅ Task completed: {task}")
            
            elif choice == '5':
                task_id = input("Enter task ID to delete: ").strip()
                task = manager.get_task(task_id)
                
                if not task:
                    print("Task not found!")
                    continue
                
                confirm = input(f"Delete '{task.title}'? (y/N): ").lower()
                if confirm == 'y':
                    manager.delete_task(task_id)
                    print("✅ Task deleted!")
                else:
                    print("Deletion cancelled.")
            
            elif choice == '6':
                stats = manager.get_statistics()
                print("\n📊 Task Statistics:")
                print(f"  Total tasks: {stats['total']}")
                print(f"  To-do: {stats['todo']}")
                print(f"  In progress: {stats['in_progress']}")
                print(f"  Completed: {stats['completed']}")
                print(f"  Cancelled: {stats['cancelled']}")
                
                print("\n📈 By Priority:")
                for priority, count in stats['by_priority'].items():
                    print(f"  {priority.title()}: {count}")
            
            elif choice == '7':
                print("👋 Goodbye!")
                break
            
            else:
                print("Invalid choice. Please enter 1-7.")
        
        except KeyboardInterrupt:
            print("\n👋 Goodbye!")
            break
        except Exception as e:
            print(f"❌ An error occurred: {e}")

if __name__ == "__main__":
    main()
```

---

## 📖 Glossary

**API (Application Programming Interface)**: A set of protocols and tools for building software applications.

**Argument**: A value passed to a function when it is called.

**Class**: A blueprint for creating objects that defines attributes and methods.

**Decorator**: A function that modifies or extends the behavior of another function.

**Dictionary**: A mutable mapping data type that stores key-value pairs.

**Exception**: An error that occurs during program execution.

**Function**: A reusable block of code that performs a specific task.

**Generator**: A function that returns an iterator using the `yield` keyword.

**Inheritance**: A mechanism where a class derives properties from another class.

**Iterator**: An object that can be iterated over, implementing `__iter__()` and `__next__()`.

**Lambda**: An anonymous function defined using the `lambda` keyword.

**List**: A mutable sequence data type that can hold ordered collections of items.

**Method**: A function that belongs to a class or object.

**Module**: A file containing Python code that can be imported and used.

**Object**: An instance of a class containing data and methods.

**Package**: A collection of modules organized in directories.

**Parameter**: A variable in a function definition that receives an argument value.

**Polymorphism**: The ability of different classes to implement the same interface.

**Set**: An unordered collection of unique elements.

**Tuple**: An immutable sequence data type similar to lists but cannot be changed.

---

## 🔗 Quick Reference Card

### Data Types
```python
# Numbers
int_num = 42
float_num = 3.14
complex_num = 3+4j

# Strings  
string = "Hello, World!"
multiline = """Multi-line
string"""

# Collections
my_list = [1, 2, 3]
my_tuple = (1, 2, 3)  
my_dict = {"key": "value"}
my_set = {1, 2, 3}
```

### Control Flow
```python
# Conditionals
if condition:
    pass
elif other_condition:
    pass
else:
    pass

# Loops
for item in iterable:
    pass

while condition:
    pass

# Exception Handling
try:
    risky_operation()
except SpecificError as e:
    handle_error(e)
finally:
    cleanup()
```

### Functions and Classes
```python
# Function
def my_function(param1, param2="default"):
    """Function docstring."""
    return result

# Class
class MyClass:
    def __init__(self, value):
        self.value = value
    
    def method(self):
        return self.value
```

### Common Built-ins
```python
len(obj)          # Length
str(obj)          # String conversion
int(obj)          # Integer conversion
float(obj)        # Float conversion
type(obj)         # Object type
isinstance(obj, type)  # Type checking
range(start, stop, step)  # Number sequence
enumerate(iterable)    # Index and value pairs
zip(iter1, iter2)     # Pair elements
```

---

## 📚 Further Reading

### Official Documentation
- [Python.org Documentation](https://docs.python.org/3/)
- [Python Tutorial](https://docs.python.org/3/tutorial/)
- [Python Standard Library](https://docs.python.org/3/library/)

### Books
- "Automate the Boring Stuff with Python" by Al Sweigart
- "Python Crash Course" by Eric Matthes
- "Effective Python" by Brett Slatkin
- "Fluent Python" by Luciano Ramalho

### Online Resources
- [Real Python](https://realpython.com/)
- [Python Package Index (PyPI)](https://pypi.org/)
- [Awesome Python](https://awesome-python.com/)
- [Python Weekly](https://www.pythonweekly.com/)

### Practice Platforms
- [LeetCode](https://leetcode.com/)
- [HackerRank](https://www.hackerrank.com/)
- [Codewars](https://www.codewars.com/)
- [Project Euler](https://projecteuler.net/)

---

## 🤝 Community Resources

### Forums and Discussion
- [r/Python](https://reddit.com/r/python) - Reddit Python community
- [Stack Overflow](https://stackoverflow.com/questions/tagged/python) - Q&A platform
- [Python Discord](https://discord.gg/python) - Real-time chat community
- [Python Forum](https://python-forum.io/) - Dedicated Python discussion forum

### Conferences and Events
- PyCon (International Python Conference)
- EuroPython (European Python Conference)  
- Local Python User Groups (PyUG)
- Django Conference
- Flask Conference

### Contributing to Python
- [Python Developer's Guide](https://devguide.python.org/)
- [Python Enhancement Proposals (PEPs)](https://peps.python.org/)
- [Python Issue Tracker](https://bugs.python.org/)
- [Python GitHub Repository](https://github.com/python/cpython)

---

## 💝 Contributing Guidelines

### How to Contribute to This Documentation

We welcome contributions to improve this Python documentation! Here's how you can help:

#### Types of Contributions
1. **Content Improvements**: Fix typos, improve explanations, add examples
2. **New Sections**: Add missing topics or expand existing ones
3. **Code Examples**: Contribute working code examples and exercises
4. **Translations**: Help translate documentation to other languages

#### Contribution Process
1. **Fork** the repository containing this documentation
2. **Create** a new branch for your changes
3. **Make** your improvements following our style guide
4. **Test** all code examples to ensure they work correctly
5. **Submit** a pull request with a clear description of changes

#### Style Guidelines
- Use clear, concise language suitable for beginners
- Include working code examples with explanations
- Follow PEP 8 for Python code formatting
- Use emoji icons consistently with existing patterns
- Maintain the progressive learning structure

#### Code Standards
- All code examples must be tested and functional
- Include error handling where appropriate
- Use meaningful variable and function names
- Add comments explaining complex concepts
- Ensure compatibility with Python 3.8+

### Reporting Issues
Found a bug or error? Please report it by:
1. Checking if the issue already exists
2. Creating a detailed issue report with:
   - Description of the problem
   - Steps to reproduce
   - Expected vs actual behavior
   - Python version and environment details

### Recognition
Contributors will be acknowledged in the documentation credits section. Significant contributions may be recognized with co-authorship.

---

## 🎉 Conclusion

Congratulations! You've completed this comprehensive Python 3.12 documentation. You've learned:

✅ **Core Concepts**: Variables, data types, operators, and control flow  
✅ **Data Structures**: Lists, tuples, dictionaries, and sets  
✅ **Functions**: Definition, parameters, scope, and advanced features  
✅ **Object-Oriented Programming**: Classes, inheritance, and polymorphism  
✅ **File Operations**: Reading, writing, and data persistence  
✅ **Error Handling**: Exception management and debugging  
✅ **Advanced Features**: Decorators, generators, and context managers  
✅ **Real-World Applications**: Projects and practical implementations  

### Next Steps

1. **Practice Regularly**: Build projects and solve coding challenges
2. **Explore Libraries**: Learn popular packages like NumPy, Pandas, Django, Flask
3. **Join the Community**: Participate in forums, contribute to open source
4. **Specialize**: Choose areas like web development, data science, or automation
5. **Keep Learning**: Python evolves continuously - stay updated with new features

### Final Words

Python's philosophy of "beautiful is better than ugly" and "simple is better than complex" makes it an excellent language for both beginners and experts. As you continue your Python journey, remember:

- **Code readability matters** - Write code that others (and future you) can understand
- **There should be one obvious way to do it** - Python often provides clear, idiomatic solutions
- **Practicality beats purity** - Focus on solving real problems effectively
- **Errors should never pass silently** - Handle exceptions appropriately
- **In the face of ambiguity, refuse the temptation to guess** - Be explicit in your code

The Python community is welcoming and supportive. Don't hesitate to ask questions, share your projects, and contribute back to the ecosystem that has given you so much.

Happy coding! 🐍✨

---

*This documentation was created with ❤️ for the Python community. Last updated: January 2024*

**Document Statistics:**
- **Chapters:** 30 comprehensive chapters
- **Projects:** 3 hands-on projects  
- **Code Examples:** 100+ working examples
- **Exercises:** 25+ practical exercises
- **Target Audience:** Beginners to intermediate Python developers
- **Python Version:** 3.12+

---

**Credits:**
- Documentation structure inspired by official Python documentation
- Code examples tested with Python 3.12
- Community feedback incorporated from Python forums and user groups
- Special thanks to the Python Software Foundation and core developers

[🔝 Back to Top](#-python-documentation)
