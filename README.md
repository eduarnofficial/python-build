# Compiler Architecture Lab using GitHub Actions

## Overview

This project demonstrates the complete C compilation pipeline using **GCC** and common binary analysis tools. The workflow is executed automatically using **GitHub Actions** whenever code is pushed to the `main` branch or the workflow is manually triggered.

## Objectives

* Understand the stages of compilation.
* Learn how source code is transformed into an executable.
* Explore object files and executable formats.
* Inspect binaries using GNU development tools.
* Automate the compilation process using GitHub Actions.

## Project Structure

```text
compiler-architecture-demo/
├── hello.c
├── README.md
└── .github/
    └── workflows/
        └── compiler-lab.yml
```

## Theory

### Compilation Pipeline

The compilation process consists of the following stages:

1. **Preprocessor**

   * Processes `#include`, `#define`, and macros.
   * Command:

     ```bash
     gcc -E hello.c -o hello.i
     ```

2. **Compiler**

   * Converts preprocessed code into assembly language.
   * Command:

     ```bash
     gcc -S hello.c -o hello.s
     ```

3. **Assembler**

   * Converts assembly code into an object file.
   * Command:

     ```bash
     gcc -c hello.c -o hello.o
     ```

4. **Linker**

   * Links object files and libraries to create the executable.
   * Command:

     ```bash
     gcc hello.o -o hello
     ```

## ELF (Executable and Linkable Format)

ELF is the standard executable format used by Linux systems. It stores executable code, shared libraries, object files, symbol tables, and debugging information.

## Object Files

Object files (`.o`) contain machine code that has not yet been linked with libraries.

## Debug Symbols

Compile with:

```bash
gcc -g hello.c -o hello
```

to include debugging information used by tools such as GDB.

## Lab Commands

### Preprocessor

```bash
gcc -E hello.c -o hello.i
```

### Generate Assembly

```bash
gcc -S hello.c -o hello.s
```

### Create Object File

```bash
gcc -c hello.c -o hello.o
```

### Link Object File

```bash
gcc hello.o -o hello
```

### Run Program

```bash
./hello
```

### View ELF Header

```bash
readelf -h hello
```

### View Symbol Table

```bash
nm hello
```

### Disassemble Executable

```bash
objdump -d hello
```

### Display Printable Strings

```bash
strings hello
```

### Display Executable Size

```bash
size hello
```

## GitHub Actions Workflow

The GitHub Actions workflow automatically:

* Checks out the repository.
* Installs GCC and Binutils.
* Compiles the C program.
* Executes the program.
* Displays ELF information.
* Lists symbols.
* Disassembles the executable.
* Shows printable strings.
* Displays executable size.

## Expected Output

```
Sum = 30
```

Additional output will include:

* ELF Header Information
* Symbol Table
* Assembly Instructions
* Printable Strings
* Executable Memory Size

## Requirements

* GCC
* Binutils
* Ubuntu/Linux (or GitHub Actions Ubuntu Runner)

## Learning Outcomes

After completing this lab, you will be able to:

* Explain each stage of the compilation pipeline.
* Generate preprocessed, assembly, object, and executable files.
* Understand ELF and object file structure.
* Inspect binaries using GNU tools.
* Automate compilation and analysis with GitHub Actions.

## Author

Compiler Architecture Lab Demo using GitHub Actions. By www.eduarn.com
