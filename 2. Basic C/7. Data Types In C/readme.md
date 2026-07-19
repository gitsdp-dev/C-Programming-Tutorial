# C Programming Tutorial: Data Types Deep Dive

[![GitHub repo](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/gitsdp-dev/C-Programming-Tutorial)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Welcome to the **C Programming Tutorial**! This repository is designed to help beginners master the fundamentals of C, starting with one of the most critical topics: **Data Types**.

In C, every variable must have a type. This README will guide you through everything you need to know about data types—from primitive types to advanced concepts like padding, floating-point anomalies, and storage classes. We've packed it with examples, quizzes, and best practices to make your learning interactive and enjoyable.

> 🚀 **New to C?** Start here. Experienced? Use this as a reference.

---

## 📚 Table of Contents

1. [Basic Data Types (Primitive)](#1-basic-data-types-primitive)  
   - [Type Modifiers](#type-modifiers)  
2. [Derived Data Types](#2-derived-data-types)  
3. [User-Defined Data Types](#3-user-defined-data-types)  
4. [Void Data Type](#4-void-data-type)  
5. [Integer Storage Mechanics](#5-integer-storage-mechanics)  
   - [Exact Bit-Width Types](#exact-bit-width-types-stdinth)  
   - [Overflow vs. Wraparound](#undefined-behavior-overflow-vs-wraparound)  
6. [Floating-Point Types & IEEE 754](#6-floating-point-types--ieee-754)  
   - [Floating-Point Anomalies](#floating-point-anomalies)  
7. [Pointers and Arrays](#7-pointers-and-arrays)  
8. [Structs, Unions, and Padding](#8-structs-unions-and-padding)  
   - [Structure Padding & Alignment](#structure-padding--alignment)  
   - [Unions and Overlapping Fields](#unions-and-overlapping-fields)  
9. [Type Conversions & Implicit Promotion](#9-type-conversions--implicit-promotion)  
   - [Integer Promotion](#integer-promotion)  
   - [Value-Destructive Conversions (Demotion)](#value-destructive-conversions-demotion)  
10. [Storage Class Specifiers](#10-storage-class-specifiers)  
11. [Exercises & Quizzes](#-exercises--quizzes)  
12. [Next Steps](#-next-steps)  

---

## 1. Basic Data Types (Primitive)

These are the built‑in types that store simple values. In C, every variable must be declared with a type before use. The table below shows the most common ones.

| Data Type        | Keyword  | Typical Size* | Format Specifier | Description                                 |
|------------------|----------|---------------|------------------|---------------------------------------------|
| Integer          | `int`    | 4 bytes       | `%d` or `%i`     | Whole numbers (no decimals)                 |
| Character        | `char`   | 1 byte        | `%c`             | Single character or ASCII value             |
| Floating‑Point   | `float`  | 4 bytes       | `%f`             | Fractional numbers (~6–7 decimal digits)    |
| Double Precision | `double` | 8 bytes       | `%lf`            | Fractional numbers (~15 decimal digits)     |

> ⚠️ *The exact size depends on your hardware and compiler. Use `sizeof()` to check on your machine.

### Type Modifiers

You can modify basic types to change their range or size:

- **`signed`** – (default) allows both positive and negative values.  
- **`unsigned`** – only positive values, doubling the upper limit.  
- **`short`** – reduces memory (often 2 bytes).  
- **`long`** / **`long long`** – increases capacity for huge numbers.

```c
signed int a = -10;      // default
unsigned int b = 20;     // only positive
short int c = 100;       // smaller
long long int d = 123456789012345LL;
```

---

## 2. Derived Data Types

Derived data types are built using the primitive data types.

### Arrays

Arrays are fixed-size collections of **identical elements** stored in **contiguous memory locations**.

```c
int arr[5] = {1, 2, 3, 4, 5};
```

Memory Layout:

```text
+----+----+----+----+----+
| 1  | 2  | 3  | 4  | 5  |
+----+----+----+----+----+
```

---

### Pointers

Pointers are variables that store the **memory addresses** of other variables.

```c
int *ptr = &arr[0];
```

Example:

```text
arr[0] = 1
Address = 0x1000

ptr = 0x1000
```

---

### Functions

Functions are reusable blocks of code with a defined **return type** and **parameter list**.

```c
int add(int x, int y)
{
    return x + y;
}
```

---

### Complete Example

```c
int arr[5] = {1, 2, 3, 4, 5};   // Array

int *ptr = &arr[0];            // Pointer

int add(int x, int y)          // Function
{
    return x + y;
}
```

---

## 3. User-Defined Data Types

C allows programmers to create custom data types to model real-world data more effectively.

### Structure (`struct`)

A structure groups multiple variables of **different data types** into a single unit.

```c
struct Person
{
    char name[50];
    int age;
};
```

Example:

```c
struct Person student;
```

---

### Union (`union`)

A union allows multiple members to **share the same memory location**.

Only one member can hold a meaningful value at a time.

```c
union Data
{
    int i;
    float f;
    char str[20];
};
```

---

### Enumeration (`enum`)

An enumeration creates a set of **named integer constants**.

```c
enum Color
{
    RED,
    GREEN,
    BLUE
};
```

By default:

```text
RED   = 0
GREEN = 1
BLUE  = 2
```

---

### Type Definition (`typedef`)

`typedef` creates an alias for an existing type.

```c
typedef unsigned long ulong;
```

Now:

```c
ulong number;
```

is equivalent to:

```c
unsigned long number;
```

---

### Complete Example

```c
struct Person
{
    char name[50];
    int age;
};

union Data
{
    int i;
    float f;
    char str[20];
};

enum Color
{
    RED,
    GREEN,
    BLUE
};

typedef unsigned long ulong;
```

---

## 4. Void Data Type

The `void` data type represents the **absence of a value**.

You cannot create ordinary variables of type `void`.

Instead, it is commonly used in the following situations.

---

### Function Returning No Value

```c
void printMessage(void)
{
    printf("Hello!\n");
}
```

---

### Function Taking No Arguments

```c
int main(void)
{
    return 0;
}
```

---

### Generic Pointers

A `void*` pointer can point to any data type.

```c
void *generic_ptr;
```

Example:

```c
int number = 10;

void *ptr = &number;
```

---

## 5. Integer Storage Mechanics

Integers are stored in **binary form**.

Modern systems typically use **Two's Complement Representation** for signed integers.

The **Most Significant Bit (MSB)** determines the sign.

```text
0 → Positive
1 → Negative
```

Example:

```text
00000101 = +5
11111011 = -5
```

---

### Mathematical Range Formulas

For an `n`-bit integer:

| Type | Range |
|-------|-------|
| Signed | `[-2^(n-1), 2^(n-1)-1]` |
| Unsigned | `[0, 2^n - 1]` |

Example for 8 bits:

| Type | Range |
|-------|-------|
| signed | -128 to 127 |
| unsigned | 0 to 255 |

---

### Exact Bit-Width Types (`<stdint.h>`)

The C99 standard introduced exact-width integer types.

```c
#include <stdint.h>

int8_t   a;
uint8_t  b;
int32_t  c;
uint64_t d;
```

| Type | Bits |
|-------|-----:|
| int8_t | 8 |
| uint8_t | 8 |
| int32_t | 32 |
| uint64_t | 64 |

---

### Overflow vs Wraparound

#### Unsigned Overflow

Unsigned integers wrap around automatically.

```c
unsigned char u = 255;

u++;
```

Result:

```text
0
```

because:

```text
255 + 1 = 256
256 mod 256 = 0
```

---

#### Signed Overflow

Signed overflow causes **Undefined Behavior (UB)**.

```c
signed char s = 127;

s++;
```

Never rely on signed overflow.

---

## 6. Floating-Point Types & IEEE 754

Most systems follow the **IEEE 754 Floating-Point Standard**.

Floating-point numbers are divided into:

- Sign
- Exponent
- Mantissa (Significand)

---

### IEEE 754 Layout

| Type | Bits | Sign | Exponent | Mantissa | Bias |
|-------|-----:|-----:|---------:|---------:|-----:|
| float | 32 | 1 | 8 | 23 | 127 |
| double | 64 | 1 | 11 | 52 | 1023 |

---

### Floating-Point Formula

```text
Value =
(-1)^S × (1.M)₂ × 2^(E - Bias)
```

---

### Rounding Errors

Many decimal numbers cannot be represented exactly in binary.

For example:

```c
if (0.1 + 0.2 == 0.3)
{
    printf("Equal");
}
```

This condition usually evaluates to:

```text
false
```

because:

```text
0.1 and 0.2 are approximated internally.
```

---

### Special Values

IEEE 754 supports special values.

| Value | Meaning |
|--------|---------|
| NaN | Not a Number |
| +Infinity | Positive Infinity |
| -Infinity | Negative Infinity |

Examples:

```c
0.0 / 0.0
```

Produces:

```text
NaN
```

---

```c
1.0 / 0.0
```

Produces:

```text
Infinity
```

---

### NaN Comparison Rule

Any comparison involving `NaN` evaluates to false.

```c
NaN == NaN
```

Result:

```text
false
```

## 7. Pointers and Arrays

Pointers and arrays are closely related concepts in C. Understanding how they work is essential for efficient memory management and advanced programming.

### Pointers

A **pointer** is a variable that stores the **memory address** of another variable.

The size of a pointer depends on the system architecture:

| Architecture | Pointer Size |
|--------------|-------------:|
| 32-bit | 4 Bytes |
| 64-bit | 8 Bytes |

> **Note:** Regardless of the data type (`int*`, `char*`, `float*`, etc.), all pointers have the same size on a given architecture.

---

### Pointer Arithmetic

The pointer's data type determines how far it moves in memory.

| Pointer Type | Increment Size |
|--------------|---------------:|
| `char*` | 1 Byte |
| `int*` | `sizeof(int)` |
| `float*` | `sizeof(float)` |
| `double*` | `sizeof(double)` |

Example:

```c
int arr[3] = {10, 20, 30};

int *p = arr;

printf("%d\n", *(p + 1));
```

Output

```text
20
```

Memory Layout

```text
Address      Value
--------     -----
1000         10
1004         20
1008         30

p = 1000

p + 1 = 1004
```

---

### Arrays and Pointer Arithmetic

Array indexing is simply a more readable form of pointer arithmetic.

```c
arr[i]
```

is equivalent to

```c
*(arr + i)
```

Example

```c
int arr[5] = {1, 2, 3, 4, 5};

printf("%d\n", arr[2]);

printf("%d\n", *(arr + 2));
```

Both statements print

```text
3
```

---

## 8. Structures, Unions, and Padding

### Structure Padding & Alignment

Processors read memory more efficiently when data is aligned to natural memory boundaries.

To improve performance, the compiler inserts **padding bytes** between structure members when necessary.

---

### Example: Poor Memory Layout

```c
struct BadLayout
{
    char a;
    int b;
    char c;
};
```

Memory Layout

```text
Byte Offset

0    a
1    Padding
2    Padding
3    Padding
4    b
5
6
7
8    c
9    Padding
10   Padding
11   Padding

Total = 12 Bytes
```

---

### Improved Memory Layout

Reordering members can reduce padding.

```c
struct GoodLayout
{
    int b;
    char a;
    char c;
};
```

Memory Layout

```text
Byte Offset

0    b
1
2
3
4    a
5    c
6    Padding
7    Padding

Total = 8 Bytes
```

---

### Union and Shared Memory

A **union** allocates memory equal to its **largest member**.

All members share the same memory location.

```c
union Data
{
    int i;
    float f;
};

union Data d;

d.i = 42;

printf("%f\n", d.f);
```

The output is **undefined**, because the bits of the integer are interpreted as a floating-point number.

Memory Illustration

```text
+-------------+
| Shared Area |
+-------------+

i
f

Both occupy the same memory.
```

---

## 9. Type Conversions & Implicit Promotion

Whenever different data types appear in the same expression, C automatically performs conversions.

---

### Integer Promotion

Types smaller than `int` are automatically promoted before arithmetic.

Examples

```c
char
short
```

become

```c
int
```

Example

```c
char a = 100;
char b = 30;

int sum = a + b;
```

Both `a` and `b` are promoted to `int` before addition.

---

### Value-Destructive Conversions (Demotion)

Assigning a larger data type to a smaller one may lose information.

#### Integer Truncation

```c
#include <stdint.h>

uint32_t big = 0x12345678;

uint16_t small = big;
```

Result

```text
small = 0x5678
```

The higher-order bits are discarded.

---

#### Floating-Point to Integer

```c
float pi = 3.14159;

int ipi = pi;
```

Result

```text
ipi = 3
```

The fractional part is **truncated**, not rounded.

---

## 10. Storage Class Specifiers

Storage classes determine a variable's **lifetime**, **visibility**, and **storage location**.

| Storage Class | Lifetime | Scope |
|---------------|----------|-------|
| `auto` | Until block ends | Local |
| `static` | Entire program | Local or File |
| `extern` | Entire program | Global |
| `register` | Until block ends | Local |

---

### `auto`

The default storage class for local variables.

```c
auto int age = 20;
```

Normally, the `auto` keyword is omitted.

---

### `static`

Inside a function:

- Value persists across function calls.

```c
static int counter = 0;
```

Outside a function:

- Limits visibility to the current source file.

---

### `extern`

Declares a variable defined in another source file.

```c
extern int globalVar;
```

---

### `register`

Suggests storing a variable in a CPU register.

```c
register int fast;
```

Modern compilers usually ignore this hint because they automatically optimize register allocation.

---

## 🧪 Exercises

<details>

<summary><strong>💡 Exercise 1: Using <code>sizeof()</code></strong></summary>

Write a C program that prints the size (in bytes) of:

- `int`
- `char`
- `float`
- `double`
- Pointer

Hint:

```c
printf("%zu\n", sizeof(int));
```

</details>

---

<details>

<summary><strong>💡 Exercise 2: Structure Padding</strong></summary>

Create a structure containing:

- `char`
- `int`
- `short`

Print its size using `sizeof()`.

Now reorder the members to reduce padding.

Compare both sizes.

</details>

---

<details>

<summary><strong>💡 Exercise 3: Overflow Check</strong></summary>

Create a program that tests:

```c
uint16_t value = 65535;

value++;
```

Observe the result.

Now repeat with:

```c
int16_t value = 32767;

value++;
```

Research why the behavior is different.

</details>

---

## 📝 Quick Quiz

<details>

<summary><strong>Click to Reveal Questions</strong></summary>

### Question 1

What is the range of a signed `char` on most systems?

- A. 0 to 255
- B. -128 to 127
- C. -127 to 128

---

### Question 2

Which keyword creates a type alias?

- A. `struct`
- B. `union`
- C. `typedef`

---

### Question 3

True or False

```c
0.1 + 0.2 == 0.3
```

is always true in C.

</details>

---

## 📚 Summary

In this chapter, you learned about:

- ✅ Pointers and pointer arithmetic
- ✅ Arrays and contiguous memory
- ✅ Structures and unions
- ✅ Memory alignment and padding
- ✅ Integer promotion
- ✅ Type conversions
- ✅ Storage class specifiers
- ✅ Practical exercises and quizzes

---

## 🚀 What's Next?

Now that you understand **Data Types**, continue with:

- 🔀 Control Flow Statements (`if`, `switch`)
- 🔁 Loops (`for`, `while`, `do-while`)
- 🔧 Functions and Recursion
- 💾 Dynamic Memory Allocation
- 📂 File Handling
- 🌳 Advanced Pointers and Data Structures

Happy Coding! 🎉