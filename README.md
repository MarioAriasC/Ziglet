# Ziglet: A Minimalist, High-Performance Virtual Machine in Zig

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/chrischtel/Ziglet?style=social)](https://github.com/chrischtel/Ziglet)

<img src="docs/logo.svg" alt="Ziglet Logo" width="300">

**Ziglet is a small, fast, and embeddable virtual machine written in Zig.
Designed for performance and simplicity, Ziglet provides a versatile platform
for running sandboxed code, scripting game logic, and more. It's a playground
for experimentation and a foundation for building lightweight, secure
applications.**

## ✨ Current Features

- **Core Architecture:**
  - 16 general-purpose registers
  - 64KB managed memory space
  - Stack-based operations
  - Comprehensive instruction set

- **Instruction Set:**
  - Arithmetic operations (ADD, SUB, MUL, DIV, MOD)
  - Memory operations (LOAD, STORE, MEMCPY)
  - Control flow (JMP, JEQ, JNE, JGT, JLT, JGE)
  - Stack operations (PUSH, POP)
  - Comparison operations (CMP)

- **Debug & Optimization:**
  - Debug mode with instruction tracing
  - Hot path detection
  - Instruction caching
  - Execution statistics
  - Detailed runtime information

- **Memory Management:**
  - Bounds checking
  - Memory protection
  - Safe memory access
  - Resource cleanup

- **Error Handling:**
  - Detailed error contexts
  - Location tracking
  - Actionable suggestions
  - Comprehensive error types

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/chrischtel/Ziglet.git
   cd Ziglet
   ```

2. **Build the project:**
   ```bash
   zig build
   ```

3. **Run the tests:**
   ```bash
   zig build test
   ```

4. **Run examples:**
   ```bash
   # Basic arithmetic
   zig build run-calculator

   # With debug output
   zig build run-calculator -- --debug
   ```

## 📚 Examples

### Basic Arithmetic

```zig
const program = &[_]Instruction{
    .{ .opcode = .LOAD, .dest_reg = 1, .operand1 = 5, .operand2 = 0 },
    .{ .opcode = .LOAD, .dest_reg = 2, .operand1 = 10, .operand2 = 0 },
    .{ .opcode = .ADD, .dest_reg = 3, .operand1 = 1, .operand2 = 2 },
    .{ .opcode = .HALT, .dest_reg = 0, .operand1 = 0, .operand2 = 0 },
};
```

### Memory Operations

```zig
const program = &[_]Instruction{
    .{ .opcode = .LOAD, .dest_reg = 1, .operand1 = 42, .operand2 = 0 },
    .{ .opcode = .STORE, .dest_reg = 1, .operand1 = 100, .operand2 = 0 },
    .{ .opcode = .LOAD_MEM, .dest_reg = 2, .operand1 = 100, .operand2 = 0 },
    .{ .opcode = .HALT, .dest_reg = 0, .operand1 = 0, .operand2 = 0 },
};
```

### Control Flow

```zig
const program = &[_]Instruction{
    .{ .opcode = .LOAD, .dest_reg = 1, .operand1 = 0, .operand2 = 0 },
    .{ .opcode = .CMP, .dest_reg = 1, .operand1 = 5, .operand2 = 0 },
    .{ .opcode = .JLT, .dest_reg = 0, .operand1 = 1, .operand2 = 0 },
    .{ .opcode = .HALT, .dest_reg = 0, .operand1 = 0, .operand2 = 0 },
};
```

## 🎯 Current Use Cases

- **Game Scripting:** Simple game logic and AI behaviors
- **Educational Tool:** Learn about VM internals and Zig
- **Code Sandboxing:** Safe execution of untrusted code
- **Embedded Systems:** Lightweight computation on constrained devices

## 🗺️ Current Development Status

- [x] Core VM implementation
- [x] Basic instruction set
- [x] Memory management
- [x] Stack operations
- [x] Debug support
- [x] Error handling
- [ ] JIT compilation
- [ ] Garbage collection
- [ ] Threading support
- [ ] Network operations
- [ ] File system access
- [ ] Standard library

## 🤝 Contributing

We welcome contributions! Current focus areas:

- Additional instruction set features
- Performance optimizations
- Documentation improvements
- Example programs
- Test coverage

## 📄 License

Ziglet is licensed under the [BSD 3-Clause](LICENSE).

## 🙏 Acknowledgements

- The Zig programming language and community
- Contributors and early adopters

---

**Project Status:** Active Development\
**Latest Update:** 15.02.2025\
**Stability:** Beta
