# 🌙 Luna: A Learning Project

This repository is part of my journey into the internals of **Operating Systems** and **Compiler Design**. It is not a production-ready compiler, but a playground where I explore how code goes from a high-level string to a binary executable.

## 🎓 Learning Objectives (so far)
The goal of this project is to understand:
- How **Lexical Analysis** works (turning text into tokens).
- How **Assembly (x86_64)** interacts with the kernel through **Syscalls**.
- How the **Linking** process works on macOS.
- How to manage a C++ project using **CMake**.

## 🛠 How it works (so far)
Currently, `luna` is a very basic translator. It can read a simple `return` statement and generate the corresponding assembly to exit a program with a specific status code.

1. **The Source**: You write a `.lu` file (e.g., `return 42;`).
2. **The Lexer**: The compiler breaks it down into tokens.
3. **The Assembly**: It generates an `out.asm` file using macOS-specific x86_64 syscalls.
4. **The Binary**: It automatically calls `nasm` and `clang` to produce an executable named `out`.

## 🚀 How to run it
If you are curious and want to see it in action on your Mac:

```bash
# Build the compiler
cmake -S . -B build
cmake --build build

# Compile a .lu file
./build/luna test.lu

# Run the result and check the exit code
./out
echo $?
