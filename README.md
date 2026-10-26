# libft (bonus included)

Libft is a custom C library that reimplements a set of standard _libc_ functions and adds extra utility functions for strings, memory, file descriptors, and linked lists.

The goal of the project is to understand how low-level C functions work internally and to build a reusable library for future 42 projects.

Completed at 42 Berlin (Dec 2023 - Jan 2024) as part of the core C curriculum.

## What this project contains

- Reimplemented libc-style functions (for example: `ft_strlen`, `ft_memcpy`, `ft_strncmp`, `ft_atoi`, `ft_strdup`, `ft_calloc`)
- Additional utility functions (for example: `ft_substr`, `ft_strjoin`, `ft_strtrim`, `ft_split`, `ft_itoa`)
- File descriptor output helpers (`ft_putchar_fd`, `ft_putstr_fd`, `ft_putendl_fd`, `ft_putnbr_fd`)
- Bonus linked-list functions (`ft_lstnew`, `ft_lstadd_front`, `ft_lstadd_back`, `ft_lstclear`, `ft_lstmap`, ...)

Output artifact:

- `libft.a` (static library)

## Prerequisites

### Operating system

This library can be compiled on Linux and macOS.

### Required tools/packages

- A C compiler supporting C code used in 42 projects (`cc`, `gcc`, or `clang`)
- `make`
- `ar` (GNU binutils on Linux, or BSD ar on macOS)
- Standard C development headers/toolchain

## Build with Makefile

- `make` or `make all`: build `libft.a`
- `make clean`: remove object files
- `make fclean`: remove object files and `libft.a`
- `make re`: full rebuild (`fclean` + `all`)

## How to use it in another project as a custom library

One common 42 workflow is to add this repository as a `libft/` directory inside another project and call its Makefile from your main Makefile.

Example variables in your project Makefile:

```makefile
LIBFT = libft
LIB = $(LIBFT)/libft.a
```

Build libft from your project:

```makefile
$(LIB):
	@make -C $(LIBFT)
```

Link your project with libft:

```makefile
$(NAME): $(OBJ) $(LIB)
	$(CC) $(CFLAGS) $(OBJ) $(LIB) -o $(NAME)
```

## Knowledge note

A **static library** (`.a` on Linux/macOS, `.lib` on Windows) is a bundle of object files that **gets copied into your program at link time**. After linking, the executable contains its own copy of every library function it uses, and it no longer needs the `.a` file to run.

The non-static kind is a **dynamic library**, also called a **shared library** (`.so` on Linux, `.dylib` on macOS, `.dll` on Windows). The linker doesn’t copy the code in. It only records “this program needs libft.so”, and the library is loaded **when the program starts** (or later, on demand). Many programs can share one copy of it in memory.

(c) Maryna Peshko
