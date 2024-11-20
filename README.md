# ft_printf

`ft_printf` is a custom implementation of the C standard library function `printf`, with added support for specific flags and format specifiers. This project mimics some of the functionality of `printf`, handling various format specifiers and flags.

## Table of Contents

- [Features](#features)
- [Supported Flags](#supported-flags)
- [Supported Specifiers](#supported-specifiers)
- [Functions](#functions)
- [Usage](#usage)
- [Examples](#examples)
- [Compilation](#compilation)

## Features

- Custom implementation of `printf` function with bonus features.
- Support for integer, hexadecimal, pointer, character, string, and percentage output.
- Supports flags like `+`, `#`, and space ` `.
- Recursive handling of numbers and strings to dynamically update length.

## Supported Flags

This implementation of `printf` supports the following flags:

- `+` : Adds a `+` sign to positive numbers.
- `#` : Adds `0x` (or `0X` for uppercase) for hexadecimal values.
- ` ` (space) : Adds a space before positive numbers if `+` is not specified.

## Supported Specifiers

`ft_printf` handles the following specifiers:

- `%c` : Character.
- `%s` : String.
- `%p` : Pointer address (with `0x` prefix).
- `%d` : Decimal integer.
- `%i` : Integer.
- `%u` : Unsigned integer.
- `%x` : Hexadecimal (lowercase).
- `%X` : Hexadecimal (uppercase).
- `%%` : Literal `%`.

## Functions

### Main Functions

- **`int ft_printf(const char *str, ...)`**: Main function that parses input and processes each format specifier.
- **`int ft_is_spec_b(char spec)`**: Checks if a character is a valid specifier.
- **`void ft_parse_flags_b(const char **str, t_flags *flags)`**: Parses flag characters (`+`, `#`, ` `) and sets corresponding flags.

### Helper Functions

- **`void ft_putchar_pf_b(char c, size_t *len)`**: Prints a single character and updates `len`.
- **`void ft_putstr_pf_b(char *str, size_t *len)`**: Prints a string and updates `len`.
- **`void ft_puthexa_pf_b(unsigned long long n, char c, t_flags *flags, size_t *len)`**: Prints a number in hexadecimal format with `0x` or `0X` prefix if the `#` flag is set.
- **`void ft_putptr_pf_b(void *ptr, t_flags *flags, size_t *len)`**: Prints a pointer address in hexadecimal format with a `0x` prefix.
- **`void ft_putsign_pf_b(int n, t_flags *flags, size_t *len)`**: Prints sign or space for a number based on the `+` or ` ` flag.
- **`void ft_putnbr_pf_b(int num, t_flags *flags, size_t *len)`**: Prints an integer with support for the `+` and space flags.
- **`void ft_putuint_pf_b(unsigned int num, size_t *len)`**: Prints an unsigned integer.

## Usage

1. Include the header file `ft_printf_bonus.h`.
2. Use `ft_printf` in your program as you would use the standard `printf` function.

### Example Usage

```c
#include "ft_printf_bonus.h"

int main()
{
    ft_printf("Hello %s!\n", "world");
    ft_printf("Unsigned: %u\n", 12345);
    ft_printf("Hexadecimal: %#x\n", 255);
    ft_printf("Pointer: %p\n", &main);
    ft_printf("Signed with + flag: %+d\n", 42);
    return 0;
}
```

### Expected Output

```
Hello world!
Unsigned: 12345
Hexadecimal: 0xff
Pointer: 0xaddress (will vary)
Signed with + flag: +42
```

## Compilation

To compile `ft_printf`, include all required source files and any dependencies. A typical command might look like:

```sh
gcc -Wall -Wextra -Werror -o ft_printf *.c
```

This will generate an executable file named `ft_printf`.

