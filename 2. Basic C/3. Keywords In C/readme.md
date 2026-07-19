# 🔑 C Keywords

> **Keywords** are reserved words in the C programming language that have predefined meanings understood directly by the compiler. They are the building blocks of C syntax and cannot be used as identifiers such as variable names, function names, or array names.

---

## 📚 Table of Contents

- [What are Keywords?](#-what-are-keywords)
- [Rules of C Keywords](#-rules-of-c-keywords)
- [The 32 Standard ANSI C Keywords](#-the-32-standard-ansi-c-keywords)
  - [1. Data Type Keywords](#1-data-type-keywords)
  - [2. Data Modifiers & Type Qualifiers](#2-data-modifiers--type-qualifiers)
  - [3. Control Flow & Loop Keywords](#3-control-flow--loop-keywords)
  - [4. Storage Class Keywords](#4-storage-class-keywords)
  - [5. User-Defined Structures & Utilities](#5-user-defined-structures--utilities)
- [Quick Reference Table](#-quick-reference-table)
- [Example Program](#-example-program)
- [Key Takeaways](#-key-takeaways)

---

# 📖 What are Keywords?

Keywords are **reserved words** whose meanings are already defined by the C language. Since the compiler recognizes these words as part of the language syntax, they **cannot be used as identifiers**.

❌ Invalid

```c
int while = 10;
```

✅ Valid

```c
int number = 10;
```

---

# 📌 Rules of C Keywords

### 1️⃣ Keywords are Always Lowercase

All standard C keywords must be written entirely in lowercase.

| Correct | Incorrect |
|---------|-----------|
| `int` | `INT` |
| `float` | `Float` |
| `return` | `RETURN` |

---

### 2️⃣ Keywords Have Fixed Meanings

Every keyword performs a specific task defined by the language.

For example:

- `if` → decision making
- `return` → exits a function
- `while` → loop execution

Their behavior **cannot be modified**.

---

### 3️⃣ Keywords Cannot be Used as Identifiers

❌ Wrong

```c
int return = 10;
```

✅ Correct

```c
int marks = 10;
```

---

### 4️⃣ Number of Keywords Depends on the C Standard

| Standard | Number of Keywords |
|----------|-------------------:|
| ANSI C (C89/C90) | 32 |
| C99 | More than 32 |
| C11 | Added `_Atomic`, `_Thread_local`, etc. |
| C23 | Includes additional modern keywords |

> This tutorial focuses on the **32 original ANSI C keywords**, as they form the foundation of C programming.

---

# 🗂️ The 32 Standard ANSI C Keywords

To make learning easier, they are grouped into functional categories.

---

# 1. Data Type Keywords

These keywords tell the compiler what kind of data will be stored.

| Keyword | Purpose |
|---------|---------|
| `char` | Character data type |
| `int` | Integer data type |
| `float` | Single precision decimal |
| `double` | Double precision decimal |
| `void` | No value / Generic pointer type |

### Example

```c
char grade = 'A';
int age = 20;
float pi = 3.14f;
double salary = 45678.98;
```

---

# 2. Data Modifiers & Type Qualifiers

These modify the properties, range, or behavior of data types.

| Keyword | Purpose |
|---------|---------|
| `short` | Smaller integer |
| `long` | Larger integer or floating point |
| `signed` | Positive and negative values |
| `unsigned` | Only positive values |
| `const` | Read-only variable |
| `volatile` | Value may change unexpectedly |

### Example

```c
unsigned int marks = 100;

const float PI = 3.14159;

volatile int sensorValue;
```

---

# 3. Control Flow & Loop Keywords

These keywords control the execution flow of a program.

| Keyword | Purpose |
|---------|---------|
| `if` | Conditional execution |
| `else` | Alternative execution |
| `switch` | Multi-way selection |
| `case` | Switch option |
| `default` | Default switch option |
| `for` | Loop |
| `while` | Loop |
| `do` | Executes once before checking condition |
| `break` | Exit loop/switch |
| `continue` | Skip current iteration |
| `goto` | Jump to label |
| `return` | Exit function |

### Example

```c
if (marks >= 40)
{
    printf("Pass");
}
else
{
    printf("Fail");
}
```

---

# 4. Storage Class Keywords

These define **where variables are stored**, **their lifetime**, and **their visibility**.

| Keyword | Purpose |
|---------|---------|
| `auto` | Automatic local variable |
| `register` | Suggest CPU register storage |
| `static` | Preserve value between function calls |
| `extern` | Variable declared elsewhere |

### Example

```c
static int count = 0;

extern int totalStudents;
```

---

# 5. User-Defined Structures & Utilities

These help create custom data types and perform special operations.

| Keyword | Purpose |
|---------|---------|
| `struct` | Group different data types |
| `union` | Share memory among members |
| `enum` | Named integer constants |
| `typedef` | Create a new type name |
| `sizeof` | Returns memory size |

### Example

```c
struct Student
{
    char name[20];
    int age;
};
```

---

# 📋 Quick Reference Table

| Category | Keywords |
|----------|----------|
| **Data Types** | `char`, `int`, `float`, `double`, `void` |
| **Modifiers** | `short`, `long`, `signed`, `unsigned`, `const`, `volatile` |
| **Control Flow** | `if`, `else`, `switch`, `case`, `default`, `for`, `while`, `do`, `break`, `continue`, `goto`, `return` |
| **Storage Classes** | `auto`, `register`, `static`, `extern` |
| **Structures & Utilities** | `struct`, `union`, `enum`, `typedef`, `sizeof` |

---

# 💻 Example Program

```c
#include <stdio.h>

int main()
{
    const float PI = 3.14;
    int radius = 5;

    if (radius > 0)
    {
        printf("Area = %.2f\n", PI * radius * radius);
    }

    return 0;
}
```

### Keywords Used

- `#include`
- `int`
- `const`
- `float`
- `if`
- `return`

---

# 💡 Key Takeaways

- ✅ Keywords are **reserved words**.
- ✅ They **cannot** be used as variable or function names.
- ✅ They are **always lowercase**.
- ✅ ANSI C contains **32 standard keywords**.
- ✅ Modern C standards introduce additional keywords.
- ✅ Understanding keywords is essential before learning variables, loops, functions, and advanced C concepts.

---

# 🎯 What's Next?

After learning **Keywords**, continue with:

- 📝 Identifiers
- 🔢 Constants
- 📦 Variables
- 🏷️ Data Types
- ➕ Operators
- 📥 Input & Output
- 🔁 Control Statements

Happy Coding! 🚀