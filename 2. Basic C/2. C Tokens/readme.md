# Tokens in C

> **Chapter:** Basic C → Tokens

---

## 📖 Introduction

A **token** is the **smallest meaningful unit** of a C program that the compiler can recognize and process.

Think of a token as a **word in a sentence**. Just as a sentence is made up of words, a C program is made up of tokens.

Every C program consists of one or more tokens.

For example:

```c
#include <stdio.h>

int main() {
    int age = 18;
    printf("Age = %d", age);
    return 0;
}
```

The compiler breaks this program into individual tokens before compiling it.

---

# Why are Tokens Important?

Without tokens, the compiler cannot understand a program.

Tokens allow the compiler to:

* Recognize keywords
* Identify variables
* Interpret operators
* Read constants
* Understand strings
* Execute program logic

---

# Types of Tokens

There are **six major types of tokens** in C.

| Token Type      | Description                             | Example               |
| --------------- | --------------------------------------- | --------------------- |
| Keywords        | Reserved words with predefined meanings | `int`, `return`, `if` |
| Identifiers     | User-defined names                      | `age`, `totalMarks`   |
| Constants       | Fixed values                            | `10`, `3.14`, `'A'`   |
| Strings         | Sequence of characters                  | `"Hello"`             |
| Operators       | Perform operations                      | `+`, `-`, `*`, `==`   |
| Special Symbols | Punctuation used in programs            | `{ } ( ) ; , #`       |

---

# Example Program

```c
#include <stdio.h>

int main() {
    int age = 18;

    printf("Age = %d", age);

    return 0;
}
```

---

# Token Breakdown

| Token        | Type                                          |
| ------------ | --------------------------------------------- |
| `#`          | Special Symbol                                |
| `include`    | Identifier (used in a preprocessor directive) |
| `<stdio.h>`  | Header File Name                              |
| `int`        | Keyword                                       |
| `main`       | Identifier                                    |
| `(`          | Special Symbol                                |
| `)`          | Special Symbol                                |
| `{`          | Special Symbol                                |
| `age`        | Identifier                                    |
| `=`          | Operator                                      |
| `18`         | Constant                                      |
| `printf`     | Identifier (library function name)            |
| `"Age = %d"` | String Literal                                |
| `,`          | Special Symbol                                |
| `return`     | Keyword                                       |
| `0`          | Constant                                      |
| `;`          | Special Symbol                                |
| `}`          | Special Symbol                                |

---

# 1. Keywords

Keywords are **reserved words** that have predefined meanings in C.

They **cannot** be used as variable names.

Examples:

```c
int
float
return
while
if
else
for
switch
break
continue
```

Example:

```c
int age = 20;
```

Here,

* `int` → Keyword
* `age` → Identifier

---

# 2. Identifiers

Identifiers are names given by the programmer to:

* Variables
* Functions
* Arrays
* Structures
* Files
* Constants

Example:

```c
int marks;
float salary;
char grade;
```

Identifiers here are:

* `marks`
* `salary`
* `grade`

---

## Rules for Identifiers

✅ Can contain:

* Letters
* Digits
* Underscores (`_`)

✅ Must begin with:

* Letter
* Underscore

❌ Cannot:

* Start with a digit
* Contain spaces
* Use special characters
* Use keywords

Valid identifiers:

```c
student
studentName
_marks
count1
```

Invalid identifiers:

```c
1count
student-name
int
total marks
```

---

# 3. Constants

Constants are fixed values that do not change during program execution.

Examples:

```c
100
25
3.14
'A'
```

Example:

```c
int age = 18;
```

Here,

`18` is a constant.

---

## Types of Constants

### Integer Constants

```c
10
25
500
```

---

### Floating Point Constants

```c
3.14
5.6
0.25
```

---

### Character Constants

```c
'A'
'B'
'9'
'@'
```

---

### String Literals

```c
"Hello"
"Programming"
"CodeCrafters"
```

---

# 4. Strings

A string is a sequence of characters enclosed within **double quotation marks**.

Example:

```c
printf("Hello World");
```

Output:

```
Hello World
```

---

# 5. Operators

Operators perform operations on data.

Examples:

```c
+
-
*
/
%
=
==
<
>
&&
||
```

Example:

```c
int sum = a + b;
```

Tokens:

* `int`
* `sum`
* `=`
* `a`
* `+`
* `b`
* `;`

---

# 6. Special Symbols

Special symbols are punctuation marks that help define the structure of a C program.

Examples:

```c
{
}
(
)
[
]
;
,
#
.
*
&
```

Example:

```c
int main() {

}
```

Special symbols here:

```text
(
)
{
}
```

---

# Complete Example

```c
#include <stdio.h>

int main() {

    int num1 = 10;
    int num2 = 20;

    int sum = num1 + num2;

    printf("Sum = %d", sum);

    return 0;
}
```

---

## Token Analysis

| Token        | Type           |
| ------------ | -------------- |
| `int`        | Keyword        |
| `num1`       | Identifier     |
| `=`          | Operator       |
| `10`         | Constant       |
| `+`          | Operator       |
| `printf`     | Identifier     |
| `"Sum = %d"` | String Literal |
| `return`     | Keyword        |
| `0`          | Constant       |

---

# Common Mistakes

### Using Keywords as Identifiers

❌ Wrong

```c
int int = 10;
```

✅ Correct

```c
int number = 10;
```

---

### Starting Identifier with a Number

❌ Wrong

```c
int 2value = 20;
```

✅ Correct

```c
int value2 = 20;
```

---

### Missing Semicolon

❌ Wrong

```c
int age = 18
```

✅ Correct

```c
int age = 18;
```

---

# Key Points

* A token is the smallest meaningful unit in a C program.
* Every C program is made up of tokens.
* C has six primary categories of tokens.
* Keywords are reserved words.
* Identifiers are programmer-defined names.
* Constants represent fixed values.
* Strings are enclosed in double quotes.
* Operators perform operations.
* Special symbols define program structure.

---

# Practice Questions

### Basic

1. What is a token in C?
2. How many major types of tokens are there?
3. What is the difference between a keyword and an identifier?
4. Can an identifier begin with a digit?
5. Is `"Hello"` a constant or a string literal?

---

### Intermediate

Identify the tokens in the following program:

```c
int x = 50;
printf("%d", x);
```

Classify each token into its correct category.

---

### Challenge

Write a C program that declares:

* Two integer variables
* One floating-point variable
* One character variable

Print all the values using `printf()`, then identify every token used in your program.

---

# Summary

Tokens are the building blocks of every C program. Before the compiler translates your code into machine language, it first separates the source code into individual tokens such as keywords, identifiers, constants, operators, string literals, and special symbols. Understanding tokens is essential because every statement you write in C is formed by combining these basic elements correctly.

---

> **Next Chapter:** Keywords →
