# 📦 C Variables

> A **variable** is a **named memory location** used to store data that can change during the execution of a C program. Instead of working with complex memory addresses, programmers use variables to store, retrieve, and manipulate data easily.

---

## 📚 Table of Contents

- [What is a Variable?](#-what-is-a-variable)
- [Variable Lifecycle](#-variable-lifecycle)
- [Basic Variable Types](#-basic-variable-types)
- [Rules for Naming Variables](#-rules-for-naming-variables)
- [Variable Scope](#-variable-scope)
- [Example Program](#-example-program)
- [Common Mistakes](#-common-mistakes)
- [Key Takeaways](#-key-takeaways)

---

# 📖 What is a Variable?

A variable acts as a **container** that stores data in your computer's memory.

Every variable has:

- 🏷️ A **name** (identifier)
- 📂 A **data type**
- 💾 A **memory location**
- 📊 A **value**

Whenever the value changes, the data stored at that memory location also changes.

### Example

```c
int age = 20;
```

Here,

- `int` → Data type
- `age` → Variable name
- `20` → Stored value

---

# 🔄 Variable Lifecycle

Every variable in C goes through three important stages.

---

## 1️⃣ Declaration

A declaration tells the compiler the **name** and **data type** of a variable.

```c
int age;
```

At this point:

- The compiler knows the variable's type.
- Memory is typically allocated as part of the definition in C.

---

## 2️⃣ Definition

A definition allocates memory for the variable.

In C, declaration and definition usually happen together.

```c
int age;
```

This statement both **declares** and **defines** the variable.

---

## 3️⃣ Initialization

Initialization assigns the variable its first value.

```c
age = 25;
```

or

```c
int age = 25;
```

This combines **definition** and **initialization** in a single statement.

---

## ⚠️ Uninitialized Variables

If a local variable is not initialized, it contains a **garbage value** (an unpredictable value already present in memory).

```c
int number;

printf("%d", number);
```

The output is unpredictable and should **not** be relied upon.

Always initialize variables before using them.

---

# 📊 Basic Variable Types

Different data types occupy different amounts of memory and store different kinds of values.

| Data Type | Keyword | Typical Size | Stores | Example |
|-----------|---------|-------------:|--------|---------|
| Integer | `int` | 4 Bytes | Whole numbers | `int age = 20;` |
| Character | `char` | 1 Byte | Single character | `char grade = 'A';` |
| Floating Point | `float` | 4 Bytes | Decimal numbers | `float price = 19.99f;` |
| Double Precision | `double` | 8 Bytes | More precise decimals | `double pi = 3.14159265;` |

> **Note:** The exact size of a data type may vary depending on the compiler and system architecture.

---

# 📝 Rules for Naming Variables

Variable names follow the same rules as **identifiers**.

---

## ✅ Allowed Characters

Variable names may contain:

- Letters (`A-Z`, `a-z`)
- Digits (`0-9`)
- Underscore (`_`)

✔ Examples

```c
studentName
roll_no
marks2025
```

---

## ✅ First Character

The first character must be:

- A letter
- An underscore (`_`)

✔ Valid

```c
student
_marks
```

❌ Invalid

```c
2student
9marks
```

---

## ❌ No Spaces or Special Characters

Spaces and symbols are not allowed.

❌ Invalid

```c
student name
student-name
student@
```

✔ Valid

```c
student_name
studentName
```

---

## ❌ Keywords Cannot Be Used

Reserved C keywords cannot be variable names.

❌ Wrong

```c
int return;
```

✔ Correct

```c
int result;
```

---

## ✅ C is Case-Sensitive

These are all different variables:

```c
count
Count
COUNT
```

---

# 🌍 Variable Scope

Scope determines **where a variable can be accessed**.

---

## 🟢 Local Variables

Local variables are declared **inside a function or block**.

### Characteristics

- Accessible only inside the block where they are declared.
- Created when the block starts.
- Destroyed when the block ends.

### Example

```c
int main()
{
    int age = 20;

    printf("%d", age);

    return 0;
}
```

Here, `age` exists only inside `main()`.

---

## 🔵 Global Variables

Global variables are declared **outside all functions**.

### Characteristics

- Accessible by all functions (within the same source file, unless restricted).
- Created when the program starts.
- Remain in memory until the program ends.

### Example

```c
int counter = 0;

int main()
{
    counter++;

    return 0;
}
```

---

# 💻 Example Program

```c
#include <stdio.h>

// Global variable
int global_counter = 0;

int main()
{
    // Local variables
    int student_id = 4502;
    float gpa = 3.85;
    char group_letter = 'B';

    printf("ID: %d\n", student_id);
    printf("GPA: %.2f\n", gpa);
    printf("Group: %c\n", group_letter);

    // Updating a variable
    gpa = 3.90;

    printf("Updated GPA: %.2f\n", gpa);

    return 0;
}
```

### Variables Used

| Variable | Type | Scope |
|----------|------|-------|
| `global_counter` | `int` | Global |
| `student_id` | `int` | Local |
| `gpa` | `float` | Local |
| `group_letter` | `char` | Local |

---

# ⚠️ Common Mistakes

### ❌ Using an Uninitialized Variable

```c
int age;

printf("%d", age);
```

---

### ❌ Starting with a Digit

```c
int 1student;
```

---

### ❌ Using a Keyword

```c
int while;
```

---

### ❌ Using Spaces

```c
int total marks;
```

---

### ❌ Using Special Characters

```c
float salary$;
```

---

# 💡 Best Practices

- ✅ Always initialize variables before using them.
- ✅ Choose meaningful names like `studentAge` instead of `a`.
- ✅ Keep variable scope as small as possible.
- ✅ Use `const` for values that should never change.
- ✅ Follow consistent naming conventions throughout your program.

---

# 🎯 Key Takeaways

- ✅ A variable is a **named memory location** used to store data.
- ✅ Every variable has a **data type**, **name**, and **value**.
- ✅ Variables are typically **declared**, **defined**, and **initialized**.
- ✅ Uninitialized local variables contain **garbage values**.
- ✅ Variable names must follow C identifier rules.
- ✅ Variables can be **local** or **global**, depending on where they are declared.
- ✅ Good naming practices make programs easier to read and maintain.

---

# 🚀 What's Next?

Now that you've learned about **Variables**, continue with:

- 🔢 Constants
- 🧮 Data Types
- ➕ Operators
- 📥 Input & Output
- 🔀 Type Conversion
- 🔁 Control Statements
- 🔧 Functions

Happy Coding! 🎉