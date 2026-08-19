# ASSEMBLY BASICS AND ALGORITHMS

This project contains a collection of **RISC-V Assembly programs** implementing recursive computation, linear search, and null-terminated string copying using both index-based and pointer-based memory traversal. It was developed as part of the **MYY505 - Computer Architecture** coursework at the **University of Ioannina**.

---

## TABLE OF CONTENTS

1. [Overview](#overview)
2. [Tech Stack](#tech-stack)
3. [Features](#features)
4. [Architecture](#architecture)
5. [Project Structure](#project-structure)
6. [Input Data](#input-data)
7. [Algorithms Implemented](#algorithms-implemented)
8. [Usage](#usage)
9. [Contributors](#contributors)
10. [License](#license)
11. [Contact](#contact)

---

## OVERVIEW

The repository contains five standalone assembly programs focused on fundamental low-level programming concepts:

- Recursive factorial computation
- Linear search using array indexing
- Linear search using pointer traversal
- Null-terminated string copying using indexed memory access
- Null-terminated string copying using pointer traversal

The implementations demonstrate register usage, memory addressing, stack management, function calls, conditional branching, and direct manipulation of arrays and strings.

---

## TECH STACK

- **Language:** RISC-V Assembly
- **Data Representation:** 32-bit words, byte-addressable strings
- **Core Operations:** Register arithmetic, memory load/store, branching, jumps, stack operations
- **System Interface:** Environment calls (`ecall`)

---

## FEATURES

- **Recursive Function Execution**
  - Recursive factorial calculation
  - Stack allocation for function state
  - Return address preservation and restoration

- **Array Traversal**
  - Index-based address calculation
  - Pointer-based sequential traversal
  - Element comparison and search-result indexing

- **String Manipulation**
  - Byte-level load and store operations
  - Null-terminated string detection
  - Index-based and pointer-based copying approaches

- **Control Flow**
  - Conditional branches
  - Explicit loops
  - Function calls and returns
  - Program termination through environment calls

---

## ARCHITECTURE

The project consists of independent RISC-V Assembly programs rather than a shared application architecture. Each source file contains the data definitions and control flow required for a specific low-level programming task.

The implementations primarily use:

- **Argument registers (`a0`–`a2`)** for addresses, values, and function arguments
- **Temporary registers (`t0`–`t2`)** for intermediate calculations and loaded data
- **Saved register (`s0`)** for traversal indexes
- **Stack pointer (`sp`)** for recursive function state
- **Return address register (`ra`)** for recursive function calls
- **Branch and jump instructions** for loops, conditions, calls, and returns

---

## PROJECT STRUCTURE

```text
.
├── factorial.s
├── search_no_pointers.s
├── search_with_pointers.s
├── strcpy_v1.s
└── strcpy_v2.s
```

- `factorial.s` — Recursive factorial implementation using stack-based function calls
- `search_no_pointers.s` — Linear search using index-based address calculation
- `search_with_pointers.s` — Linear search using direct pointer traversal
- `strcpy_v1.s` — Null-terminated string copy using indexed memory access
- `strcpy_v2.s` — Null-terminated string copy using pointer increments

---

## INPUT DATA

The examples use statically defined input values within the assembly source files.

### Factorial

`factorial.s` initializes the factorial argument to:

```text
4
```

### Linear Search

Both search implementations operate on:

```text
[10, 3, -10, 234, 22, 5]
```

with:

```text
Search value: 22
Number of elements: 6
```

### String Copy

Both string-copy implementations use:

```text
Source: "This is a 0 string!"
Destination buffer: 100 bytes
```

---

## ALGORITHMS IMPLEMENTED

### Recursive Factorial

`factorial.s` computes the factorial of an integer recursively.

For each recursive call, the program:

1. Allocates an 8-byte stack frame.
2. Stores the return address and current argument.
3. Checks the base condition.
4. Decrements the argument and recursively calls the factorial function.
5. Restores the previous argument and return address.
6. Multiplies the current value by the recursive result.

The recursive relationship is:

```text
factorial(n) = n × factorial(n - 1)
```

with the implemented base case returning `1` when the argument is less than `1`.

### Linear Search — Index-Based

`search_no_pointers.s` performs sequential linear search using an index.

For each element, the address is calculated using:

```text
address = base_address + (index × 4)
```

The current 32-bit value is loaded and compared with the target. The index is incremented until the target is found or all elements have been examined.

### Linear Search — Pointer-Based

`search_with_pointers.s` implements the same sequential search while traversing memory directly.

Instead of recalculating each element address from the base address and index, the array pointer advances by four bytes after each comparison:

```text
pointer = pointer + 4
```

An index is maintained separately to identify the position of a matching element.

### String Copy — Index-Based

`strcpy_v1.s` copies a null-terminated string byte by byte using an index to calculate source and destination addresses.

The process continues until the copied byte is zero, representing the string terminator.

### String Copy — Pointer-Based

`strcpy_v2.s` performs the same byte-level copy using direct source and destination pointers.

After each byte is copied, both pointers advance by one byte:

```text
source_pointer = source_pointer + 1
destination_pointer = destination_pointer + 1
```

Traversal stops after the null terminator has been copied.

---

## USAGE

Each `.s` file is a standalone assembly program and can be executed independently in a RISC-V environment that supports the instructions and environment calls used by the source code.

Select the program to examine or execute:

```text
factorial.s
search_no_pointers.s
search_with_pointers.s
strcpy_v1.s
strcpy_v2.s
```

The example inputs are defined directly in the corresponding source files and can be modified before execution to test different values.

---

## CONTRIBUTORS

- **Christos Gkovaris** — GitHub: [ChristosGkovaris](https://github.com/ChristosGkovaris)

---

## LICENSE

No formal software license is included in the provided project files.

This project was developed as part of the **MYY505 - Computer Architecture** coursework at the **University of Ioannina**.

---

## CONTACT

**Christos Gkovaris**  
Computer Science and Engineering  
University of Ioannina  
GitHub: [ChristosGkovaris](https://github.com/ChristosGkovaris)