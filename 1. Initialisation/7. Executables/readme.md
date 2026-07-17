# 🖥️ Executable Files in C

After compilation and linking, the final result is an **executable file** that the operating system can run.

---

# 📑 Table of Contents

- What is an Executable?
- How it is Created
- Platform Differences
- Running an Executable
- Complete Build Process
- Summary

---

# What is an Executable?

An executable is the final program produced after:

1. Compilation
2. Linking

It contains all the machine instructions required to run your program.

---

# Windows

Executable extension:

```
.exe
```

Example:

```
hello.exe
```

Run:

```bash
hello.exe
```

or

```bash
hello
```

---

# Linux

Usually no extension:

```
hello
```

Run:

```bash
./hello
```

---

# macOS

Also:

```
./hello
```

---

# Complete Build Process

```
hello.c
     │
     ▼
 Compilation
     │
     ▼
hello.o
     │
     ▼
 Linking
     │
     ▼
hello.exe
     │
     ▼
 Execution
     │
     ▼
Output on Screen
```

---

# Where is the Executable?

It is created in the same directory unless another output location is specified.

Example:

```
Project/
│
├── hello.c
├── hello.exe
```

---

# Why is an Executable Important?

Without an executable:

- The operating system has nothing to run.
- Your source code remains just text.
- The CPU cannot directly execute C source code.

---

# Executable vs Source Code

| Source Code | Executable |
|-------------|------------|
| Human-readable | Machine-readable |
| Editable | Not easily editable |
| `.c` | `.exe` (Windows) or no extension (Linux/macOS) |
| Requires compilation | Ready to run |

---

# Summary

- The executable is the final output of the build process.
- It is generated after successful compilation and linking.
- It contains machine code that the operating system can execute.
- Running the executable produces your program's output.

---

# Build Pipeline Recap

```
Source Code (.c)
        │
        ▼
Compilation
        │
        ▼
Object File (.o / .obj)
        │
        ▼
Linking
        │
        ▼
Executable (.exe / binary)
        │
        ▼
Program Runs
```

Congratulations! 🎉 You now understand the complete journey of a C program—from source code to a running application.