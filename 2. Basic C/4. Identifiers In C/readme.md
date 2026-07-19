# 🏷️ C Identifiers

> **Identifiers** are **user-defined names** used to identify or name various program elements such as variables, functions, arrays, structures, labels, and more. They help the compiler distinguish one program entity from another.

---

## 📚 Table of Contents

- [What are Identifiers?](#-what-are-identifiers)
- [Rules for Naming Identifiers](#-rules-for-naming-identifiers)
- [Valid vs Invalid Identifiers](#-valid-vs-invalid-identifiers)
- [Keywords vs Identifiers](#-keywords-vs-identifiers)
- [Coding Conventions](#-coding-conventions)
- [Example Program](#-example-program)
- [Key Takeaways](#-key-takeaways)

---

# 📖 What are Identifiers?

Identifiers are **names created by programmers** to represent various entities in a C program.

They can be used for:

- 📦 Variables
- 🔧 Functions
- 📑 Arrays
- 🏗️ Structures
- 🏷️ Labels
- 📚 Enumerations
- 🔗 Typedefs

Unlike **keywords**, identifiers are completely defined by the programmer.

### Example

```c
int age;
float salary;
char grade;

void displayMessage();
```

Here,

- `age`
- `salary`
- `grade`
- `displayMessage`

are all **identifiers**.

---

# 📌 Rules for Naming Identifiers

The C compiler follows strict rules for identifiers.

---

## 1️⃣ Allowed Characters

Identifiers may contain:

- Uppercase letters (`A-Z`)
- Lowercase letters (`a-z`)
- Digits (`0-9`)
- Underscore (`_`)

✅ Valid

```c
student
student1
student_name
_marks
```

❌ Invalid

```c
student-name
student@name
student name
```

---

## 2️⃣ First Character Rule

The first character **must be either**:

- A letter
- An underscore (`_`)

It **cannot** start with a number.

✅ Valid

```c
marks
_total
student1
```

❌ Invalid

```c
1student
9marks
```

---

## 3️⃣ Keywords Cannot Be Used

Identifiers cannot have the same name as a C keyword.

❌ Wrong

```c
int return = 5;
```

```c
float while = 10.5;
```

✅ Correct

```c
int result = 5;
float temperature = 10.5;
```

---

## 4️⃣ C is Case-Sensitive

Uppercase and lowercase letters are treated as different identifiers.

```c
total
Total
TOTAL
```

These are **three different identifiers**.

---

## 5️⃣ No Special Characters

Special symbols and spaces are **not allowed**.

❌ Invalid

```c
student-name
marks%
user@name
student name
```

✅ Valid

```c
student_name
marks2025
userName
```

---

# ✅ Valid vs Invalid Identifiers

| Identifier | Status | Reason |
|------------|--------|--------|
| `student_name` | ✅ Valid | Uses letters and underscore |
| `_temp` | ✅ Valid | Starts with underscore |
| `value1` | ✅ Valid | Digits appear after letters |
| `CalculateSum` | ✅ Valid | Uses uppercase and lowercase letters |
| `student name` | ❌ Invalid | Contains a space |
| `2data` | ❌ Invalid | Starts with a digit |
| `value$1` | ❌ Invalid | Contains `$` |
| `long` | ❌ Invalid | Reserved C keyword |

---

# 🔄 Keywords vs Identifiers

| Feature | Keywords | Identifiers |
|---------|----------|-------------|
| **Definition** | Reserved words with predefined meanings | User-defined names |
| **Created By** | C Language | Programmer |
| **Case** | Always lowercase | Can contain uppercase and lowercase |
| **Characters Allowed** | Alphabetical letters only | Letters, digits, and underscores |
| **Purpose** | Defines C syntax | Identifies program elements |
| **Can be Modified?** | ❌ No | ✅ Yes |

---

# 📝 Coding Conventions

Although the compiler accepts many valid names, following good naming practices makes code easier to read and maintain.

---

## ✅ Use camelCase for Variables & Functions

```c
int totalMarks;
float averageScore;

void calculateArea();
void displayResult();
```

---

## ✅ Use UPPER_SNAKE_CASE for Constants

```c
#define PI 3.14159
#define MAX_BUFFER_SIZE 1024
#define MAX_STUDENTS 100
```

---

## ✅ Choose Descriptive Names

Good names explain the purpose of the variable.

✔ Good

```c
studentAge
employeeSalary
totalAmount
```

❌ Poor

```c
a
b
x
temp1
```

---

## ✅ Avoid Reserved Identifier Patterns

Avoid names beginning with:

```c
__
```

or

```c
_A
```

Examples:

```c
__count
__value
_Age
```

These patterns are often reserved for the compiler or operating system.

---

# 💻 Example Program

```c
#include <stdio.h>

int main()
{
    int studentAge = 20;
    float averageMarks = 89.5;

    printf("Age: %d\n", studentAge);
    printf("Average Marks: %.2f\n", averageMarks);

    return 0;
}
```

### Identifiers Used

- `main`
- `studentAge`
- `averageMarks`

---

# ⚠️ Common Mistakes

❌ Starting an identifier with a number

```c
int 10marks;
```

---

❌ Using spaces

```c
int total marks;
```

---

❌ Using special symbols

```c
float salary$;
```

---

❌ Using keywords

```c
int switch;
```

---

# 💡 Key Takeaways

- ✅ Identifiers are **user-defined names**.
- ✅ They are used for variables, functions, arrays, structures, labels, and more.
- ✅ They may contain **letters, digits, and underscores**.
- ✅ They **cannot begin with a digit**.
- ✅ They **cannot be C keywords**.
- ✅ C is **case-sensitive**, so `value`, `Value`, and `VALUE` are different identifiers.
- ✅ Meaningful names improve code readability and maintainability.

---

# 🎯 What's Next?

Now that you understand **Identifiers**, continue with:

- 🔑 Keywords
- 🔢 Constants
- 📦 Variables
- 🧮 Data Types
- ➕ Operators
- 📥 Input & Output
- 🔁 Control Statements

Happy Coding! 🚀