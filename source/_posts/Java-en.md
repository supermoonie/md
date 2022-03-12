---
title: Java-en
date: 2022-03-11 15:34:05
tags:
- Java
- Base
---

### What are the characteristics of java language ?

- easy to lean
- cross-platform
- object-oriented(encapsulation, inheritance, polymorphism)
- garbage collection
- safety
- reliability
- compilation and interpretation coexist

### JVM vs JRE vs JDK

- JVM: Java Virtual Machine, is a virtual machine that runs Java bytecode.
- JRE: Java Runtime Environment, It is a collection of everything to run a compiled java program.
- JDK: JDK is short for Java Development Kit, it has everything that JRE has, plus the compiler(javac) and tools(like javadoc and jdb). It can create and compile programs.

### What is bytecode? What are the benefits of bytecode ?

bytecode is the code that JVM can understand. It solves the problem of low execution efficiency of traditional interpreted languages, and at the same time contains the portability of interpreted languages.

### What is it said that the java language "compile and interprets side by side" ?

Programs written in java must be compiled first to generate bytecode, which must be interpreted and executed by java interpreter.

### Difference of Java and C++ ?

All object-oriented language that support encapsulation, inheritance, polymorphism.

1. Java cross-platform, C++ not
2. Java has GC, C++ not
3. C++ has pointer that can access memory, Java not
4. C++ is multi-inheritance, Java is not but can implement multi interface
5. C++ support operator overloading, Java not support

### The difference between character constants and string constants ?

- A character constants is a character enclosed by single quotes, and a string constants is zero or more character enclosed by double quotes
- Character constants occupy 2 bytes, string constants occupy several bytes
- A character equal to an integer value, string constants represents an address value(where the string constants stored in memory)

### The difference between identifier and keyword ?

Identifier is the names for program、classes、variable、methods、etc. Keyword is the special identifier.

### The difference between continue、break and return ?

- continue: stop current loop, continue next loop
- break: stop all the loop
- return: stop the method and return

### The difference between == and equals ?



### The difference between overloading and overriding ?

