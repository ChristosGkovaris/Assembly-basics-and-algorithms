# ASSEMBLY BASICS AND ALGORITHMS

This repository contains a **collection of introductory RISC-V Assembly programs**, designed to demonstrate core low-level computing concepts such as recursion, memory access, pointer manipulation, and basic array/string operations.  
It was developed as part of the **Computer Architecture** coursework at the **University of Ioannina**.

---

## TABLE OF CONTENTS
1. [Overview](#overview)  
2. [Features](#features)  
3. [Included Programs](#included-programs)  
4. [Implementation Details](#implementation-details)  
5. [License](#license)  
6. [Contact](#contact)

---

## OVERVIEW

This repository contains **five standalone RISC-V assembly programs** that illustrate fundamental architecture-level mechanisms:

- **Recursive computation**  
- **Linear search**, both with pointer arithmetic and with direct indexing  
- **String copy**, implemented in two different versions using array indexing and pointer traversal  

Each program was developed to strengthen understanding of:

- Register usage conventions  
- Memory addressing modes  
- Function call mechanics (stack frames, saving/restoring registers)  
- Control flow using branches and jumps  

---

## FEATURES

- Clear, minimal RISC-V assembly programs  
- Demonstration of recursion using stack-based activation records  
- Examples of memory load/store instructions  
- Pointer vs. index-based traversal techniques  
- Modular structure with well-commented code  
- Suitable for beginners learning ISA fundamentals

---

## INCLUDED PROGRAMS

### **1. factorial.s**
- Implements recursive factorial calculation  
- Demonstrates stack usage, jal/jr control flow, and base–recursive case structure

### **2. search_no_pointers.s**
- Performs linear search using array indexing  
- Shows address calculation and sequential element checking

### **3. search_with_pointers.s**
- Implements the same search algorithm but using pointer increments  
- Highlights differences between pointer-style and index-style memory traversal

### **4. strcpy_v1.s**
- Copies a null-terminated string using direct index access  
- Demonstrates byte loads/stores and termination conditions

### **5. strcpy_v2.s**
- Pointer-based implementation of string copy  
- Uses pointer increments for more optimized traversal

---

## IMPLEMENTATION DETAILS

- **Instruction set:** RISC-V RV32I  
- **Memory operations:** `lb`, `sb`, `lw`, `sw` for accessing data  
- **Control flow:** `beq`, `bne`, `j`, `jal`, `jr`  
- **Recursion:** Stack-allocated frames with saved return addresses  
- **Strings & arrays:** Null-terminated traversal and sequential memory scanning  
- **Pointer arithmetic:** Incremental updates on base addresses for efficient iteration  

All programs are fully commented to help understand the logic and register usage.

---

## LICENSE

This project was developed as part of the  
**Computer Architecture** course at the University of Ioannina.

Final implementation by the project creators.

---

## CONTACT

**Christos Gkovaris**  
University of Ioannina – Computer Science and Engineering  
GitHub: https://github.com/ChristosGkovaris
