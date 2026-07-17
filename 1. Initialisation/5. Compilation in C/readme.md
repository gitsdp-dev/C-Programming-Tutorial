# ⚙️ Compilation in C

Compilation is the process of converting human-readable C source code into machine-readable object code.

---

# 📑 Table of Contents

- What is Compilation?
- Why Compilation is Needed
- Compilation Process
- Using GCC
- Object Files
- Compiler Errors
- Summary

---

# What is Compilation?

Computers cannot understand C code directly.

They only understand **machine language (binary instructions).**

The compiler translates your source code into machine code.

```
hello.c
    │
    ▼
Compiler
    │
    ▼
hello.o
```

Notice that the output is **not yet executable**.

It is called an **Object File**.

---

# Why Compilation is Needed

Without compilation:

❌ Computer cannot understand C code.

Compilation also checks:

- Syntax errors
- Type errors
- Missing declarations
- Invalid statements

---

# Using GCC

Compile only:

```bash
gcc -c hello.c
```

The `-c` flag tells GCC:

> Compile only. Do not create an executable.

Result:

```
hello.o
```

Windows may generate:

```
hello.obj
```

---

# What is an Object File?

An object file contains:

- Machine instructions
- Function definitions
- Variables
- Symbol information

However, it is **incomplete** because it may reference functions located in other files or libraries.

---

# Compiler Errors

Example:

```c
printf("Hello")
```

Output:

```
error: expected ';'
```

Compilation stops until the error is fixed.

---

# Compilation Flow

```
Source Code
      │
      ▼
Compiler
      │
      ▼
Object File (.o / .obj)
```

---

# Summary

- Compilation converts C source code into object code.
- GCC performs syntax checking.
- The output is an object file.
- The program is **not yet executable**.