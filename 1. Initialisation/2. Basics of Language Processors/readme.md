# What Are Language Processors??
Let's take a real-world example to understand this...

Suppose you got a chance to talk to one of the best players in football history, Lionel Messi. You know English, but he only understands Spanish only. Suppose you also do not understand Spanish. Now, there would be a need of a translator who would translate your English into Spanish for Messi, and he would translate Messi's Spanish into English for you to maintain the communication... isn't it??? 😄😄

Now, that's the same case with you and your computer. You only know English and your regional language only. But, Computer only understand 0s and 1s, or ON or OFF, or TRUE and FALSE (Binary Language or Machine Language (sometimes referred as Machine Code)), not English or any other language. So, we use Programming language, which uses English syntax, for communicating with the computer. Now, the question is..... We generally don't code in Binary. So, how can machines understand the languages such as C, C++, C#, Java, Python???

Now there comes the play of Language Processors, which are the same as the translators in normal life. 

## Language Procesors:
**Language Processors are the system softwares which converts the source code writtenm in a particular programming language into machine-readable codes or machine codes or jusr Binary Language, that is understood by Computer necessary for execution.** 

*Language Processors are broadly divided into three types:*
1. Interpreters
2. Compilers
3. Assemblers



## Table of Difference Between Interpreters, Compilers and Assemblers:

| **Point of Difference** | **Compiler** | **Interpreter** | **Assembler** |
|-------------------------|--------------|-----------------|---------------|
| **Input Language** | High-level language (e.g., C++, Java) | High-level language (e.g., Python, JavaScript) | Low-level Assembly language |
| **Translation Method** | Scans and translates the entire program at once | Translates and executes statement by statement | Translates mnemonic codes into binary |
| **Output File** | Generates permanent intermediate object/executable code | Does not generate any separate object file | Generates an object file that needs linking |
| **Execution Speed** | Very fast (once compiled, it runs directly) | Slower (translation happens during every run) | Fast (close to machine instructions) |
| **Error Detection** | Displays all errors collectively after scanning | Displays errors line by line and stops instantly | Displays errors during the parsing phases |
| **Memory Usage** | High (requires space for source, object code, and workspace) | Low (no intermediate files are saved) | Moderate (varies by architecture) |
| **Examples** | GCC (C), Clang, javac | Python Interpreter, Node.js (JavaScript) | GNU Assembler (GAS), NASM |

## Definitions:

### Interpreters: 
These are softwares that read, translate and execute programming instructions sequentially, **line-by-line** , directly into machine code or bytecode or binary code without having to compile the entire program first

### Compilers:
These are special software programs that translates entire block of human-readable source code into low-level machine code or binary code or bytecode all at once. 

**We will use *GCC compiler* to work with C language after sometimes 😄***

### Assemblers: 
This is a fundamental software program that translates human-readable assembly language into the raw binary machine code that a computer can process and execute directly. 
