*This project has been created as part of the 42 curriculum by cwoon.*

# Libft

Libft is a C library developed as part of the 42 curriculum. It reimplements selected functions from the C standard library and adds utility functions for string manipulation, memory management, and singly linked-list operations.

The goal is to build a reusable collection of C functions while learning how source files are compiled, packaged into a static library, and integrated into other programs.

## Features

- **Character handling:** Character classification and case conversion.
- **String manipulation:** String length, comparison, searching, copying, joining, trimming, splitting, and conversion.
- **Memory operations:** Memory initialization, copying, comparison, and allocation.
- **Output utilities:** Writing characters, strings, and integers to a specified file descriptor.
- **Singly linked lists:** Node creation, insertion, traversal, transformation, and deletion.
- **Static library:** Packages the implemented functions into `libft.a` for reuse in other C programs.

## Technical Overview

| Component | Details |
|---|---|
| Language | C |
| Build system | Make |
| Compiler | GCC, as configured in the current Makefile |
| Compiler flags | `-Wall -Wextra -Werror` |
| Library format | Static archive (`libft.a`) |
| Archive tool | `ar` |

### Implementation

The project separates functions into individual C source files and declares their interfaces in `libft.h`. The Makefile maintains separate source lists for the mandatory and bonus implementations.

The bonus portion extends the library with singly linked-list operations using a `t_list` structure containing a content pointer and a pointer to the next node.

The build process compiles source files into object files and uses `ar` to package them into a static library.

## Getting Started

### Prerequisites

- GCC or a compatible C compiler
- GNU Make
- `ar`

### Compilation

Clone the repository and enter the project directory:

```bash
git clone https://github.com/colin-woon/1.0_libft.git
cd 1.0_libft
```

Build the mandatory library:

```bash
make
```

Build the library with bonus functions:

```bash
make bonus
```

Other Makefile targets:

```bash
make clean
make fclean
make re
```

The intended output is `libft.a`. The current repository should be checked for the linked-list header include paths before treating these commands as a verified, clean build.

### Using the Library

Include `libft.h` in the source file that calls the library functions. Once the archive has been built successfully, link it when compiling the program:

```bash
gcc main.c -I. -L. -lft -o program
```

Replace `main.c` with your own source file. The linker options `-L.` and `-lft` locate and link `libft.a` from the current directory.

## Testing

The implementation was tested with external test suites:

- [libft-unit-test — alelievr](https://github.com/alelievr/libft-unit-test)
- [libftTester — Tripouille](https://github.com/Tripouille/libftTester)
- [Libftest — jtoty](https://github.com/jtoty/Libftest)

These test suites provided a way to exercise the functions against predefined test cases. When a test failed, investigating the specific case helped develop an understanding of debugging, tracing incorrect behavior, and identifying possible root causes.

The suites used are documented here for reference. This README does not claim that every test in every suite passed.

## Challenges and Lessons Learned

### Understanding the Build Process and Static Libraries

One of the main learning points was understanding what happens after writing individual C functions.

Initially, I did not fully understand the purpose of compiling the functions into a library. During peer evaluation, an evaluator explained how the compiled library could be integrated into another program and used to test its functions.

This helped connect the individual pieces of the project: compiling source files, creating a static archive, and linking the archive into a separate program.

**Key takeaway:** A working function is only one part of the process. Understanding how code is compiled, packaged, and integrated is also essential.

### Learning to Debug Through Test Suites

Using external test suites exposed me to systematic testing. Rather than relying only on whether a function appeared to work for a normal input, I began learning to investigate individual test failures and trace them back to potential causes.

This provided an early introduction to edge cases, debugging, and the importance of checking a function's behavior against expected results.

**Key takeaway:** A failing test provides a specific behavior to investigate. Understanding why the result differs from the expected behavior is more valuable than simply changing code until the test passes.

## Resources

### Project Specification

- [42 Libft repository](https://github.com/colin-woon/1.0_libft)

### Testing Tools

- [alelievr/libft-unit-test](https://github.com/alelievr/libft-unit-test)
- [Tripouille/libftTester](https://github.com/Tripouille/libftTester)
- [jtoty/Libftest](https://github.com/jtoty/Libftest)

### AI Usage

AI tools were used primarily as a learning aid during development. They helped explain unfamiliar code and clarify C syntax, as well as resolve minor issues when I encountered syntax or implementation details I did not fully understand.

The project implementation, testing, and understanding of the code remained part of the learning process. AI assistance was used to support comprehension rather than as a substitute for learning the underlying concepts.

## Author

**cwoon**

[GitHub repository](https://github.com/colin-woon/1.0_libft)
