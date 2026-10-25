# Libft

## Your very first own library

Summary:

This project is about coding a C library. It will contain a lot of general purpose functions your programs will rely upon.

Version: 16

## Chapter I

## Introduction

C programming can be very tedious when one doesn’t have access to the highly useful standard functions. This project is about understanding the way these functions work, implementing and learning to use them. Your will create your own library. It will be helpful since you will use it in your next C school assignments.

Take the time to expand your libft throughout the year. However, when working on a new project, don’t forget to ensure the functions used in your library are allowed in the project guidelines.

## Chapter II

## Common Instructions

* Your project must be written in C.
* Your project must be written in accordance with the Norm. If you have bonus files/functions, they are included in the norm check and you will receive a 0 if there is a norm error inside.
* Your functions should not quit unexpectedly (segmentation fault, bus error, double free, etc) apart from undefined behaviors. If this happens, your project will be considered non functional and will receive a 0 during the evaluation.
* All heap allocated memory space must be properly freed when necessary. No leaks will be tolerated.
* If the subject requires it, you must submit a Makefile which will compile your source files to the required output with the flags -Wall, -Wextra and -Werror, use cc, and your Makefile must not relink.
* Your Makefile must at least contain the rules $(NAME), all, clean, fclean and re.
* If your project allows you to use your libft, you must copy its sources and its associated Makefile in a libft folder with its associated Makefile. Your project’s Makefile must compile the library by using its Makefile, then compile the project.
* We encourage you to create test programs for your project even though this work won’t have to be submitted and won’t be graded. It will give you a chance to easily test your work and your peers’ work. You will find those tests especially useful during your defence. Indeed, during defence, you are free to use your tests and/or the tests of the peer you are evaluating.

## Chapter III

## Mandatory part

### Program name: libft.a

**Description**: Write your own library: a collection of functions that will be a useful tool for your cursus.

### III.1 Technical considerations

* Declaring global variables is forbidden.
* If you need helper functions to split a more complex function, define them as _static functions. This way, their scope will be limited to the appropriate file.
* Place all your files at the root of your repository.
* Turning in unused files is forbidden.
* Every .c files must compile with the flags _-Wall -Wextra -Werror_.
* You must use the command _ar_ to create your library. Using the _libtool_ command is forbidden.
* Your _libft.a_ has to be created at the root of your repository.

### III.2 Part 1 - Libc functions

To begin, you must redo a set of functions from the _libc_. Your functions will have the same prototypes and implement the same behaviors as the originals. They must comply with the way they are defined in their man. The only difference will be their names. They will begin with the ’ft_’ prefix. For instance, strlen becomes ft_strlen.

You must write your own function implementing the following original ones. They do not require any external functions:

* isalpha, isdigit, isalnum, isascii, isprint
* strlen, memset, bzero, memcpy, memmove, strlcpy
* strlcat, toupper, tolower, strchr, strrchr
* strncmp, memchr, memcmp, strnstr, atoi

In order to implement the two following functions, you will use malloc():

* calloc
* strdup

### III.3 Part 2 - Additional functions

In this second part, you must develop a set of functions that are either not in the libc, or that are part of it but in a different form.

**Function name:** ft_substr

**Description:** Allocates (with malloc(3)) and returns a substring from the string ’s’. The substring begins at index ’start’ and is of
maximum size ’len’.

**Function name:** ft_strjoin

**Description:** Allocates (with malloc(3)) and returns a new string, which is the result of the concatenation of ’s1’ and ’s2’.

**Function name:** ft_strtrim

**Description:** Allocates (with malloc(3)) and returns a copy of ’s1’ with the characters specified in ’set’ removed from the beginning and the end of the string.

**Function name:** ft_split

**Description:** Allocates (with malloc(3)) and returns an array of strings obtained by splitting ’s’ using the character ’c’ as a delimiter. The array must end with a NULL pointer.

**Function name:** ft_itoa

**Description:** Allocates (with malloc(3)) and returns a string representing the integer received as an argument. Negative numbers must be handled.

**Function name:** ft_strmapi

**Description:** Applies the function ’f’ to each character of the string ’s’, and passing its index as first argument to create a new string (with malloc(3)) resulting from successive applications of ’f’.

**Function name:** ft_striteri

**Description:** Applies the function ’f’ on each character of the string passed as argument, passing its index as first argument. Each character is passed by address to ’f’ to be modified if necessary.

**Function name:** ft_putchar_fd

**Description:** Outputs the character ’c’ to the given file descriptor.

**Function name:** ft_putstr_fd

**Description:** Outputs the string ’s’ to the given file descriptor.

**Function name:** ft_putendl_fd

**Description:** Outputs the string ’s’ to the given file descriptor followed by a newline.

**Function name:** ft_putnbr_fd

**Description:** Outputs the integer ’n’ to the given file descriptor.

## Chapter IV

## Bonus part

If you completed the mandatory part, do not hesitate to go further by doing this extra one. It will bring bonus points if passed successfully.

Functions to manipulate memory and strings is very useful. But you will soon discover that manipulating lists is even more useful.

You have to use the following structure to represent a node of your list. Add its declaration to your libft.h file:

```C
typedef struct      s_list
{
    void            *content;
    struct s_list   *next;
}                   t_list;
```

Implement the following functions in order to easily use your lists.

ft_lstnew, ft_lstadd_front, ft_lstsize, ft_lstlast, ft_lstadd_back, ft_lstdelone, ft_lstclear, ft_lstiter, ft_lstmap