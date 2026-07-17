# Setting Up Your C Environment: 
# What is GCC?

**GCC** stands for

> **GNU Compiler Collection**

Although its name suggests multiple languages, GCC supports many programming languages including:

- C
- C++
- Objective-C
- Fortran
- Ada
- Go

For this tutorial, we'll only use **C**.

GCC is:

- ✅ Free
- ✅ Open Source
- ✅ Industry Standard
- ✅ Fast
- ✅ Available on Windows, Linux and macOS

---

# What is an IDE?

IDE stands for

> **Integrated Development Environment**

An IDE is software that helps you write programs more easily.

Instead of using only Notepad, an IDE provides:

- Syntax Highlighting
- Auto Completion
- Error Detection
- File Explorer
- Integrated Terminal
- Debugger
- Extensions

Think of it like this:

| Without IDE | With IDE |
|-------------|----------|
| Writing on plain paper | Writing with smart assistance |
| No colors | Colored syntax |
| No suggestions | Auto-complete |
| Difficult debugging | Easy debugging |

---

# Installing GCC Compiler

---

# Windows Installation

Windows does **not** include GCC by default.

The easiest way is to install **MSYS2**, which provides GCC.

## Step 1

Download MSYS2

https://www.msys2.org/

---

## Step 2

Install MSYS2 normally.

Default installation location:

```
C:\msys64
```

---

## Step 3

Open

```
MSYS2 UCRT64
```

from the Start Menu.

---

## Step 4

Update packages

Run

```bash
pacman -Syu
```

Close the terminal if prompted.

Open it again.

Run

```bash
pacman -Su
```

---

## Step 5

Install GCC

```bash
pacman -S mingw-w64-ucrt-x86_64-gcc
```

Type

```
Y
```

when asked.

Wait for installation.

---

## Step 6

Add GCC to PATH

Open

```
Environment Variables
```

Find

```
Path
```

Click

```
Edit
```

Add

```
C:\msys64\ucrt64\bin
```

Click

```
OK
```

Restart the terminal.

---

# Linux Installation

Most Linux distributions already provide GCC.

## Ubuntu / Debian

```bash
sudo apt update
sudo apt install gcc
```

---

## Fedora

```bash
sudo dnf install gcc
```

---

## Arch Linux

```bash
sudo pacman -S gcc
```

---

# macOS Installation

Install Apple's Command Line Tools.

Open Terminal.

```bash
xcode-select --install
```

Follow the instructions.

GCC (actually Clang with GCC compatibility) will be installed.

---

# Verifying GCC Installation

Open Terminal (or Command Prompt).

Type

```bash
gcc --version
```

You should see something like

```text
gcc (GCC) 15.x.x
```

If you see

```
'gcc' is not recognized...
```

then GCC is either:

- Not installed
- PATH is incorrect

---

# Installing Visual Studio Code

Download VS Code

https://code.visualstudio.com/

Install using default settings.

Launch VS Code.

---

# Why VS Code?

VS Code is one of the most popular editors because it is

- Free
- Lightweight
- Fast
- Cross Platform
- Highly Customizable
- Beginner Friendly

---

# Installing Extensions

Open Extensions

```
Ctrl + Shift + X
```

Install the following.

---

## C/C++

Publisher:

```
Microsoft
```

Provides

- IntelliSense
- Auto Complete
- Debugging
- Error Detection

---

## Code Runner (Optional)

Allows running code quickly.

Publisher

```
Jun Han
```

---

## Error Lens (Optional)

Displays errors directly in your code.

---

## Better Comments (Optional)

Makes comments colorful and easier to read.

---

# Creating Your First Project

Create a folder

```
C-Tutorial
```

Open it in VS Code.

Inside it create

```
hello.c
```

---

# Writing Your First Program

```c
#include <stdio.h>

int main()
{
    printf("Hello, World!");

    return 0;
}
```

Save using

```
Ctrl + S
```

---

# Opening the Terminal

Press

```
Ctrl + `
```

or

```
Terminal → New Terminal
```

---

# Compiling the Program

Run

```bash
gcc hello.c -o hello
```

Explanation

```
gcc
```

Compiler

```
hello.c
```

Source file

```
-o
```

Output option

```
hello
```

Name of executable

---

# Running the Program

## Windows

```bash
hello
```

or

```bash
hello.exe
```

---

## Linux/macOS

```bash
./hello
```

Output

```
Hello, World!
```

Congratulations!

You have successfully compiled and executed your first C program.

---

# How Compilation Works

```
hello.c
      │
      ▼
 gcc Compiler
      │
      ▼
 hello.exe
      │
      ▼
 Execute
      │
      ▼
 Output on Screen
```

---