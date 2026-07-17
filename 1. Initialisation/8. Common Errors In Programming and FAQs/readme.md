# Common Errors:
**The errors are all total again summarised here as follows:**

## Error

```text
'gcc' is not recognized
```

Reason

GCC is not installed or PATH is incorrect.

Solution

- Install GCC
- Restart Terminal
- Verify PATH

---

## Error

```text
fatal error: stdio.h: No such file
```

Reason

Compiler installation is incomplete.

Solution

Reinstall GCC.

---

## Error

```text
No such file or directory
```

Reason

Wrong file name or wrong folder.

Solution

Use

```bash
dir
```

(Windows)

or

```bash
ls
```

(Linux/macOS)

to verify the file exists.

---

## Error

```text
Permission denied
```

Reason

Trying to execute without permissions or using the wrong command.

Solution

- On Linux/macOS, use `./program_name`
- Ensure the executable has execution permissions if necessary (`chmod +x program_name`).

---

# Best Practices

- Keep one concept per file while learning.
- Save your work frequently (`Ctrl + S`).
- Give files meaningful names.
- Read compiler error messages carefully—they usually tell you what went wrong.
- Practice writing code instead of only reading examples.
- Avoid copying code without understanding it.

---

# Frequently Asked Questions (FAQs)

### Do I need an internet connection to write C programs?

No. Once GCC and your IDE are installed, you can write, compile, and run C programs completely offline.

---

### Can I use another IDE?

Yes. Popular choices include:

- Code::Blocks
- CodeLite
- CLion
- Dev-C++
- Visual Studio (Windows)

For this tutorial, we recommend **Visual Studio Code** because it is lightweight, free, and works consistently across Windows, Linux, and macOS.

---

### What's the difference between a compiler and an IDE?

- **Compiler (GCC):** Converts your C code into an executable program.
- **IDE (VS Code):** Helps you write, edit, organize, and debug your code.

You need both for a comfortable development experience.

---
