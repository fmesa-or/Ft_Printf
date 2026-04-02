<div align="center">

# ft_printf

![Norminette](https://img.shields.io/badge/Norm-passing-brightgreen?style=flat-square) ![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white) ![Makefile](https://img.shields.io/badge/Makefile-427819?style=flat-square) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) ![macOS](https://img.shields.io/badge/macOS-000000?style=flat-square&logo=apple&logoColor=white) ![42 School](https://img.shields.io/badge/42-School-000000?style=flat-square)

*A custom implementation of the printf function in C.*

</div>

---

## About the Project

ft_printf is a custom implementation of the standard C `printf` function. This project recreates the printf functionality to handle various format specifiers and conversion types. It serves as a fundamental exercise in understanding variadic functions, format string parsing, and output formatting at 42 School.

## Requirements

- Compiler: `gcc`
- Flags: `-Wall -Wextra -Werror`
- OS: Linux / macOS
- Standard: C99 or later

## Installation and Usage

### Building

```bash
# Clone the repository
git clone https://github.com/usuario/ft_printf.git
cd ft_printf

# Compile the library
make

# Clean build artifacts
make clean

# Remove all generated files including the library
make fclean

# Rebuild everything
make re
```

### Using the Library

1. Include the header file in your program:
```c
#include "ft_printf.h"
```

2. Compile your program with the ft_printf library:
```bash
gcc -Wall -Wextra -Werror your_file.c -L. -lftprintf -o your_program
```

Or if you need to specify the include path:
```bash
gcc -Wall -Wextra -Werror your_file.c -I. -L. -lftprintf -o your_program
```

### Example

```c
#include "ft_printf.h"

int main(void)
{
    ft_printf("Hello, %s!\n", "World");
    ft_printf("Integer: %d, Hex: %x\n", 42, 42);
    ft_printf("Float: %.2f\n", 3.14159);
    return (0);
}
```

## Supported Format Specifiers

### Conversion Specifiers

- `%c` - Single character
- `%s` - String
- `%p` - Pointer address (hexadecimal)
- `%d` - Decimal integer
- `%i` - Integer
- `%u` - Unsigned decimal integer
- `%x` - Unsigned hexadecimal integer (lowercase)
- `%X` - Unsigned hexadecimal integer (uppercase)
- `%o` - Unsigned octal integer
- `%%` - Literal percent sign

### Flags and Modifiers

- `-` - Left-align output
- `0` - Pad with zeros
- `.` - Precision specifier
- `*` - Width or precision from argument
- `+` - Always show sign for numbers
- ` ` - Space for positive numbers
- `#` - Alternative form

## Implementation Details

### Core Functions

- `ft_printf` - Main printf function
- Format parsing and conversion handling
- Buffer management for output
- Support for variadic arguments

### Additional Utilities

- String manipulation for conversions
- Number formatting and padding
- Character classification for format validation
- Precision and width handling

## File Structure

```
.
├── Makefile              # Compilation rules
├── ft_printf.h           # Header file with function declarations
├── ft_printf.c           # Main printf implementation
├── ft_printf_utils.c     # Utility functions
├── ft_printf_utils2.c    # Additional utility functions
└── README.md             # This file
```

## Compilation Notes

- The library is compiled as a static library: `libftprintf.a`
- The implementation follows the 42 School Norm standards
- All functions handle edge cases and invalid inputs gracefully
- Memory is managed efficiently without external dependencies beyond libc

## Testing

To test the printf implementation, you can create a test program:

```c
#include "ft_printf.h"
#include <stdio.h>

int main(void)
{
    // Example: Basic string formatting
    ft_printf("String: %s\n", "Hello");
    
    // Example: Number formatting
    ft_printf("Numbers: %d, %u, %x\n", -42, 42, 42);
    
    // Example: Alignment and padding
    ft_printf("Padding: |%5d| |%-5d|\n", 42, 42);
    
    // Example: Precision
    ft_printf("Float: %.2f\n", 3.14159);
    
    return (0);
}
```

Compile and run:
```bash
make
gcc -Wall -Wextra -Werror test.c libftprintf.a -o test
./test
```

## Comparison with Standard printf

Key differences and considerations:

- Custom implementation may have subtle behavioral differences in edge cases
- Not all advanced format specifiers may be supported
- Performance characteristics may differ from standard library implementation
- Use for educational purposes and 42 School projects

## Performance Considerations

- Functions are optimized for correctness and compliance with requirements
- Use standard library printf for production code requiring specific optimizations
- Consider using valgrind for memory leak detection: `valgrind ./your_program`

---

<div align="center">
Made with ☕ at <a href="https://42malaga.com">42 Málaga</a>
</div>
