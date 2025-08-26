# 🐚 Bash Documentation
*Version: 5.2.21 | Last Updated: August 26, 2025*

Bash (Bourne Again Shell) is a powerful command-line interpreter and scripting language that serves as the default shell for most Unix-like operating systems. It combines the best features of the original Bourne shell with additional functionality for interactive use and scripting.

## 📑 Table of Contents

- [📚 Introduction & Setup](#-introduction--setup)
  - [What is Bash?](#what-is-bash)
  - [Why Use Bash?](#why-use-bash)
  - [Installation and Setup](#installation-and-setup)
  - [Development Environment](#development-environment)
  - [Hello World Example](#hello-world-example)
- [🔤 Basic Syntax and Structure](#-basic-syntax-and-structure)
  - [Commands and Arguments](#commands-and-arguments)
  - [Comments](#comments)
  - [Line Continuation](#line-continuation)
  - [Case Sensitivity](#case-sensitivity)
- [📊 Variables and Data Types](#-variables-and-data-types)
  - [Variable Declaration](#variable-declaration)
  - [Environment Variables](#environment-variables)
  - [Special Variables](#special-variables)
  - [Arrays](#arrays)
  - [Variable Expansion](#variable-expansion)
- [🔄 Control Structures](#-control-structures)
  - [Conditional Statements](#conditional-statements)
  - [Loops](#loops)
  - [Case Statements](#case-statements)
  - [Exit Status and Return Values](#exit-status-and-return-values)
- [⚡ Functions and Scope](#-functions-and-scope)
  - [Function Definition](#function-definition)
  - [Function Parameters](#function-parameters)
  - [Local Variables](#local-variables)
  - [Recursive Functions](#recursive-functions)
- [📁 File Operations](#-file-operations)
  - [File Tests](#file-tests)
  - [Reading Files](#reading-files)
  - [Writing Files](#writing-files)
  - [File Manipulation](#file-manipulation)
- [🔧 Input/Output and Redirection](#-inputoutput-and-redirection)
  - [Standard Streams](#standard-streams)
  - [Redirection Operators](#redirection-operators)
  - [Pipes and Filters](#pipes-and-filters)
  - [Here Documents](#here-documents)
- [🎭 Pattern Matching and Regular Expressions](#-pattern-matching-and-regular-expressions)
  - [Wildcards and Globbing](#wildcards-and-globbing)
  - [Pattern Matching](#pattern-matching)
  - [Regular Expressions](#regular-expressions)
  - [String Manipulation](#string-manipulation)
- [⚙️ Process Management](#-process-management)
  - [Job Control](#job-control)
  - [Background Processes](#background-processes)
  - [Signal Handling](#signal-handling)
  - [Process Substitution](#process-substitution)
- [🔒 Error Handling and Debugging](#-error-handling-and-debugging)
  - [Error Handling Strategies](#error-handling-strategies)
  - [Debugging Techniques](#debugging-techniques)
  - [Logging and Monitoring](#logging-and-monitoring)
  - [Testing Scripts](#testing-scripts)
- [🚀 Advanced Features](#-advanced-features)
  - [Parameter Expansion](#parameter-expansion)
  - [Command Substitution](#command-substitution)
  - [Arithmetic Expansion](#arithmetic-expansion)
  - [Brace Expansion](#brace-expansion)
- [📦 Script Organization and Modularity](#-script-organization-and-modularity)
  - [Script Structure](#script-structure)
  - [Including External Scripts](#including-external-scripts)
  - [Creating Libraries](#creating-libraries)
  - [Configuration Management](#configuration-management)
- [🚀 Real-World Applications](#-real-world-applications)
  - [System Administration Scripts](#system-administration-scripts)
  - [Automation and DevOps](#automation-and-devops)
  - [Data Processing](#data-processing)
- [📖 Appendices](#-appendices)
  - [Quick Reference Card](#quick-reference-card)
  - [Glossary](#glossary)
  - [Further Reading](#further-reading)
  - [Community Resources](#community-resources)
  - [Contributing Guidelines](#contributing-guidelines)

---

## 📚 Introduction & Setup

📊 **Chapter 1 of 13**
🎯 **Learning Objectives:**
- Understand what Bash is and its role in Unix-like systems
- Install and configure Bash on different platforms
- Set up an effective development environment
- Write your first Bash script

⏱️ **Estimated Reading Time:** 15 minutes
📋 **Prerequisites:** Basic familiarity with command-line interfaces

### What is Bash?

Bash (Bourne Again Shell) is a Unix shell and command language written by Brian Fox for the GNU Project as a free software replacement for the Bourne shell. First released in 1989, Bash has become the default login shell for most Linux distributions and macOS (though macOS switched to zsh as default in newer versions).

Bash serves multiple roles:

1. **Interactive Shell**: Provides a command-line interface for users to interact with the operating system
2. **Scripting Language**: Allows automation of tasks through script files
3. **Command Processor**: Interprets and executes commands from users or scripts

The name "Bash" is both a play on words (being a "better" shell that you can "bash away" at) and an acronym for "Bourne Again Shell," honoring its predecessor, the Bourne shell (sh).

### Why Use Bash?

Bash offers numerous advantages that make it an essential tool for system administrators, developers, and power users:

**🔧 System Integration**
- Native to Unix-like systems (Linux, macOS, BSD)
- Direct access to system calls and utilities
- Seamless integration with existing command-line tools

**🚀 Automation Power**
- Automate repetitive tasks and system maintenance
- Create complex workflows and pipelines
- Schedule tasks with cron jobs

**📈 Productivity Benefits**
- Rapid prototyping of system utilities
- Quick data processing and text manipulation
- Efficient file and directory operations

**🌐 Universality**
- Available on virtually all Unix-like systems
- Portable scripts across different platforms
- Standard tool in DevOps and cloud environments

**💰 Cost-Effective**
- Free and open-source
- No licensing fees for enterprise use
- Extensive community support and documentation

### Installation and Setup

#### Linux Systems

Most Linux distributions come with Bash pre-installed. You can verify the installation and version:

```bash
# Check if bash is installed
which bash

# Check bash version
bash --version

# Check current shell
echo $SHELL
```

If Bash is not installed or you need to update it:

```bash
# Ubuntu/Debian
sudo apt update && sudo apt install bash

# CentOS/RHEL/Fedora
sudo yum install bash
# or for newer versions
sudo dnf install bash

# Arch Linux
sudo pacman -S bash
```

#### macOS

macOS includes Bash, but older versions may be outdated due to licensing changes:

```bash
# Check current version
bash --version

# Install latest version via Homebrew
brew install bash

# Add new bash to allowed shells
echo /opt/homebrew/bin/bash | sudo tee -a /etc/shells

# Change default shell
chsh -s /opt/homebrew/bin/bash
```

#### Windows

For Windows users, several options provide Bash functionality:

**Windows Subsystem for Linux (WSL)**
```powershell
# Install WSL2 with Ubuntu
wsl --install -d Ubuntu
```

**Git Bash**
- Download from https://git-scm.com/
- Provides Git tools with Bash environment

**Cygwin**
- Download from https://www.cygwin.com/
- Unix-like environment for Windows

### Development Environment

#### Setting Up Your Bash Environment

**1. Configure Your Shell Profile**

Add customizations to your `.bashrc` (Linux) or `.bash_profile` (macOS):

```bash
# ~/.bashrc or ~/.bash_profile

# Aliases for common commands
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
alias grep='grep --color=auto'

# Environment variables
export EDITOR=vim
export PAGER=less
export HISTSIZE=10000
export HISTFILESIZE=20000

# Custom prompt
export PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '

# Enable programmable completion
if [ -f /etc/bash_completion ] && ! shopt -oq posix; then
    . /etc/bash_completion
fi
```

**2. Editor Configuration**

For Vim users, create or edit `~/.vimrc`:

```vim
" Basic settings for bash scripting
syntax on
set number
set expandtab
set tabstop=4
set shiftwidth=4
set autoindent

" Bash-specific settings
autocmd FileType sh setlocal expandtab shiftwidth=2 tabstop=2
```

**3. IDE and Text Editor Options**

- **Visual Studio Code**: Excellent Bash support with extensions
- **Vim/Neovim**: Lightweight with powerful bash editing capabilities
- **Emacs**: Comprehensive editing environment
- **Sublime Text**: Fast with good bash syntax highlighting
- **IntelliJ IDEA**: Full-featured IDE with bash plugin support

### Hello World Example

Let's create your first Bash script:

```bash
#!/bin/bash
# hello_world.sh - My first Bash script

# Print a greeting
echo "Hello, World!"

# Get current date and time
current_date=$(date)
echo "Current date and time: $current_date"

# Get username
echo "Hello, $USER! Welcome to Bash scripting."

# Simple calculation
echo "2 + 3 = $((2 + 3))"
```

**Making the Script Executable and Running It:**

```bash
# Make the script executable
chmod +x hello_world.sh

# Run the script
./hello_world.sh
```

**Expected Output:**
```
Hello, World!
Current date and time: Mon Aug 26 07:33:50 UTC 2025
Hello, user! Welcome to Bash scripting.
2 + 3 = 5
```

**💡 Code Explanation:**

1. `#!/bin/bash` - The shebang line tells the system which interpreter to use
2. `echo` - Prints text to the console
3. `$(date)` - Command substitution that executes the `date` command
4. `$USER` - Environment variable containing the current username
5. `$((2 + 3))` - Arithmetic expansion for mathematical operations

### ⚠️ Common Pitfalls

1. **Missing Shebang**: Always include `#!/bin/bash` at the beginning of scripts
2. **File Permissions**: Remember to make scripts executable with `chmod +x`
3. **Path Issues**: Use `./script.sh` to run scripts in the current directory
4. **Shell vs. Bash**: Some systems use `/bin/sh` which may not support all Bash features

### ✅ Best Practices

1. **Use Descriptive Names**: Choose clear, meaningful script names
2. **Add Comments**: Document your code for future reference
3. **Error Checking**: Always check if commands succeed
4. **Consistent Formatting**: Use consistent indentation and spacing
5. **Version Control**: Track your scripts with Git

### 🏋️ Exercise 1: Environment Setup

**Difficulty:** 🟢 Beginner
**Estimated Time:** 20 minutes

Create a script called `system_info.sh` that displays:
1. Current Bash version
2. Current user and home directory
3. Current working directory
4. Available disk space
5. Current date and time formatted as "YYYY-MM-DD HH:MM:SS"

<details>
<summary>💡 Click to see hints</summary>

- Use `bash --version` for Bash version
- Environment variables: `$USER`, `$HOME`, `$PWD`
- Commands: `df -h`, `date`
- Date formatting: `date "+%Y-%m-%d %H:%M:%S"`

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# system_info.sh - Display system information

echo "=== System Information ==="
echo

# Bash version
echo "Bash Version:"
bash --version | head -1
echo

# User information
echo "Current User: $USER"
echo "Home Directory: $HOME"
echo "Current Directory: $PWD"
echo

# Disk space
echo "Available Disk Space:"
df -h /
echo

# Current date and time
formatted_date=$(date "+%Y-%m-%d %H:%M:%S")
echo "Current Date and Time: $formatted_date"
```

**Explanation:**
- `head -1` extracts only the first line of bash version output
- `df -h /` shows disk space in human-readable format for the root filesystem
- Date formatting uses `+` to specify custom format
- The script uses consistent formatting with separators for readability

</details>

---

## 🔤 Basic Syntax and Structure

📊 **Chapter 2 of 13**
🎯 **Learning Objectives:**
- Master fundamental Bash syntax rules
- Understand command structure and execution
- Learn proper commenting and documentation practices
- Handle special characters and escaping

⏱️ **Estimated Reading Time:** 20 minutes
📋 **Prerequisites:** Completed Chapter 1

### Commands and Arguments

Bash commands follow a simple structure: `command [options] [arguments]`

```bash
#!/bin/bash
# command_structure.sh - Demonstrating command structure

# Simple command
ls

# Command with options (flags)
ls -l

# Command with multiple options
ls -la

# Command with options and arguments
ls -la /home /var

# Long format options (GNU-style)
ls --long --all

# Mixed short and long options
ls -l --human-readable

# Commands with complex arguments
find /etc -name "*.conf" -type f -exec grep -l "ssh" {} \;
```

**Understanding Command Components:**

1. **Command**: The program or built-in to execute
2. **Options/Flags**: Modify command behavior (usually start with `-` or `--`)
3. **Arguments**: Input data or parameters for the command

### Comments

Proper commenting is crucial for maintainable scripts:

```bash
#!/bin/bash
# comprehensive_commenting.sh - Examples of different commenting styles

#
# File: comprehensive_commenting.sh
# Author: Your Name
# Date: $(date +%Y-%m-%d)
# Purpose: Demonstrate various commenting techniques
# Version: 1.0
#

# Single-line comment
echo "This is a simple command"  # Inline comment

# Multi-line comment block
# This is a longer explanation that spans
# multiple lines and describes a complex
# operation or algorithm

: <<'COMMENT'
This is a here-document comment block.
Everything between these markers is ignored.
Useful for temporarily disabling large code blocks.
COMMENT

# Function documentation
# Purpose: Calculate the factorial of a number
# Parameters: $1 - The number to calculate factorial for
# Returns: The factorial value
# Example: factorial 5
factorial() {
    local num=$1
    # Implementation details...
    echo $((num == 0 ? 1 : num * $(factorial $((num - 1)))))
}

# Section separators
#===============================================
# MAIN PROGRAM EXECUTION
#===============================================

# TODO: Add error handling
# FIXME: Optimize this algorithm
# NOTE: This works only with positive integers
echo "Script execution begins..."
```

### Line Continuation

Handle long commands across multiple lines:

```bash
#!/bin/bash
# line_continuation.sh - Working with long lines

# Method 1: Backslash continuation
long_command_with_many_options \
    --option1 value1 \
    --option2 value2 \
    --option3 value3 \
    --final-option final-value

# Method 2: Logical operators for continuation
[ -f "/etc/passwd" ] && \
[ -r "/etc/passwd" ] && \
echo "Password file exists and is readable"

# Method 3: Pipe continuation
cat /etc/passwd | \
    grep "^root" | \
    cut -d: -f1,3 | \
    sort

# Method 4: Array continuation
long_array=(
    "element1"
    "element2"
    "element3"
    "element4"
)

# Method 5: String continuation
long_string="This is a very long string that spans "\
"multiple lines and needs to be readable "\
"while maintaining proper formatting"

echo "$long_string"

# Method 6: Function definition continuation
create_backup() {
    local source_dir=$1
    local backup_dir=$2

    # Complex tar command across multiple lines
    tar -czf "${backup_dir}/backup_$(date +%Y%m%d_%H%M%S).tar.gz" \
        --exclude="*.tmp" \
        --exclude="*.log" \
        --exclude=".git" \
        "$source_dir"
}
```

### Case Sensitivity

Bash is case-sensitive, which affects variables, commands, and file names:

```bash
#!/bin/bash
# case_sensitivity.sh - Understanding case sensitivity

# Variable names are case-sensitive
name="John"
Name="Jane"
NAME="Bob"

echo "name: $name"     # Output: John
echo "Name: $Name"     # Output: Jane
echo "NAME: $NAME"     # Output: Bob

# Function names are case-sensitive
myFunction() {
    echo "lowercase function"
}

MyFunction() {
    echo "capitalized function"
}

MYFUNCTION() {
    echo "uppercase function"
}

# Call different functions
myFunction   # Output: lowercase function
MyFunction   # Output: capitalized function
MYFUNCTION   # Output: uppercase function

# File operations are case-sensitive
touch file.txt
touch FILE.txt
touch File.txt

ls -la file.txt FILE.txt File.txt  # All three files exist

# Command comparison (these would be different commands if they existed)
# ls vs LS vs Ls (only 'ls' is the real command)

# String comparisons are case-sensitive
string1="Hello"
string2="hello"

if [ "$string1" = "$string2" ]; then
    echo "Strings are equal"
else
    echo "Strings are not equal"  # This will be executed
fi

# Case-insensitive comparison
if [[ "${string1,,}" = "${string2,,}" ]]; then
    echo "Strings are equal when compared case-insensitively"
fi
```

### Special Characters and Escaping

Understanding how Bash interprets special characters:

```bash
#!/bin/bash
# special_characters.sh - Working with special characters

# Characters with special meaning in Bash
echo "Special characters demonstration:"

# Dollar sign ($) - Variable expansion
var="test"
echo "Variable: $var"
echo "Literal dollar: \$var"

# Asterisk (*) - Wildcard
echo "Files: *.txt"
echo "Literal asterisk: \*.txt"

# Question mark (?) - Single character wildcard
echo "Pattern: file?.txt"
echo "Literal question mark: file\?.txt"

# Square brackets ([]) - Character classes
echo "Pattern: [abc].txt"
echo "Literal brackets: \[abc\].txt"

# Parentheses () - Subshells and grouping
echo "Subshell: $(echo "Hello")"
echo "Literal parentheses: \$(echo \"Hello\")"

# Braces {} - Expansion and variable delimitation
echo "Expansion: file{1,2,3}.txt"
echo "Variable delimitation: ${var}ing"
echo "Literal braces: \{1,2,3\}"

# Semicolon (;) - Command separator
echo "First"; echo "Second"
echo "Literal semicolon: First\; Second"

# Ampersand (&) - Background execution
# sleep 5 &  # Uncomment to run in background
echo "Literal ampersand: Tom \& Jerry"

# Pipe (|) - Command pipeline
echo "Hello World" | grep "World"
echo "Literal pipe: Tom \| Jerry"

# Redirection operators (< > >> <<)
echo "Hello" > temp.txt
echo "Literal: 2 \> 1"

# Quotes and escaping
echo 'Single quotes preserve everything literally'
echo "Double quotes allow variable expansion: $var"
echo "Escaped quote: \"Hello\""

# Backslash escaping
echo "Newline: First line\nSecond line"
echo -e "Interpreted newline: First line\nSecond line"

# Clean up
rm -f temp.txt
```

### Command Execution and Return Codes

Understanding how Bash executes commands and handles return values:

```bash
#!/bin/bash
# command_execution.sh - Command execution and return codes

# Simple command execution
echo "Executing simple command:"
ls /tmp

# Capturing return codes
echo "Checking return codes:"
ls /nonexistent/directory
exit_code=$?
echo "ls command returned: $exit_code"

# Using return codes in conditionals
if ls /etc > /dev/null 2>&1; then
    echo "/etc directory exists and is accessible"
else
    echo "/etc directory is not accessible"
fi

# Command grouping
echo "Command grouping:"
{ echo "First command"; echo "Second command"; }

# Subshell execution
echo "Subshell execution:"
(cd /tmp && pwd)
echo "Current directory: $(pwd)"

# Command substitution variations
echo "Command substitution:"
current_date=$(date)
current_date2=`date`  # Older syntax, not recommended

echo "Using \$(): $current_date"
echo "Using backticks: $current_date2"

# Testing commands
echo "Testing command success:"
if command -v git > /dev/null 2>&1; then
    echo "Git is installed: $(git --version)"
else
    echo "Git is not installed"
fi
```

### ⚠️ Common Pitfalls

1. **Spacing Issues**: Bash is sensitive to spaces around operators
   ```bash
   # Wrong
   if [$var -eq 5]; then  # Missing spaces around brackets

   # Correct
   if [ $var -eq 5 ]; then
   ```

2. **Unquoted Variables**: Can cause word splitting and globbing
   ```bash
   # Wrong
   if [ $var = "hello world" ]; then  # Fails if var contains spaces

   # Correct
   if [ "$var" = "hello world" ]; then
   ```

3. **Case Sensitivity Confusion**: Remember that everything is case-sensitive

4. **Special Character Misuse**: Not escaping special characters when needed

### ✅ Best Practices

1. **Consistent Quoting**: Always quote variables unless you specifically need word splitting
2. **Clear Comments**: Use comments to explain complex logic
3. **Readable Formatting**: Use line continuation for long commands
4. **Error Checking**: Always check return codes for critical operations
5. **Consistent Naming**: Use consistent case conventions for variables and functions

### 🏋️ Exercise 2: Syntax Mastery

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 30 minutes

Create a script called `file_analyzer.sh` that:
1. Takes a filename as an argument
2. Checks if the file exists and displays appropriate messages
3. If the file exists, displays:
   - File size in bytes and human-readable format
   - File permissions
   - Last modification date
   - First and last 3 lines of the file (if it's a text file)
4. Handles filenames with spaces and special characters properly
5. Uses proper commenting and line continuation where appropriate

<details>
<summary>💡 Click to see hints</summary>

- Use `test` or `[ ]` for file existence checks
- Commands you'll need: `ls -lh`, `stat`, `head`, `tail`, `file`
- Quote all variables to handle spaces
- Use `$1` for the first command-line argument
- Check if argument is provided with `$#`

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# file_analyzer.sh - Analyze file properties and content
# Usage: ./file_analyzer.sh "filename"

#===============================================
# INPUT VALIDATION
#===============================================

# Check if filename argument is provided
if [ $# -eq 0 ]; then
    echo "Error: Please provide a filename as an argument"
    echo "Usage: $0 <filename>"
    exit 1
fi

# Get the filename from command line argument
filename="$1"

#===============================================
# FILE EXISTENCE CHECK
#===============================================

if [ ! -f "$filename" ]; then
    echo "Error: File '$filename' does not exist or is not a regular file"
    exit 1
fi

echo "=== File Analysis Report ==="
echo "File: $filename"
echo

#===============================================
# BASIC FILE INFORMATION
#===============================================

# File size in bytes and human-readable format
echo "File Size Information:"
file_size_bytes=$(stat -c%s "$filename" 2>/dev/null || \
                  stat -f%z "$filename" 2>/dev/null)
echo "  Size in bytes: $file_size_bytes"

# Human-readable size using ls
ls -lh "$filename" | awk '{print "  Human-readable: " $5}'
echo

#===============================================
# FILE PERMISSIONS AND METADATA
#===============================================

echo "File Permissions and Metadata:"
ls -la "$filename" | \
    awk '{print "  Permissions: " $1 "\n  Owner: " $3 "\n  Group: " $4}'

# Last modification date
echo "  Last modified: $(stat -c%y "$filename" 2>/dev/null || \
                         stat -f%Sm "$filename" 2>/dev/null)"
echo

#===============================================
# FILE CONTENT ANALYSIS
#===============================================

# Check if it's a text file
file_type=$(file -b "$filename")
echo "File type: $file_type"

# If it appears to be a text file, show first and last lines
if file "$filename" | grep -q "text"; then
    echo
    echo "Content Preview:"
    echo "--- First 3 lines ---"
    head -n 3 "$filename"

    echo "--- Last 3 lines ---"
    tail -n 3 "$filename"
else
    echo "Note: Not a text file, skipping content preview"
fi

echo
echo "=== Analysis Complete ==="
```

**Explanation:**
- The script uses proper argument validation with `$#` and `$1`
- All variables are quoted to handle filenames with spaces
- Line continuation is used for long `stat` commands with fallback options
- Error output is suppressed with `2>/dev/null` where appropriate
- The script provides informative error messages and usage instructions
- Cross-platform compatibility is maintained with fallback `stat` options
- Consistent formatting makes the output readable

</details>

---

## 📊 Variables and Data Types

📊 **Chapter 3 of 13**
🎯 **Learning Objectives:**
- Master variable declaration and assignment
- Understand different variable scopes and types
- Work with arrays and associative arrays
- Master variable expansion techniques

⏱️ **Estimated Reading Time:** 25 minutes
📋 **Prerequisites:** Chapters 1-2

### Variable Declaration

Bash variables are dynamically typed and don't require explicit declaration:

```bash
#!/bin/bash
# variable_declaration.sh - Variable declaration and assignment

# Basic variable assignment (no spaces around =)
name="John Doe"
age=30
is_student=true

# Displaying variables
echo "Name: $name"
echo "Age: $age"
echo "Student status: $is_student"

# Variable naming rules
valid_name="Valid"
_underscore_name="Also valid"
name123="Numbers allowed"
# 123name="Invalid"  # Cannot start with number
# name-with-hyphens="Invalid"  # Hyphens not allowed

# Dynamic assignment
counter=1
echo "Counter: $counter"
counter=$((counter + 1))
echo "Counter after increment: $counter"

# Assignment from command output
current_user=$(whoami)
current_date=$(date "+%Y-%m-%d")
echo "Current user: $current_user"
echo "Current date: $current_date"

# Multiple assignment techniques
var1="first" var2="second" var3="third"
echo "Multiple assignment: $var1, $var2, $var3"

# Reading from user input
echo "Enter your favorite color:"
read favorite_color
echo "Your favorite color is: $favorite_color"

# Reading with prompt
read -p "Enter your age: " user_age
echo "You are $user_age years old"

# Reading sensitive information (passwords)
read -s -p "Enter password: " password
echo  # New line after hidden input
echo "Password entered (hidden)"
```

### Environment Variables

Environment variables are available to all processes and subshells:

```bash
#!/bin/bash
# environment_variables.sh - Working with environment variables

# Display all environment variables
echo "=== Common Environment Variables ==="
echo "HOME: $HOME"
echo "USER: $USER"
echo "SHELL: $SHELL"
echo "PATH: $PATH"
echo "PWD: $PWD"
echo "HOSTNAME: $HOSTNAME"

# Setting environment variables for current session
export MY_VAR="This is exported"
export DATABASE_URL="postgresql://localhost:5432/mydb"
export DEBUG_MODE="true"

# Temporary environment variable for single command
MY_TEMP_VAR="temporary" env | grep MY_TEMP_VAR

# Using environment variables in configuration
config_file="${HOME}/.myapp/config"
log_file="${HOME}/logs/app.log"

echo "Config file path: $config_file"
echo "Log file path: $log_file"

# Default values for environment variables
database_host=${DATABASE_HOST:-"localhost"}
database_port=${DATABASE_PORT:-5432}
debug_mode=${DEBUG_MODE:-"false"}

echo "Database: $database_host:$database_port"
echo "Debug mode: $debug_mode"

# Checking if environment variable is set
if [ -n "$EDITOR" ]; then
    echo "Default editor: $EDITOR"
else
    echo "No default editor set"
fi

# Unsetting variables
unset MY_VAR
echo "MY_VAR after unset: '$MY_VAR'"  # Should be empty

# Making variables readonly
readonly PI=3.14159
echo "PI: $PI"
# PI=3.14  # This would cause an error

# Displaying variable attributes
declare -p PI
declare -p HOME
```

### Special Variables

Bash provides several special variables for script parameters and status:

```bash
#!/bin/bash
# special_variables.sh - Understanding special variables

echo "=== Script Information ==="
echo "Script name: $0"
echo "Number of arguments: $#"
echo "All arguments: $@"
echo "All arguments as single string: $*"
echo "Process ID: $$"
echo "Exit status of last command: $?"

echo
echo "=== Argument Processing ==="
echo "First argument: $1"
echo "Second argument: $2"
echo "Third argument: $3"
echo "Tenth argument: ${10}"  # Use braces for arguments > 9

# Processing all arguments
echo
echo "=== Iterating Through Arguments ==="
for arg in "$@"; do
    echo "Argument: $arg"
done

# Using shift to process arguments
echo
echo "=== Using shift ==="
while [ $# -gt 0 ]; do
    echo "Processing: $1"
    shift
done

# Demonstrating $? (exit status)
echo
echo "=== Exit Status Examples ==="
ls /etc > /dev/null
echo "ls /etc exit status: $?"

ls /nonexistent > /dev/null 2>&1
echo "ls /nonexistent exit status: $?"

# Background process ID
sleep 10 &
background_pid=$!
echo "Background sleep process ID: $background_pid"
kill $background_pid  # Clean up

# Additional special variables
echo
echo "=== Additional Special Variables ==="
echo "Current shell options: $-"
echo "Name of shell or script: $0"

# IFS (Internal Field Separator)
original_ifs="$IFS"
data="apple,banana,cherry"
IFS=","
read -ra fruits <<< "$data"
for fruit in "${fruits[@]}"; do
    echo "Fruit: $fruit"
done
IFS="$original_ifs"  # Restore original IFS
```

### Arrays

Bash supports indexed and associative arrays for storing multiple values:

```bash
#!/bin/bash
# arrays.sh - Working with arrays in Bash

echo "=== Indexed Arrays ==="

# Array declaration methods
fruits=("apple" "banana" "cherry" "date")
numbers=(1 2 3 4 5)
mixed=("text" 42 "more text" 3.14)

# Alternative declaration
declare -a colors
colors[0]="red"
colors[1]="green"
colors[2]="blue"
colors[5]="purple"  # Sparse arrays allowed

# Display array elements
echo "Fruits: ${fruits[@]}"
echo "Numbers: ${numbers[*]}"
echo "First fruit: ${fruits[0]}"
echo "Last fruit: ${fruits[-1]}"  # Bash 4.3+

# Array length
echo "Number of fruits: ${#fruits[@]}"
echo "Number of colors: ${#colors[@]}"

# Array indices
echo "Fruit indices: ${!fruits[@]}"
echo "Color indices: ${!colors[@]}"

# Adding elements
fruits+=("elderberry")
echo "After adding elderberry: ${fruits[@]}"

# Removing elements
unset fruits[1]  # Remove "banana"
echo "After removing banana: ${fruits[@]}"
echo "Indices after removal: ${!fruits[@]}"

echo
echo "=== Associative Arrays ==="

# Declare associative array
declare -A person
person[name]="John Doe"
person[age]=30
person[city]="New York"
person[occupation]="Developer"

# Alternative declaration
declare -A scores=(
    [math]=95
    [english]=87
    [science]=92
)

# Access elements
echo "Name: ${person[name]}"
echo "Age: ${person[age]}"

# Display all key-value pairs
echo "Person details:"
for key in "${!person[@]}"; do
    echo "  $key: ${person[$key]}"
done

# Array operations
echo
echo "=== Array Operations ==="

# Iterate through indexed array
echo "Iterating through fruits:"
for fruit in "${fruits[@]}"; do
    echo "  - $fruit"
done

# Iterate with indices
echo "Fruits with indices:"
for i in "${!fruits[@]}"; do
    echo "  Index $i: ${fruits[$i]}"
done

# Slicing arrays
numbers=(0 1 2 3 4 5 6 7 8 9)
echo "Original numbers: ${numbers[@]}"
echo "Slice [2:5]: ${numbers[@]:2:3}"
echo "From index 5: ${numbers[@]:5}"

# Copying arrays
backup_fruits=("${fruits[@]}")
echo "Backup fruits: ${backup_fruits[@]}"

# Merging arrays
combined=("${fruits[@]}" "${colors[@]}")
echo "Combined arrays: ${combined[@]}"
```

### Variable Expansion

Advanced techniques for working with variables:

```bash
#!/bin/bash
# variable_expansion.sh - Advanced variable expansion techniques

name="John Doe"
filename="/path/to/document.txt"
empty_var=""
unset_var

echo "=== Basic Expansion ==="
echo "Name: $name"
echo "Name with braces: ${name}"

echo
echo "=== Parameter Expansion ==="

# Default values
echo "Unset variable with default: ${unset_var:-'default value'}"
echo "Empty variable with default: ${empty_var:-'default value'}"
echo "Set variable with default: ${name:-'default value'}"

# Assign default if unset
echo "Before assignment: unset_var='$unset_var'"
echo "With assignment: ${unset_var:='assigned default'}"
echo "After assignment: unset_var='$unset_var'"

# Error if unset
# echo "${undefined_var:?'Variable must be set'}"  # Would exit with error

# Alternative value if set
echo "Alternative if set: ${name:+'Name is set'}"
echo "Alternative if unset: ${unset_var2:+'This wont show'}"

echo
echo "=== String Manipulation ==="

# String length
echo "Length of name: ${#name}"

# Substring extraction
echo "First 4 characters: ${name:0:4}"
echo "From position 5: ${name:5}"
echo "Last 3 characters: ${name: -3}"

# Pattern matching and replacement
text="Hello World Hello Universe"
echo "Original: $text"
echo "Replace first 'Hello': ${text/Hello/Hi}"
echo "Replace all 'Hello': ${text//Hello/Hi}"
echo "Replace suffix: ${text/%Universe/Galaxy}"
echo "Replace prefix: ${text/#Hello/Hi}"

# Case conversion (Bash 4.0+)
mixed_case="Hello World"
echo "Original: $mixed_case"
echo "Uppercase: ${mixed_case^^}"
echo "Lowercase: ${mixed_case,,}"
echo "First letter uppercase: ${mixed_case^}"
echo "First letter lowercase: ${mixed_case,}"

# Pattern removal
echo "Filename: $filename"
echo "Directory: ${filename%/*}"
echo "Basename: ${filename##*/}"
echo "Extension: ${filename##*.}"
echo "Name without extension: ${filename%.*}"

# Advanced pattern removal
path="/usr/local/bin/script.sh"
echo "Path: $path"
echo "Remove shortest from end: ${path%/*}"    # /usr/local/bin
echo "Remove longest from end: ${path%%/*}"    # (empty)
echo "Remove shortest from start: ${path#*/}"  # usr/local/bin/script.sh
echo "Remove longest from start: ${path##*/}"  # script.sh
```

### ⚠️ Common Pitfalls

1. **Array Index Confusion**: Remember arrays can be sparse
   ```bash
   arr[0]="first"
   arr[5]="sixth"
   echo ${#arr[@]}  # Returns 2, not 6
   ```

2. **Unquoted Array Expansion**: Always quote array expansions
   ```bash
   # Wrong
   for item in ${array[@]}; do

   # Correct
   for item in "${array[@]}"; do
   ```

3. **Variable Assignment Spacing**: No spaces around the equals sign
   ```bash
   # Wrong
   var = "value"

   # Correct
   var="value"
   ```

4. **Scope Confusion**: Variables are global by default in functions

### ✅ Best Practices

1. **Quote Variables**: Always quote variables to prevent word splitting
2. **Use Meaningful Names**: Choose descriptive variable names
3. **Initialize Variables**: Set default values for important variables
4. **Use Arrays**: Prefer arrays over delimiter-separated strings
5. **Consistent Naming**: Use consistent naming conventions (snake_case recommended)

### 🏋️ Exercise 3: Variable Mastery

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 35 minutes

Create a script called `student_manager.sh` that:
1. Uses an associative array to store student information (name, age, grade, subjects)
2. Implements functions to add, display, and search students
3. Processes command-line arguments to determine the action
4. Uses parameter expansion for input validation
5. Demonstrates different array operations

<details>
<summary>💡 Click to see hints</summary>

- Use `declare -A` for associative arrays
- Store multiple values using delimiters and split them when needed
- Use `$1` for action, `$2+` for parameters
- Parameter expansion: `${var:?error}` for required parameters
- Array operations: adding, searching, displaying all

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# student_manager.sh - Student management system using arrays
# Usage: ./student_manager.sh [add|list|search|help] [parameters...]

# Associative array to store students
declare -A students

#===============================================
# HELPER FUNCTIONS
#===============================================

# Display usage information
show_help() {
    cat << EOF
Student Manager - Usage:
  $0 add <name> <age> <grade> <subjects>
  $0 list
  $0 search <name>
  $0 help

Examples:
  $0 add "John Doe" 20 A "Math,Physics,Chemistry"
  $0 search "John"
  $0 list
EOF
}

# Add a student
add_student() {
    local name="${1:?Name is required}"
    local age="${2:?Age is required}"
    local grade="${3:?Grade is required}"
    local subjects="${4:?Subjects are required}"

    # Validate age is numeric
    if ! [[ "$age" =~ ^[0-9]+$ ]]; then
        echo "Error: Age must be numeric"
        return 1
    fi

    # Store student data (using | as delimiter)
    students["$name"]="$age|$grade|$subjects"
    echo "Student '$name' added successfully"
}

# List all students
list_students() {
    if [ ${#students[@]} -eq 0 ]; then
        echo "No students found"
        return
    fi

    echo "=== Student List ==="
    printf "%-20s %-5s %-7s %s\n" "Name" "Age" "Grade" "Subjects"
    printf "%-20s %-5s %-7s %s\n" "----" "---" "-----" "--------"

    for name in "${!students[@]}"; do
        IFS='|' read -r age grade subjects <<< "${students[$name]}"
        printf "%-20s %-5s %-7s %s\n" "$name" "$age" "$grade" "$subjects"
    done
}

# Search for a student
search_student() {
    local search_name="${1:?Search name is required}"
    local found=false

    echo "=== Search Results for '$search_name' ==="

    for name in "${!students[@]}"; do
        if [[ "$name" == *"$search_name"* ]]; then
            IFS='|' read -r age grade subjects <<< "${students[$name]}"
            echo "Name: $name"
            echo "Age: $age"
            echo "Grade: $grade"
            echo "Subjects: $subjects"
            echo "---"
            found=true
        fi
    done

    if [ "$found" = false ]; then
        echo "No students found matching '$search_name'"
    fi
}

#===============================================
# MAIN PROGRAM
#===============================================

# Load sample data
students["Alice Johnson"]="19|A|Math,Physics,Chemistry"
students["Bob Smith"]="20|B|English,History,Art"
students["Carol Davis"]="18|A|Biology,Chemistry,Math"

# Check command line arguments
if [ $# -eq 0 ]; then
    echo "Error: No action specified"
    show_help
    exit 1
fi

# Process commands
case "$1" in
    add)
        if [ $# -lt 5 ]; then
            echo "Error: Insufficient arguments for add command"
            show_help
            exit 1
        fi
        add_student "$2" "$3" "$4" "$5"
        ;;
    list)
        list_students
        ;;
    search)
        if [ $# -lt 2 ]; then
            echo "Error: Search term required"
            show_help
            exit 1
        fi
        search_student "$2"
        ;;
    help|--help|-h)
        show_help
        ;;
    *)
        echo "Error: Unknown command '$1'"
        show_help
        exit 1
        ;;
esac
```

**Explanation:**
- Uses associative arrays to store structured student data
- Implements parameter expansion with error messages (`${var:?error}`)
- Demonstrates string manipulation with IFS and delimiter splitting
- Provides comprehensive error handling and input validation
- Shows practical use of arrays for data management
- Uses proper function organization and documentation

</details>

---

## 🔄 Control Structures

📊 **Chapter 4 of 13**
🎯 **Learning Objectives:**
- Master conditional statements and logical operators
- Implement various loop constructs effectively
- Use case statements for multi-way branching
- Understand exit status and flow control

⏱️ **Estimated Reading Time:** 30 minutes
📋 **Prerequisites:** Chapters 1-3

### Conditional Statements

Bash provides several ways to implement conditional logic:

```bash
#!/bin/bash
# conditionals.sh - Mastering conditional statements

echo "=== Basic If Statements ==="

# Simple if statement
number=10
if [ $number -gt 5 ]; then
    echo "$number is greater than 5"
fi

# If-else statement
age=18
if [ $age -ge 18 ]; then
    echo "You are an adult"
else
    echo "You are a minor"
fi

# If-elif-else statement
score=85
if [ $score -ge 90 ]; then
    echo "Grade: A"
elif [ $score -ge 80 ]; then
    echo "Grade: B"
elif [ $score -ge 70 ]; then
    echo "Grade: C"
elif [ $score -ge 60 ]; then
    echo "Grade: D"
else
    echo "Grade: F"
fi

echo
echo "=== Test Operators ==="

# Numeric comparisons
num1=10
num2=20
echo "num1=$num1, num2=$num2"

[ $num1 -eq $num2 ] && echo "Equal" || echo "Not equal"
[ $num1 -ne $num2 ] && echo "Not equal" || echo "Equal"
[ $num1 -lt $num2 ] && echo "$num1 less than $num2"
[ $num1 -le $num2 ] && echo "$num1 less than or equal to $num2"
[ $num1 -gt $num2 ] && echo "$num1 greater than $num2" || echo "$num1 not greater than $num2"
[ $num1 -ge $num2 ] && echo "$num1 greater than or equal to $num2" || echo "$num1 not greater than or equal to $num2"

# String comparisons
str1="hello"
str2="world"
str3="hello"

echo
echo "String comparisons:"
[ "$str1" = "$str3" ] && echo "str1 equals str3"
[ "$str1" != "$str2" ] && echo "str1 not equal to str2"
[ "$str1" \< "$str2" ] && echo "str1 lexicographically less than str2"
[ -z "$empty_var" ] && echo "empty_var is empty or unset"
[ -n "$str1" ] && echo "str1 is not empty"

# File tests
echo
echo "File tests:"
test_file="/etc/passwd"
if [ -f "$test_file" ]; then
    echo "$test_file is a regular file"
    [ -r "$test_file" ] && echo "  - Readable"
    [ -w "$test_file" ] && echo "  - Writable" || echo "  - Not writable"
    [ -x "$test_file" ] && echo "  - Executable" || echo "  - Not executable"
fi

# Directory tests
test_dir="/tmp"
if [ -d "$test_dir" ]; then
    echo "$test_dir is a directory"
fi

echo
echo "=== Advanced Conditionals ==="

# Double bracket tests (bash specific)
string="Hello World"
if [[ $string =~ ^Hello ]]; then
    echo "String starts with 'Hello'"
fi

if [[ $string == *"World"* ]]; then
    echo "String contains 'World'"
fi

# Logical operators
user_age=25
has_license=true

if [ $user_age -ge 18 ] && [ "$has_license" = "true" ]; then
    echo "Can drive"
elif [ $user_age -ge 16 ] && [ "$has_license" = "true" ]; then
    echo "Can drive with restrictions"
else
    echo "Cannot drive"
fi

# Compound conditions
if [[ $user_age -ge 18 && "$has_license" == "true" ]]; then
    echo "Eligible for car rental"
fi

# Testing multiple conditions
weather="sunny"
temperature=75

if [[ "$weather" == "sunny" && $temperature -gt 70 ]]; then
    echo "Perfect day for outdoor activities!"
elif [[ "$weather" == "rainy" || $temperature -lt 50 ]]; then
    echo "Better stay indoors"
else
    echo "Decent weather for a walk"
fi
```

### Loops

Bash supports several loop constructs for iteration:

```bash
#!/bin/bash
# loops.sh - Mastering loop constructs

echo "=== For Loops ==="

# Basic for loop with list
echo "Iterating over a list:"
for fruit in apple banana cherry date; do
    echo "  Fruit: $fruit"
done

# For loop with array
fruits=("apple" "banana" "cherry" "date" "elderberry")
echo "Iterating over array:"
for fruit in "${fruits[@]}"; do
    echo "  Fruit: $fruit"
done

# For loop with range (brace expansion)
echo "Numbers 1 to 5:"
for i in {1..5}; do
    echo "  Number: $i"
done

# For loop with step
echo "Even numbers 2 to 10:"
for i in {2..10..2}; do
    echo "  Even: $i"
done

# C-style for loop
echo "C-style loop:"
for ((i=1; i<=5; i++)); do
    echo "  Iteration: $i"
done

# For loop with command substitution
echo "Files in current directory:"
for file in $(ls *.sh 2>/dev/null); do
    echo "  Script: $file"
done

echo
echo "=== While Loops ==="

# Basic while loop
counter=1
echo "While loop counting to 3:"
while [ $counter -le 3 ]; do
    echo "  Counter: $counter"
    ((counter++))
done

# While loop reading file
echo "Reading /etc/passwd (first 3 lines):"
line_count=0
while IFS=: read -r username password uid gid gecos home shell; do
    echo "  User: $username, Shell: $shell"
    ((line_count++))
    [ $line_count -ge 3 ] && break
done < /etc/passwd

# While loop with user input
echo "Enter numbers (0 to stop):"
sum=0
while true; do
    read -p "Number: " num
    if [ "$num" -eq 0 ] 2>/dev/null; then
        break
    elif [[ "$num" =~ ^[0-9]+$ ]]; then
        ((sum += num))
        echo "  Running sum: $sum"
    else
        echo "  Please enter a valid number"
    fi
done
echo "Final sum: $sum"

echo
echo "=== Until Loops ==="

# Until loop (opposite of while)
countdown=5
echo "Countdown using until:"
until [ $countdown -eq 0 ]; do
    echo "  $countdown"
    ((countdown--))
    sleep 1
done
echo "  Blast off!"

echo
echo "=== Loop Control ==="

# Break and continue
echo "Loop control demonstration:"
for i in {1..10}; do
    if [ $i -eq 3 ]; then
        echo "  Skipping $i"
        continue
    fi
    if [ $i -eq 8 ]; then
        echo "  Breaking at $i"
        break
    fi
    echo "  Processing $i"
done

# Nested loops with labeled break
echo "Nested loop with labeled break:"
outer_loop: for i in {1..3}; do
    echo "  Outer loop: $i"
    for j in {1..3}; do
        echo "    Inner loop: $j"
        if [ $i -eq 2 ] && [ $j -eq 2 ]; then
            echo "    Breaking outer loop"
            break 2  # Break out of both loops
        fi
    done
done

echo
echo "=== Advanced Loop Patterns ==="

# Loop with array indices
declare -a colors=("red" "green" "blue" "yellow")
echo "Array with indices:"
for i in "${!colors[@]}"; do
    echo "  Index $i: ${colors[$i]}"
done

# Loop with associative array
declare -A person=(
    [name]="John Doe"
    [age]="30"
    [city]="New York"
    [job]="Developer"
)

echo "Associative array:"
for key in "${!person[@]}"; do
    echo "  $key: ${person[$key]}"
done

# Infinite loop with break condition
echo "Processing files (simulated):"
file_count=0
while true; do
    ((file_count++))
    echo "  Processing file $file_count"

    # Simulate some condition to break
    if [ $file_count -ge 3 ]; then
        echo "  All files processed"
        break
    fi

    sleep 1
done
```

### Case Statements

Case statements provide clean multi-way branching:

```bash
#!/bin/bash
# case_statements.sh - Mastering case statements

echo "=== Basic Case Statement ==="

# Simple case statement
read -p "Enter a day of the week: " day

case "$day" in
    Monday|monday|MONDAY|Mon|mon)
        echo "Start of the work week!"
        ;;
    Tuesday|tuesday|TUESDAY|Tue|tue)
        echo "Tuesday blues"
        ;;
    Wednesday|wednesday|WEDNESDAY|Wed|wed)
        echo "Hump day!"
        ;;
    Thursday|thursday|THURSDAY|Thu|thu)
        echo "Almost there!"
        ;;
    Friday|friday|FRIDAY|Fri|fri)
        echo "TGIF!"
        ;;
    Saturday|saturday|SATURDAY|Sat|sat)
        echo "Weekend fun!"
        ;;
    Sunday|sunday|SUNDAY|Sun|sun)
        echo "Rest day"
        ;;
    *)
        echo "Invalid day: $day"
        ;;
esac

echo
echo "=== Pattern Matching in Case ==="

# Case with patterns
read -p "Enter a filename: " filename

case "$filename" in
    *.txt)
        echo "Text file detected"
        ;;
    *.jpg|*.jpeg|*.png|*.gif)
        echo "Image file detected"
        ;;
    *.sh)
        echo "Shell script detected"
        ;;
    *.py)
        echo "Python script detected"
        ;;
    [0-9]*)
        echo "Filename starts with a number"
        ;;
    [A-Z]*)
        echo "Filename starts with uppercase letter"
        ;;
    *)
        echo "Unknown file type"
        ;;
esac

echo
echo "=== Case Statement for Menu System ==="

# Menu system using case
show_menu() {
    echo "=== System Menu ==="
    echo "1) Show date and time"
    echo "2) Show disk usage"
    echo "3) Show memory usage"
    echo "4) Show running processes"
    echo "5) Exit"
    echo
}

while true; do
    show_menu
    read -p "Choose an option (1-5): " choice

    case "$choice" in
        1)
            echo "Current date and time: $(date)"
            ;;
        2)
            echo "Disk usage:"
            df -h /
            ;;
        3)
            echo "Memory usage:"
            free -h
            ;;
        4)
            echo "Running processes:"
            ps aux | head -10
            ;;
        5)
            echo "Goodbye!"
            break
            ;;
        *)
            echo "Invalid option: $choice"
            ;;
    esac

    echo
    read -p "Press Enter to continue..."
    echo
done

echo
echo "=== Advanced Case Patterns ==="

# Case with complex patterns
test_string="user@example.com"

case "$test_string" in
    *@*.*)
        echo "Looks like an email address"
        ;;
    [0-9][0-9][0-9]-[0-9][0-9][0-9]-[0-9][0-9][0-9][0-9])
        echo "Looks like a phone number (XXX-XXX-XXXX)"
        ;;
    [0-9][0-9][0-9].[0-9][0-9][0-9].[0-9][0-9][0-9].[0-9][0-9][0-9])
        echo "Looks like an IP address"
        ;;
    /*)
        echo "Absolute path"
        ;;
    ./*)
        echo "Relative path starting with ./"
        ;;
    *)
        echo "Unrecognized pattern"
        ;;
esac
```

### Exit Status and Return Values

Understanding how commands and functions return status:

```bash
#!/bin/bash
# exit_status.sh - Working with exit status and return values

echo "=== Understanding Exit Status ==="

# Function that returns different exit codes
check_number() {
    local number=$1

    if [ -z "$number" ]; then
        echo "Error: No number provided"
        return 1
    elif ! [[ "$number" =~ ^[0-9]+$ ]]; then
        echo "Error: Not a valid number"
        return 2
    elif [ "$number" -lt 0 ]; then
        echo "Error: Negative number"
        return 3
    elif [ "$number" -eq 0 ]; then
        echo "Number is zero"
        return 10
    else
        echo "Number is positive: $number"
        return 0
    fi
}

# Test the function with different inputs
test_inputs=("" "abc" "-5" "0" "42")

for input in "${test_inputs[@]}"; do
    echo "Testing input: '$input'"
    check_number "$input"
    exit_code=$?

    case $exit_code in
        0)
            echo "  Success"
            ;;
        1)
            echo "  Error: Missing input"
            ;;
        2)
            echo "  Error: Invalid format"
            ;;
        3)
            echo "  Error: Negative value"
            ;;
        10)
            echo "  Special case: Zero"
            ;;
        *)
            echo "  Unexpected exit code: $exit_code"
            ;;
    esac
    echo
done

echo "=== Using Exit Status in Control Flow ==="

# Using exit status directly in conditionals
if ls /etc > /dev/null 2>&1; then
    echo "/etc directory exists"
else
    echo "/etc directory does not exist"
fi

# Chaining commands based on exit status
mkdir temp_dir && echo "Directory created" || echo "Failed to create directory"

# Complex conditional chaining
if command -v git > /dev/null 2>&1; then
    if git status > /dev/null 2>&1; then
        echo "Git repository detected"
        git status --short
    else
        echo "Git available but not in a repository"
    fi
else
    echo "Git is not installed"
fi

# Clean up
rmdir temp_dir 2>/dev/null

echo
echo "=== Error Handling Patterns ==="

# Function with comprehensive error handling
safe_division() {
    local dividend=$1
    local divisor=$2

    #
 Input validation
    if [ $# -ne 2 ]; then
        echo "Error: Exactly two arguments required" >&2
        return 1
    fi

    if ! [[ "$dividend" =~ ^
[0-9]+$ ]] || ! [[ "$divisor" =~ ^[0-9]+$ ]]; then
        echo
 "Error: Arguments must be positive integers" >&2
        return
 2
    fi

    if
 [ "$divisor" -eq 0 ]; then
        echo "Error: Division by zero" >&2
        return 3
    fi
    
    # Perform calculation
    local result=$((dividend / divisor))
    echo "Result: $result"
    return 0
}

# Test error handling
echo "Testing error handling:"
safe_division 10 2    # Success
safe_division 10 0    # Division by zero
safe_division 10      # Missing argument
safe_division a b     # Invalid arguments

echo
echo "=== Exit Strategies ==="

# Graceful exit function
graceful_exit() {
    local exit_code=${1:-0}
    echo "Cleaning up..."
    # Add cleanup code here
    echo "Exit code: $exit_code"
    exit $exit_code
}

# Trap signals for cleanup
cleanup_on_signal() {
    echo "Signal received, cleaning up..."
    # Cleanup code
    exit 130  # Standard exit code for Ctrl+C
}

trap cleanup_on_signal INT TERM

# Demonstrate different exit scenarios
echo "Script execution complete"
# graceful_exit 0  # Uncomment to test
```

### ⚠️ Common Pitfalls

1. **Missing Spaces in Test Conditions**:
   ```bash
   # Wrong
   if [$var -eq 5]; then
   
   # Correct
   if [ $var -eq 5 ]; then
   ```

2. **String vs Numeric Comparisons**:
   ```bash
   # Wrong for numbers
   if [ "$num1" > "$num2" ]; then  # Lexicographic comparison
   
   # Correct for numbers
   if [ "$num1" -gt "$num2" ]; then
   ```

3. **Unquoted Variables in Tests**:
   ```bash
   # Wrong
   if [ $var = "value" ]; then  # Fails if var is empty
   
   # Correct
   if [ "$var" = "value" ]; then
   ```

4. **Infinite Loops**: Always ensure loop conditions can be met

### ✅ Best Practices

1. **Quote Variables**: Always quote variables in test conditions
2. **Use Double Brackets**: Prefer `[[ ]]` over `[ ]` for advanced features
3. **Check Exit Codes**: Always check return values of important commands
4. **Defensive Programming**: Validate inputs and handle edge cases
5. **Meaningful Exit Codes**: Use descriptive exit codes for different error conditions

### 🏋️ Exercise 4: Control Flow Mastery

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 40 minutes

Create a script called `file_processor.sh` that:
1. Takes a directory path as an argument
2. Validates the directory exists and is accessible
3. Processes different file types with a case statement
4. Uses loops to iterate through files
5. Implements error handling with appropriate exit codes
6. Provides a summary of processed files

<details>
<summary>💡 Click to see hints</summary>

- Use `find` or `for file in directory/*` to iterate through files
- Case statement for file extensions: `*.txt`, `*.jpg`, etc.
- File tests: `-f` (regular file), `-r` (readable), `-s` (non-empty)
- Arrays to collect statistics
- Functions for different file types
- Exit codes: 0 (success), 1 (usage), 2 (directory not found), 3 (permission denied)

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# file_processor.sh - Process files in a directory by type
# Usage: ./file_processor.sh <directory_path>

#===============================================
# GLOBAL VARIABLES
#===============================================

declare -A file_counts
declare -A file_sizes
declare -a processed_files
declare -a error_files

#===============================================
# UTILITY FUNCTIONS
#===============================================

# Display usage information
show_usage() {
    cat << EOF
File Processor - Usage:
  $0 <directory_path>

Description:
  Processes files in the specified directory, categorizing them by type
  and providing statistics about the processing results.

Exit Codes:
  0 - Success
  1 - Invalid usage
  2 - Directory not found
  3 - Permission denied
EOF
}

# Process text files
process_text_file() {
    local file="$1"
    local size=$(stat -c%s "$file" 2>/dev/null || stat -f%z "$file" 2>/dev/null)
    
    file_counts["text"]=$((${file_counts["text"]} + 1))
    file_sizes["text"]=$((${file_sizes["text"]} + size))
    processed_files+=("$file (text)")
    
    echo "  Processing text file: $(basename "$file") (${size} bytes)"
}

# Process image files
process_image_file() {
    local file="$1"
    local size=$(stat -c%s "$file" 2>/dev/null || stat -f%z "$file" 2>/dev/null)
    
    file_counts["image"]=$((${file_counts["image"]} + 1))
    file_sizes["image"]=$((${file_sizes["image"]} + size))
    processed_files+=("$file (image)")
    
    echo "  Processing image file: $(basename "$file") (${size} bytes)"
}

# Process script files
process_script_file() {
    local file="$1"
    local size=$(stat -c%s "$file" 2>/dev/null || stat -f%z "$file" 2>/dev/null)
    
    file_counts["script"]=$((${file_counts["script"]} + 1))
    file_sizes["script"]=$((${file_sizes["script"]} + size))
    processed_files+=("$file (script)")
    
    echo "  Processing script file: $(basename "$file") (${size} bytes)"
    
    # Check if script is executable
    if [ -x "$file" ]; then
        echo "    - Executable"
    else
        echo "    - Not executable"
    fi
}

# Process other files
process_other_file() {
    local file="$1"
    local size=$(stat -c%s "$file" 2>/dev/null || stat -f%z "$file" 2>/dev/null)
    
    file_counts["other"]=$((${file_counts["other"]} + 1))
    file_sizes["other"]=$((${file_sizes["other"]} + size))
    processed_files+=("$file (other)")
    
    echo "  Processing other file: $(basename "$file") (${size} bytes)"
}

# Process a single file based on its type
process_file() {
    local file="$1"
    
    # Skip if not a regular file
    if [ ! -f "$file" ]; then
        return 0
    fi
    
    # Skip if not readable
    if [ ! -r "$file" ]; then
        echo "  Warning: Cannot read $file (permission denied)"
        error_files+=("$file (permission denied)")
        return 1
    fi
    
    # Determine file type and process accordingly
    case "$file" in
        *.txt|*.md|*.rst|*.log)
            process_text_file "$file"
            ;;
        *.jpg|*.jpeg|*.png|*.gif|*.bmp|*.tiff)
            process_image_file "$file"
            ;;
        *.sh|*.bash|*.py|*.pl|*.rb)
            process_script_file "$file"
            ;;
        *)
            process_other_file "$file"
            ;;
    esac
}

# Display processing summary
show_summary() {
    echo
    echo "=== Processing Summary ==="
    
    local total_files=0
    local total_size=0
    
    for type in "${!file_counts[@]}"; do
        local count=${file_counts[$type]}
        local size=${file_sizes[$type]}
        
        if [ "$count" -gt 0 ]; then
            echo "$type files: $count ($(numfmt --to=iec $size))"
            ((total_files += count))
            ((total_size += size))
        fi
    done
    
    echo "Total files processed: $total_files"
    echo "Total size: $(numfmt --to=iec $total_size)"
    
    if [ ${#error_files[@]} -gt 0 ]; then
        echo
        echo "Errors encountered: ${#error_files[@]}"
        for error in "${error_files[@]}"; do
            echo "  - $error"
        done
    fi
}

#===============================================
# INPUT VALIDATION
#===============================================

# Check command line arguments
if [ $# -eq 0 ]; then
    echo "Error: Directory path required"
    show_usage
    exit 1
fi

if [ $# -gt 1 ]; then
    echo "Error: Too many arguments"
    show_usage
    exit 1
fi

directory="$1"

# Validate directory
if [ ! -e "$directory" ]; then
    echo "Error: Directory '$directory' does not exist"
    exit 2
fi

if [ ! -d "$directory" ]; then
    echo "Error: '$directory' is not a directory"
    exit 2
fi

if [ ! -r "$directory" ]; then
    echo "Error: Permission denied accessing '$directory'"
    exit 3
fi

#===============================================
# MAIN PROCESSING
#===============================================

# Initialize counters
file_counts["text"]=0
file_counts["image"]=0
file_counts["script"]=0
file_counts["other"]=0

file_sizes["text"]=0
file_sizes["image"]=0
file_sizes["script"]=0
file_sizes["other"]=0

echo "Processing files in: $directory"
echo

# Process all files in the directory
for file in "$directory"/*; do
    # Skip if glob didn't match anything
    [ ! -e "$file" ] && continue
    
    process_file "$file"
done

# Process subdirectories if any
for subdir in "$directory"/*/; do
    # Skip if no subdirectories
    [ ! -d "$subdir" ] && continue
    
    echo
    echo "Processing subdirectory: $(basename "$subdir")"
    
    for file in "$subdir"*; do
        [ ! -e "$file" ] && continue
        process_file "$file"
    done
done

# Show final summary
show_summary

echo
echo "Processing complete!"
exit 0
```

**Explanation:**
- Demonstrates comprehensive input validation with appropriate exit codes
- Uses associative arrays for statistics collection
- Implements different processing functions for file types
- Shows advanced loop patterns with file iteration
- Provides detailed error handling and reporting
- Uses case statements for file type detection
- Includes proper cleanup and summary reporting

</details>

---

## ⚡ Functions and Scope

📊 **Chapter 5 of 13**
🎯 **Learning Objectives:**
- Define and call functions effectively
- Understand parameter passing and return values
- Master variable scope and local variables
- Implement recursive functions and advanced patterns

⏱️ **Estimated Reading Time:** 25 minutes
📋 **Prerequisites:** Chapters 1-4

### Function Definition

Functions in Bash provide code reusability and organization:

```bash
#!/bin/bash
# functions.sh - Mastering function definition and usage

echo "=== Basic Function Definition ==="

# Method 1: function keyword
function greet() {
    echo "Hello, World!"
}

# Method 2: function name followed by parentheses (preferred)
say_hello() {
    echo "Hello from say_hello function!"
}

# Method 3: POSIX-compliant syntax
goodbye() {
    echo "Goodbye!"
}

# Call the functions
greet
say_hello
goodbye

echo
echo "=== Functions with Parameters ==="

# Function with parameters
greet_person() {
    local name="$1"
    local age="$2"
    
    if [ -z "$name" ]; then
        echo "Error: Name is required"
        return 1
    fi
    
    echo "Hello, $name!"
    
    if [ -n "$age" ]; then
        echo "You are $age years old."
    fi
}

# Function with default parameters
greet_with_default() {
    local name="${1:-Anonymous}"
    local greeting="${2:-Hello}"
    
    echo "$greeting, $name!"
}

# Test parameter functions
echo "Testing parameter functions:"
greet_person "Alice" "25"
greet_person "Bob"
greet_person  # This will show an error

echo
greet_with_default "Charlie" "Hi"
greet_with_default "David"
greet_with_default

echo
echo "=== Function Return Values ==="

# Function that returns a value via echo
calculate_sum() {
    local num1="$1"
    local num2="$2"
    echo $((num1 + num2))
}

# Function that returns exit status
is_even() {
    local number="$1"
    
    if [ $((number % 2)) -eq 0 ]; then
        return 0  # True (even)
    else
        return 1  # False (odd)
    fi
}

# Using function return values
result=$(calculate_sum 15 25)
echo "Sum of 15 and 25: $result"

# Using function exit status
if is_even 10; then
    echo "10 is even"
else
    echo "10 is odd"
fi

if is_even 7; then
    echo "7 is even"
else
    echo "7 is odd"
fi

echo
echo "=== Advanced Function Patterns ==="

# Function with variable number of arguments
print_args() {
    echo "Number of arguments: $#"
    echo "All arguments: $*"
    
    local counter=1
    for arg in "$@"; do
        echo "Argument $counter: $arg"
        ((counter++))
    done
}

print_args "first" "second" "third"

# Function that modifies global variables
counter=0
increment_counter() {
    ((counter++))
    echo "Counter is now: $counter"
}

echo "Initial counter: $counter"
increment_counter
increment_counter
echo "Final counter: $counter"

# Function with array parameters
print_array() {
    local -n array_ref=$1  # Name reference (Bash 4.3+)
    
    echo "Array contents:"
    for element in "${array_ref[@]}"; do
        echo "  - $element"
    done
}

fruits=("apple" "banana" "cherry")
print_array fruits
```

### Function Parameters

Advanced parameter handling techniques:

```bash
#!/bin/bash
# function_parameters.sh - Advanced parameter handling

echo "=== Parameter Validation ==="

# Function with comprehensive parameter validation
validate_user() {
    local username="$1"
    local email="$2"
    local age="$3"
    
    # Check required parameters
    if [ $# -lt 2 ]; then
        echo "Error: Username and email are required"
        echo "Usage: validate_user <username> <email> [age]"
        return 1
    fi
    
    # Validate username
    if [ -z "$username" ] || [[ ! "$username" =~ ^[a-zA-Z][a-zA-Z0-9_]{2,15}$ ]]; then
        echo "Error: Invalid username. Must be 3-16 characters, start with letter"
        return 2
    fi
    
    # Validate email
    if [[ ! "$email" =~ ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$ ]]; then
        echo "Error: Invalid email format"
        return 3
    fi
    
    # Validate age if provided
    if [ -n "$age" ]; then
        if ! [[ "$age" =~ ^[0-9]+$ ]] || [ "$age" -lt 1 ] || [ "$age" -gt 120 ]; then
            echo "Error: Age must be between 1 and 120"
            return 4
        fi
    fi
    
    echo "Valid user: $username ($email)"
    [ -n "$age" ] && echo "Age: $age"
    return 0
}

# Test validation function
echo "Testing user validation:"
validate_user "john_doe" "john@example.com" "30"
validate_user "a" "invalid-email"
validate_user "valid_user" "user@domain.com"

echo
echo "=== Named Parameters Pattern ==="

# Function using associative array for named parameters
create_user_profile() {
    local -A params
    
    # Parse named parameters
    while [ $# -gt 0 ]; do
        case "$1" in
            --name)
                params[name]="$2"
                shift 2
                ;;
            --email)
                params[email]="$2"
                shift 2
                ;;
            --age)
                params[age]="$2"
                shift 2
                ;;
            --department)
                params[department]="$2"
                shift 2
                ;;
            *)
                echo "Unknown parameter: $1"
                return 1
                ;;
        esac
    done
    
    # Validate required parameters
    if [ -z "${params[name]}" ] || [ -z "${params[email]}" ]; then
        echo "Error: Name and email are required"
        return 1
    fi
    
    # Display profile
    echo "=== User Profile ==="
    echo "Name: ${params[name]}"
    echo "Email: ${params[email]}"
    echo "Age: ${params[age]:-Not specified}"
    echo "Department: ${params[department]:-Not specified}"
}

# Test named parameters
create_user_profile --name "Jane Smith" --email "jane@company.com" --age "28" --department "Engineering"

echo
echo "=== Function Overloading Pattern ==="

# Simulate function overloading based on parameter count
process_data() {
    case $# in
        1)
            process_data_single "$1"
            ;;
        2)
            process_data_pair "$1" "$2"
            ;;
        3)
            process_data_triple "$1" "$2" "$3"
            ;;
        *)
            echo "Error: Unsupported number of parameters: $#"
            return 1
            ;;
    esac
}

process_data_single() {
    echo "Processing single value: $1"
}

process_data_pair() {
    echo "Processing pair: $1 and $2"
}

process_data_triple() {
    echo "Processing triple: $1, $2, and $3"
}

# Test overloading pattern
process_data "single"
process_data "first" "second"
process_data "one" "two" "three"
```

### Local Variables

Understanding variable scope in functions:

```bash
#!/bin/bash
# local_variables.sh - Variable scope in functions

echo "=== Global vs Local Variables ==="

# Global variables
global_var="I am global"
counter=0

# Function without local variables (bad practice)
bad_function() {
    global_var="Modified by bad_function"
    counter=100
    new_var="Created in function"
}

# Function with local variables (good practice)
good_function() {
    local local_var="I am local"
    local global_var="Local override"
    local counter=50
    
    echo "Inside good_function:"
    echo "  local_var: $local_var"
    echo "  global_var (local): $global_var"
    echo "  counter (local): $counter"
}

echo "Before function calls:"
echo "global_var: $global_var"
echo "counter: $counter"

echo
good_function

echo
echo "After good_function (globals unchanged):"
echo "global_var: $global_var"
echo "counter: $counter"

echo
bad_function

echo
echo "After bad_function (globals modified):"
echo "global_var: $global_var"
echo "counter: $counter"
echo "new_var: $new_var"

echo
echo "=== Local Array Variables ==="

# Function with local arrays
array_function() {
    local -a local_array=("local1" "local2" "local3")
    local -A local_assoc_array=(
        [key1]="value1"
        [key2]="value2"
    )
    
    echo "Local indexed array: ${local_array[@]}"
    echo "Local associative array:"
    for key in "${!local_assoc_array[@]}"; do
        echo "  $key: ${local_assoc_array[$key]}"
    done
}

array_function

echo
echo "=== Variable Inheritance ==="

# Demonstrate variable inheritance
parent_var="From parent"

parent_function() {
    local child_var="From child"
    
    echo "In parent_function:"
    echo "  parent_var: $parent_var"
    echo "  child_var: $child_var"
    
    child_function
}

child_function() {
    echo "In child_function:"
    echo "  parent_var: $parent_var"
    echo "  child_var: $child_var"  # This will be empty
}

parent_function

echo
echo "=== Read-only Variables ==="

# Read-only variables in functions
readonly_demo() {
    local -r readonly_var="Cannot be changed"
    echo "readonly_var: $readonly_var"
    
    # This would cause an error:
    # readonly_var="New value"
}

readonly_demo
```

### Recursive Functions

Implementing recursion in Bash:

```bash
#!/bin/bash
# recursive_functions.sh - Recursive function examples

echo "=== Basic Recursion ==="

# Calculate factorial recursively
factorial() {
    local n=$1
    
    # Base case
    if [ "$n" -le 1 ]; then
        echo 1
        return
    fi
    
    # Recursive case
    local prev_result
    prev_result=$(factorial $((n - 1)))
    echo $((n * prev_result))
}

echo "Factorial of 5: $(factorial 5)"
echo "Factorial of 0: $(factorial 0)"
echo "Factorial of 7: $(factorial 7)"

echo
echo "=== Fibonacci Sequence ==="

# Generate Fibonacci number recursively
fibonacci() {
    local n=$1
    
    # Base cases
    if [ "$n" -eq 0 ]; then
        echo 0
        return
    elif [ "$n" -eq 1 ]; then
        echo 1
        return
    fi
    
    # Recursive case
    local fib1 fib2
    fib1=$(fibonacci $((n - 1)))
    fib2=$(fibonacci $((n - 2)))
    echo $((fib1 + fib2))
}

# Generate Fibonacci sequence
echo "Fibonacci sequence (first 10 numbers):"
for i in {0..9}; do
    echo -n "$(fibonacci $i) "
done
echo

echo
echo "=== Directory Tree Traversal ==="

# Recursive directory listing
list_directory_tree() {
    local dir="$1"
    local prefix="${2:-}"
    local max_depth="${3:-5}"  # Prevent infinite recursion
    
    # Safety check
    if [ "$max_depth" -le 0 ]; then
        echo "${prefix}... (max depth reached)"
        return
    fi
    
    # List current directory contents
    for item in "$dir"/*; do
        # Skip if no files match
        [ ! -e "$item" ] && continue
        
        local basename_item
        basename_item=$(basename "$item")
        
        if [ -d "$item" ]; then
            echo "${prefix}📁 $basename_item/"
            list_directory_tree "$item" "$prefix  " $((max_depth - 1))
        else
            echo "${prefix}📄 $basename_item"
        fi
    done
}

# Demonstrate recursive directory listing
echo "Directory tree for /tmp (limited depth):"
list_directory_tree "/tmp" "" 2

echo
echo "=== Optimized Fibonacci with Memoization ==="

# Memoized Fibonacci for better performance
declare -A fib_cache

fibonacci_memo() {
    local n=$1
    
    # Check cache first
    if [ -n "${fib_cache[$n]}" ]; then
        echo "${fib_cache[$n]}"
        return
    fi
    
    # Base cases
    if [ "$n" -eq 0 ]; then
        fib_cache[$n]=0
        echo 0
        return
    elif [ "$n" -eq 1 ]; then
        fib_cache[$n]=1
        echo 1
        return
    fi
    
    # Recursive case with caching
    local fib1 fib2 result
    fib1=$(fibonacci_memo $((n - 1)))
    fib2=$(fibonacci_memo $((n - 2)))
    result=$((fib1 + fib2))
    
    fib_cache[$n]=$result
    echo $result
}

# Compare performance (conceptually - timing would require time command)
echo "Memoized Fibonacci of 15: $(fibonacci_memo 15)"
echo "Cache contents:"
for key in "${!fib_cache[@]}"; do
    echo "  fib($key) = ${fib_cache[$key]}"
done

echo
echo "=== Tail Recursion Example ==="

# Tail-recursive countdown
countdown() {
    local n=$1
    
    if [ "$n" -le 0 ]; then
        echo "🚀 Blast off!"
        return
    fi
    
    echo "$n"
    sleep 0.5
    countdown $((n - 1))
}

echo "Countdown from 5:"
countdown 5
```

### ⚠️ Common Pitfalls

1. **Forgetting Local Variables**: Always use `local` for function variables
   ```bash
   # Wrong
   my_function() {
       var="value"  # This modifies global scope
   }
   
   # Correct
   my_function() {
       local var="value"  # This is local
   }
   ```

2. **Incorrect Return Usage**: `return` sets exit status, not return value
   ```bash
   # Wrong
   get_number() {
       return 42  # This sets exit status, not return value
   }
   
   # Correct
   get_number() {
       echo 42  # This returns the value
   }
   ```

3. **Parameter Quoting**: Always quote parameters that might contain spaces
   ```bash
   # Wrong
   my_function() {
       echo $1  # Fails with "hello world"
   }
   
   # Correct
   my_function() {
       echo "$1"  # Handles spaces correctly
   }
   ```

### ✅ Best Practices

1. **Use Local Variables**: Always declare function variables as local
2. **Parameter Validation**: Validate function parameters
3. **Meaningful Names**: Use descriptive function names
4. **Single Responsibility**: Each function should do one thing well
5. **Documentation**: Add comments explaining function purpose and parameters

### 🏋️ Exercise 5: Function Mastery

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 45 minutes

Create a script called `math_calculator.sh` that implements:
1. A calculator with functions for basic operations (+, -, *, /, %)
2. Advanced functions (factorial, fibonacci, prime checking)
3. Input validation and error handling
4. A menu system using functions
5. Local variables and proper scope management

<details>
<summary>💡 Click to see hints</summary>

- Create separate functions for each operation
- Use local variables for all function variables
- Implement parameter validation in each function
- Use a main menu loop with case statement
- Return appropriate exit codes for error conditions
- Consider using recursion for factorial and fibonacci

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# math_calculator.sh - Advanced calculator with functions
# Usage: ./math_calculator.sh

#===============================================
# BASIC ARITHMETIC FUNCTIONS
#===============================================

add() {
    local num1="$1"
    local num2="$2"
    echo $((num1 + num2))
}

subtract() {
    local num1="$1"
    local num2="$2"
    echo $((num1 - num2))
}

multiply() {
    local num1="$1"
    local num2="$2"
    echo $((num1 * num2))
}

divide() {
    local num1="$1"
    local num2="$2"
    
    if [ "$num2" -eq 0 ]; then
        echo "Error: Division by zero" >&2
        return 1
    fi
    
    echo $((num1 / num2))
}

modulo() {
    local num1="$1"
    local num2="$2"
    
    if [ "$num2" -eq 0 ]; then
        echo "Error: Division by zero in modulo" >&2
        return 1
    fi
    
    echo $((num1 % num2))
}

#===============================================
# ADVANCED MATHEMATICAL FUNCTIONS
#===============================================

factorial() {
    local n="$1"
    
    if [ "$n" -lt 0 ]; then
        echo "Error: Factorial of negative number undefined" >&2
        return 1
    fi
    
    if [ "$n" -le 1 ]; then
        echo 1
        return 0
    fi
    
    local prev_result
    prev_result=$(factorial $((n - 1)))
    echo $((n * prev_result))
}

fibonacci() {
    local n="$1"
    
    if [ "$n" -lt 0 ]; then
        echo "Error: Fibonacci of negative number undefined" >&2
        return 1
    fi
    
    if [ "$n" -eq 0 ]; then
        echo 0
        return 0
    elif [ "$n" -eq 1 ]; then
        echo 1
        return 0
    fi
    
    local fib1 fib2
    fib1=$(fibonacci $((n - 1)))
    fib2=$(fibonacci $((n - 2)))
    echo $((fib1 + fib2))
}

is_prime() {
    local n="$1"
    
    if [ "$n" -lt 2 ]; then
        return 1  # Not prime
    fi
    
    if [ "$n" -eq 2 ]; then
        return 0  # Prime
    fi
    
    if [ $((n % 2)) -eq 0 ]; then
        return 1  # Not prime (even)
    fi
    
    local i
    for ((i = 3; i * i <= n; i += 2)); do
        if [ $((n % i)) -eq 0 ]; then
            return 1  # Not prime
        fi
    done
    
    return 0  # Prime
}

#===============================================
# INPUT VALIDATION FUNCTIONS
#===============================================

validate_number() {
    local input="$1"
    
    if [[ ! "$input" =~ ^-?[0-9]+$ ]]; then
        echo "Error: '$input' is not a valid integer" >&2
        return 1
    fi
    
    return 0
}

get_number() {
    local prompt="$1"
    local number
    
    while true; do
        read -p "$prompt" number
        if validate_number "$number"; then
            echo "$number"
            return 0
        fi
        echo "Please enter a valid integer."
    done
}

#===============================================
# MENU SYSTEM FUNCTIONS
#===============================================

show_main_menu() {
    echo
    echo "=== Math Calculator ==="
    echo "1) Basic Operations"
    echo "2) Advanced Functions"
    echo "3) Prime Number Check"
    echo "4) Exit"
    echo
}

show_basic_menu() {
    echo
    echo "=== Basic Operations ==="
    echo "1) Addition"
    echo "2) Subtraction"
    echo "3) Multiplication"
    echo "4) Division"
    echo "5) Modulo"
    echo "6) Back to main menu"
    echo
}

show_advanced_menu() {
    echo
    echo "=== Advanced Functions ==="
    echo "1) Factorial"
    echo "2) Fibonacci"
    echo "3) Back to main menu"
    echo
}

handle_basic_operations() {
    while true; do
        show_basic_menu
        read -p "Choose an option (1-6): " choice
        
        case "$choice" in
            1)
                local num1 num2 result
                num1=$(get_number "Enter first number: ")
                num2=$(get_number "Enter second number: ")
                result=$(add "$num1" "$num2")
                echo "Result: $num1 + $num2 = $result"
                ;;
            2)
                local num1 num2 result
                num1=$(get_number "Enter first number: ")
                num2=$(get_number "Enter second number: ")
                result=$(subtract "$num1" "$num2")
                echo "Result: $num1 - $num2 = $result"
                ;;
            3)
                local num1 num2 result
                num1=$(get_number "Enter first number: ")
                num2=$(get_number "Enter second number: ")
                result=$(multiply "$num1" "$num2")
                echo "Result: $num1 * $num2 = $result"
                ;;
            4)
                local num1 num2 result
                num1=$(get_number "Enter dividend: ")
                num2=$(get_number "Enter divisor: ")
                if result=$(divide "$num1" "$num2"); then
                    echo "Result: $num1 / $num2 = $result"
                fi
                ;;
            5)
                local num1 num2 result
                num1=$(get_number "Enter dividend: ")
                num2=$(get_number "Enter divisor: ")
                if result=$(modulo "$num1" "$num2"); then
                    echo "Result: $num1 % $num2 = $result"
                fi
                ;;
            6)
                return 0
                ;;
            *)
                echo "Invalid option. Please choose 1-6."
                ;;
        esac
        
        echo
        read -p "Press Enter to continue..."
    done
}

handle_advanced_operations() {
    while true; do
        show_advanced_menu
        read -p "Choose an option (1-3): " choice
        
        case "$choice" in
            1)
                local num result
                num=$(get_number "Enter a number: ")
                if result=$(factorial "$num"); then
                    echo "Result: $num! = $result"
                fi
                ;;
            2)
                local num result
                num=$(get_number "Enter a number: ")
                if result=$(fibonacci "$num"); then
                    echo "Result: fibonacci($num) = $result"
                fi
                ;;
            3)
                return 0
                ;;
            *)
                echo "Invalid option. Please choose 1-3."
                ;;
        esac
        
        echo
        read -p "Press Enter to continue..."
    done
}

handle_prime_check() {
    local num
    num=$(get_number "Enter a number to check: ")
    
    if is_prime "$num"; then
        echo "$num is a prime number"
    else
        echo "$num is not a prime number"
    fi
    
    echo
    read -p "Press Enter to continue..."
}

#===============================================
# MAIN PROGRAM
#===============================================

main() {
    echo "Welcome to the Math Calculator!"
    
    while true; do
        show_main_menu
        read -p "Choose an option (1-4): " choice
        
        case "$choice" in
            1)
                handle_basic_operations
                ;;
            2)
                handle_advanced_operations
                ;;
            3)
                handle_prime_check
                ;;
            4)
                echo "Thank you for using Math Calculator!"
                exit 0
                ;;
            *)
                echo "Invalid option. Please choose 1-4."
                ;;
        esac
    done
}

# Start the program
main "$@"
```

**Explanation:**
- Demonstrates comprehensive function organization with clear separation of concerns
- Uses local variables throughout to maintain proper scope
- Implements robust input validation with dedicated functions
- Shows recursive functions for factorial and fibonacci calculations
- Provides a complete menu system using functions
- Handles errors gracefully with appropriate return codes
- Uses proper parameter passing and return value handling

</details>

---

## 📁 File Operations

📊 **Chapter 6 of 13**
🎯 **Learning Objectives:**
- Master file testing and attribute checking
- Implement file reading and writing operations
- Understand file permissions and manipulation
- Work with directories and file systems

⏱️ **Estimated Reading Time:** 30 minutes
📋 **Prerequisites:** Chapters 1-5

### File Tests

Bash provides comprehensive file testing operators:

```bash
#!/bin/bash
# file_tests.sh - Comprehensive file testing examples

echo "=== Basic File Tests ==="

# Test file for examples
test_file="/etc/passwd"
test_dir="/tmp"
nonexistent_file="/path/to/nowhere"

echo "Testing file: $test_file"

# Existence tests
if [ -e "$test_file" ]; then
    echo "✓ File exists"
else
    echo "✗ File does not exist"
fi

# File type tests
if [ -f "$test_file" ]; then
    echo "✓ Is a regular file"
fi

if [ -d "$test_dir" ]; then
    echo "✓ $test_dir is a directory"
fi

if [ -L "/bin/sh" ]; then
    echo "✓ /bin/sh is a symbolic link"
fi

if [ -b "/dev/sda" ]; then
    echo "✓ /dev/sda is a block device"
fi

if [ -c "/dev/null" ]; then
    echo "✓ /dev/null is a character device"
fi

# Permission tests
echo
echo "=== Permission Tests ==="
if [ -r "$test_file" ]; then
    echo "✓ File is readable"
fi

if [ -w "$test_file" ]; then
    echo "✓ File is writable"
else
    echo "✗ File is not writable"
fi

if [ -x "/bin/ls" ]; then
    echo "✓ /bin/ls is executable"
fi

# Advanced file tests
echo
echo "=== Advanced File Tests ==="

# File size test
if [ -s "$test_file" ]; then
    echo "✓ File is not empty"
fi

# File age comparison
touch newer_file
if [ "$test_file" -ot "newer_file" ]; then
    echo "✓ $test_file is older than newer_file"
fi

if [ "newer_file" -nt "$test_file" ]; then
    echo "✓ newer_file is newer than $test_file"
fi

# Same file test
if [ "$test_file" -ef "$test_file" ]; then
    echo "✓ File is the same as itself"
fi

# Clean up
rm -f newer_file

echo
echo "=== File Testing Function ==="

# Comprehensive file analysis function
analyze_file() {
    local file="$1"
    
    if [ -z "$file" ]; then
        echo "Error: No file specified"
        return 1
    fi
    
    echo "Analyzing: $file"
    echo "===================="
    
    # Existence
    if [ ! -e "$file" ]; then
        echo "✗ File does not exist"
        return 1
    fi
    
    # Type
    if [ -f "$file" ]; then
        echo "Type: Regular file"
    elif [ -d "$file" ]; then
        echo "Type: Directory"
    elif [ -L "$file" ]; then
        echo "Type: Symbolic link"
        echo "Target: $(readlink "$file")"
    elif [ -b "$file" ]; then
        echo "Type: Block device"
    elif [ -c "$file" ]; then
        echo "Type: Character device"
    elif [ -p "$file" ]; then
        echo "Type: Named pipe (FIFO)"
    elif [ -S "$file" ]; then
        echo "Type: Socket"
    fi
    
    # Permissions
    echo -n "Permissions: "
    [ -r "$file" ] && echo -n "r" || echo -n "-"
    [ -w "$file" ] && echo -n "w" || echo -n "-"
    [ -x "$file" ] && echo -n "x" || echo -n "-"
    echo
    
    # Size (for regular files)
    if [ -f "$file" ]; then
        local size
        size=$(stat -c%s "$file" 2>/dev/null || stat -f%z "$file" 2>/dev/null)
        echo "Size: $size bytes"
        
        if [ -s "$file" ]; then
            echo "Status: Non-empty"
        else
            echo "Status: Empty"
        fi
    fi
    
    # Timestamps
    echo "Last modified: $(stat -c%y "$file" 2>/dev/null || stat -f%Sm "$file" 2>/dev/null)"
}

# Test the analysis function
analyze_file "/etc/passwd"
echo
analyze_file "/tmp"
echo
analyze_file "/nonexistent/file"
```

### Reading Files

Various methods for reading file content in Bash:

```bash
#!/bin/bash
# reading_files.sh - File reading techniques

echo "=== Basic File Reading ==="

# Create a test file
cat > test_data.txt << 'EOF'
Line 1: First line
Line 2: Second line with numbers: 123
Line 3: Third line with symbols: @#$%
Line 4: Last line
EOF

echo "Created test file with content:"
cat test_data.txt

echo
echo "=== Reading Methods ==="

# Method 1: Using cat (entire file)
echo "Method 1 - Using cat:"
cat test_data.txt

echo
echo "Method 2 - Using while read loop:"
while IFS= read -r line; do
    echo "Read: $line"
done < test_data.txt

echo
echo "Method 3 - Reading into array:"
mapfile -t lines < test_data.txt
for i in "${!lines[@]}"; do
    echo "Line $((i+1)): ${lines[i]}"
done

echo
echo "Method 4 - Reading with line numbers:"
line_num=1
while IFS= read -r line; do
    printf "%3d: %s\n" "$line_num" "$line"
    ((line_num++))
done < test_data.txt

echo
echo "=== Advanced Reading Techniques ==="

# Reading CSV-like data
cat > data.csv << 'EOF'
Name,Age,City,Occupation
John Doe,30,New York,Developer
Jane Smith,25,Los Angeles,Designer
Bob Johnson,35,Chicago,Manager
EOF

echo "Reading CSV data:"
{
    # Read header
    IFS=',' read -r name_h age_h city_h occupation_h
    echo "Headers: $name_h | $age_h | $city_h | $occupation_h"
    echo "----------------------------------------"
    
    # Read data rows
    while IFS=',' read -r name age city occupation; do
        printf "%-12s %-3s %-12s %s\n" "$name" "$age" "$city" "$occupation"
    done
} < data.csv

echo
echo "=== Reading Configuration Files ==="

# Create a config file
cat > app.config << 'EOF'
# Application Configuration
database_host=localhost
database_port=5432
database_name=myapp
debug_mode=true
max_connections=100

# Server settings
server_port=8080
server_host=0.0.0.0
EOF

echo "Reading configuration file:"
declare -A config

while IFS= read -r line; do
    # Skip comments and empty lines
    [[ "$line" =~ ^[[:space:]]*# ]] && continue
    [[ "$line" =~ ^[[:space:]]*$ ]] && continue
    
    # Parse key=value pairs
    if [[ "$line" =~ ^([^=]+)=(.*)$ ]]; then
        key="${BASH_REMATCH[1]}"
        value="${BASH_REMATCH[2]}"
        config["$key"]="$value"
        echo "Config: $key = $value"
    fi
done < app.config

echo
echo "Accessing configuration values:"
echo "Database: ${config[database_host]}:${config[database_port]}/${config[database_name]}"
echo "Debug mode: ${config[debug_mode]}"

echo
echo "=== Reading Large Files Efficiently ==="

# Reading file in chunks
read_file_chunks() {
    local file="$1"
    local chunk_size="${2:-1024}"
    local total_bytes=0
    local chunk
    
    while IFS= read -r -n "$chunk_size" chunk; do
        total_bytes=$((total_bytes + ${#chunk}))
        echo "Read chunk of ${#chunk} bytes"
    done < "$file"
    
    echo "Total bytes read: $total_bytes"
}

echo "Reading in chunks:"
read_file_chunks "test_data.txt" 20

# Clean up
rm -f test_data.txt data.csv app.config
```

### Writing Files

Techniques for writing and modifying files:

```bash
#!/bin/bash
# writing_files.sh - File writing techniques

echo "=== Basic File Writing ==="

# Method 1: Simple redirection
echo "Hello, World!" > simple_output.txt
echo "Content written to simple_output.txt:"
cat simple_output.txt

# Method 2: Appending to files
echo "First line" > append_test.txt
echo "Second line" >> append_test.txt
echo "Third line" >> append_test.txt

echo
echo "Appended content:"
cat append_test.txt

# Method 3: Here document
cat > here_document.txt << 'EOF'
This is a here document.
It can contain multiple lines.
Variables like $HOME will not be expanded in single quotes.
Special characters: @#$%^&*()
EOF

echo
echo "Here document content:"
cat here_document.txt

# Method 4: Here document with variable expansion
name="John Doe"
age=30
cat > variable_expansion.txt << EOF
User Information:
Name: $name
Age: $age
Home: $HOME
Date: $(date)
EOF

echo
echo "Here document with variables:"
cat variable_expansion.txt

echo
echo "=== Advanced Writing Techniques ==="

# Writing arrays to files
fruits=("apple" "banana" "cherry" "date")
echo "Writing array to file:"
printf "%s\n" "${fruits[@]}" > fruits.txt
cat fruits.txt

# Writing associative arrays
declare -A person=(
    [name]="Jane Smith"
    [age]=28
    [city]="Boston"
    [job]="Engineer"
)

echo
echo "Writing associative array:"
for key in "${!person[@]}"; do
    echo "$key=${person[$key]}"
done > person.txt
cat person.txt

echo
echo "=== File Modification ==="

# Create a file to modify
cat > modify_me.txt << 'EOF'
Line 1: Original content
Line 2: This will be changed
Line 3: Original content
Line 4: This will be changed
Line 5: Original content
EOF

echo "Original file:"
cat modify_me.txt

# Method 1: In-place editing with sed
sed -i 's/This will be changed/This has been modified/g' modify_me.txt

echo
echo "After sed modification:"
cat modify_me.txt

# Method 2: Line-by-line modification
echo
echo "Line-by-line modification:"
{
    line_num=1
    while IFS= read -r line; do
        if [ $((line_num % 2)) -eq 0 ]; then
            echo "$line [EVEN LINE MARKED]"
        else
            echo "$line"
        fi
        ((line_num++))
    done < modify_me.txt
} > modified_output.txt

cat modified_output.txt

echo
echo "=== Secure File Writing ==="

# Writing with proper permissions
write_secure_file() {
    local filename="$1"
    local content="$2"
    local permissions="${3:-600}"
    
    # Create file with restrictive permissions
    touch "$filename"
    chmod "$permissions" "$filename"
    
    # Write content
    echo "$content" > "$filename"
    
    echo "Secure file created: $filename"
    ls -la "$filename"
}

write_secure_file "secure.txt" "Sensitive information" "600"

echo
echo "=== Atomic File Writing ==="

# Atomic file writing (write to temp, then move)
write_atomic() {
    local target_file="$1"
    local content="$2"
    local temp_file="${target_file}.tmp.$$"
    
    # Write to temporary file
    if echo "$content" > "$temp_file"; then
        # Move to final location (atomic operation)
        mv "$temp_file" "$target_file"
        echo "Atomically wrote to $target_file"
    else
        # Clean up on failure
        rm -f "$temp_file"
        echo "Failed to write to $target_file"
        return 1
    fi
}

write_atomic "atomic_file.txt" "This was written atomically"
cat atomic_file.txt

echo
echo "=== Backup and Write ==="

# Create backup before writing
backup_and_write() {
    local file="$1"
    local new_content="$2"
    
    # Create backup if file exists
    if [ -f "$file" ]; then
        cp "$file" "${file}.backup.$(date +%Y%m%d_%H%M%S)"
        echo "Backup created: ${file}.backup.*"
    fi
    
    # Write new content
    echo "$new_content" > "$file"
    echo "New content written to $file"
}

echo "Original content" > backup_test.txt
backup_and_write "backup_test.txt" "New content after backup"

echo "Files created:"
ls -la backup_test.txt*

# Clean up
rm -f simple_output.txt append_test.txt here_document.txt variable_expansion.txt
rm -f fruits.txt person.txt modify_me.txt modified_output.txt
rm -f secure.txt atomic_file.txt backup_test.txt*
```

### File Manipulation

Advanced file manipulation operations:

```bash
#!/bin/bash
# file_manipulation.sh - Advanced file operations

echo "=== File Copying and Moving ==="

# Create test directory structure
mkdir -p test_files/{src,dest,backup}

# Create test files
for i in {1..5}; do
    echo "Content of file $i" > "test_files/src/file$i.txt"
done

echo "Created test files:"
ls -la test_files/src/

# Safe copy function
safe_copy() {
    local source="$1"
    local destination="$2"
    
    if [ ! -f "$source" ]; then
        echo "Error: Source file '$source' does not exist"
        return 1
    fi
    
    if [ -f "$destination" ]; then
        echo -n "Destination '$destination' exists. Overwrite? (y/n): "
        read -r response
        if [[ ! "$response" =~ ^[Yy] ]]; then
            echo "Copy cancelled"
            return 1
        fi
    fi
    
    if cp "$source" "$destination"; then
        echo "Successfully copied '$source' to '$destination'"
        return 0
    else
        echo "Failed to copy '$source' to '$destination'"
        return 1
    fi
}

# Test safe copy
echo
echo "Testing safe copy:"
safe_copy "test_files/src/file1.txt" "test_files/dest/file1.txt"

echo
echo "=== Bulk File Operations ==="

# Bulk rename function
bulk_rename() {
    local directory="$1"
    local old_pattern="$2"
    local new_pattern="$3"
    
    if [ ! -d "$directory" ]; then
        echo "Error: Directory '$directory' does not exist"
        return 1
    fi
    
    local count=0
    for file in "$directory"/*"$old_pattern"*; do
        [ ! -f "$file" ] && continue
        
        local basename_file
        basename_file=$(basename "$file")
        local new_name="${basename_file/$old_pattern/$new_pattern}"
        local new_path="$directory/$new_name"
        
        if mv "$file" "$new_path"; then
            echo "Renamed: $basename_file -> $new_name"
            ((count++))
        else
            echo "Failed to rename: $basename_file"
        fi
    done
    
    echo "Renamed $count files"
}

# Test bulk rename
echo
echo "Testing bulk rename:"
bulk_rename "test_files/src" "file" "document"

echo "Files after rename:"
ls -la test_files/src/

echo
echo "=== File Synchronization ==="

# Simple sync function
sync_directories() {
    local source_dir="$1"
    local dest_dir="$2"
    local backup_dir="${3:-}"
    
    if [ ! -d "$source_dir" ]; then
        echo "Error: Source directory does not exist"
        return 1
    fi
    
    mkdir -p "$dest_dir"
    [ -n "$backup_dir" ] && mkdir -p "$backup_dir"
    
    echo "Synchronizing $source_dir -> $dest_dir"
    
    for source_file in "$source_dir"/*; do
        [ ! -f "$source_file" ] && continue
        
        local filename
        filename=$(basename "$source_file")
        local dest_file="$dest_dir/$filename"
        local backup_file="$backup_dir/$filename.backup"
        
        # Check if destination exists and is different
        if [ -f "$dest_file" ]; then
            if ! cmp -s "$source_file" "$dest_file"; then
                echo "File differs: $filename"
                
                # Create backup if backup directory specified
                if [ -n "$backup_dir" ]; then
                    cp "$dest_file" "$backup_file"
                    echo "  Backup created: $backup_file"
                fi
                
                cp "$source_file" "$dest_file"
                echo "  Updated: $filename"
            else
                echo "File unchanged: $filename"
            fi
        else
            cp "$source_file" "$dest_file"
            echo "File copied: $filename"
        fi
    done
}

# Test synchronization
echo
sync_directories "test_files/src" "test_files/dest" "test_files/backup"

echo
echo "=== File Cleanup Operations ==="

# Find and remove empty files
cleanup_empty_files() {
    local directory="$1"
    local dry_run="${2:-false}"
    
    echo "Searching for empty files in: $directory"
    
    local count=0
    while IFS= read -r -d '' file; do
        if [ "$dry_run" = "true" ]; then
            echo "Would remove empty file: $file"
        else
            rm "$file"
            echo "Removed empty file: $file"
        fi
        ((count++))
    done < <(find "$directory" -type f -empty -print0)
    
    echo "Found $count empty files"
}

# Create some empty files for testing
touch test_files/src/empty1.txt test_files/src/empty2.txt

echo
echo "Before cleanup:"
ls -la test_files/src/

cleanup_empty_files "test_files/src" "false"

echo
echo "After cleanup:"
ls -la test_files/src/

echo
echo "=== File Archiving ==="

# Create archive function
create_archive() {
    local source_dir="$1"
    local archive_name="${2:-archive_$(date +%Y%m%d_%H%M%S).tar.gz}"
    local exclude_pattern="${3:-}"
    
    echo "Creating archive: $archive_name"
    
    local tar_opts="-czf $archive_name"
    
    if [ -n "$exclude_pattern" ]; then
        tar_opts="$tar_opts --exclude=$exclude_pattern"
        echo "Excluding pattern: $exclude_pattern"
    fi
    
    if tar $tar_opts "$source_dir"; then
        echo "Archive created successfully"
        echo "Archive size: $(stat -c%s "$archive_name" 2>/dev/null || stat -f%z "$archive_name" 2>/dev/null) bytes"
        return 0
    else
        echo "Failed to create archive"
        return 1
    fi
}

# Test archiving
echo
create_archive "test_files" "test_backup.tar.gz" "*.backup"

echo "Archive contents:"
tar -tzf test_backup.tar.gz | head -10

# Clean up
rm -rf test_files test_backup.tar.gz
```

### ⚠️ Common Pitfalls

1. **Overwriting Files**: Always check if destination exists before copying
2. **Permission Issues**: Ensure proper permissions for file operations
3. **Race Conditions**: Use atomic operations for critical file updates
4. **Missing Backups**: Always backup important files before modification

### ✅ Best Practices

1. **Validate Inputs**: Check file existence and permissions before operations
2. **Error Handling**: Always check return codes of file operations
3. **Atomic Operations**: Use temporary files for critical updates
4. **Proper Permissions**: Set appropriate file permissions for security

### 🏋️ Exercise 6: File Management System

**Difficulty:** 🟡 Intermediate  
**Estimated Time:** 40 minutes

Create a script called `file_manager.sh` that implements:
1. File backup with timestamp
2. File integrity checking using checksums
3. Batch file operations (rename, copy, move)
4. File cleanup based on age or size
5. Directory synchronization

<details>
<summary>💡 Click to see hints</summary>

- Use `md5sum` or `sha256sum` for checksums
- `find` command for age-based cleanup
- `stat` for file information
- Atomic operations with temporary files
- Progress indicators for batch operations

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# file_manager.sh - Comprehensive file management system

#===============================================
# GLOBAL VARIABLES
#===============================================

declare -A checksums
backup_dir="$HOME/.file_manager_backups"
log_file="$HOME/.file_manager.log"

#===============================================
# UTILITY FUNCTIONS
#===============================================

log_message() {
    local message="$1"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    echo "[$timestamp] $message" | tee -a "$log_file"
}

show_progress() {
    local current=$1
    local total=$2
    local percent=$((current * 100 / total))
    printf "\rProgress: [%3d%%] %d/%d" "$percent" "$current" "$total"
}

#===============================================
# FILE BACKUP FUNCTIONS
#===============================================

create_backup() {
    local source_file="$1"
    local backup_name="${2:-}"
    
    if [ ! -f "$source_file" ]; then
        echo "Error: Source file does not exist: $source_file"
        return 1
    fi
    
    mkdir -p "$backup_dir"
    
    local filename=$(basename "$source_file")
    local timestamp=$(date '+%Y%m%d_%H%M%S')
    
    if [ -z "$backup_name" ]; then
        backup_name="${filename}.backup.${timestamp}"
    fi
    
    local backup_path="$backup_dir/$backup_name"
    
    if cp "$source_file" "$backup_path"; then
        log_message "Backup created: $backup_path"
        echo "$backup_path"
        return 0
    else
        log_message "Backup failed: $source_file"
        return 1
    fi
}

#===============================================
# INTEGRITY CHECKING
#===============================================

calculate_checksum() {
    local file="$1"
    if command -v sha256sum >/dev/null 2>&1; then
        sha256sum "$file" | cut -d' ' -f1
    elif command -v md5sum >/dev/null 2>&1; then
        md5sum "$file" | cut -d' ' -f1
    else
        echo "Error: No checksum utility available"
        return 1
    fi
}

verify_integrity() {
    local file="$1"
    local stored_checksum="$2"
    
    if [ ! -f "$file" ]; then
        echo "File not found: $file"
        return 1
    fi
    
    local current_checksum
    current_checksum=$(calculate_checksum "$file")
    
    if [ "$current_checksum" = "$stored_checksum" ]; then
        echo "✓ Integrity verified: $file"
        return 0
    else
        echo "✗ Integrity check failed: $file"
        echo "  Expected: $stored_checksum"
        echo "  Current:  $current_checksum"
        return 1
    fi
}

#===============================================
# BATCH OPERATIONS
#===============================================

batch_rename() {
    local directory="$1"
    local pattern="$2"
    local replacement="$3"
    
    if [ ! -d "$directory" ]; then
        echo "Error: Directory does not exist: $directory"
        return 1
    fi
    
    local files=("$directory"/*"$pattern"*)
    local total=${#files[@]}
    local current=0
    local success=0
    
    for file in "${files[@]}"; do
        ((current++))
        show_progress "$current" "$total"
        
        [ ! -f "$file" ] && continue
        
        local basename_file=$(basename "$file")
        local new_name="${basename_file/$pattern/$replacement}"
        local new_path="$directory/$new_name"
        
        if [ "$basename_file" != "$new_name" ]; then
            if mv "$file" "$new_path" 2>/dev/null; then
                ((success++))
            fi
        fi
    done
    
    echo
    log_message "Batch rename completed: $success/$total files renamed"
}

#===============================================
# CLEANUP FUNCTIONS
#===============================================

cleanup_old_files() {
    local directory="$1"
    local days_old="${2:-30}"
    local dry_run="${3:-false}"
    
    if [ ! -d "$directory" ]; then
        echo "Error: Directory does not exist: $directory"
        return 1
    fi
    
    local count=0
    echo "Searching for files older than $days_old days in: $directory"
    
    while IFS= read -r -d '' file; do
        if [ "$dry_run" = "true" ]; then
            echo "Would remove: $file"
        else
            if rm "$file" 2>/dev/null; then
                log_message "Removed old file: $file"
            fi
        fi
        ((count++))
    done < <(find "$directory" -type f -mtime +$days_old -print0)
    
    echo "Found $count files older than $days_old days"
}

#===============================================
# MAIN MENU SYSTEM
#===============================================

show_menu() {
    echo
    echo "=== File Manager ==="
    echo "1) Create backup"
    echo "2) Verify file integrity"
    echo "3) Batch rename"
    echo "4) Cleanup old files"
    echo "5) Show statistics"
    echo "6) Exit"
    echo
}

handle_backup() {
    read -p "Enter file path to backup: " file_path
    if [ -f "$file_path" ]; then
        backup_path=$(create_backup "$file_path")
        if [ $? -eq 0 ]; then
            local checksum
            checksum=$(calculate_checksum "$file_path")
            checksums["$file_path"]="$checksum"
            echo "Backup created: $backup_path"
            echo "Checksum stored for integrity verification"
        fi
    else
        echo "File not found: $file_path"
    fi
}

handle_integrity() {
    read -p "Enter file path to verify: " file_path
    if [ -n "${checksums[$file_path]}" ]; then
        verify_integrity "$file_path" "${checksums[$file_path]}"
    else
        echo "No stored checksum found for: $file_path"
        echo "Calculate new checksum? (y/n): "
        read response
        if [[ "$response" =~ ^[Yy] ]]; then
            local checksum
            checksum=$(calculate_checksum "$file_path")
            checksums["$file_path"]="$checksum"
            echo "Checksum calculated and stored: $checksum"
        fi
    fi
}

main() {
    log_message "File Manager started"
    
    while true; do
        show_menu
        read -p "Choose option (1-6): " choice
        
        case "$choice" in
            1) handle_backup ;;
            2) handle_integrity ;;
            3)
                read -p "Directory: " dir
                read -p "Pattern to replace: " pattern
                read -p "Replacement: " replacement
                batch_rename "$dir" "$pattern" "$replacement"
                ;;
            4)
                read -p "Directory: " dir
                read -p "Days old (default 30): " days
                days=${days:-30}
                read -p "Dry run? (y/n): " dry_run
                [[ "$dry_run" =~ ^[Yy] ]] && dry_run="true" || dry_run="false"
                cleanup_old_files "$dir" "$days" "$dry_run"
                ;;
            5)
                echo "Backup directory: $backup_dir"
                echo "Log file: $log_file"
                echo "Stored checksums: ${#checksums[@]}"
                if [ -d "$backup_dir" ]; then
                    echo "Backup files: $(find "$backup_dir" -type f | wc -l)"
                fi
                ;;
            6)
                log_message "File Manager exited"
                echo "Goodbye!"
                exit 0
                ;;
            *)
                echo "Invalid option"
                ;;
        esac
        
        echo
        read -p "Press Enter to continue..."
    done
}

main "$@"
```

**Explanation:**
- Implements comprehensive file management with backup, integrity checking, and batch operations
- Uses checksums for file integrity verification
- Provides progress indicators for batch operations
- Includes logging and error handling throughout
- Demonstrates real-world file management patterns

</details>

---

## 🔧 Input/Output and Redirection

📊 **Chapter 7 of 13**
🎯 **Learning Objectives:**
- Master input/output redirection techniques
- Understand standard streams (stdin, stdout, stderr)
- Implement pipes and filters effectively
- Work with here documents and here strings

⏱️ **Estimated Reading Time:** 25 minutes
📋 **Prerequisites:** Chapters 1-6

### Standard Streams

Understanding the three standard streams in Unix-like systems:

```bash
#!/bin/bash
# standard_streams.sh - Working with standard streams

echo "=== Understanding Standard Streams ==="

echo "This goes to stdout (file descriptor 1)"
echo "This also goes to stdout" >&1  # Explicit stdout

# Writing to stderr
echo "This goes to stderr" >&2
echo "Error message" 1>&2  # Alternative syntax

# Reading from stdin
echo "=== Reading from Standard Input ==="
echo "Enter your name:"
read name < /dev/stdin  # Explicit stdin
echo "Hello, $name!"

echo
echo "=== Stream Redirection Examples ==="

# Redirect stdout to file
echo "This goes to a file" > output.txt
echo "Content of output.txt:"
cat output.txt

# Redirect stderr to file
ls /nonexistent/directory 2> error.txt
echo "Content of error.txt:"
cat error.txt

# Redirect both stdout and stderr
echo "Both streams" > both.txt 2>&1
ls /nonexistent/directory >> both.txt 2>&1
echo "Content of both.txt:"
cat both.txt

echo
echo "=== Advanced Stream Handling ==="

# Function that uses different streams
stream_demo() {
    echo "Normal output to stdout"
    echo "Error message to stderr" >&2
    echo "Debug info to stderr" >&2
    return 0
}

echo "Calling function with stream separation:"
stream_demo > stdout.txt 2> stderr.txt

echo "Stdout content:"
cat stdout.txt

echo "Stderr content:"
cat stderr.txt

# Clean up
rm -f output.txt error.txt both.txt stdout.txt stderr.txt
```

### Redirection Operators

Comprehensive guide to redirection operators:

```bash
#!/bin/bash
# redirection_operators.sh - Mastering redirection

echo "=== Basic Redirection Operators ==="

# Output redirection
echo "Overwrite file" > test_file.txt
echo "Append to file" >> test_file.txt
echo "Content of test_file.txt:"
cat test_file.txt

echo
echo "=== Advanced Redirection ==="

# Here document
cat << EOF > here_doc.txt
This is a here document.
It can contain multiple lines.
Variables are expanded: $USER
Command substitution works: $(date)
EOF

echo "Here document content:"
cat here_doc.txt

# Here string
cat <<< "This is a here string" > here_string.txt
echo "Here string content:"
cat here_string.txt

echo
echo "=== Error Redirection ==="

# Separate stdout and stderr
{
    echo "This is stdout"
    echo "This is stderr" >&2
    ls /nonexistent 2>/dev/null || echo "Command failed" >&2
} > output.log 2> error.log

echo "Output log:"
cat output.log

echo "Error log:"
cat error.log

echo
echo "=== Combining Streams ==="

# Redirect stderr to stdout
ls /etc /nonexistent 2>&1 | grep "Permission denied" || echo "No permission errors"

# Redirect stdout to stderr
echo "This goes to stderr" 1>&2

# Discard output
ls /etc > /dev/null 2>&1
echo "Directory listing sent to /dev/null"

echo
echo "=== File Descriptor Manipulation ==="

# Using custom file descriptors
exec 3> custom_fd.txt  # Open FD 3 for writing
echo "Writing to custom file descriptor" >&3
exec 3>&-  # Close FD 3

echo "Custom FD content:"
cat custom_fd.txt

# Reading with custom file descriptor
exec 4< /etc/passwd
echo "Reading first line from custom FD:"
read -u 4 first_line
echo "First line: $first_line"
exec 4<&-  # Close FD 4

echo
echo "=== Process Substitution ==="

# Process substitution for reading
while read line; do
    echo "Line: $line"
done < <(echo -e "Line 1\nLine 2\nLine 3")

# Process substitution for writing
echo "Process substitution result:" > >(cat > proc_sub.txt)
echo "Content written via process substitution:"
cat proc_sub.txt

# Clean up
rm -f test_file.txt here_doc.txt here_string.txt output.log error.log
rm -f custom_fd.txt proc_sub.txt
```

### Pipes and Filters

Using pipes to connect commands:

```bash
#!/bin/bash
# pipes_filters.sh - Mastering pipes and filters

echo "=== Basic Pipes ==="

# Simple pipe
echo "apple banana cherry date" | tr ' ' '\n' | sort
echo

# Chain multiple commands
ps aux | grep bash | awk '{print $2, $11}' | head -5

echo
echo "=== Advanced Pipe Patterns ==="

# Tee command - split output
echo "This goes to both file and stdout" | tee output.txt
echo "File contains:"
cat output.txt

# Multiple tees
echo "Multiple outputs" | tee file1.txt | tee file2.txt | cat
echo "Files created: file1.txt, file2.txt"

echo
echo "=== Named Pipes (FIFOs) ==="

# Create named pipe
mkfifo mypipe

# Background process writing to pipe
{
    for i in {1..5}; do
        echo "Message $i: $(date)"
        sleep 1
    done
} > mypipe &

# Read from pipe
echo "Reading from named pipe:"
while read line; do
    echo "Received: $line"
done < mypipe

# Clean up named pipe
rm -f mypipe

echo
echo "=== Filter Examples ==="

# Create sample data
cat > data.txt << 'EOF'
John,25,Engineer,New York
Jane,30,Designer,Los Angeles  
Bob,22,Student,Chicago
Alice,28,Manager,Boston
Charlie,35,Developer,Seattle
EOF

echo "Sample data:"
cat data.txt

echo
echo "Filtered results:"

# Filter and format data
echo "Engineers and Developers:"
cat data.txt | grep -E "(Engineer|Developer)" | cut -d',' -f1,3,4

echo
echo "People over 25:"
cat data.txt | awk -F',' '$2 > 25 {print $1 " (" $2 " years old) - " $4}'

echo
echo "Sorted by age:"
cat data.txt | sort -t',' -k2 -n | awk -F',' '{print $1, $2}'

echo
echo "=== Complex Pipeline Example ==="

# Log analysis simulation
cat > access.log << 'EOF'
192.168.1.1 - - [01/Jan/2024:10:00:01 +0000] "GET /index.html HTTP/1.1" 200 1024
192.168.1.2 - - [01/Jan/2024:10:00:02 +0000] "GET /about.html HTTP/1.1" 200 2048
192.168.1.1 - - [01/Jan/2024:10:00:03 +0000] "POST /login HTTP/1.1" 401 512
192.168.1.3 - - [01/Jan/2024:10:00:04 +0000] "GET /index.html HTTP/1.1" 200 1024
192.168.1.2 - - [01/Jan/2024:10:00:05 +0000] "GET /contact.html HTTP/1.1" 404 256
EOF

echo "Access log analysis:"
echo "Top IPs by request count:"
cat access.log | \
    awk '{print $1}' | \
    sort | \
    uniq -c | \
    sort -nr | \
    head -3

echo
echo "Error responses (4xx, 5xx):"
cat access.log | \
    awk '$9 >= 400 {print $1, $7, $9}' | \
    column -t

# Clean up
rm -f output.txt file1.txt file2.txt data.txt access.log
```

### Here Documents

Advanced here document usage:

```bash
#!/bin/bash
# here_documents.sh - Mastering here documents

echo "=== Basic Here Documents ==="

# Simple here document
cat << 'EOF'
This is a basic here document.
No variable expansion occurs.
$HOME remains literal.
EOF

echo
# Here document with variable expansion
name="John Doe"
cat << EOF
This here document expands variables.
User: $name
Home: $HOME
Date: $(date)
EOF

echo
echo "=== Here Documents in Functions ==="

generate_config() {
    local app_name="$1"
    local port="$2"
    local debug="${3:-false}"
    
    cat << EOF
# Configuration for $app_name
app_name=$app_name
server_port=$port
debug_mode=$debug
log_file=/var/log/${app_name}.log
pid_file=/var/run/${app_name}.pid

# Generated on: $(date)
EOF
}

echo "Generated configuration:"
generate_config "myapp" "8080" "true"

echo
echo "=== Here Documents with Indentation ==="

# Using <<- to ignore leading tabs
if true; then
	cat <<- EOF
	This here document ignores leading tabs.
	Each line can be indented for readability.
	The delimiter must also be indented with tabs.
	EOF
fi

echo
echo "=== Here Documents for Multi-line Strings ==="

# Storing multi-line content in variables
help_text=$(cat << 'EOF'
Usage: myscript [OPTIONS] [ARGUMENTS]

OPTIONS:
    -h, --help     Show this help message
    -v, --verbose  Enable verbose output
    -q, --quiet    Suppress output

ARGUMENTS:
    file           Input file to process
    
Examples:
    myscript -v input.txt
    myscript --quiet data.csv
EOF
)

echo "$help_text"

echo
echo "=== Here Documents for Email/Templates ==="

send_email() {
    local to="$1"
    local subject="$2"
    local name="$3"
    
    # Simulate sending email
    cat << EOF > email.txt
To: $to
Subject: $subject

Dear $name,

Thank you for your interest in our services.
This is an automated message generated on $(date).

Best regards,
The Team
EOF
    
    echo "Email saved to email.txt"
}

send_email "user@example.com" "Welcome!" "John"
echo "Email content:"
cat email.txt

echo
echo "=== Here Documents with Command Substitution ==="

# Generate SQL script
create_sql_script() {
    local table_name="$1"
    local timestamp=$(date '+%Y%m%d_%H%M%S')
    
    cat << EOF > "${table_name}_script.sql"
-- Auto-generated script for $table_name
-- Created: $(date)

CREATE TABLE IF NOT EXISTS $table_name (
    id INTEGER PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO $table_name (name) VALUES 
    ('Sample Data 1'),
    ('Sample Data 2'),
    ('Sample Data 3');

-- Script generated at: $timestamp
EOF
    
    echo "SQL script created: ${table_name}_script.sql"
}

create_sql_script "users"
echo "SQL script content:"
cat users_script.sql

# Clean up
rm -f email.txt users_script.sql
```

### ⚠️ Common Pitfalls

1. **Redirection Order**: Order matters in redirection
   ```bash
   # Wrong
   command 2>&1 > file  # stderr goes to terminal, stdout to file
   
   # Correct  
   command > file 2>&1  # both to file
   ```

2. **Here Document Indentation**: Use `<<-` for tab indentation
3. **Pipe Failures**: Use `set -o pipefail` to catch pipe failures
4. **File Descriptor Leaks**: Always close custom file descriptors

### ✅ Best Practices

1. **Use Meaningful Redirections**: Be explicit about stream handling
2. **Error Handling**: Always handle stderr appropriately
3. **Cleanup**: Close file descriptors and remove temporary files
4. **Documentation**: Comment complex redirection patterns

### 🏋️ Exercise 7: Advanced I/O System

**Difficulty:** 🔴 Advanced  
**Estimated Time:** 50 minutes

Create a script called `log_processor.sh` that:
1. Processes multiple log files simultaneously using pipes
2. Filters and analyzes log data with complex pipelines
3. Uses here documents for report generation
4. Implements custom file descriptors for different output streams
5. Handles errors and provides progress feedback

<details>
<summary>💡 Click to see hints</summary>

- Use named pipes for inter-process communication
- Process substitution for parallel processing
- Custom file descriptors for different report sections
- Here documents for formatted output
- `tee` for multiple output streams

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# log_processor.sh - Advanced log processing system

set -euo pipefail  # Exit on error, undefined vars, pipe failures

#===============================================
# GLOBAL VARIABLES
#===============================================

readonly SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
readonly TEMP_DIR="/tmp/log_processor_$$"
readonly REPORT_DIR="$HOME/log_reports"

# File descriptors
exec 3> >(tee -a "$TEMP_DIR/debug.log" >&2)  # Debug output
exec 4> >(tee -a "$TEMP_DIR/stats.log")      # Statistics
exec 5> >(tee -a "$TEMP_DIR/errors.log" >&2) # Error output

#===============================================
# UTILITY FUNCTIONS
#===============================================

cleanup() {
    echo "Cleaning up..." >&3
    exec 3>&- 4>&- 5>&-  # Close custom FDs
    rm -rf "$TEMP_DIR"
}

trap cleanup EXIT

debug() {
    echo "[DEBUG $(date '+%H:%M:%S')] $*" >&3
}

log_stat() {
    echo "[STAT $(date '+%H:%M:%S')] $*" >&4
}

log_error() {
    echo "[ERROR $(date '+%H:%M:%S')] $*" >&5
}

#===============================================
# INITIALIZATION
#===============================================

initialize() {
    mkdir -p "$TEMP_DIR" "$REPORT_DIR"
    debug "Initialized temporary directory: $TEMP_DIR"
    debug "Report directory: $REPORT_DIR"
}

#===============================================
# LOG PROCESSING FUNCTIONS
#===============================================

create_sample_logs() {
    debug "Creating sample log files"
    
    # Access log
    cat << 'EOF' > "$TEMP_DIR/access.log"
192.168.1.1 - - [01/Jan/2024:10:00:01] "GET /index.html" 200 1024
192.168.1.2 - - [01/Jan/2024:10:00:02] "GET /about.html" 200 2048
192.168.1.1 - - [01/Jan/2024:10:00:03] "POST /login" 401 512
192.168.1.3 - - [01/Jan/2024:10:00:04] "GET /index.html" 200 1024
192.168.1.2 - - [01/Jan/2024:10:00:05] "GET /contact.html" 404 256
192.168.1.4 - - [01/Jan/2024:10:00:06] "GET /admin" 403 128
192.168.1.1 - - [01/Jan/2024:10:00:07] "GET /data" 200 4096
EOF
    
    # Error log
    cat << 'EOF' > "$TEMP_DIR/error.log"
[01/Jan/2024:10:00:03] [error] Authentication failed for 192.168.1.1
[01/Jan/2024:10:00:05] [warn] File not found: /contact.html
[01/Jan/2024:10:00:06] [error] Access denied to /admin for 192.168.1.4
[01/Jan/2024:10:00:08] [info] Daily backup completed
[01/Jan/2024:10:00:09] [error] Database connection timeout
EOF
    
    debug "Sample logs created"
}

process_access_log() {
    local log_file="$1"
    debug "Processing access log: $log_file"
    
    # Create named pipes for parallel processing
    mkfifo "$TEMP_DIR/ip_pipe" "$TEMP_DIR/status_pipe" "$TEMP_DIR/size_pipe"
    
    # Process IPs in background
    {
        cut -d' ' -f1 "$log_file" | sort | uniq -c | sort -nr
    } > "$TEMP_DIR/ip_stats.txt" &
    
    # Process status codes in background  
    {
        awk '{print $9}' "$log_file" | sort | uniq -c | sort -nr
    } > "$TEMP_DIR/status_stats.txt" &
    
    # Process request sizes
    {
        awk '{sum += $10; count++} END {print "Average size:", sum/count, "bytes"}'  "$log_file"
    } > "$TEMP_DIR/size_stats.txt" &
    
    wait  # Wait for all background processes
    
    log_stat "Access log processed: $(wc -l < "$log_file") requests"
}

process_error_log() {
    local log_file="$1"
    debug "Processing error log: $log_file"
    
    # Error level analysis
    grep -o '\[error\]' "$log_file" | wc -l > "$TEMP_DIR/error_count.txt"
    grep -o '\[warn\]' "$log_file" | wc -l > "$TEMP_DIR/warn_count.txt"  
    grep -o '\[info\]' "$log_file" | wc -l > "$TEMP_DIR/info_count.txt"
    
    log_stat "Error log processed: $(wc -l < "$log_file") entries"
}

#===============================================
# REPORT GENERATION
#===============================================

generate_report() {
    local report_file="$REPORT_DIR/log_report_$(date +%Y%m%d_%H%M%S).html"
    debug "Generating report: $report_file"
    
    # Generate HTML report using here document
    cat << EOF > "$report_file"
<!DOCTYPE html>
<html>
<head>
    <title>Log Analysis Report</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 40px; }
        h1, h2 { color: #333; }
        table { border-collapse: collapse; width: 100%; margin: 20px 0; }
        th, td { border: 1px solid #ddd; padding: 8px; text-align: left; }
        th { background-color: #f2f2f2; }
        .error { color: red; }
        .warn { color: orange; }
        .info { color: green; }
    </style>
</head>
<body>
    <h1>Log Analysis Report</h1>
    <p>Generated on: $(date)</p>
    
    <h2>Summary Statistics</h2>
    <table>
        <tr><th>Metric</th><th>Value</th></tr>
        <tr><td>Total Requests</td><td>$(wc -l < "$TEMP_DIR/access.log")</td></tr>
        <tr><td>Unique IPs</td><td>$(cut -d' ' -f1 "$TEMP_DIR/access.log" | sort -u | wc -l)</td></tr>
        <tr><td class="error">Errors</td><td>$(cat "$TEMP_DIR/error_count.txt")</td></tr>
        <tr><td class="warn">Warnings</td><td>$(cat "$TEMP_DIR/warn_count.txt")</td></tr>
        <tr><td class="info">Info Messages</td><td>$(cat "$TEMP_DIR/info_count.txt")</td></tr>
    </table>
    
    <h2>Top IP Addresses</h2>
    <table>
        <tr><th>Requests</th><th>IP Address</th></tr>
EOF
    
    # Add IP statistics to report
    head -5 "$TEMP_DIR/ip_stats.txt" | while read count ip; do
        echo "        <tr><td>$count</td><td>$ip</td></tr>" >> "$report_file"
    done
    
    cat << EOF >> "$report_file"
    </table>
    
    <h2>HTTP Status Codes</h2>
    <table>
        <tr><th>Count</th><th>Status Code</th><th>Description</th></tr>
EOF
    
    # Add status code statistics
    while read count status; do
        case "$status" in
            200) desc="OK" ;;
            401) desc="Unauthorized" ;;
            403) desc="Forbidden" ;;
            404) desc="Not Found" ;;
            *) desc="Other" ;;
        esac
        echo "        <tr><td>$count</td><td>$status</td><td>$desc</td></tr>" >> "$report_file"
    done < "$TEMP_DIR/status_stats.txt"
    
    cat << EOF >> "$report_file"
    </table>
    
    <h2>Performance Metrics</h2>
    <p>$(cat "$TEMP_DIR/size_stats.txt")</p>
    
    <h2>Generated Files</h2>
    <ul>
        <li>Debug log: $TEMP_DIR/debug.log</li>
        <li>Statistics log: $TEMP_DIR/stats.log</li>
        <li>Error log: $TEMP_DIR/errors.log</li>
    </ul>
    
    <hr>
    <p><small>Report generated by log_processor.sh</small></p>
</body>
</html>
EOF
    
    echo "$report_file"
}

#===============================================
# MAIN PROGRAM
#===============================================

main() {
    initialize
    create_sample_logs
    
    echo "Processing logs..."
    process_access_log "$TEMP_DIR/access.log"
    process_error_log "$TEMP_DIR/error.log"
    
    echo "Generating report..."
    local report_file
    report_file=$(generate_report)
    
    echo "Report generated: $report_file"
    echo "Debug information available in: $TEMP_DIR"
    
    log_stat "Processing complete"
}

main "$@"
```

**Explanation:**
- Implements advanced I/O redirection with custom file descriptors for different output streams
- Uses named pipes and process substitution for parallel processing
- Demonstrates here documents for complex report generation
- Shows proper cleanup of resources and file descriptors
- Provides comprehensive error handling and logging

</details>

---

## 🎭 Pattern Matching and Regular Expressions

📊 **Chapter 8 of 13**
🎯 **Learning Objectives:**
- Master wildcards and globbing patterns
- Implement pattern matching in conditionals
- Use regular expressions with grep and sed
- Perform advanced string manipulation

⏱️ **Estimated Reading Time:** 30 minutes
📋 **Prerequisites:** Chapters 1-7

### Wildcards and Globbing

Understanding Bash globbing patterns:

```bash
#!/bin/bash
# wildcards_globbing.sh - Mastering wildcards and globbing

echo "=== Basic Wildcards ==="

# Create test files
mkdir -p test_glob
cd test_glob
touch file1.txt file2.txt file3.doc script.sh backup.bak
touch File1.TXT image.jpg image.png data.csv
mkdir dir1 dir2

echo "Test files created:"
ls -la

echo
echo "=== Asterisk (*) - Match any characters ==="
echo "*.txt files:"
ls *.txt

echo "file* pattern:"
ls file*

echo "*.* (files with extensions):"
ls *.*

echo
echo "=== Question Mark (?) - Match single character ==="
echo "file?.txt pattern:"
ls file?.txt

echo "*.??? (three-letter extensions):"
ls *.???

echo
echo "=== Square Brackets [...] - Character classes ==="
echo "[Ff]ile* pattern:"
ls [Ff]ile*

echo "*.[jJ][pP][gG] pattern:"
ls *.[jJ][pP][gG] 2>/dev/null || echo "No matches"

echo "*.[0-9]* pattern:"
ls *.[0-9]* 2>/dev/null || echo "No matches"

echo
echo "=== Advanced Globbing Patterns ==="

# Enable extended globbing
shopt -s extglob

echo "Extended globbing enabled"

# Create more test files
touch test.log test.txt test.bak
touch app.config app.json app.yaml

echo "?(pattern) - Zero or one occurrence:"
ls app.?(config|json)

echo "*(pattern) - Zero or more occurrences:"  
ls test.*(txt|log|bak)

echo "+(pattern) - One or more occurrences:"
ls +(file|script)*

echo "!(pattern) - Not matching pattern:"
ls !(*.bak|*.log)

echo "@(pattern) - Exactly one occurrence:"
ls @(*.txt|*.sh)

cd ..
rm -rf test_glob
```

### Pattern Matching

Pattern matching in conditionals and case statements:

```bash
#!/bin/bash  
# pattern_matching.sh - Advanced pattern matching techniques

echo "=== Pattern Matching in Conditionals ==="

test_patterns() {
    local string="$1"
    echo "Testing string: '$string'"
    
    # Basic pattern matching with [[ ]]
    if [[ "$string" == *".txt"* ]]; then
        echo "  Contains .txt"
    fi
    
    if [[ "$string" == [0-9]* ]]; then
        echo "  Starts with digit"
    fi
    
    if [[ "$string" =~ ^[a-zA-Z]+$ ]]; then
        echo "  Contains only letters"
    fi
    
    # Case-insensitive matching (Bash 4.0+)
    shopt -s nocasematch
    if [[ "$string" == *"FILE"* ]]; then
        echo "  Contains 'file' (case-insensitive)"
    fi
    shopt -u nocasematch
    
    echo
}

test_patterns "file123.txt"
test_patterns "9document.pdf"
test_patterns "HelloWorld"
test_patterns "MyFile.TXT"

echo "=== Pattern Matching in Case Statements ==="

classify_file() {
    local filename="$1"
    
    case "$filename" in
        *.txt|*.md|*.rst)
            echo "$filename: Text document"
            ;;
        *.jpg|*.png|*.gif|*.bmp)
            echo "$filename: Image file"
            ;;
        *.sh|*.bash)
            echo "$filename: Shell script"
            ;;
        *.py|*.pl|*.rb)
            echo "$filename: Script file"
            ;;
        [0-9]*)
            echo "$filename: Starts with number"
            ;;
        [A-Z]*)
            echo "$filename: Starts with uppercase"
            ;;
        .*)
            echo "$filename: Hidden file"
            ;;
        *)
            echo "$filename: Unknown type"
            ;;
    esac
}

echo "File classification:"
classify_file "document.txt"
classify_file "photo.jpg"
classify_file "script.sh"
classify_file "9data.csv"
classify_file "README.md"
classify_file ".bashrc"

echo
echo "=== Advanced Pattern Examples ==="

# Email validation pattern
validate_email() {
    local email="$1"
    
    if [[ "$email" =~ ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$ ]]; then
        echo "Valid email: $email"
        return 0
    else
        echo "Invalid email: $email"
        return 1
    fi
}

echo "Email validation:"
validate_email "user@example.com"
validate_email "invalid.email"
validate_email "test+tag@domain.co.uk"

echo
# Phone number patterns
validate_phone() {
    local phone="$1"
    
    case "$phone" in
        [0-9][0-9][0-9]-[0-9][0-9][0-9]-[0-9][0-9][0-9][0-9])
            echo "Valid US phone: $phone"
            ;;
        \([0-9][0-9][0-9]\)\ [0-9][0-9][0-9]-[0-9][0-9][0-9][0-9])
            echo "Valid US phone (formatted): $phone"
            ;;
        +[0-9]*)
            echo "International phone: $phone"
            ;;
        *)
            echo "Invalid phone: $phone"
            ;;
    esac
}

echo "Phone validation:"
validate_phone "555-123-4567"
validate_phone "(555) 123-4567"
validate_phone "+1-555-123-4567"
validate_phone "invalid-phone"
```

### Regular Expressions

Using regular expressions with command-line tools:

```bash
#!/bin/bash
# regular_expressions.sh - Working with regex in Bash

echo "=== Regular Expressions with grep ==="

# Create test data
cat > sample_data.txt << 'EOF'
John Doe, john@example.com, 555-1234
Jane Smith, jane.smith@company.org, (555) 567-8900  
Bob Johnson, bob123@test.net, 555.789.0123
Alice Brown, alice_brown@domain.co.uk, +1-555-999-8888
Charlie Wilson, charlie@invalid, 123-45-67
Mary Davis, mary.davis@email.com, 555-CALL-NOW
EOF

echo "Sample data:"
cat sample_data.txt

echo
echo "=== Basic grep patterns ==="

echo "Lines containing 'john' (case-insensitive):"
grep -i "john" sample_data.txt

echo
echo "Lines with valid email domains (.com, .org, .net):"
grep -E "\.com|\.org|\.net" sample_data.txt

echo
echo "Lines with phone numbers (digit-dash-digit pattern):"
grep -E "[0-9]+-[0-9]+-[0-9]+" sample_data.txt

echo
echo "=== Advanced grep patterns ==="

echo "Valid email addresses:"
grep -E "^[^,]+, [a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}," sample_data.txt

echo
echo "Names starting with vowels:"
grep -E "^[AEIOU]" sample_data.txt

echo
echo "Phone numbers with parentheses or plus:"
grep -E "\(|\+" sample_data.txt

echo
echo "=== sed with Regular Expressions ==="

echo "Original data:"
cat sample_data.txt

echo
echo "Replace email domains with '[DOMAIN]':"
sed -E 's/@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}/@[DOMAIN]/g' sample_data.txt

echo
echo "Extract just the names (first field):"
sed -E 's/^([^,]+),.*/\1/' sample_data.txt

echo
echo "Format phone numbers consistently:"
sed -E 's/\(?([0-9]{3})\)?[- .]?([0-9]{3})[- .]?([0-9]{4})/(\1) \2-\3/g' sample_data.txt

echo
echo "=== Complex Pattern Matching ==="

# Log analysis example
cat > server.log << 'EOF'
[2024-01-01 10:00:01] INFO: Server started on port 8080
[2024-01-01 10:00:15] ERROR: Database connection failed
[2024-01-01 10:00:30] WARN: High memory usage detected: 85%
[2024-01-01 10:01:00] INFO: New user registered: user@example.com
[2024-01-01 10:01:15] ERROR: Authentication failed for 192.168.1.100
[2024-01-01 10:01:30] INFO: File uploaded: document.pdf (2.5MB)
EOF

echo "Server log analysis:"
cat server.log

echo
echo "Extract timestamps:"
grep -oE '\[[0-9]{4}-[0-9]{2}-[0-9]{2} [0-9]{2}:[0-9]{2}:[0-9]{2}\]' server.log

echo
echo "Error messages only:"
grep "ERROR:" server.log | sed -E 's/.*ERROR: //'

echo
echo "Extract IP addresses:"
grep -oE '([0-9]{1,3}\.){3}[0-9]{1,3}' server.log

echo
echo "Extract file sizes:"
grep -oE '\([0-9.]+[KMGT]?B\)' server.log

echo
echo "=== Pattern Replacement in Variables ==="

# String manipulation with patterns
text="The quick brown fox jumps over the lazy dog"
echo "Original: $text"

# Pattern substitution
echo "Replace 'fox' with 'cat': ${text/fox/cat}"
echo "Replace all 'o' with '0': ${text//o/0}"
echo "Remove 'the ' (case insensitive): ${text//[Tt]he /}"

# Pattern matching for validation
url="https://www.example.com/path?param=value"
echo "URL: $url"

if [[ "$url" =~ ^https?://[a-zA-Z0-9.-]+(/.*)?$ ]]; then
    echo "Valid URL format"
    # Extract components
    [[ "$url" =~ ^(https?)://([^/]+)(/.*)? ]]
    protocol="${BASH_REMATCH[1]}"
    domain="${BASH_REMATCH[2]}"
    path="${BASH_REMATCH[3]}"
    
    echo "  Protocol: $protocol"
    echo "  Domain: $domain"  
    echo "  Path: $path"
fi

# Clean up
rm -f sample_data.txt server.log
```

### String Manipulation

Advanced string manipulation techniques:

```bash
#!/bin/bash
# string_manipulation.sh - Advanced string manipulation

echo "=== Parameter Expansion Patterns ==="

# Sample data
filename="/path/to/document.backup.txt"
text="Hello World Hello Universe"
mixed_case="ThIs Is MiXeD cAsE"

echo "Filename: $filename"
echo "Text: $text"
echo "Mixed case: $mixed_case"

echo
echo "=== Path manipulation ==="
echo "Directory: ${filename%/*}"
echo "Basename: ${filename##*/}"
echo "Extension: ${filename##*.}"
echo "Name without extension: ${filename%.*}"
echo "Remove all extensions: ${filename%%.*}"

echo
echo "=== String replacement patterns ==="
echo "Replace first 'Hello': ${text/Hello/Hi}"
echo "Replace all 'Hello': ${text//Hello/Hi}"
echo "Replace at beginning: ${text/#Hello/Hi}"
echo "Replace at end: ${text/%Universe/Galaxy}"

echo
echo "=== Case conversion (Bash 4.0+) ==="
echo "Uppercase all: ${mixed_case^^}"
echo "Lowercase all: ${mixed_case,,}"
echo "Uppercase first: ${mixed_case^}"
echo "Lowercase first: ${mixed_case,}"
echo "Toggle case: ${mixed_case~~}"

echo
echo "=== Advanced String Functions ==="

# Custom string manipulation functions
reverse_string() {
    local str="$1"
    local reversed=""
    local i
    
    for ((i=${#str}-1; i>=0; i--)); do
        reversed="${reversed}${str:$i:1}"
    done
    
    echo "$reversed"
}

count_words() {
    local text="$1"
    local count=0
    local word
    
    for word in $text; do
        ((count++))
    done
    
    echo "$count"
}

extract_numbers() {
    local text="$1"
    # Use parameter expansion to remove non-digits
    local numbers_only="${text//[^0-9 ]/}"
    echo "$numbers_only"
}

title_case() {
    local text="$1"
    local result=""
    local word
    
    for word in $text; do
        # Capitalize first letter, lowercase rest
        result="$result ${word^${word:1},,}"
    done
    
    echo "${result# }"  # Remove leading space
}

echo "String function demonstrations:"
echo "Reverse 'Hello World': $(reverse_string 'Hello World')"
echo "Word count of '$text': $(count_words "$text")"
echo "Extract numbers from 'abc123def456': $(extract_numbers 'abc123def456')"
echo "Title case 'hello world': $(title_case 'hello world')"

echo
echo "=== Pattern-based Validation ==="

validate_input() {
    local input="$1"
    local type="$2"
    
    case "$type" in
        "username")
            [[ "$input" =~ ^[a-zA-Z][a-zA-Z0-9_]{2,15}$ ]]
            ;;
        "email")
            [[ "$input" =~ ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$ ]]
            ;;
        "phone")
            [[ "$input" =~ ^(\+?1[-.]?)?(\([0-9]{3}\)|[0-9]{3})[-.]?[0-9]{3}[-.]?[0-9]{4}$ ]]
            ;;
        "ipv4")
            [[ "$input" =~ ^([0-9]{1,3}\.){3}[0-9]{1,3}$ ]]
            ;;
        "date")
            [[ "$input" =~ ^[0-9]{4}-[0-9]{2}-[0-9]{2}$ ]]
            ;;
        *)
            return 1
            ;;
    esac
}

test_validation() {
    local input="$1"
    local type="$2"
    
    if validate_input "$input" "$type"; then
        echo "✓ Valid $type: $input"
    else
        echo "✗ Invalid $type: $input"
    fi
}

echo "Input validation tests:"
test_validation "john_doe" "username"
test_validation "a" "username"
test_validation "user@example.com" "email"
test_validation "invalid-email" "email"
test_validation "555-123-4567" "phone"
test_validation "192.168.1.1" "ipv4"
test_validation "2024-01-01" "date"
```

### ⚠️ Common Pitfalls

1. **Globbing in Variables**: Quote variables to prevent unwanted expansion
2. **Case Sensitivity**: Remember Bash pattern matching is case-sensitive by default
3. **Regex vs Globbing**: Don't confuse shell globbing with regular expressions
4. **Special Characters**: Escape special characters in patterns

### ✅ Best Practices

1. **Quote Patterns**: Always quote regex patterns to prevent shell interpretation
2. **Test Thoroughly**: Test patterns with edge cases
3. **Use Appropriate Tool**: Choose between shell patterns, grep, sed based on needs
4. **Document Complex Patterns**: Comment complex regex patterns

### 🏋️ Exercise 8: Pattern Matching System

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 45 minutes

Create a script called `data_validator.sh` that:
1. Validates different data formats using patterns
2. Processes log files with regex
3. Implements a configuration file parser
4. Provides detailed validation reports
5. Uses advanced string manipulation

<details>
<summary>💡 Click to see hints</summary>

- Use associative arrays for validation rules
- Implement different validation functions for each data type
- Use grep and sed for log processing
- Pattern matching in case statements for file types
- String manipulation for data cleaning

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# data_validator.sh - Comprehensive data validation system

#===============================================
# GLOBAL VARIABLES
#===============================================

declare -A validation_rules
declare -A validation_results
declare -a error_messages
declare -a processed_files

#===============================================
# VALIDATION PATTERNS
#===============================================

init_validation_rules() {
    validation_rules[email]='^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
    validation_rules[phone]='^(\+?1[-.]?)?\(?([0-9]{3})\)?[-.]?([0-9]{3})[-.]?([0-9]{4})$'
    validation_rules[ssn]='^[0-9]{3}-[0-9]{2}-[0-9]{4}$'
    validation_rules[ipv4]='^([0-9]{1,3}\.){3}[0-9]{1,3}$'
    validation_rules[date]='^[0-9]{4}-[0-9]{2}-[0-9]{2}$'
    validation_rules[time]='^[0-9]{2}:[0-9]{2}(:[0-9]{2})?$'
    validation_rules[username]='^[a-zA-Z][a-zA-Z0-9_]{2,19}$'
    validation_rules[url]='^https?://[a-zA-Z0-9.-]+(/.*)?$'
}

#===============================================
# VALIDATION FUNCTIONS
#===============================================

validate_field() {
    local value="$1"
    local type="$2"
    local pattern="${validation_rules[$type]}"
    
    if [[ -z "$pattern" ]]; then
        echo "Unknown validation type: $type"
        return 1
    fi
    
    if [[ "$value" =~ $pattern ]]; then
        return 0
    else
        return 1
    fi
}

validate_data_file() {
    local file="$1"
    local format="$2"
    
    if [[ ! -f "$file" ]]; then
        error_messages+=("File not found: $file")
        return 1
    fi
    
    case "$format" in
        "csv")
            validate_csv_file "$file"
            ;;
        "log")
            validate_log_file "$file"
            ;;
        "config")
            validate_config_file "$file"
            ;;
        *)
            error_messages+=("Unknown file format: $format")
            return 1
            ;;
    esac
}

validate_csv_file() {
    local file="$1"
    local line_num=0
    local errors=0
    local warnings=0
    
    echo "Validating CSV file: $file"
    
    while IFS=',' read -r name email phone date; do
        ((line_num++))
        
        # Skip header line
        [[ $line_num -eq 1 ]] && continue
        
        # Validate each field
        if ! validate_field "$name" "username"; then
            echo "  Line $line_num: Invalid name '$name'"
            ((errors++))
        fi
        
        if ! validate_field "$email" "email"; then
            echo "  Line $line_num: Invalid email '$email'"
            ((errors++))
        fi
        
        if ! validate_field "$phone" "phone"; then
            echo "  Line $line_num: Invalid phone '$phone'"
            ((warnings++))
        fi
        
        if ! validate_field "$date" "date"; then
            echo "  Line $line_num: Invalid date '$date'"
            ((errors++))
        fi
        
    done < "$file"
    
    validation_results["$file"]="Lines: $line_num, Errors: $errors, Warnings: $warnings"
    processed_files+=("$file")
    
    echo "  Summary: $line_num lines, $errors errors, $warnings warnings"
}

validate_log_file() {
    local file="$1"
    local total_lines=0
    local error_lines=0
    local warning_lines=0
    local info_lines=0
    
    echo "Validating log file: $file"
    
    # Count different log levels
    total_lines=$(wc -l < "$file")
    error_lines=$(grep -c "\[ERROR\]" "$file" 2>/dev/null || echo 0)
    warning_lines=$(grep -c "\[WARN\]" "$file" 2>/dev/null || echo 0)
    info_lines=$(grep -c "\[INFO\]" "$file" 2>/dev/null || echo 0)
    
    # Validate timestamp format
    local invalid_timestamps
    invalid_timestamps=$(grep -v '^\[20[0-9][0-9]-[0-9][0-9]-[0-9][0-9] [0-9][0-9]:[0-9][0-9]:[0-9][0-9]\]' "$file" | wc -l)
    
    echo "  Total lines: $total_lines"
    echo "  Errors: $error_lines"
    echo "  Warnings: $warning_lines"
    echo "  Info: $info_lines"
    echo "  Invalid timestamps: $invalid_timestamps"
    
    # Extract unique IP addresses
    echo "  Unique IPs found:"
    grep -oE '([0-9]{1,3}\.){3}[0-9]{1,3}' "$file" | sort -u | head -5
    
    validation_results["$file"]="Total: $total_lines, Errors: $error_lines, Warnings: $warning_lines"
    processed_files+=("$file")
}

validate_config_file() {
    local file="$1"
    local valid_keys=0
    local invalid_lines=0
    local comments=0
    
    echo "Validating config file: $file"
    
    while IFS= read -r line; do
        # Skip empty lines
        [[ -z "$line" ]] && continue
        
        # Count comments
        if [[ "$line" =~ ^[[:space:]]*# ]]; then
            ((comments++))
            continue
        fi
        
        # Validate key=value format
        if [[ "$line" =~ ^[a-zA-Z_][a-zA-Z0-9_]*=[^[:space:]]+ ]]; then
            ((valid_keys++))
        else
            echo "  Invalid line: $line"
            ((invalid_lines++))
        fi
        
    done < "$file"
    
    echo "  Valid keys: $valid_keys"
    echo "  Invalid lines: $invalid_lines"
    echo "  Comments: $comments"
    
    validation_results["$file"]="Keys: $valid_keys, Invalid: $invalid_lines, Comments: $comments"
    processed_files+=("$file")
}

#===============================================
# SAMPLE DATA GENERATION
#===============================================

create_sample_data() {
    # Create sample CSV
    cat > sample.csv << 'EOF'
name,email,phone,date
john_doe,john@example.com,555-123-4567,2024-01-01
jane_smith,jane.smith@company.org,(555) 567-8900,2024-01-02
bob123,invalid-email,123-456-7890,2024-01-03
alice_b,alice@domain.co.uk,555.789.0123,invalid-date
charlie,charlie@test.com,+1-555-999-8888,2024-01-05
EOF
    
    # Create sample log
    cat > sample.log << 'EOF'
[2024-01-01 10:00:01] [INFO] Server started on port 8080
[2024-01-01 10:00:15] [ERROR] Database connection failed from 192.168.1.100
[2024-01-01 10:00:30] [WARN] High memory usage detected: 85%
Invalid timestamp format ERROR: Something went wrong
[2024-01-01 10:01:15] [ERROR] Authentication failed for 192.168.1.200
[2024-01-01 10:01:30] [INFO] User logged in from 10.0.0.1
EOF
    
    # Create sample config
    cat > sample.config << 'EOF'
# Database configuration
database_host=localhost
database_port=5432
database_name=myapp

# Server settings
server_port=8080
server_host=0.0.0.0
debug_mode=true

invalid line without equals
another_invalid_line =

# Valid setting with special chars
api_key=abc123-def456-ghi789
EOF
}

#===============================================
# REPORT GENERATION
#===============================================

generate_report() {
    echo
    echo "=== VALIDATION REPORT ==="
    echo "Generated on: $(date)"
    echo
    
    echo "Files processed:"
    for file in "${processed_files[@]}"; do
        echo "  $file: ${validation_results[$file]}"
    done
    
    echo
    if [[ ${#error_messages[@]} -gt 0 ]]; then
        echo "Errors encountered:"
        for error in "${error_messages[@]}"; do
            echo "  - $error"
        done
    else
        echo "No critical errors found."
    fi
    
    echo
    echo "Validation rules used:"
    for rule in "${!validation_rules[@]}"; do
        echo "  $rule: ${validation_rules[$rule]}"
    done
}

#===============================================
# MAIN PROGRAM
#===============================================

show_help() {
    cat << 'EOF'
Data Validator - Usage:
  ./data_validator.sh [OPTIONS] [FILES...]

OPTIONS:
  -h, --help     Show this help
  -t, --test     Run with sample data
  -f, --format   Specify file format (csv|log|config)

EXAMPLES:
  ./data_validator.sh -t
  ./data_validator.sh -f csv data.csv
  ./data_validator.sh app.log config.ini
EOF
}

main() {
    init_validation_rules
    
    local format=""
    local use_samples=false
    
    # Parse command line arguments
    while [[ $# -gt 0 ]]; do
        case "$1" in
            -h|--help)
                show_help
                exit 0
                ;;
            -t|--test)
                use_samples=true
                shift
                ;;
            -f|--format)
                format="$2"
                shift 2
                ;;
            -*)
                echo "Unknown option: $1"
                show_help
                exit 1
                ;;
            *)
                break
                ;;
        esac
    done
    
    if [[ "$use_samples" == true ]]; then
        echo "Creating sample data..."
        create_sample_data
        
        validate_data_file "sample.csv" "csv"
        validate_data_file "sample.log" "log"  
        validate_data_file "sample.config" "config"
        
        # Clean up samples
        rm -f sample.csv sample.log sample.config
    else
        if [[ $# -eq 0 ]]; then
            echo "No files specified. Use -h for help."
            exit 1
        fi
        
        for file in "$@"; do
            local file_format="$format"
            
            # Auto-detect format if not specified
            if [[ -z "$file_format" ]]; then
                case "$file" in
                    *.csv) file_format="csv" ;;
                    *.log) file_format="log" ;;
                    *.conf|*.config|*.ini) file_format="config" ;;
                    *) 
                        echo "Cannot determine format for $file. Use -f option."
                        continue
                        ;;
                esac
            fi
            
            validate_data_file "$file" "$file_format"
        done
    fi
    
    generate_report
}

main "$@"
```

**Explanation:**
- Implements comprehensive data validation with multiple file formats
- Uses associative arrays for validation rules and results tracking
- Demonstrates advanced pattern matching for different data types
- Provides detailed validation reports with statistics
- Shows practical use of regex patterns for data validation

</details>

---

## ⚙️ Process Management

📊 **Chapter 9 of 13**
🎯 **Learning Objectives:**
- Master job control and background processes
- Implement signal handling and traps
- Use process substitution effectively
- Monitor and manage system processes

⏱️ **Estimated Reading Time:** 25 minutes
📋 **Prerequisites:** Chapters 1-8

### Job Control

Managing jobs and background processes:

```bash
#!/bin/bash
# job_control.sh - Mastering job control in Bash

echo "=== Basic Job Control ==="

echo "Starting background jobs..."

# Start background jobs
sleep 10 &
echo "Started sleep 10 (PID: $!)"

sleep 15 &  
echo "Started sleep 15 (PID: $!)"

# List jobs
echo
echo "Current jobs:"
jobs

echo
echo "Jobs with PIDs:"
jobs -l

echo
echo "=== Job Control Commands ==="

# Start a job and suspend it
echo "Starting long running process..."
{
    for i in {1..20}; do
        echo "Working... $i"
        sleep 1
    done
} &

job_pid=$!
echo "Started job with PID: $job_pid"

# Let it run for a bit
sleep 3

# Suspend the job
echo "Suspending job..."
kill -STOP $job_pid

echo "Job status after suspension:"
jobs

# Resume in background
echo "Resuming job in background..."
bg %1

# Let it run a bit more
sleep 3

# Bring to foreground
echo "Bringing job to foreground..."
fg %1 &
wait

echo
echo "=== Process Monitoring ==="

# Monitor background processes
monitor_jobs() {
    while jobs | grep -q "Running"; do
        echo "Active jobs: $(jobs | grep Running | wc -l)"
        sleep 2
    done
    echo "All background jobs completed"
}

echo "Monitoring background jobs..."
monitor_jobs
```

### Background Processes

Advanced background process management:

```bash
#!/bin/bash
# background_processes.sh - Advanced background process management

echo "=== Background Process Patterns ==="

# Function to run in background
background_task() {
    local task_name="$1"
    local duration="$2"
    local output_file="$3"
    
    echo "[$task_name] Starting at $(date)" > "$output_file"
    
    for i in $(seq 1 "$duration"); do
        echo "[$task_name] Step $i/$(duration) at $(date)" >> "$output_file"
        sleep 1
    done
    
    echo "[$task_name] Completed at $(date)" >> "$output_file"
}

# Start multiple background tasks
echo "Starting parallel tasks..."
background_task "Task1" 5 "task1.log" &
task1_pid=$!

background_task "Task2" 7 "task2.log" &
task2_pid=$!

background_task "Task3" 3 "task3.log" &
task3_pid=$!

echo "Started tasks with PIDs: $task1_pid, $task2_pid, $task3_pid"

# Monitor specific processes
monitor_process() {
    local pid="$1"
    local name="$2"
    
    while kill -0 "$pid" 2>/dev/null; do
        echo "$name (PID: $pid) is still running..."
        sleep 1
    done
    echo "$name (PID: $pid) has finished"
}

# Wait for all tasks to complete
wait $task1_pid && echo "Task1 completed"
wait $task2_pid && echo "Task2 completed"  
wait $task3_pid && echo "Task3 completed"

echo
echo "=== Process Communication ==="

# Using named pipes for process communication
mkfifo task_queue
mkfifo result_queue

# Worker process
worker_process() {
    local worker_id="$1"
    echo "Worker $worker_id started"
    
    while read task < task_queue; do
        [[ "$task" == "QUIT" ]] && break
        
        echo "Worker $worker_id processing: $task"
        sleep $((RANDOM % 3 + 1))  # Simulate work
        echo "Worker $worker_id completed: $task" > result_queue
    done
    
    echo "Worker $worker_id shutting down"
}

# Start worker processes
worker_process 1 &
worker1_pid=$!

worker_process 2 &
worker2_pid=$!

# Send tasks to workers
{
    echo "Task A"
    echo "Task B" 
    echo "Task C"
    echo "Task D"
    echo "QUIT"
    echo "QUIT"
} > task_queue &

# Collect results
{
    for i in {1..4}; do
        read result < result_queue
        echo "Result: $result"
    done
} &

# Wait for workers to finish
wait $worker1_pid $worker2_pid

# Clean up
rm -f task_queue result_queue task*.log
```

### Signal Handling

Implementing signal handling and traps:

```bash
#!/bin/bash
# signal_handling.sh - Signal handling and traps

echo "=== Basic Signal Handling ==="

# Signal handler function
cleanup_handler() {
    echo
    echo "Cleanup handler called (signal received)"
    echo "Performing cleanup operations..."
    
    # Kill background processes
    for pid in "${background_pids[@]}"; do
        if kill -0 "$pid" 2>/dev/null; then
            echo "Killing process $pid"
            kill "$pid"
        fi
    done
    
    # Remove temporary files
    rm -f /tmp/signal_test_*
    
    echo "Cleanup completed"
    exit 0
}

# Error handler
error_handler() {
    echo "Error handler called on line $1"
    echo "Last command: $2"
    cleanup_handler
}

# Set up traps
trap cleanup_handler INT TERM
trap 'error_handler $LINENO "$BASH_COMMAND"' ERR

echo "Signal handlers set up. Try Ctrl+C to test..."

# Array to track background processes
declare -a background_pids

echo
echo "=== Signal Handling Examples ==="

# Start some background processes
for i in {1..3}; do
    {
        while true; do
            echo "Process $i running at $(date)" > "/tmp/signal_test_$i.log"
            sleep 2
        done
    } &
    
    background_pids+=($!)
    echo "Started background process $i (PID: $!)"
done

echo
echo "Background processes started. Press Ctrl+C to test signal handling..."
echo "Or wait 10 seconds for automatic termination"

# Wait for a while or until interrupted
sleep 10

echo "Normal termination - calling cleanup"
cleanup_handler

echo
echo "=== Advanced Signal Handling ==="

# Custom signal handlers for different signals
handle_sigusr1() {
    echo "Received SIGUSR1 - toggling debug mode"
    if [[ "$debug_mode" == "on" ]]; then
        debug_mode="off"
    else
        debug_mode="on"
    fi
    echo "Debug mode: $debug_mode"
}

handle_sigusr2() {
    echo "Received SIGUSR2 - printing status"
    echo "Process ID: $$"
    echo "Running time: $SECONDS seconds"
    echo "Background jobs: $(jobs | wc -l)"
}

# Set up custom signal handlers
trap handle_sigusr1 USR1
trap handle_sigusr2 USR2

debug_mode="off"

echo "Advanced signal handling demo"
echo "Process ID: $$"
echo "Send SIGUSR1 to toggle debug: kill -USR1 $$"
echo "Send SIGUSR2 to show status: kill -USR2 $$"
echo "Send SIGTERM to exit: kill $$"

# Main loop
counter=0
while true; do
    ((counter++))
    
    if [[ "$debug_mode" == "on" ]]; then
        echo "Debug: Main loop iteration $counter"
    fi
    
    sleep 2
    
    # Auto-exit after reasonable time
    if [[ $counter -gt 20 ]]; then
        echo "Demo completed"
        break
    fi
done
```

### Process Substitution

Using process substitution for advanced data processing:

```bash
#!/bin/bash
# process_substitution.sh - Advanced process substitution techniques

echo "=== Basic Process Substitution ==="

# Reading from process substitution
echo "Reading from command output:"
while read line; do
    echo "Line: $line"
done < <(echo -e "Line 1\nLine 2\nLine 3")

echo
echo "=== Comparing Files with Process Substitution ==="

# Create test data
seq 1 10 > file1.txt
seq 5 15 > file2.txt

echo "Comparing files:"
diff <(sort file1.txt) <(sort file2.txt) || echo "Files differ"

echo
echo "=== Multiple Input Process Substitution ==="

# Process multiple data streams
echo "Processing multiple data streams:"
paste <(seq 1 5) <(seq 10 14) <(seq 20 24) | while read a b c; do
    echo "Sum of $a + $b + $c = $((a + b + c))"
done

echo
echo "=== Output Process Substitution ==="

# Writing to process substitution
echo "Writing to process substitution:"
{
    echo "Data line 1"
    echo "Data line 2" 
    echo "Data line 3"
} > >(sed 's/^/Processed: /' > processed_output.txt)

echo "Processed output:"
cat processed_output.txt

echo
echo "=== Complex Process Substitution Example ==="

# Log analysis using process substitution
create_sample_log() {
    cat << 'EOF'
2024-01-01 10:00:01 INFO User login: john@example.com
2024-01-01 10:00:15 ERROR Database connection failed
2024-01-01 10:00:30 WARN High memory usage: 85%
2024-01-01 10:01:00 INFO User login: jane@example.com
2024-01-01 10:01:15 ERROR Authentication failed: admin
2024-01-01 10:01:30 INFO User logout: john@example.com
2024-01-01 10:02:00 WARN Disk space low: 90%
2024-01-01 10:02:15 INFO User login: bob@example.com
EOF
}

echo "Log analysis using process substitution:"

# Analyze different log levels in parallel
echo "Error analysis:"
grep ERROR <(create_sample_log) | cut -d' ' -f4-

echo
echo "User activity analysis:"
grep -E "(login|logout)" <(create_sample_log) | \
    awk '{print $4, $5}' | \
    sort | uniq -c

echo
echo "=== Process Substitution with Functions ==="

# Function that processes data streams
process_data() {
    local input_source="$1"
    local filter="$2"
    
    while read line; do
        if [[ "$line" =~ $filter ]]; then
            echo "Matched: $line"
        fi
    done < "$input_source"
}

# Use function with process substitution
echo "Processing with function and process substitution:"
process_data <(create_sample_log) "ERROR|WARN"

# Clean up
rm -f file1.txt file2.txt processed_output.txt
```

### ⚠️ Common Pitfalls

1. **Zombie Processes**: Always wait for background processes
2. **Signal Handling**: Properly clean up resources in signal handlers
3. **Race Conditions**: Be careful with shared resources between processes
4. **File Descriptor Leaks**: Close unused file descriptors

### ✅ Best Practices

1. **Clean Exit**: Always implement proper cleanup procedures
2. **Signal Handling**: Handle signals gracefully
3. **Process Monitoring**: Monitor background processes for completion
4. **Resource Management**: Clean up temporary files and processes

### 🏋️ Exercise 9: Process Manager

**Difficulty:** 🔴 Advanced
**Estimated Time:** 50 minutes

Create a script called `process_manager.sh` that:
1. Manages multiple background processes
2. Implements comprehensive signal handling
3. Provides process monitoring and logging
4. Uses process substitution for data processing
5. Handles process communication via pipes

<details>
<summary>💡 Click to see hints</summary>

- Use arrays to track process PIDs
- Implement multiple signal handlers
- Named pipes for inter-process communication
- Process substitution for monitoring
- Proper cleanup in all exit scenarios

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# process_manager.sh - Advanced process management system

set -euo pipefail

#===============================================
# GLOBAL VARIABLES
#===============================================

declare -a managed_processes=()
declare -A process_info=()
declare -A process_logs=()
readonly LOG_DIR="/tmp/process_manager_$$"
readonly STATUS_FILE="$LOG_DIR/status.log"
readonly COMMAND_PIPE="$LOG_DIR/commands"
readonly RESPONSE_PIPE="$LOG_DIR/responses"

#===============================================
# UTILITY FUNCTIONS
#===============================================

log_message() {
    local level="$1"
    local message="$2"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    echo "[$timestamp] [$level] $message" | tee -a "$STATUS_FILE"
}

#===============================================
# SIGNAL HANDLERS
#===============================================

cleanup_handler() {
    log_message "INFO" "Cleanup handler called"
    
    # Stop all managed processes
    for pid in "${managed_processes[@]}"; do
        if kill -0 "$pid" 2>/dev/null; then
            log_message "INFO" "Stopping process $pid"
            kill -TERM "$pid" 2>/dev/null || true
            sleep 1
            kill -KILL "$pid" 2>/dev/null || true
        fi
    done
    
    # Clean up pipes and temp files
    rm -rf "$LOG_DIR"
    
    log_message "INFO" "Cleanup completed"
    exit 0
}

status_handler() {
    log_message "INFO" "Status requested via SIGUSR1"
    show_status > "$STATUS_FILE.tmp" && mv "$STATUS_FILE.tmp" "$STATUS_FILE"
}

reload_handler() {
    log_message "INFO" "Reload requested via SIGUSR2"
    # Implement configuration reload logic here
}

#===============================================
# PROCESS MANAGEMENT FUNCTIONS
#===============================================

start_worker_process() {
    local worker_id="$1"
    local task_type="$2"
    
    case "$task_type" in
        "cpu")
            start_cpu_worker "$worker_id"
            ;;
        "io")
            start_io_worker "$worker_id"
            ;;
        "network")
            start_network_worker "$worker_id"
            ;;
        *)
            log_message "ERROR" "Unknown task type: $task_type"
            return 1
            ;;
    esac
}

start_cpu_worker() {
    local worker_id="$1"
    local log_file="$LOG_DIR/cpu_worker_$worker_id.log"
    
    {
        while true; do
            echo "CPU Worker $worker_id: $(date) - Computing..." 
            # Simulate CPU-intensive work
            for i in {1..1000000}; do
                : $((i * i))
            done
            sleep 2
        done
    } > "$log_file" 2>&1 &
    
    local pid=$!
    managed_processes+=("$pid")
    process_info["$pid"]="cpu_worker_$worker_id"
    process_logs["$pid"]="$log_file"
    
    log_message "INFO" "Started CPU worker $worker_id (PID: $pid)"
    echo "$pid"
}

start_io_worker() {
    local worker_id="$1"
    local log_file="$LOG_DIR/io_worker_$worker_id.log"
    local work_dir="$LOG_DIR/io_work_$worker_id"
    
    mkdir -p "$work_dir"
    
    {
        while true; do
            echo "IO Worker $worker_id: $(date) - File operations..."
            # Simulate I/O work
            for i in {1..10}; do
                echo "Data $i: $(date)" > "$work_dir/file_$i.txt"
            done
            cat "$work_dir"/file_*.txt > "$work_dir/combined.txt"
            rm "$work_dir"/file_*.txt
            sleep 3
        done
    } > "$log_file" 2>&1 &
    
    local pid=$!
    managed_processes+=("$pid")
    process_info["$pid"]="io_worker_$worker_id"
    process_logs["$pid"]="$log_file"
    
    log_message "INFO" "Started I/O worker $worker_id (PID: $pid)"
    echo "$pid"
}

start_network_worker() {
    local worker_id="$1"
    local log_file="$LOG_DIR/network_worker_$worker_id.log"
    
    {
        while true; do
            echo "Network Worker $worker_id: $(date) - Network operations..."
            # Simulate network work
            ping -c 1 localhost >/dev/null 2>&1 && \
                echo "Network test successful" || \
                echo "Network test failed"
            sleep 5
        done
    } > "$log_file" 2>&1 &
    
    local pid=$!
    managed_processes+=("$pid")
    process_info["$pid"]="network_worker_$worker_id"
    process_logs["$pid"]="$log_file"
    
    log_message "INFO" "Started network worker $worker_id (PID: $pid)"
    echo "$pid"
}

#===============================================
# MONITORING FUNCTIONS
#===============================================

show_status() {
    echo "=== Process Manager Status ==="
    echo "Timestamp: $(date)"
    echo "Manager PID: $$"
    echo "Log Directory: $LOG_DIR"
    echo
    
    echo "Managed Processes:"
    for pid in "${managed_processes[@]}"; do
        if kill -0 "$pid" 2>/dev/null; then
            local cpu_usage
            cpu_usage=$(ps -p "$pid" -o %cpu --no-headers 2>/dev/null || echo "N/A")
            local mem_usage
            mem_usage=$(ps -p "$pid" -o %mem --no-headers 2>/dev/null || echo "N/A")
            
            echo "  PID: $pid (${process_info[$pid]})"
            echo "    Status: Running"
            echo "    CPU: ${cpu_usage}%"
            echo "    Memory: ${mem_usage}%"
            echo "    Log: ${process_logs[$pid]}"
        else
            echo "  PID: $pid (${process_info[$pid]}) - STOPPED"
        fi
    done
    
    echo
    echo "System Resources:"
    echo "  Load Average: $(uptime | awk '{print $NF}')"
    echo "  Memory Usage: $(free -h | awk '/^Mem:/ {print $3 "/" $2}')"
}

monitor_processes() {
    while true; do
        {
            echo "=== Process Monitor Report $(date) ==="
            
            # Check process health
            for pid in "${managed_processes[@]}"; do
                if ! kill -0 "$pid" 2>/dev/null; then
                    log_message "WARN" "Process $pid (${process_info[$pid]}) has stopped"
                fi
            done
            
            # Resource usage summary
            echo "Resource Usage Summary:"
            ps -p "${managed_processes[@]}" -o pid,ppid,%cpu,%mem,cmd 2>/dev/null || true
            
        } > >(tee -a "$LOG_DIR/monitor.log" >/dev/null)
        
        sleep 10
    done
}

#===============================================
# COMMAND INTERFACE
#===============================================

setup_command_interface() {
    mkfifo "$COMMAND_PIPE" "$RESPONSE_PIPE"
    
    {
        while true; do
            if read -r command < "$COMMAND_PIPE"; then
                case "$command" in
                    "status")
                        show_status > "$RESPONSE_PIPE"
                        ;;
                    "start_cpu")
                        local pid
                        pid=$(start_cpu_worker $((${#managed_processes[@]} + 1)))
                        echo "Started CPU worker (PID: $pid)" > "$RESPONSE_PIPE"
                        ;;
                    "start_io")
                        local pid
                        pid=$(start_io_worker $((${#managed_processes[@]} + 1)))
                        echo "Started I/O worker (PID: $pid)" > "$RESPONSE_PIPE"
                        ;;
                    "quit")
                        echo "Shutting down..." > "$RESPONSE_PIPE"
                        cleanup_handler
                        ;;
                    *)
                        echo "Unknown command: $command" > "$RESPONSE_PIPE"
                        ;;
                esac
            fi
        done
    } &
}

#===============================================
# INITIALIZATION
#===============================================

initialize() {
    # Create log directory
    mkdir -p "$LOG_DIR"
    
    # Set up signal handlers
    trap cleanup_handler INT TERM EXIT
    trap status_handler USR1
    trap reload_handler USR2
    
    # Initialize logging
    log_message "INFO" "Process Manager starting (PID: $$)"
    log_message "INFO" "Log directory: $LOG_DIR"
    
    # Set up command interface
    setup_command_interface
    
    log_message "INFO" "Initialization completed"
}

#===============================================
# MAIN PROGRAM
#===============================================

main() {
    initialize
    
    # Start initial workers
    start_worker_process 1 "cpu"
    start_worker_process 2 "io"
    start_worker_process 3 "network"
    
    # Start monitoring
    monitor_processes &
    local monitor_pid=$!
    
    log_message "INFO" "Process manager fully operational"
    log_message "INFO" "Send SIGUSR1 for status: kill -USR1 $$"
    log_message "INFO" "Send commands to: $COMMAND_PIPE"
    
    # Main loop
    while true; do
        sleep 5
        
        # Cleanup stopped processes from our tracking
        local active_processes=()
        for pid in "${managed_processes[@]}"; do
            if kill -0 "$pid" 2>/dev/null; then
                active_processes+=("$pid")
            else
                unset process_info["$pid"]
                unset process_logs["$pid"]
            fi
        done
        managed_processes=("${active_processes[@]}")
        
        # Check if we have any processes left
        if [[ ${#managed_processes[@]} -eq 0 ]]; then
            log_message "WARN" "No active processes remaining"
            # Optionally restart some workers or exit
        fi
    done
}

main "$@"
```

**Explanation:**
- Implements comprehensive process management with multiple worker types
- Uses advanced signal handling for different management operations
- Provides real-time process monitoring and resource usage tracking
- Implements command interface using named pipes
- Demonstrates proper cleanup and resource management

</details>

---

## 🔒 Error Handling and Debugging

📊 **Chapter 10 of 13**
🎯 **Learning Objectives:**
- Implement robust error handling strategies
- Master debugging techniques and tools
- Set up logging and monitoring systems
- Create comprehensive testing frameworks

⏱️ **Estimated Reading Time:** 30 minutes
📋 **Prerequisites:** Chapters 1-9

### Error Handling Strategies

Comprehensive error handling approaches:

```bash
#!/bin/bash
# error_handling.sh - Comprehensive error handling strategies

# Enable strict error handling
set -euo pipefail

echo "=== Basic Error Handling ==="

# Function with error handling
safe_operation() {
    local operation="$1"
    local file="$2"
    
    case "$operation" in
        "read")
            if [[ ! -f "$file" ]]; then
                echo "Error: File '$file' does not exist" >&2
                return 1
            fi
            
            if [[ ! -r "$file" ]]; then
                echo "Error: File '$file' is not readable" >&2
                return 2
            fi
            
            cat "$file"
            ;;
        "write")
            local dir
            dir=$(dirname "$file")
            
            if [[ ! -d "$dir" ]]; then
                echo "Error: Directory '$dir' does not exist" >&2
                return 1
            fi
            
            if [[ ! -w "$dir" ]]; then
                echo "Error: Directory '$dir' is not writable" >&2
                return 2
            fi
            
            echo "Safe write operation to $file"
            ;;
        *)
            echo "Error: Unknown operation '$operation'" >&2
            return 3
            ;;
    esac
}

# Test error handling
echo "Testing safe operations:"
safe_operation "read" "/etc/passwd" && echo "Read successful"
safe_operation "read" "/nonexistent/file" || echo "Read failed with code $?"
safe_operation "write" "/tmp/test" && echo "Write check successful"
safe_operation "invalid" "file" || echo "Invalid operation failed with code $?"

echo
echo "=== Advanced Error Handling ==="

# Error handling with logging
ERROR_LOG="/tmp/script_errors.log"
DEBUG_LOG="/tmp/script_debug.log"

# Logging functions
log_error() {
    local message="$1"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    echo "[$timestamp] ERROR: $message" | tee -a "$ERROR_LOG" >&2
}

log_debug() {
    local message="$1"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    [[ "${DEBUG:-}" == "1" ]] && echo "[$timestamp] DEBUG: $message" | tee -a "$DEBUG_LOG"
}

log_info() {
    local message="$1"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    echo "[$timestamp] INFO: $message"
}

# Function with comprehensive error handling
process_file() {
    local input_file="$1"
    local output_file="$2"
    
    log_debug "Starting file processing: $input_file -> $output_file"
    
    # Validate input
    if [[ -z "$input_file" ]] || [[ -z "$output_file" ]]; then
        log_error "Missing required parameters"
        return 1
    fi
    
    if [[ ! -f "$input_file" ]]; then
        log_error "Input file does not exist: $input_file"
        return 2
    fi
    
    # Check file size
    local file_size
    file_size=$(stat -c%s "$input_file" 2>/dev/null || stat -f%z "$input_file" 2>/dev/null)
    
    if [[ "$file_size" -eq 0 ]]; then
        log_error "Input file is empty: $input_file"
        return 3
    fi
    
    log_debug "Input file size: $file_size bytes"
    
    # Process file with error checking
    if ! cp "$input_file" "$output_file"; then
        log_error "Failed to copy file"
        return 4
    fi
    
    log_info "File processed successfully: $input_file -> $output_file"
    return 0
}

# Test with debug enabled
DEBUG=1
echo "Testing file processing with debugging:"
echo "Test content" > /tmp/test_input.txt
process_file "/tmp/test_input.txt" "/tmp/test_output.txt"
process_file "/nonexistent.txt" "/tmp/test_output.txt" || echo "Expected failure"

echo
echo "=== Error Recovery Patterns ==="

# Retry mechanism
retry_operation() {
    local max_attempts="$1"
    local delay="$2"
    shift 2
    local command=("$@")
    
    local attempt=1
    while [[ $attempt -le $max_attempts ]]; do
        log_debug "Attempt $attempt/$max_attempts: ${command[*]}"
        
        if "${command[@]}"; then
            log_info "Operation successful on attempt $attempt"
            return 0
        else
            local exit_code=$?
            log_error "Attempt $attempt failed with exit code $exit_code"
            
            if [[ $attempt -lt $max_attempts ]]; then
                log_info "Retrying in $delay seconds..."
                sleep "$delay"
            fi
        fi
        
        ((attempt++))
    done
    
    log_error "All $max_attempts attempts failed"
    return 1
}

# Test retry mechanism
echo "Testing retry mechanism:"
# This will fail but demonstrate retry
retry_operation 3 2 ls /nonexistent/directory || echo "All retries exhausted"

# Clean up test files
rm -f /tmp/test_input.txt /tmp/test_output.txt
```

### Debugging Techniques

Advanced debugging methods and tools:

```bash
#!/bin/bash
# debugging_techniques.sh - Advanced debugging techniques

echo "=== Debug Mode Control ==="

# Debug mode toggle
DEBUG_MODE=${DEBUG_MODE:-0}
VERBOSE_MODE=${VERBOSE_MODE:-0}

debug_print() {
    [[ "$DEBUG_MODE" -eq 1 ]] && echo "DEBUG: $*" >&2
}

verbose_print() {
    [[ "$VERBOSE_MODE" -eq 1 ]] && echo "VERBOSE: $*"
}

# Function with debug instrumentation
complex_function() {
    local param1="$1"
    local param2="$2"
    
    debug_print "Entering complex_function with params: '$param1', '$param2'"
    verbose_print "Function called with $# parameters"
    
    # Validate parameters
    if [[ -z "$param1" ]]; then
        debug_print "param1 is empty"
        return 1
    fi
    
    # Simulate complex processing
    local result
    if [[ "$param1" == "error" ]]; then
        debug_print "Simulating error condition"
        return 2
    fi
    
    result="processed_${param1}_${param2}"
    debug_print "Processing result: $result"
    
    echo "$result"
    debug_print "Exiting complex_function successfully"
    return 0
}

echo "Testing with debug mode off:"
complex_function "test" "data"

echo
echo "Testing with debug mode on:"
DEBUG_MODE=1 VERBOSE_MODE=1
complex_function "test" "data"
complex_function "error" "data" || echo "Function failed as expected"

echo
echo "=== Trace Execution ==="

# Function to trace execution
trace_execution() {
    # Enable execution tracing
    set -x
    
    local file="/tmp/trace_test.txt"
    echo "Creating test file"
    echo "test content" > "$file"
    
    echo "Reading test file"
    cat "$file"
    
    echo "Processing content"
    local content
    content=$(cat "$file" | tr '[:lower:]' '[:upper:]')
    echo "Processed: $content"
    
    echo "Cleaning up"
    rm "$file"
    
    # Disable execution tracing
    set +x
}

echo "Function execution with tracing:"
trace_execution

echo
echo "=== Debugging with Breakpoints ==="

# Simulated breakpoint function
debug_breakpoint() {
    local message="$1"
    if [[ "$DEBUG_MODE" -eq 1 ]]; then
        echo "BREAKPOINT: $message"
        echo "Variables at this point:"
        echo "  PWD: $PWD"
        echo "  User: $USER"
        echo "  Args: $*"
        read -p "Press Enter to continue..." -r
    fi
}

# Function with breakpoints
function_with_breakpoints() {
    local data="$1"
    debug_breakpoint "Starting function with data: $data"
    
    local processed_data="${data}_processed"
    debug_breakpoint "Data processed: $processed_data"
    
    echo "$processed_data"
    debug_breakpoint "Function completed"
}

# Test breakpoints (will only activate if DEBUG_MODE=1)
echo "Testing breakpoints (set DEBUG_MODE=1 to activate):"
function_with_breakpoints "test_data"

echo
echo "=== Stack Trace Implementation ==="

# Simple stack trace function
print_stack_trace() {
    local frame=0
    echo "Stack trace:"
    
    while caller $frame; do
        ((frame++))
    done | while read line func file; do
        echo "  at $func() in $file:$line"
    done
}

# Function that calls stack trace on error
function_with_stack_trace() {
    local param="$1"
    
    if [[ "$param" == "error" ]]; then
        echo "Error occurred in function_with_stack_trace"
        print_stack_trace
        return 1
    fi
    
    echo "Function executed successfully"
}

# Wrapper function to demonstrate nested calls
wrapper_function() {
    echo "In wrapper function"
    function_with_stack_trace "$1"
}

echo "Testing stack trace:"
wrapper_function "normal"
echo
wrapper_function "error" || echo "Function failed with stack trace"
```

### Logging and Monitoring

Setting up comprehensive logging systems:

```bash
#!/bin/bash
# logging_monitoring.sh - Comprehensive logging and monitoring

echo "=== Logging System Setup ==="

# Logging configuration
readonly LOG_DIR="/tmp/bash_logs"
readonly LOG_FILE="$LOG_DIR/application.log"
readonly ERROR_LOG="$LOG_DIR/errors.log"
readonly DEBUG_LOG="$LOG_DIR/debug.log"
readonly AUDIT_LOG="$LOG_DIR/audit.log"

# Log levels
readonly LOG_LEVEL_ERROR=1
readonly LOG_LEVEL_WARN=2
readonly LOG_LEVEL_INFO=3
readonly LOG_LEVEL_DEBUG=4

# Current log level (can be set via environment)
CURRENT_LOG_LEVEL=${LOG_LEVEL:-$LOG_LEVEL_INFO}

# Initialize logging
init_logging() {
    mkdir -p "$LOG_DIR"
    
    # Set up log rotation
    for log in "$LOG_FILE" "$ERROR_LOG" "$DEBUG_LOG" "$AUDIT_LOG"; do
        if [[ -f "$log" ]] && [[ $(stat -c%s "$log" 2>/dev/null || stat -f%z "$log" 2>/dev/null) -gt 1048576 ]]; then
            mv "$log" "${log}.old"
        fi
    done
}

# Logging functions
log() {
    local level="$1"
    local message="$2"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    local caller_info="${BASH_SOURCE[2]##*/}:${BASH_LINENO[1]}:${FUNCNAME[2]}"
    
    case "$level" in
        "ERROR")
            [[ $CURRENT_LOG_LEVEL -ge $LOG_LEVEL_ERROR ]] && \
                echo "[$timestamp] [ERROR] [$caller_info] $message" | tee -a "$LOG_FILE" "$ERROR_LOG" >&2
            ;;
        "WARN")
            [[ $CURRENT_LOG_LEVEL -ge $LOG_LEVEL_WARN ]] && \
                echo "[$timestamp] [WARN] [$caller_info] $message" | tee -a "$LOG_FILE"
            ;;
        "INFO")
            [[ $CURRENT_LOG_LEVEL -ge $LOG_LEVEL_INFO ]] && \
                echo "[$timestamp] [INFO] [$caller_info] $message" | tee -a "$LOG_FILE"
            ;;
        "DEBUG")
            [[ $CURRENT_LOG_LEVEL -ge $LOG_LEVEL_DEBUG ]] && \
                echo "[$timestamp] [DEBUG] [$caller_info] $message" | tee -a "$LOG_FILE" "$DEBUG_LOG"
            ;;
    esac
}

# Audit logging
audit_log() {
    local action="$1"
    local details="$2"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    local user="${USER:-unknown}"
    
    echo "[$timestamp] [$user] [$action] $details" >> "$AUDIT_LOG"
}

# Performance monitoring
performance_monitor() {
    local operation="$1"
    local start_time
    local end_time
    local duration
    
    start_time=$(date +%s.%N)
    
    # Execute the operation
    "$@"
    local exit_code=$?
    
    end_time=$(date +%s.%N)
    duration=$(echo "$end_time - $start_time" | bc -l 2>/dev/null || echo "N/A")
    
    log "INFO" "Operation '$operation' completed in ${duration}s with exit code $exit_code"
    audit_log "PERFORMANCE" "$operation took ${duration}s"
    
    return $exit_code
}

# Initialize logging
init_logging

echo "Testing logging system:"
log "INFO" "Application started"
log "DEBUG" "Debug information"
log "WARN" "Warning message"
log "ERROR" "Error occurred"

audit_log "USER_ACTION" "User performed test operation"

echo
echo "Testing performance monitoring:"
performance_monitor "sleep_test" sleep 2

echo
echo "Log files created:"
ls -la "$LOG_DIR"

echo
echo "Sample log content:"
echo "--- Application Log ---"
head -3 "$LOG_FILE"
echo "--- Error Log ---"
head -3 "$ERROR_LOG" 2>/dev/null || echo "No errors logged"
```

### Testing Scripts

Creating comprehensive testing frameworks:

```bash
#!/bin/bash
# testing_framework.sh - Comprehensive testing framework

echo "=== Bash Testing Framework ==="

# Test framework variables
TESTS_RUN=0
TESTS_PASSED=0
TESTS_FAILED=0
declare -a FAILED_TESTS=()

# Test assertion functions
assert_equals() {
    local expected="$1"
    local actual="$2"
    local test_name="${3:-test_$TESTS_RUN}"
    
    ((TESTS_RUN++))
    
    if [[ "$expected" == "$actual" ]]; then
        echo "✓ PASS: $test_name"
        ((TESTS_PASSED++))
        return 0
    else
        echo "✗ FAIL: $test_name"
        echo "  Expected: '$expected'"
        echo "  Actual:   '$actual'"
        ((TESTS_FAILED++))
        FAILED_TESTS+=("$test_name")
        return 1
    fi
}

assert_not_equals() {
    local not_expected="$1"
    local actual="$2"
    local test_name="${3:-test_$TESTS_RUN}"
    
    ((TESTS_RUN++))
    
    if [[ "$not_expected" != "$actual" ]]; then
        echo "✓ PASS: $test_name"
        ((TESTS_PASSED++))
        return 0
    else
        echo "✗ FAIL: $test_name"
        echo "  Should not equal: '$not_expected'"
        echo "  Actual:          '$actual'"
        ((TESTS_FAILED++))
        FAILED_TESTS+=("$test_name")
        return 1
    fi
}

assert_true() {
    local condition="$1"
    local test_name="${2:-test_$TESTS_RUN}"
    
    ((TESTS_RUN++))
    
    if eval "$condition"; then
        echo "✓ PASS: $test_name"
        ((TESTS_PASSED++))
        return 0
    else
        echo "✗ FAIL: $test_name"
        echo "  Condition failed: '$condition'"
        ((TESTS_FAILED++))
        FAILED_TESTS+=("$test_name")
        return 1
    fi
}

assert_file_exists() {
    local file="$1"
    local test_name="${2:-file_exists_test}"
    
    assert_true "[[ -f '$file' ]]" "$test_name"
}

# Test suite runner
run_test_suite() {
    local suite_name="$1"
    echo "Running test suite: $suite_name"
    echo "================================"
}

# Sample functions to test
add_numbers() {
    local a="$1"
    local b="$2"
    echo $((a + b))
}

string_reverse() {
    local str="$1"
    local reversed=""
    local i
    
    for ((i=${#str}-1; i>=0; i--)); do
        reversed="${reversed}${str:$i:1}"
    done
    
    echo "$reversed"
}

is_even() {
    local number="$1"
    [[ $((number % 2)) -eq 0 ]]
}

# Test cases
run_test_suite "Basic Math Tests"
assert_equals "5" "$(add_numbers 2 3)" "add_positive_numbers"
assert_equals "0" "$(add_numbers -5 5)" "add_negative_positive"
assert_equals "-3" "$(add_numbers -1 -2)" "add_negative_numbers"

echo
run_test_suite "String Tests"
assert_equals "olleh" "$(string_reverse "hello")" "reverse_string"
assert_equals "" "$(string_reverse "")" "reverse_empty_string"
assert_equals "a" "$(string_reverse "a")" "reverse_single_char"

echo
run_test_suite "Logic Tests"
assert_true "is_even 2" "even_number_test"
assert_true "! is_even 3" "odd_number_test"
assert_true "is_even 0" "zero_is_even"

echo
run_test_suite "File Tests"
# Create test file
echo "test content" > /tmp/test_file.txt
assert_file_exists "/tmp/test_file.txt" "test_file_creation"
assert_true "[[ -r /tmp/test_file.txt ]]" "test_file_readable"

# Clean up
rm -f /tmp/test_file.txt

echo
# Test summary
echo "================================"
echo "Test Summary:"
echo "Tests run:    $TESTS_RUN"
echo "Tests passed: $TESTS_PASSED"
echo "Tests failed: $TESTS_FAILED"

if [[ $TESTS_FAILED -gt 0 ]]; then
    echo
    echo "Failed tests:"
    for test in "${FAILED_TESTS[@]}"; do
        echo "  - $test"
    done
    exit 1
else
    echo "All tests passed! 🎉"
    exit 0
fi
```

### ⚠️ Common Pitfalls

1. **Ignoring Exit Codes**: Always check return values of critical operations
2. **Poor Error Messages**: Provide specific, actionable error messages
3. **No Cleanup**: Ensure resources are cleaned up even on errors
4. **Silent Failures**: Don't suppress important error information

### ✅ Best Practices

1. **Use set -euo pipefail**: Enable strict error handling
2. **Comprehensive Logging**: Log at appropriate levels with context
3. **Input Validation**: Validate all inputs before processing
4. **Graceful Degradation**: Handle errors gracefully when possible
5. **Testing**: Write tests for critical functionality

### 🏋️ Exercise 10: Error Handling Framework

**Difficulty:** 🔴 Advanced
**Estimated Time:** 60 minutes

Create a script called `robust_processor.sh` that:
1. Implements comprehensive error handling with custom error types
2. Provides detailed logging with multiple levels
3. Includes retry mechanisms with exponential backoff
4. Has a complete testing suite
5. Monitors performance and generates reports

<details>
<summary>💡 Click to see hints</summary>

- Use associative arrays for error codes and messages
- Implement custom exception-like error handling
- Create comprehensive logging with rotation
- Use background processes for monitoring
- Include performance metrics collection

</details>

<details>
<summary>✅ Click to see solution</summary>

```bash
#!/bin/bash
# robust_processor.sh - Comprehensive error handling and monitoring system

set -euo pipefail

#===============================================
# CONFIGURATION
#===============================================

readonly SCRIPT_NAME="robust_processor"
readonly VERSION="1.0.0"
readonly LOG_DIR="/tmp/${SCRIPT_NAME}_logs"
readonly CONFIG_FILE="${LOG_DIR}/config.conf"
readonly METRICS_FILE="${LOG_DIR}/metrics.json"

# Error codes
declare -A ERROR_CODES=(
    [SUCCESS]=0
    [GENERAL_ERROR]=1
    [FILE_NOT_FOUND]=2
    [PERMISSION_DENIED]=3
    [INVALID_INPUT]=4
    [NETWORK_ERROR]=5
    [TIMEOUT_ERROR]=6
    [RESOURCE_EXHAUSTED]=7
)

declare -A ERROR_MESSAGES=(
    [SUCCESS]="Operation completed successfully"
    [GENERAL_ERROR]="General error occurred"
    [FILE_NOT_FOUND]="File or directory not found"
    [PERMISSION_DENIED]="Permission denied"
    [INVALID_INPUT]="Invalid input provided"
    [NETWORK_ERROR]="Network operation failed"
    [TIMEOUT_ERROR]="Operation timed out"
    [RESOURCE_EXHAUSTED]="System resources exhausted"
)

#===============================================
# LOGGING SYSTEM
#===============================================

init_logging() {
    mkdir -p "$LOG_DIR"
    
    # Initialize configuration if it doesn't exist
    if [[ ! -f "$CONFIG_FILE" ]]; then
        cat > "$CONFIG_FILE" << EOF
# Robust Processor Configuration
LOG_LEVEL=INFO
MAX_RETRIES=3
RETRY_DELAY=2
TIMEOUT=30
ENABLE_MONITORING=true
EOF
    fi
    
    source "$CONFIG_FILE"
}

log() {
    local level="$1"
    local message="$2"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    local pid="$$"
    local caller="${FUNCNAME[2]:-main}"
    
    echo "[$timestamp] [$pid] [$level] [$caller] $message" | \
        tee -a "${LOG_DIR}/application.log"
    
    # Also log to specific level files
    case "$level" in
        "ERROR") echo "[$timestamp] [$pid] $message" >> "${LOG_DIR}/errors.log" ;;
        "WARN")  echo "[$timestamp] [$pid] $message" >> "${LOG_DIR}/warnings.log" ;;
        "DEBUG") [[ "${LOG_LEVEL:-INFO}" == "DEBUG" ]] && \
                 echo "[$timestamp] [$pid] $message" >> "${LOG_DIR}/debug.log" ;;
    esac
}

#===============================================
# ERROR HANDLING SYSTEM
#===============================================

throw_error() {
    local error_type="$1"
    local context="${2:-No additional context}"
    local exit_code="${ERROR_CODES[$error_type]}"
    
    log "ERROR" "${ERROR_MESSAGES[$error_type]}: $context"
    
    # Update metrics
    update_metrics "errors" "$error_type"
    
    return "$exit_code"
}

retry_with_backoff() {
    local max_attempts="${MAX_RETRIES:-3}"
    local base_delay="${RETRY_DELAY:-2}"
    local max_delay=60
    shift
    local command=("$@")
    
    local attempt=1
    local delay="$base_delay"
    
    while [[ $attempt -le $max_attempts ]]; do
        log "INFO" "Attempt $attempt/$max_attempts: ${command[*]}"
        
        if "${command[@]}"; then
            log "INFO" "Operation successful on attempt $attempt"
            update_metrics "retries" "success_$attempt"
            return 0
        else
            local exit_code=$?
            log "WARN" "Attempt $attempt failed with exit code $exit_code"
            
            if [[ $attempt -lt $max_attempts ]]; then
                log "INFO" "Retrying in ${delay}s..."
                sleep "$delay"
                delay=$(( delay > max_delay ? max_delay : delay * 2 ))
            fi
        fi
        
        ((attempt++))
    done
    
    update_metrics "retries" "exhausted"
    throw_error "GENERAL_ERROR" "All $max_attempts retry attempts failed"
}

#===============================================
# MONITORING SYSTEM
#===============================================

init_metrics() {
    cat > "$METRICS_FILE" << EOF
{
  "start_time": "$(date -Iseconds)",
  "operations": {},
  "errors": {},
  "retries": {},
  "performance": {}
}
EOF
}

update_metrics() {
    local category="$1"
    local key="$2"
    local value="${3:-1}"
    
    # Simple JSON update (in real implementation, use jq or similar)
    local temp_file="${METRICS_FILE}.tmp"
    
    if [[ -f "$METRICS_FILE" ]]; then
        # Basic metrics update (simplified for this example)
        cp "$METRICS_FILE" "$temp_file"
        echo "Updated metrics: $category.$key = $value" >> "${LOG_DIR}/metrics.log"
    fi
}

performance_monitor() {
    local operation_name="$1"
    shift
    local command=("$@")
    
    local start_time=$(date +%s.%N)
    local start_memory=$(ps -o vsz= -p $$ | tr -d ' ')
    
    log "DEBUG" "Starting performance monitoring for: $operation_name"
    
    "${command[@]}"
    local exit_code=$?
    
    local end_time=$(date +%s.%N)
    local end_memory=$(ps -o vsz= -p $$ | tr -d ' ')
    local duration=$(echo "$end_time - $start_time" | bc -l 2>/dev/null || echo "0")
    local memory_diff=$((end_memory - start_memory))
    
    log "INFO" "Performance: $operation_name took ${duration}s, memory change: ${memory_diff}KB"
    update_metrics "performance" "$operation_name" "$duration"
    
    return $exit_code
}

#===============================================
# CORE PROCESSING FUNCTIONS
#===============================================

validate_input() {
    local input="$1"
    local input_type="$2"
    
    case "$input_type" in
        "file")
            [[ -f "$input" ]] || throw_error "FILE_NOT_FOUND" "$input"
            [[ -r "$input" ]] || throw_error "PERMISSION_DENIED" "Cannot read $input"
            ;;
        "directory")
            [[ -d "$input" ]] || throw_error "FILE_NOT_FOUND" "$input"
            [[ -x "$input" ]] || throw_error "PERMISSION_DENIED" "Cannot access $input"
            ;;
        "number")
            [[ "$input" =~ ^[0-9]+$ ]] || throw_error "INVALID_INPUT" "Not a number: $input"
            ;;
        *)
            throw_error "INVALID_INPUT" "Unknown validation type: $input_type"
            ;;
    esac
}

process_file() {
    local input_file="$1"
    local output_file="$2"
    
    log "INFO" "Processing file: $input_file -> $output_file"
    
    validate_input "$input_file" "file"
    
    # Simulate processing with potential failure
    if [[ "$(basename "$input_file")" == "error_file.txt" ]]; then
        throw_error "GENERAL_ERROR" "Simulated processing error"
    fi
    
    # Perform actual processing
    if cp "$input_file" "$output_file"; then
        log "INFO" "File processed successfully"
        update_metrics "operations" "file_processed"
        return 0
    else
        throw_error "GENERAL_ERROR" "Failed to process file"
    fi
}

#===============================================
# TESTING FRAMEWORK
#===============================================

run_tests() {
    local test_count=0
    local test_passed=0
    
    echo "Running test suite..."
    
    # Test 1: Successful operation
    ((test_count++))
    echo "Test content" > /tmp/test_input.txt
    if process_file "/tmp/test_input.txt" "/tmp/test_output.txt" 2>/dev/null; then
        echo "✓ Test 1 PASSED: Successful file processing"
        ((test_passed++))
    else
        echo "✗ Test 1 FAILED: Successful file processing"
    fi
    
    # Test 2: File not found
    ((test_count++))
    if ! process_file "/nonexistent/file.txt" "/tmp/output.txt" 2>/dev/null; then
        echo "✓ Test 2 PASSED: File not found error handling"
        ((test_passed++))
    else
        echo "✗ Test 2 FAILED: Should have failed for nonexistent file"
    fi
    
    # Test 3: Input validation
    ((test_count++))
    if validate_input "123" "number" 2>/dev/null; then
        echo "✓ Test 3 PASSED: Number validation"
        ((test_passed++))
    else
        echo "✗ Test 3 FAILED: Number validation"
    fi
    
    # Test 4: Retry mechanism
    ((test_count++))
    echo "error_content" > /tmp/error_file.txt
    if ! retry_with_backoff 2 1 process_file "/tmp/error_file.txt" "/tmp/output.txt" 2>/dev/null; then
        echo "✓ Test 4 PASSED: Retry mechanism with failure"
        ((test_passed++))
    else
        echo "✗ Test 4 FAILED: Retry should have failed"
    fi
    
    echo
    echo "Test Results: $test_passed/$test_count passed"
    
    # Cleanup
    rm -f /tmp/test_input.txt /tmp/test_output.txt /tmp/error_file.txt
    
    [[ $test_passed -eq $test_count ]]
}

#===============================================
# MAIN PROGRAM
#===============================================

show_help() {
    cat << EOF
$SCRIPT_NAME v$VERSION - Robust File Processor

Usage: $0 [OPTIONS] [COMMAND] [ARGS...]

Commands:
  process <input> <output>  Process a file
  test                      Run test suite
  monitor                   Show monitoring information
  help                      Show this help

Options:
  --debug                   Enable debug logging
  --config <file>           Use custom config file

Examples:
  $0 process input.txt output.txt
  $0 --debug test
  $0 monitor
EOF
}

main() {
    # Initialize systems
    init_logging
    init_metrics
    
    log "INFO" "$SCRIPT_NAME v$VERSION starting"
    
    # Parse command line arguments
    while [[ $# -gt 0 ]]; do
        case "$1" in
            --debug)
                LOG_LEVEL="DEBUG"
                log "DEBUG" "Debug mode enabled"
                shift
                ;;
            --config)
                CONFIG_FILE="$2"
                source "$CONFIG_FILE"
                log "INFO" "Using config file: $CONFIG_FILE"
                shift 2
                ;;
            process)
                if [[ $# -lt 3 ]]; then
                    throw_error "INVALID_INPUT" "Process command requires input and output files"
                fi
                
                performance_monitor "file_processing" \
                    retry_with_backoff \
                    process_file "$2" "$3"
                shift 3
                ;;
            test)
                run_tests
                shift
                ;;
            monitor)
                echo "=== Monitoring Information ==="
                echo "Log directory: $LOG_DIR"
                echo "Configuration: $CONFIG_FILE"
                echo "Metrics: $METRICS_FILE"
                echo
                echo "Recent logs:"
                tail -5 "${LOG_DIR}/application.log" 2>/dev/null || echo "No logs found"
                shift
                ;;
            help|--help|-h)
                show_help
                exit 0
                ;;
            *)
                throw_error "INVALID_INPUT" "Unknown command or option: $1"
                ;;
        esac
    done
    
    # If no command provided, show help
    if [[ $# -eq 0 ]] && [[ "${1:-}" != "monitor" ]]; then
        show_help
        exit 0
    fi
    
    log "INFO" "$SCRIPT_NAME completed successfully"
}

# Cleanup on exit
trap 'log "INFO" "Script interrupted, cleaning up..."; exit 130' INT TERM

main "$@"
```

**Explanation:**
- Implements a comprehensive error handling system with custom error types and codes
- Provides multi-level logging with automatic log rotation
- Includes retry mechanisms with exponential backoff for resilience
- Features performance monitoring and metrics collection
- Contains a complete testing framework with multiple test cases
- Demonstrates advanced Bash error handling patterns and best practices

</details>

---

## 📦 Script Organization and Modularity

Organizing Bash scripts for maintainability and reusability.

### Script Structure

Best practices for organizing script files:

```📚 Documentation/🐚 Bash-Documentation.md#L7986-8020
#!/bin/bash
# my_script.sh - Example of well-structured script
# Version: 1.0.0
# Description: Demonstrates good script organization
# Author: Your Name
# Usage: ./my_script.sh [options] [arguments]

set -euo pipefail

#===============================================
# CONFIGURATION
#===============================================

readonly SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
readonly SCRIPT_NAME="$(basename "$0")"
readonly LOG_FILE="/var/log/${SCRIPT_NAME%.sh}.log"
readonly CONFIG_FILE="$SCRIPT_DIR/config.conf"

# Default values
DEFAULT_TIMEOUT=30
DEFAULT_RETRIES=3

#===============================================
# UTILITY FUNCTIONS
#===============================================

log() {
    local level="$1"
    shift
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] [$level] $*" | tee -a "$LOG_FILE"
}

die() {
    log "ERROR" "$*"
    exit 1
}

#===============================================
# MAIN FUNCTIONS
#===============================================

main() {
    log "INFO" "Starting $SCRIPT_NAME"
    
    # Script logic here
    
    log "INFO" "Completed successfully"
}

# Only run main if script is executed directly
if [[ "${BASH_SOURCE[0]}" == "${0}" ]]; then
    main "$@"
fi
```

### Including External Scripts

Methods for including and sourcing external scripts:

```📚 Documentation/🐚 Bash-Documentation.md#L8021-8070
#!/bin/bash
# main_script.sh - Demonstrates script inclusion

# Source utility functions
source "$(dirname "$0")/lib/utils.sh"
source "$(dirname "$0")/lib/logging.sh"

# Alternative: check if file exists before sourcing
if [[ -f "$(dirname "$0")/lib/optional.sh" ]]; then
    source "$(dirname "$0")/lib/optional.sh"
fi

# Function to safely source files
safe_source() {
    local file="$1"
    if [[ -f "$file" && -r "$file" ]]; then
        source "$file"
        return 0
    else
        echo "Warning: Cannot source $file" >&2
        return 1
    fi
}

# Use safe sourcing
safe_source "$(dirname "$0")/config/settings.conf"
safe_source "$(dirname "$0")/lib/database.sh"

# Example directory structure:
# project/
# ├── main_script.sh
# ├── config/
# │   └── settings.conf
# └── lib/
#     ├── utils.sh
#     ├── logging.sh
#     └── database.sh
```

### Creating Libraries

Building reusable function libraries:

```📚 Documentation/🐚 Bash-Documentation.md#L8071-8150
#!/bin/bash
# lib/utils.sh - Utility function library

# Prevent multiple inclusions
if [[ -n "${UTILS_LOADED:-}" ]]; then
    return 0
fi
readonly UTILS_LOADED=1

#===============================================
# STRING UTILITIES
#===============================================

# Check if string is empty
is_empty() {
    [[ -z "${1:-}" ]]
}

# Trim whitespace from string
trim() {
    local var="$1"
    # Remove leading whitespace
    var="${var#"${var%%[![:space:]]*}"}"
    # Remove trailing whitespace
    var="${var%"${var##*[![:space:]]}"}"
    echo "$var"
}

# Convert to uppercase
to_upper() {
    echo "${1^^}"
}

# Convert to lowercase
to_lower() {
    echo "${1,,}"
}

#===============================================
# FILE UTILITIES
#===============================================

# Check if file is readable
is_readable() {
    [[ -f "$1" && -r "$1" ]]
}

# Get file size in bytes
file_size() {
    if [[ -f "$1" ]]; then
        stat -c%s "$1" 2>/dev/null || stat -f%z "$1" 2>/dev/null
    else
        return 1
    fi
}

# Create directory if it doesn't exist
ensure_dir() {
    local dir="$1"
    if [[ ! -d "$dir" ]]; then
        mkdir -p "$dir"
    fi
}

#===============================================
# VALIDATION UTILITIES
#===============================================

# Check if value is a valid email
is_email() {
    local email="$1"
    [[ "$email" =~ ^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$ ]]
}

# Check if value is a valid IP address
is_ip() {
    local ip="$1"
    [[ "$ip" =~ ^([0-9]{1,3}\.){3}[0-9]{1,3}$ ]]
}

# Check if port is valid
is_valid_port() {
    local port="$1"
    [[ "$port" =~ ^[0-9]+$ && "$port" -ge 1 && "$port" -le 65535 ]]
}
```

### Configuration Management

Handling configuration files and settings:

```📚 Documentation/🐚 Bash-Documentation.md#L8151-8220
#!/bin/bash
# lib/config.sh - Configuration management library

# Configuration file format (config.conf):
# # Comments start with #
# KEY=value
# ANOTHER_KEY="value with spaces"
# NUMERIC_KEY=123

#===============================================
# CONFIGURATION FUNCTIONS
#===============================================

# Load configuration from file
load_config() {
    local config_file="$1"
    
    if [[ ! -f "$config_file" ]]; then
        echo "Error: Configuration file not found: $config_file" >&2
        return 1
    fi
    
    # Read configuration file, ignoring comments and empty lines
    while IFS='=' read -r key value; do
        # Skip comments and empty lines
        [[ "$key" =~ ^[[:space:]]*# ]] && continue
        [[ -z "$key" ]] && continue
        
        # Remove quotes from value
        value="${value%\"}"
        value="${value#\"}"
        value="${value%\'}"
        value="${value#\'}"
        
        # Export as environment variable
        export "$key"="$value"
        
    done < <(grep -E '^[^#]*=' "$config_file")
}

# Get configuration value with default
get_config() {
    local key="$1"
    local default="${2:-}"
    
    if [[ -n "${!key:-}" ]]; then
        echo "${!key}"
    else
        echo "$default"
    fi
}

# Validate required configuration
require_config() {
    local key="$1"
    local description="${2:-$key}"
    
    if [[ -z "${!key:-}" ]]; then
        echo "Error: Required configuration missing: $description" >&2
        return 1
    fi
}

# Example usage:
# load_config "config/app.conf"
# DATABASE_URL=$(get_config "DATABASE_URL" "localhost:5432")
# require_config "API_KEY" "API Key for external service"
```

### ⚠️ Common Pitfalls

1. **Forgetting to make scripts executable**:
   ```bash
   chmod +x script.sh
   ```

2. **Not handling missing dependencies**:
   ```bash
   # Good - check before sourcing
   if ! source lib/utils.sh; then
       echo "Error: Required library missing" >&2
       exit 1
   fi
   ```

3. **Circular dependencies between scripts**

### ✅ Best Practices

1. **Use consistent directory structure**
2. **Document dependencies clearly**
3. **Implement proper error handling**
4. **Use meaningful function and variable names**
5. **Keep functions focused and single-purpose**

### 🏋️ Exercise 12: Modular Script System

Create a modular backup system:

```📚 Documentation/🐚 Bash-Documentation.md#L8221-8280
# Project structure:
# backup_system/
# ├── backup.sh (main script)
# ├── config/
# │   └── backup.conf
# └── lib/
#     ├── logging.sh
#     ├── compression.sh
#     └── notification.sh

# Main script (backup.sh):
#!/bin/bash
source "$(dirname "$0")/lib/logging.sh"
source "$(dirname "$0")/lib/compression.sh"
source "$(dirname "$0")/lib/notification.sh"

main() {
    log_info "Starting backup process"
    
    # Create backup
    if create_backup "/home/user" "/backup/user_$(date +%Y%m%d).tar.gz"; then
        log_info "Backup completed successfully"
        send_notification "Backup completed" "User backup finished successfully"
    else
        log_error "Backup failed"
        send_notification "Backup failed" "User backup encountered errors"
        exit 1
    fi
}

main "$@"
```

---

## 🚀 Advanced Features

📊 **Chapter 11 of 13**
🎯 **Learning Objectives:**
- Master parameter expansion techniques
- Implement command substitution patterns
- Use arithmetic expansion effectively
- Understand brace expansion for automation

⏱️ **Estimated Reading Time:** 25 minutes
📋 **Prerequisites:** Chapters 1-10

### Parameter Expansion

Advanced parameter expansion techniques:

```bash
#!/bin/bash
# parameter_expansion.sh - Advanced parameter expansion techniques

echo "=== Basic Parameter Expansion ==="

# Sample variables
filename="/path/to/document.backup.2024.txt"
text="Hello World Hello Universe"
empty_var=""
unset_var

echo "Filename: $filename"
echo "Text: $text"

echo
echo "=== Default Value Expansion ==="

# Use default value if unset or null
echo "Unset var with default: '${unset_var:-default_value}'"
echo "Empty var with default: '${empty_var:-default_value}'"
echo "Set var with default: '${filename:-default_value}'"

# Assign default value if unset
echo "Before: unset_var='$unset_var'"
echo "With assignment: '${unset_var:=assigned_default}'"
echo "After: unset_var='$unset_var'"

# Display alternate value if set
echo "Alternate if set: '${filename:+Variable is set}'"
echo "Alternate if unset: '${unset_var2:+This won't show}'"

# Error if unset
echo "Testing error expansion:"
# echo "${undefined_var:?Error: Variable must be set}" # Would exit

echo
echo "=== String Length and Substrings ==="

echo "Length of filename: ${#filename}"
echo "Length of text: ${#text}"

# Substring extraction
echo "First 10 characters: '${filename:0:10}'"
echo "Characters 5-15: '${filename:5:10}'"
echo "From position 10: '${filename:10}'"
echo "Last 10 characters: '${filename:(-10)}'"
echo "All but last 4: '${filename:0:(-4)}'"

echo
echo "=== Pattern Matching and Removal ==="

echo "Original filename: $filename"

# Remove from beginning (shortest match)
echo "Remove path (shortest): '${filename#*/}'"

# Remove from beginning (longest match)  
echo "Remove path (longest): '${filename##*/}'"

# Remove from end (shortest match)
echo "Remove extension: '${filename%.*}'"

# Remove from end (longest match)
echo "Remove all extensions: '${filename%%.*}'"

# More complex patterns
path="/usr/local/bin/script.sh"
echo "Path: $path"
echo "Directory: '${path%/*}'"
echo "Basename: '${path##*/}'"
echo "Extension: '${path##*.}'"
echo "Name without extension: '${path##*/}'; echo '${_%.sh}'"

echo
echo "=== Pattern Replacement ==="

echo "Original text: '$text'"

# Replace first occurrence
echo "Replace first 'Hello': '${text/Hello/Hi}'"

# Replace all occurrences
echo "Replace all 'Hello': '${text//Hello/Hi}'"

# Replace at beginning
echo "Replace at beginning: '${text/#Hello/Hi}'"

# Replace at end
echo "Replace at end: '${text/%Universe/Galaxy}'"

# More complex replacements
data="user@domain.com:password123"
echo "Data: $data"
echo "Hide password: '${data/:*/:***}'"

# Replace with patterns
numbers="123-456-7890"
echo "Phone: $numbers"
echo "Format phone: '${numbers//-/.}'"

echo
echo "=== Case Modification (Bash 4.0+) ==="

mixed="Hello World"
echo "Original: '$mixed'"
echo "All uppercase: '${mixed^^}'"
echo "All lowercase: '${mixed,,}'"
echo "First char uppercase: '${mixed^}'"
echo "First char lowercase: '${mixed,}'"

# Pattern-based case modification
text_with_vowels="Hello World"
echo "Uppercase vowels: '${text_with_vowels^^[aeiou]}'"
echo "Lowercase consonants: '${text_with_vowels,,[!aeiou]}'"

echo
echo "=== Array Parameter Expansion ==="

# Array expansion
fruits=("apple" "banana" "cherry" "date")
echo "All fruits: '${fruits[@]}'"
echo "All fruits (string): '${fruits[*]}'"
echo "Number of fruits: '${#fruits[@]}'"
echo "Indices: '${!fruits[@]}'"
echo "First fruit length: '${#fruits[0]}'"

# Array slicing
echo "First 2 fruits: '${fruits[@]:0:2}'"
echo "From index 2: '${fruits[@]:2}'"
echo "Last 2 fruits: '${fruits[@]:(-2)}'"

# Pattern operations on arrays
paths=("/usr/bin/ls" "/bin/cat" "/usr/local/bin/custom")
echo "All paths: ${paths[*]}"
echo "Basenames: ${paths[*]##*/}"
echo "Directories: ${paths[*]%/*}"

echo
echo "=== Variable Name Expansion ==="

# Indirect variable reference
var_name="filename"
echo "Indirect reference: '${!var_name}'"

# Variable names matching pattern
prefix="PATH"
for var in ${!prefix*}; do
    echo "$var = ${!var}"
done
```

### Command Substitution

Advanced command substitution techniques:


        echo
        
        # Memory Information
        echo "=== MEMORY INFORMATION ==="
        free -h
        echo
        
        # Disk Usage
        echo "=== DISK USAGE ==="
        df -h
        echo
        
        # Network Interfaces
        echo "=== NETWORK INTERFACES ==="
        ip addr show | grep -E "(^[0-9]|inet )"
        echo
        
        # Running Services
        echo "=== CRITICAL SERVICES ==="
        for service in sshd cron rsyslog; do
            if systemctl is-active "$service" >/dev/null 2>&1; then
                echo "✓ $service: Running"
            else
                echo "✗ $service: Not running"
            fi
        done
        echo
        ### Command Substitution

        Advanced command substitution techniques:

        ```bash
        #!/bin/bash
        # command_substitution.sh - Advanced command substitution

        echo "=== Basic Command Substitution ==="

        # Modern syntax (preferred)
        current_date=$(date)
        echo "Current date: $current_date"

        # Legacy syntax (avoid)
        current_user=`whoami`
        echo "Current user: $current_user"

        echo
        echo "=== Nested Command Substitution ==="

        # Nested substitution
        echo "Files in current directory: $(ls -1 $(pwd) | wc -l)"

        # Complex nested example
        echo "Largest file: $(ls -la $(find . -type f -name "*.txt" 2>/dev/null | head -1) 2>/dev/null || echo "No files found")"

        echo
        echo "=== Command Substitution with Error Handling ==="

        # Safe command substitution
        safe_command_sub() {
            local command="$1"
            local result
            local exit_code
    
            result=$(eval "$command" 2>/dev/null)
            exit_code=$?
    
            if [[ $exit_code -eq 0 ]]; then
                echo "$result"
            else
                echo "Command failed: $command" >&2
                return $exit_code
            fi
        }

        echo "Safe command substitution:"
        safe_command_sub "date"
        safe_command_sub "nonexistent_command" || echo "Handled error gracefully"

        echo
        echo "=== Advanced Patterns ==="

        # Multi-line command substitution
        config_info=$(cat << 'EOF'
        System Information:
        - Hostname: $(hostname)
        - Uptime: $(uptime | cut -d',' -f1)
        - Load: $(uptime | awk '{print $NF}')
        EOF
        )

        echo "Config info template created"

        # Process list filtering
        running_bash_processes=$(ps aux | grep bash | grep -v grep | wc -l)
        echo "Running bash processes: $running_bash_processes"

        # File processing
        largest_log=$(find /var/log -name "*.log" -type f -exec ls -la {} \; 2>/dev/null | 
                      sort -k5 -nr | head -1 | awk '{print $NF}' || echo "No logs found")
        echo "Largest log file: $largest_log"
        ```

        ### ⚠️ Common Pitfalls

        1. **Using backticks instead of `$()`**:
           ```bash
           # Bad
           result=`command`
   
           # Good
           result=$(command)
           ```

        2. **Not handling command failures**:
           ```bash
           # Bad
           result=$(command_that_might_fail)
   
           # Good
           if result=$(command_that_might_fail 2>/dev/null); then
               echo "Success: $result"
           else
               echo "Command failed"
           fi
           ```

        ### ✅ Best Practices

        1. **Always use `$()` over backticks**
        2. **Quote command substitutions when used as strings**
        3. **Handle potential failures**
        4. **Use local variables in functions**

        ### 🏋️ Exercise 11: Advanced Features Mastery

        Create a system monitoring script that uses all advanced features:

        ```bash
        #!/bin/bash
        # system_monitor.sh - Advanced system monitoring

        monitor_system() {
            local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
            local uptime_info=$(uptime)
            local disk_usage=$(df -h / | awk 'NR==2 {print $5}')
            local memory_usage=$(free | awk 'NR==2{printf "%.2f%%", $3*100/$2}')
    
            echo "[$timestamp] System Status:"
            echo "  Uptime: $uptime_info"
            echo "  Disk Usage: $disk_usage"
            echo "  Memory Usage: $memory_usage"
    
            # Advanced arithmetic
            local load_avg=$(uptime | awk '{print $NF}' | cut -d',' -f1)
            local alert_threshold=2.0
    
            if (( $(echo "$load_avg > $alert_threshold" | bc -l) )); then
                echo "  ⚠️ High load detected: $load_avg"
            fi
    
            # Brace expansion for multiple checks
            for service in {ssh,nginx,mysql}; do
                if systemctl is-active --quiet "$service"; then
                    echo "  ✅ $service is running"
                else
                    echo "  ❌ $service is not running"
                fi
            done
        }

        monitor_system
        ```

        *This documentation is maintained by the community. Last updated: December 2024*

---

## 🚀 Real-World Applications

Practical applications and complete project examples.

### System Administration Scripts

Complete system administration tools:

```bash
#!/bin/bash
# system_admin.sh - Comprehensive system administration toolkit
# Version: 2.0.0
# Description: Complete system monitoring and maintenance

set -euo pipefail

#===============================================
# CONFIGURATION
#===============================================

readonly SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
readonly LOG_DIR="/var/log/sysadmin"
readonly BACKUP_DIR="/var/backups/system"
readonly VERSION="2.0.0"

# Ensure directories exist
mkdir -p "$LOG_DIR" "$BACKUP_DIR"

#===============================================
# LOGGING FUNCTIONS
#===============================================

log() {
    local level="$1"
    shift
    local message="$*"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    
    echo "[$timestamp] [$level] $message" | tee -a "$LOG_DIR/system_admin.log"
    
    # Send critical messages to syslog
    if [[ "$level" == "ERROR" || "$level" == "CRITICAL" ]]; then
        logger -t "system_admin" "$level: $message"
    fi
}

#===============================================
# MONITORING FUNCTIONS
#===============================================

monitor_system_health() {
    local report_file="$LOG_DIR/health_report_$(date +%Y%m%d_%H%M%S).txt"
    
    log "INFO" "Generating system health report"
    
    {
        echo "=== SYSTEM HEALTH REPORT ==="
        echo "Generated: $(date)"
        echo "Hostname: $(hostname)"
        echo
        
        # System uptime and load
        echo "=== SYSTEM STATUS ==="
        uptime
        echo
        
        # Memory usage
        echo "=== MEMORY USAGE ==="
        free -h
        echo
        
        # Disk usage
        echo "=== DISK USAGE ==="
        df -h
        echo
        
        # Top processes
        echo "=== TOP PROCESSES ==="
        ps aux --sort=-%cpu | head -10
        echo
        
        # Network connections
        echo "=== NETWORK CONNECTIONS ==="
        ss -tuln | head -20
        echo
        
    } > "$report_file"
    
    log "INFO" "Health report generated: $report_file"
    echo "$report_file"
}

check_system_resources() {
    local cpu_threshold=80
    local memory_threshold=85
    local disk_threshold=90
    
    # Check CPU usage
    local cpu_usage=$(top -bn1 | grep "Cpu(s)" | awk '{print $2}' | sed 's/%us,//')
    if (( $(echo "$cpu_usage > $cpu_threshold" | bc -l) )); then
        log "WARN" "High CPU usage detected: ${cpu_usage}%"
    fi
    
    # Check memory usage
    local memory_usage=$(free | awk 'NR==2{printf "%.2f", $3*100/$2}')
    if (( $(echo "$memory_usage > $memory_threshold" | bc -l) )); then
        log "WARN" "High memory usage detected: ${memory_usage}%"
    fi
    
    # Check disk usage
    while read -r line; do
        local usage=$(echo "$line" | awk '{print $5}' | sed 's/%//')
        local mount=$(echo "$line" | awk '{print $6}')
        
        if [[ "$usage" -gt "$disk_threshold" ]]; then
            log "WARN" "High disk usage on $mount: ${usage}%"
        fi
    done < <(df -h | grep -E '^/dev/')
}

#===============================================
# BACKUP FUNCTIONS
#===============================================

backup_system_configs() {
    local backup_name="system_config_$(date +%Y%m%d_%H%M%S)"
    local backup_path="$BACKUP_DIR/$backup_name.tar.gz"
    
    log "INFO" "Starting system configuration backup"
    
    local config_dirs=(
        "/etc"
        "/boot"
        "/var/spool/cron"
    )
    
    if tar -czf "$backup_path" "${config_dirs[@]}" 2>/dev/null; then
        log "INFO" "System backup completed: $backup_path"
        chmod 600 "$backup_path"
        
        # Keep only last 30 days of backups
        find "$BACKUP_DIR" -name "system_config_*.tar.gz" -mtime +30 -delete
        
        echo "$backup_path"
    else
        log "ERROR" "System backup failed"
        return 1
    fi
}

#===============================================
# MAINTENANCE FUNCTIONS
#===============================================

system_cleanup() {
    log "INFO" "Starting system cleanup"
    
    # Clean temporary files
    find /tmp -type f -mtime +7 -delete 2>/dev/null || true
    find /var/tmp -type f -mtime +30 -delete 2>/dev/null || true
    
    # Clean old logs
    find /var/log -name "*.log.*" -mtime +30 -delete 2>/dev/null || true
    
    # Package manager cleanup
    if command -v apt >/dev/null; then
        apt autoremove -y
        apt autoclean
    elif command -v yum >/dev/null; then
        yum autoremove -y
        yum clean all
    fi
    
    log "INFO" "System cleanup completed"
}

#===============================================
# MAIN PROGRAM
#===============================================

show_help() {
    cat << EOF
System Administration Toolkit v$VERSION

Usage: $0 [COMMAND] [OPTIONS]

Commands:
  monitor         Generate system health report
  check-resources Check system resource usage
  backup          Backup system configurations  
  cleanup         Clean temporary files and caches
  all            Run all maintenance tasks
  help           Show this help message

Examples:
  $0 monitor
  $0 check-resources
  $0 backup
  $0 cleanup
  $0 all
EOF
}

main() {
    case "${1:-help}" in
        monitor)
            monitor_system_health
            ;;
        check-resources)
            check_system_resources
            ;;
        backup)
            backup_system_configs
            ;;
        cleanup)
            system_cleanup
            ;;
        all)
            log "INFO" "Running complete system maintenance"
            monitor_system_health
            check_system_resources
            backup_system_configs
            system_cleanup
            log "INFO" "Complete system maintenance finished"
            ;;
        help|--help|-h)
            show_help
            ;;
        *)
            echo "Unknown command: $1"
            show_help
            exit 1
            ;;
    esac
}

main "$@"
```

### Automation and DevOps

CI/CD pipeline automation:

```bash
#!/bin/bash
# cicd_pipeline.sh - Complete CI/CD pipeline automation
# Version: 1.5.0

set -euo pipefail

#===============================================
# CONFIGURATION
#===============================================

readonly SCRIPT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
readonly PROJECT_ROOT="$(dirname "$SCRIPT_DIR")"
readonly BUILD_DIR="$PROJECT_ROOT/build"
readonly DEPLOY_DIR="$PROJECT_ROOT/deploy"

#===============================================
# PIPELINE FUNCTIONS
#===============================================

build_application() {
    local environment="${1:-development}"
    local version="${2:-$(git rev-parse --short HEAD 2>/dev/null || date +%Y%m%d_%H%M%S)}"
    
    echo "🔨 Building application for $environment environment (version: $version)"
    
    mkdir -p "$BUILD_DIR"
    
    # Language-specific build process
    if [[ -f "package.json" ]]; then
        npm ci
        npm run build:"$environment"
    elif [[ -f "requirements.txt" ]]; then
        python -m pip install --user -r requirements.txt
        python setup.py build
    elif [[ -f "Cargo.toml" ]]; then
        cargo build --release
    elif [[ -f "Makefile" ]]; then
        make clean
        make build ENV="$environment"
    fi
    
    echo "$version" > "$BUILD_DIR/VERSION"
    echo "✅ Build completed: $version"
}

run_tests() {
    local test_type="${1:-unit}"
    
    echo "🧪 Running $test_type tests..."
    
    case "$test_type" in
        unit)
            if [[ -f "package.json" ]]; then
                npm test
            elif [[ -f "requirements.txt" ]]; then
                python -m pytest tests/unit/ -v
            elif [[ -f "Cargo.toml" ]]; then
                cargo test
            fi
            ;;
        integration)
            if [[ -f "package.json" ]]; then
                npm run test:integration
            elif [[ -f "requirements.txt" ]]; then
                python -m pytest tests/integration/ -v
            fi
            ;;
        security)
            # Security scanning
            if command -v bandit >/dev/null; then
                bandit -r . -f json -o security-report.json || true
            fi
            if command -v npm-audit >/dev/null && [[ -f "package.json" ]]; then
                npm audit --audit-level=high
            fi
            ;;
    esac
    
    echo "✅ $test_type tests completed"
}

deploy_application() {
    local environment="$1"
    local version="$2"
    
    echo "🚀 Deploying version $version to $environment"
    
    case "$environment" in
        staging)
            deploy_to_staging "$version"
            ;;
        production)
            deploy_to_production "$version"
            ;;
        *)
            echo "❌ Unknown environment: $environment"
            exit 1
            ;;
    esac
}

deploy_to_staging() {
    local version="$1"
    local staging_server="staging.example.com"
    
    echo "📦 Deploying to staging server..."
    
    # Deploy with rsync for efficiency
    rsync -avz --delete "$BUILD_DIR/" "deploy@$staging_server:/var/www/staging/"
    
    # Restart services
    ssh "deploy@$staging_server" "systemctl restart myapp-staging"
    
    # Health check
    local health_url="http://$staging_server/health"
    local retries=5
    
    for ((i=1; i<=retries; i++)); do
        if curl -f "$health_url" >/dev/null 2>&1; then
            echo "✅ Staging deployment successful"
            return 0
        fi
        echo "⏳ Health check attempt $i/$retries failed, retrying..."
        sleep 10
    done
    
    echo "❌ Staging deployment failed health check"
    exit 1
}

deploy_to_production() {
    local version="$1"
    local production_servers=("prod1.example.com" "prod2.example.com")
    
    echo "🔄 Starting blue-green deployment to production..."
    
    for server in "${production_servers[@]}"; do
        echo "📦 Deploying to $server..."
        
        # Create backup
        ssh "deploy@$server" "cp -r /var/www/current /var/www/backup-$(date +%Y%m%d_%H%M%S)" || true
        
        # Deploy new version
        rsync -avz --delete "$BUILD_DIR/" "deploy@$server:/var/www/new/"
        
        # Atomic switch
        ssh "deploy@$server" "ln -sfn /var/www/new /var/www/current"
        ssh "deploy@$server" "systemctl reload myapp"
        
        # Health check
        local health_url="http://$server/health"
        if curl -f "$health_url" >/dev/null 2>&1; then
            echo "✅ Production deployment to $server successful"
        else
            echo "❌ Production deployment to $server failed, rolling back..."
            ssh "deploy@$server" "ln -sfn /var/www/backup-* /var/www/current"
            ssh "deploy@$server" "systemctl reload myapp"
            exit 1
        fi
    done
}

run_complete_pipeline() {
    local environment="$1"
    local skip_tests="${2:-false}"
    
    echo "🎯 Starting complete CI/CD pipeline for $environment"
    
    local version
    if git rev-parse --git-dir >/dev/null 2>&1; then
        version="$(git describe --tags --always --dirty)"
    else
        version="$(date +%Y%m%d_%H%M%S)"
    fi
    
    # Pipeline stages
    build_application "$environment" "$version"
    
    if [[ "$skip_tests" != "true" ]]; then
        run_tests "unit"
        run_tests "integration"
        run_tests "security"
    fi
    
    deploy_application "$environment" "$version"
    
    echo "🎉 Pipeline completed successfully for $environment (version: $version)"
}

#===============================================
# MAIN PROGRAM
#===============================================

show_pipeline_help() {
    cat << EOF
CI/CD Pipeline Automation v1.5.0

Usage: $0 [COMMAND] [OPTIONS]

Commands:
  build [env] [version]     Build application
  test [type]              Run tests (unit|integration|security)
  deploy <env> <version>   Deploy to environment
  pipeline <env>           Run complete pipeline
  help                     Show this help

Options:
  --skip-tests            Skip test execution
  --dry-run              Show what would be done

Examples:
  $0 build production v1.2.3
  $0 test unit
  $0 deploy staging v1.2.3
  $0 pipeline production
EOF
}

main() {
    case "${1:-help}" in
        build)
            build_application "${2:-development}" "${3:-}"
            ;;
        test)
            run_tests "${2:-unit}"
            ;;
        deploy)
            if [[ $# -lt 3 ]]; then
                echo "❌ Error: Environment and version required"
                exit 1
            fi
            deploy_application "$2" "$3"
            ;;
        pipeline)
            if [[ $# -lt 2 ]]; then
                echo "❌ Error: Environment required"
                exit 1
            fi
            local skip_tests="false"
            [[ "${3:-}" == "--skip-tests" ]] && skip_tests="true"
            run_complete_pipeline "$2" "$skip_tests"
            ;;
        help|--help|-h)
            show_pipeline_help
            ;;
        *)
            echo "❌ Unknown command: $1"
            show_pipeline_help
            exit 1
            ;;
    esac
}

main "$@"
```

### Data Processing

Advanced data processing and analysis:

```bash
#!/bin/bash
# data_processor.sh - Advanced data processing pipeline
# Version: 2.0.0

set -euo pipefail

#===============================================
# DATA PROCESSING FUNCTIONS
#===============================================

process_csv_data() {
    local input_file="$1"
    local output_file="$2"
    local operations="${3:-clean,validate,transform}"
    
    echo "📊 Processing CSV data: $input_file -> $output_file"
    
    [[ ! -f "$input_file" ]] && { echo "❌ Input file not found: $input_file"; return 1; }
    
    local temp_file
    temp_file=$(mktemp)
    cp "$input_file" "$temp_file"
    
    # Process operations
    for operation in ${operations//,/ }; do
        case "$operation" in
            clean)
                echo "🧹 Cleaning data..."
                sed -i '/^[[:space:]]*$/d' "$temp_file"
                sed -i 's/^[[:space:]]*//;s/[[:space:]]*$//' "$temp_file"
                ;;
            validate)
                echo "✅ Validating data..."
                local expected_cols
                expected_cols=$(head -1 "$temp_file" | tr ',' '\n' | wc -l)
                
                awk -F',' -v cols="$expected_cols" '
                NR == 1 { next }
                NF != cols { 
                    print "⚠️ Line " NR " has " NF " columns, expected " cols > "/dev/stderr"
                    error_count++
                }
                END { 
                    if (error_count > 0) {
                        print "Found " error_count " validation errors" > "/dev/stderr"
                    }
                }' "$temp_file"
                ;;
            transform)
                echo "🔄 Transforming data..."
                awk -F',' 'BEGIN { OFS="," }
                NR == 1 { print; next }
                {
                    # Convert dates to ISO format
                    gsub(/([0-9]{1,2})\/([0-9]{1,2})\/([0-9]{4})/, "\\3-\\1-\\2")
                    
                    # Normalize whitespace
                    for(i=1; i<=NF; i++) {
                        gsub(/^[ \t]+|[ \t]+$/, "", $i)
                    }
                    
                    print
                }' "$temp_file" > "${temp_file}.transform"
                mv "${temp_file}.transform" "$temp_file"
                ;;
        esac
    done
    
    mv "$temp_file" "$output_file"
    echo "✅ CSV processing completed: $output_file"
}

generate_data_report() {
    local data_file="$1"
    local report_file="${2:-${data_file%.*}_report.txt}"
    
    echo "📋 Generating data report for $data_file"
    
    {
        echo "=== DATA ANALYSIS REPORT ==="
        echo "File: $data_file"
        echo "Generated: $(date)"
        echo
        
        # Basic file info
        echo "=== FILE STATISTICS ==="
        echo "Total lines: $(wc -l < "$data_file")"
        echo "Data lines: $(($(wc -l < "$data_file") - 1))"
        echo "File size: $(du -h "$data_file" | cut -f1)"
        echo
        
        # Column analysis
        echo "=== COLUMN ANALYSIS ==="
        local cols
        cols=$(head -1 "$data_file" | tr ',' '\n' | wc -l)
        echo "Number of columns: $cols"
        
        head -1 "$data_file" | tr ',' '\n' | nl -w2 -s': '
        echo
        
        # Numeric column statistics
        for ((i=1; i<=cols; i++)); do
            local col_name
            col_name=$(head -1 "$data_file" | cut -d',' -f"$i")
            
            # Check if column contains numeric data
            local numeric_count
            numeric_count=$(awk -F',' -v col="$i" '
                NR > 1 && $col ~ /^[0-9]+\.?[0-9]*$/ { count++ }
                END { print count+0 }
            ' "$data_file")
            
            if [[ "$numeric_count" -gt 0 ]]; then
                echo "=== STATISTICS for $col_name ==="
                awk -F',' -v col="$i" '
                NR > 1 && $col ~ /^[0-9]+\.?[0-9]*$/ {
                    values[++count] = $col
                    sum += $col
                    if ($col > max || max == "") max = $col
                    if ($col < min || min == "") min = $col
                }
                END {
                    if (count > 0) {
                        print "Count: " count
                        print "Sum: " sum
                        print "Average: " (sum/count)
                        print "Min: " min
                        print "Max: " max
                        
                        # Calculate median
                        asort(values)
                        if (count % 2 == 1) {
                            median = values[(count+1)/2]
                        } else {
                            median = (values[count/2] + values[count/2+1])/2
                        }
                        print "Median: " median
                    }
                }' "$data_file"
                echo
            fi
        done
        
    } > "$report_file"
    
    echo "✅ Report generated: $report_file"
}

create_data_visualization() {
    local data_file="$1"
    local column="${2:-2}"
    local chart_type="${3:-bar}"
    
    echo "📊 Creating $chart_type chart for column $column"
    
    case "$chart_type" in
        bar)
            awk -F',' -v col="$column" '
            NR == 1 { next }
            {
                if ($col ~ /^[0-9]+\.?[0-9]*$/) {
                    data[NR] = $col
                    label[NR] = $1
                    if ($col > max) max = $col
                }
            }
            END {
                scale = max / 60  # Scale to 60 characters width
                print "BAR CHART - Column " col
                print "=" sprintf("%*s", 60, "")
                for (i in data) {
                    bar_length = int(data[i] / scale)
                    printf "%-15s |", substr(label[i], 1, 15)
                    for (j = 1; j <= bar_length; j++) {
                        printf "█"
                    }
                    printf " %.1f\n", data[i]
                }
            }' "$data_file"
            ;;
        histogram)
            awk -F',' -v col="$column" '
            NR == 1 { next }
            {
                if ($col ~ /^[0-9]+\.?[0-9]*$/) {
                    bucket = int($col/10)*10
                    freq[bucket]++
                    if (freq[bucket] > max_freq) max_freq = freq[bucket]
                }
            }
            END {
                scale = max_freq / 40
                print "HISTOGRAM - Column " col
                print "=" sprintf("%*s", 40, "")
                for (bucket in freq) {
                    bar_length = int(freq[bucket] / scale)
                    printf "%6d-%3d |", bucket, bucket+9
                    for (j = 1; j <= bar_length; j++) {
                        printf "█"
                    }
                    printf " %d\n", freq[bucket]
                }
            }' "$data_file" | sort -n
            ;;
    esac
}

#===============================================
# MAIN PROGRAM
#===============================================

show_data_help() {
    cat << EOF
Data Processing Pipeline v2.0.0

Usage: $0 [COMMAND] [OPTIONS]

Commands:
  process <input> <output> [ops]  Process CSV data
  report <file> [output]          Generate data report
  chart <file> [column] [type]    Create visualization
  help                           Show this help

Operations for process:
  clean      - Remove empty lines and whitespace
  validate   - Check data consistency
  transform  - Apply data transformations

Chart types:
  bar        - Bar chart
  histogram  - Frequency distribution

Examples:
  $0 process data.csv clean_data.csv "clean,validate"
  $0 report sales_data.csv
  $0 chart sales_data.csv 3 bar
EOF
}

main() {
    case "${1:-help}" in
        process)
            if [[ $# -lt 3 ]]; then
                echo "❌ Error: Input and output files required"
                exit 1
            fi
            process_csv_data "$2" "$3" "${4:-clean,validate,transform}"
            ;;
        report)
            if [[ $# -lt 2 ]]; then
                echo "❌ Error: Data file required"
                exit 1
            fi
            generate_data_report "$2" "${3:-}"
            ;;
        chart)
            if [[ $# -lt 2 ]]; then
                echo "❌ Error: Data file required"
                exit 1
            fi
            create_data_visualization "$2" "${3:-2}" "${4:-bar}"
            ;;
        help|--help|-h)
            show_data_help
            ;;
        *)
            echo "❌ Unknown command: $1"
            show_data_help
            exit 1
            ;;
    esac
}

main "$@"
```

---

## 📖 Appendices

### Quick Reference Card

```bash
# BASH QUICK REFERENCE CARD

# Variables
var="value"                 # Assignment
echo $var                   # Basic expansion
echo ${var}                 # Explicit expansion
echo ${var:-default}        # Default value
echo ${var:=default}        # Assign default
echo ${var:+alternate}      # Alternate value
echo ${#var}               # String length

# Arrays
arr=(a b c)                # Indexed array
declare -A map             # Associative array
echo ${arr[0]}             # Access element
echo ${arr[@]}             # All elements
echo ${#arr[@]}            # Array length
echo ${!arr[@]}            # All indices

# Parameter Expansion
${var#pattern}             # Remove shortest prefix
${var##pattern}            # Remove longest prefix
${var%pattern}             # Remove shortest suffix
${var%%pattern}            # Remove longest suffix
${var/old/new}             # Replace first occurrence
${var//old/new}            # Replace all occurrences
${var^}                    # Uppercase first char
${var^^}                   # Uppercase all
${var,}                    # Lowercase first char
${var,,}                   # Lowercase all

# Conditionals
if [[ condition ]]; then   # If statement
elif [[ condition ]]; then # Else if
else                       # Else
fi                         # End if

# String Tests
[[ -z $str ]]              # String is empty
[[ -n $str ]]              # String is not empty
[[ $str == pattern ]]      # Pattern match
[[ $str =~ regex ]]        # Regex match

# Numeric Tests
[[ $num -eq 5 ]]           # Equal
[[ $num -ne 5 ]]           # Not equal
[[ $num -lt 5 ]]           # Less than
[[ $num -le 5 ]]           # Less than or equal
[[ $num -gt 5 ]]           # Greater than
[[ $num -ge 5 ]]           # Greater than or equal

# File Tests
[[ -f $file ]]             # File exists
[[ -d $dir ]]              # Directory exists
[[ -r $file ]]             # File is readable
[[ -w $file ]]             # File is writable
[[ -x $file ]]             # File is executable
[[ -s $file ]]             # File is not empty

# Loops
for var in list; do        # For loop
    commands
done

while [[ condition ]]; do  # While loop
    commands
done

until [[ condition ]]; do  # Until loop
    commands
done

# Case Statement
case $var in
    pattern1) commands ;;
    pattern2) commands ;;
    *) default ;;
esac

# Functions
function_name() {          # Function definition
    local var="value"      # Local variable
    echo "$1"              # First parameter
    return 0               # Return value
}

# I/O Redirection
command > file             # Redirect stdout
command >> file            # Append stdout
command 2> file            # Redirect stderr
command &> file            # Redirect both
command < file             # Input from file
command | command2         # Pipe
command1 && command2       # Run if successful
command1 || command2       # Run if failed

# Special Variables
$0                         # Script name
$1, $2, ...               # Positional parameters
$#                         # Number of parameters
$@                         # All parameters
$*                         # All parameters as string
$$                         # Process ID
$!                         # Last background PID
$?                         # Exit status
```

### Glossary

**Array**: A collection of values that can be accessed by index (indexed array) or key (associative array).

**Brace Expansion**: A mechanism that generates multiple strings from a pattern containing braces, e.g., `{a,b,c}` or `{1..10}`.

**Command Substitution**: The ability to capture the output of a command and use it as part of another command using `$(command)` or backticks.

**Exit Status**: A numeric value returned by a command indicating success (0) or failure (non-zero).

**Globbing**: Pattern matching using wildcards like `*`, `?`, and `[...]` to match filenames.

**Here Document**: A method of providing input to a command using `<<` followed by a delimiter.

**Parameter Expansion**: Advanced variable manipulation techniques using `${variable...}` syntax.

**Pipeline**: A sequence of commands connected by pipes (`|`) where the output of one command becomes the input of the next.

**Process Substitution**: A feature that allows the output of a command to appear as a file using `<(command)` or `>(command)`.

**Redirection**: The ability to change where a command's input comes from or where its output goes.

**Shell**: A command-line interpreter that provides a user interface to the operating system.

**Shebang**: The `#!` sequence at the beginning of a script that specifies which interpreter to use.

**Subshell**: A separate shell process spawned to execute commands, often created with parentheses `(commands)`.

**Variable**: A named storage location that can hold a value, referenced using `$name` or `${name}`.

### Further Reading

**Official Documentation**:
- [Bash Manual](https://www.gnu.org/software/bash/manual/)
- [POSIX Shell Standard](https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html)

**Advanced Resources**:
- "Advanced Bash-Scripting Guide" by Mendel Cooper
- "Learning the Bash Shell" by Cameron Newham
- "Bash Cookbook" by Carl Albing and JP Vossen

**Online Resources**:
- [ShellCheck](https://www.shellcheck.net/) - Shell script analysis tool
- [Bash FAQ](http://mywiki.wooledge.org/BashFAQ)
- [Bash Pitfalls](http://mywiki.wooledge.org/BashPitfalls)

### Community Resources

**Forums and Communities**:
- Stack Overflow - [bash] tag
- Reddit - r/bash
- Unix & Linux Stack Exchange

**Practice Platforms**:
- HackerRank Shell challenges
- LeetCode Shell problems
- Project Euler

**Tools and Utilities**:
- **ShellCheck**: Static analysis tool for shell scripts
- **Bashdb**: Debugger for Bash scripts
- **Bats**: Bash Automated Testing System

### Contributing Guidelines

This documentation is open for community contributions. Here's how you can help:

**Reporting Issues**:
1. Check existing issues first
2. Provide clear reproduction steps
3. Include your Bash version and OS

**Suggesting Improvements**:
1. Open an issue describing the enhancement
2. Provide examples and use cases
3. Consider backward compatibility

**Contributing Code Examples**:
1. Follow the established style and format
2. Test all code examples thoroughly
3. Include proper error handling
4. Add appropriate comments and documentation

**Style Guidelines**:
- Use 4-space indentation
- Quote all variable references
- Use meaningful variable and function names
- Include error handling where appropriate
- Add comments for complex logic

**Review Process**:
1. Submit pull requests with clear descriptions
2. Include tests for new functionality
3. Update documentation as needed
4. Respond to review feedback promptly

Thank you for helping make this documentation better for everyone! 🎉

---

*This documentation is maintained by the community. Last updated: December 2024*
