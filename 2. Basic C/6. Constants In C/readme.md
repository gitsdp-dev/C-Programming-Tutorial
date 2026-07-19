# 🔒 C Constants

> A **constant** is a **fixed value** that **cannot be modified** during the execution of a C program. Constants improve code readability, prevent accidental modifications, and make programs easier to maintain.

---

## 📚 Table of Contents

- [What is a Constant?](#-what-is-a-constant)
- [Methods to Define Constants](#-methods-to-define-constants)
  - [1. const Keyword](#1-the-const-keyword)
  - [2. #define Preprocessor Directive](#2-the-define-preprocessor-directive)
  - [3. Enumeration (enum)](#3-enumeration-constants-enum)
- [Comparison of Constant Methods](#-comparison-of-constant-methods)
- [Types of Constant Literals](#-types-of-constant-literals)
- [Example Program](#-example-program)
- [Best Practices](#-best-practices)
- [Key Takeaways](#-key-takeaways)

---

# 📖 What is a Constant?

A **constant** is a value whose content remains **unchanged** throughout the lifetime of a program.

Unlike variables, constants **cannot be reassigned** after they are defined.

### Example

```c
const int MAX_STUDENTS = 100;
```

Here,

- `MAX_STUDENTS` always stores **100**.
- Attempting to change it results in a compilation error.

---

# 🛠️ Methods to Define Constants

C provides **three primary ways** to define constants.

1. `const` Keyword
2. `#define` Preprocessor Directive
3. `enum` (Enumeration)

Each method serves a different purpose.

---

# 1. The `const` Keyword

The `const` keyword creates a **read-only variable**.

It **must be initialized** when declared.

### Example

```c
#include <stdio.h>

int main()
{
    const double PI = 3.14159;

    printf("PI = %f\n", PI);

    return 0;
}
```

---

### ❌ Attempting to Modify a Constant

```c
const int age = 20;

age = 25;
```

Compilation Error

```
assignment of read-only variable
```

---

## ✅ Advantages

- Type-safe
- Checked by the compiler
- Has a memory address
- Easier to debug

---

# 2. The `#define` Preprocessor Directive

`#define` creates a **symbolic constant**.

Instead of creating a variable, the **preprocessor replaces** every occurrence of the macro name with its value **before compilation**.

### Syntax

```c
#define NAME value
```

Notice:

- ❌ No `=`
- ❌ No `;`

---

### Example

```c
#include <stdio.h>

#define MAX_ATTEMPTS 3

int main()
{
    printf("%d", MAX_ATTEMPTS);

    return 0;
}
```

Before compilation, the compiler effectively sees:

```c
printf("%d", 3);
```

---

## ✅ Advantages

- No memory allocation
- Fast replacement during preprocessing
- Commonly used for mathematical constants and configuration values

---

# 3. Enumeration Constants (`enum`)

An **enumeration** defines a collection of related **integer constants**.

By default:

- First value → `0`
- Next values increase by `1`

### Example

```c
enum Days
{
    MON = 1,
    TUE,
    WED,
    THU,
    FRI,
    SAT,
    SUN
};
```

The values become:

| Constant | Value |
|----------|------:|
| `MON` | 1 |
| `TUE` | 2 |
| `WED` | 3 |
| `THU` | 4 |
| `FRI` | 5 |
| `SAT` | 6 |
| `SUN` | 7 |

---

## ✅ Advantages

- Improves readability
- Automatically assigns values
- Ideal for menus, states, weekdays, months, etc.

---

# 📊 Comparison of Constant Methods

| Feature | `const` | `#define` | `enum` |
|---------|---------|-----------|--------|
| Nature | Read-only variable | Text substitution macro | Integer constants |
| Handled By | Compiler | Preprocessor | Compiler |
| Type Safe | ✅ Yes | ❌ No | ✅ Yes |
| Memory Address | ✅ Yes | ❌ No | ❌ No |
| Scope | Block/File Scope | Global from definition point | Block/File Scope |
| Data Types | Any type | Any literal | Integers only |

---

# 📚 Types of Constant Literals

Constants written directly in code are called **literals**.

---

# 🔢 Integer Constants

Whole numbers without decimal points.

### Decimal

```c
10
25
-100
```

---

### Octal

Starts with **0**

```c
023
075
```

---

### Hexadecimal

Starts with **0x**

```c
0x2F
0xFF
```

---

### Integer Suffixes

```c
70U
```

Unsigned Integer

```c
50L
```

Long Integer

```c
100UL
```

Unsigned Long Integer

---

# 🌊 Floating-Point Constants

Numbers containing decimal values.

### Standard Form

```c
3.14
-25.65
0.005
```

---

### Scientific Notation

```c
4.2e3
```

Means

```
4.2 × 10³ = 4200
```

Another example

```c
5.6e-2
```

Means

```
5.6 × 10⁻² = 0.056
```

---

# 🔤 Character Constants

A **single character** enclosed in **single quotes**.

Examples

```c
'A'
'B'
'9'
'$'
```

---

# 📝 String Constants

A sequence of characters enclosed in **double quotes**.

Examples

```c
"Hello"
"CodeCrafters"
"C Programming"
```

---

# 🔙 Escape Sequence Constants

Escape sequences begin with a backslash (`\`) and represent special characters.

| Escape Sequence | Meaning |
|----------------|---------|
| `\n` | New Line |
| `\t` | Horizontal Tab |
| `\\` | Backslash |
| `\"` | Double Quote |
| `\'` | Single Quote |
| `\0` | Null Character |

### Example

```c
printf("Hello\nWorld");
```

Output

```
Hello
World
```

---

# 💻 Example Program

```c
#include <stdio.h>

#define MAX_MARKS 100

enum Days
{
    MON = 1,
    TUE,
    WED
};

int main()
{
    const float PI = 3.14159;

    printf("PI = %.5f\n", PI);
    printf("Maximum Marks = %d\n", MAX_MARKS);
    printf("First Day = %d\n", MON);

    return 0;
}
```

---

# ⚠️ Common Mistakes

### ❌ Trying to Modify a `const`

```c
const int speed = 100;

speed = 120;
```

---

### ❌ Using `=` with `#define`

```c
#define PI = 3.14
```

Correct

```c
#define PI 3.14
```

---

### ❌ Adding a Semicolon

```c
#define MAX 100;
```

Correct

```c
#define MAX 100
```

---

### ❌ Using Double Quotes for Characters

```c
char grade = "A";
```

Correct

```c
char grade = 'A';
```

---

# 💡 Best Practices

- ✅ Use `const` whenever a value should never change.
- ✅ Use `#define` for compile-time macros and configuration constants.
- ✅ Use `enum` for groups of related integer values.
- ✅ Give constants meaningful names such as `MAX_BUFFER_SIZE` or `PI`.
- ✅ Follow the `UPPER_SNAKE_CASE` naming convention for macro constants.

---

# 🎯 Key Takeaways

- ✅ Constants are **fixed values** that cannot change during program execution.
- ✅ C provides **three ways** to define constants:
  - `const`
  - `#define`
  - `enum`
- ✅ `const` creates a type-safe, read-only variable.
- ✅ `#define` performs text substitution before compilation.
- ✅ `enum` is ideal for related integer constants.
- ✅ Constant literals include:
  - Integer
  - Floating-point
  - Character
  - String
  - Escape sequence constants

---

# 🚀 What's Next?

Now that you've learned about **Constants**, continue with:

- 🧮 Data Types
- ➕ Operators
- 📥 Input & Output
- 🔀 Type Conversion
- 🔁 Control Statements
- 🔧 Functions
- 📚 Storage Classes

Happy Coding! 🚀