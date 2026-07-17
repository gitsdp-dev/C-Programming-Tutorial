# 🚀 Running Your First C Program

Congratulations! Your C development environment is now ready. In this chapter, you'll write, compile, and run your very first C program.

---

# 📑 Table of Contents

- Creating a C File
- Writing the Program
- Saving the File
- Compiling the Program
- Running the Program
- Understanding the Output
- Common Mistakes
- Summary

---

# Step 1: Create a New File

Open your IDE (Visual Studio Code or any other editor).

Create a new file named:

```

hello.c

```

> **Why `.c`?**
>
> Every C source file must have the `.c` extension so the compiler recognizes it as C code.

---

# Step 2: Write Your First Program

Type the following code:

```c
#include <stdio.h>

int main()
{
    printf("Hello, World!\n");

    return 0;
}
```

Save the file using:

```
Ctrl + S
```

---

# Understanding the Code

## `#include <stdio.h>`

Imports the Standard Input/Output library, allowing you to use functions like `printf()`.

---

## `int main()`

Every C program starts executing from the `main()` function.

Think of it as the **entry point** of your program.

---

## `printf()`

Displays text on the screen.

```c
printf("Hello, World!");
```

Output:

```
Hello, World!
```

---

## `return 0;`

Returns control back to the operating system.

A return value of `0` usually means the program executed successfully.

---

# Step 3: Open the Terminal

In Visual Studio Code:

```
Terminal → New Terminal
```

or press:

```
Ctrl + `
```

Navigate to the folder containing your program if necessary.

---

# Step 4: Compile the Program

Run:

```bash
gcc hello.c -o hello
```

If there are no errors, the compiler will create an executable file.

---

# Step 5: Run the Program

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

---

# Expected Output

```
Hello, World!
```

If you see this message, congratulations! 🎉

You have successfully written, compiled, and executed your first C program.

---

# What Just Happened?

```
Write Code
     │
     ▼
Save File (.c)
     │
     ▼
Compile using GCC
     │
     ▼
Executable Created
     │
     ▼
Run Executable
     │
     ▼
Program Output
```

---

# Common Mistakes

## Forgot to save the file

Always press:

```
Ctrl + S
```

before compiling.

---

## File name is incorrect

Correct:

```
hello.c
```

Incorrect:

```
hello.txt
hello.cpp
```

---

## GCC not found

Error:

```
'gcc' is not recognized...
```

This means GCC is not installed correctly or its path hasn't been added.

---

## Typing mistakes

Even a missing semicolon can prevent compilation.

Example:

Wrong

```c
printf("Hello")
```

Correct

```c
printf("Hello");
```

---

# Summary

✔ Created a C source file

✔ Wrote your first program

✔ Compiled it using GCC

✔ Ran the executable

✔ Displayed output on the screen

---

# Next Chapter

Now that you've successfully run your first program, it's time to understand **how C transforms your source code into an executable program** through the stages of **Compilation, Linking, and Execution**.