# SrikanthCC - A C++ Subset Compiler  
A high-performance, custom-engineered compiler for a well-defined subset of the **C++** programming language. This project delivers a complete **compiler toolchain** with a focus on **execution efficiency** and **optimized code generation**, incorporating essential stages such as **lexical analysis**, **assembly**, **syntax parsing**, **semantic validation**, and **targeted code emission**.

## Key Components  
- **Lexical Analysis**: Performs precise tokenization, breaking source code into valid C++ lexemes  
- **Assembler**: Converts intermediate assembly into executable MIPS machine code  
- **Parsing**: Implements an LR(1) parser for robust syntax tree construction  
- **Semantic Analysis**: Validates abstract syntax trees for type correctness and rule conformity  
- **Code Generation**: Produces optimized x86 instructions with minimal overhead

## Supported Language Subset  
The compiler handles a focused subset of C++, emphasizing fundamental constructs for clarity and speed. Supported features include:

- **Variables**: Only `int` and `int*` types, initialized with unsigned constants or `NULL`  
- **Control Flow**: Supports `if` (requires `else`), `while`, and `return` constructs  
- **Expressions**: Includes variables, memory ops (`new`, `delete[]`), address/reference operators (`&`, `*`), and arithmetic/relational operators  
- **Memory Management**: Dynamic memory handled via `new` and `delete[]`  
- **Function Constraints**: Functions must end with a single `return` statement

### Finite Automaton Representation  
  ![image](https://github.com/user-attachments/assets/c436f155-027b-4574-b448-93048fd5dc83)


### Lexical Grammar  
The compiler recognizes identifiers, integers, standard delimiters (`() {}`), keywords (`return`, `if`, `else`, `while`), and operators (`+`, `-`, `*`, etc.). Tokens are case-sensitive, and all comments and whitespace are ignored for parsing simplicity.

### Context-Free Grammar  
Programs follow a well-defined CFG structure: functions contain ordered declarations and statements, with expressions built from standard arithmetic and pointer operations. Only basic types (`int`, `int*`) are allowed, and all code adheres to structured, predictable syntax patterns.

### Context-Sensitive Rules  
Semantic checks ensure proper typing, uniqueness of function names, valid variable usage (no use-before-declaration), and consistency in function calls. Recursion is supported, but mutual recursion is deliberately excluded to reduce parsing complexity.

### Semantic Behavior  
The compiler ensures that every accepted program is both syntactically correct and semantically aligned with C++ standards. This allows for seamless integration of the generated x86 code with C++ programs or toolchains, while preserving deterministic behavior.

## Source Code Access & Contact  
The source code is protected under intellectual property considerations due to the effort and originality behind its design. If you’re interested in collaboration, reviewing the implementation, or contributing ideas—especially as newer C++ features are being added (e.g., init-statements, concepts, structured bindings)—please feel free to reach out:  
📧 [tcsrikan@uwaterloo.ca](mailto:tcsrikan@uwaterloo.ca)
