Buffer overflows can occur in C when a program writes or reads beyond the boundaries of an allocated buffer. This can happen when the size of the buffer is not correctly determined or when a function that writes or reads data into a buffer** does not check the size of the input or output.**

Here are some common functions that can cause buffer overflows in C:

`gets()`: reads a line of text from the standard input and stores it in a buffer, but it does not check the length of the input

`scanf()`:reads input from the standard input and stores it in a buffer, but it does not check the length of the input

`strcpy()`: copies a string from one buffer to another, but it does not check if the destination buffer has enough space to hold the entire string

`sprintf()`: formats a string and writes it to a buffer, but it does not check if the buffer has enough space to hold the entire formatted string

------------------------------------------
## difference between gets() and scanf()

Both `gets()` and `scanf()` are functions in C that can be used to read input from the user, but there are some differences between them.

The main difference is that `gets()` reads a line of text from the standard input and stores it in a buffer, while` scanf()` reads formatted input from the standard input and stores it in variables.

Here are some more differences between gets() and scanf():

1. Input format: `gets()` reads a line of text until a newline character is encountered, while `scanf()` reads input based on a format string that specifies the type and format of the data to be read.

2. Error handling: `gets()` does not check the length of the input and can cause buffer overflow vulnerabilities, while `scanf()` returns a value that indicates the number of input items successfully read and can be used to detect input errors.

3. Buffer size: `gets()` does not check the size of the input buffer and can potentially read more data than the buffer can hold, while `scanf()` allows you to specify the maximum length of input to be read.

Because of its vulnerability to buffer overflow attacks, `gets()` is generally not recommended for use. `scanf()` is a more versatile function that can handle various input formats and is safer to use because it checks the length of the input and returns a value that can be used to detect errors. However, it's still important to validate user input to ensure that it is within the expected range.

`scanf()` is also vulnerable to buffer overflow if the input length exceeds the size of the buffer used to store the input. However, `scanf()` does offer some additional features that can help mitigate this vulnerability.

One of these features is the **ability to specify a maximum field width in the format string**, which limits the maximum number of characters that can be read into a string. For example, the format string "`%10s`" specifies that a string with a maximum length of 10 characters should be read.

In addition, the `scanf()` function returns the number of input items successfully read, which can be used to detect input errors and prevent buffer overflow. 

--------------------------------------
### formatted input

In C, formatted input refers to the reading of input data from the standard input or a file in a specific format specified by a format string. The `scanf()` function is an example of a C function that reads formatted input.

In formatted input, the format string is used to specify the expected input data types and their format. For example, the format string "`%d`" specifies that an integer should be read from the input, while the format string "`%f`" specifies that a floating-point number should be read.

Here's an example of using scanf() to read formatted input:

```c
int age;
char name[20];

scanf("%d %s", &age, name);
```
In this example, the format string `%d %s` specifies that an integer followed by a string should be read from the input. The `scanf()` function reads an integer and a string from the standard input and stores them in the variables age and name, respectively.

Formatted input is useful when you need to read input in a specific format and convert it to the appropriate data types. 




