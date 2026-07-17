# 🔗 Linking in C

Compilation creates object files, but object files alone cannot run.

They must be **linked together**.

---

# 📑 Table of Contents

- What is Linking?
- Why Linking is Needed
- Static Libraries
- Dynamic Libraries
- Linking Process
- Linker Errors
- Summary

---

# What is Linking?

The linker combines:

- Object files
- Standard libraries
- User-defined libraries

into one executable program.

```
hello.o
    │
    ▼
Linker
    │
    ▼
hello.exe
```

---

# Why is Linking Needed?

Suppose your program contains:

```c
printf("Hello");
```

Where is `printf()`?

It is **not** inside your program.

It exists inside the C Standard Library.

The linker connects your program with that library.

---

# Linking Multiple Files

Example:

```
main.c
math.c
```

Compile:

```bash
gcc -c main.c
gcc -c math.c
```

Produces:

```
main.o
math.o
```

Link:

```bash
gcc main.o math.o -o program
```

Output:

```
program.exe
```

---

# Linker Errors

Example:

```
undefined reference to add
```

Reason:

The linker couldn't find the implementation of `add()`.

Possible causes:

- Missing source file
- Missing library
- Incorrect function name

---

# Linking Flow

```
main.o
math.o
stdio Library
      │
      ▼
     Linker
      │
      ▼
Executable
```

---

# Summary

- Linking combines object files.
- Standard libraries are linked automatically.
- Missing functions produce linker errors.
- Successful linking creates the final executable.