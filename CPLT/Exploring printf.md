Let's dive a bit deeper into `printf` as we'll be using it a lot throughout our C programming journey.

`printf` is a standard output function declared in the `stdio.h` header file. 
`printf` stands for print formatted. As the name suggests it prints the contents given to it with custom formatting.

To print text with `printf` you can simply use `printf("<text>");` like we did in the hello world example.
But programs aren't always that simple. What if say you want to print sum of 2 numbers, multiplied by a third number in a function.

```C
void my_fn(int a, int b, int c) {
	//print "(a + b) * c = " (a + b) * c
}
```

What do you do now? Well, `printf` gives us a simple solution for this, formatting.

You can specify the formatting you want to use for your output in the format string. It's easier to explain with code than with words so basically, you'd do the following:
```C
void my_fn(int a, int b, int c) {
	printf("(a + b) * c = %d\n", (a + b) * c);
}
```
Here %d is the format specifier, which tells the `printf` function we want to print a number, Following is the list of formatting specifiers to be used for each data type.

|SPECIFIER|USED FOR|
|---|---|
|%c|a single character|
|%s|a string|
|%hi|short (signed)|
|%hu|short (unsigned)|
|%Lf|long double|
|%n|prints nothing|
|%d|a decimal integer (assumes base 10)|
|%lu| a long unsigned integer|
|%llu| a long long unsigned integer|
|%ld|a long integer|
|%lld| a long long integer|
|%i|a decimal integer (detects the base automatically)|
|%o|an octal (base 8) integer|
|%x|a hexadecimal (base 16) integer|
|%p|an address (or pointer)|
|%f|a floating point number for floats|
|%u|int unsigned decimal|
|%e|a floating point number in scientific notation|
|%E|a floating point number in scientific notation|
|\%\%|the % symbol|

Now this is good and all, but what does the \\n do? the \\n is an escape character. It's called the newline character. It basically changes the line to the next one. There are multiple escape characters, following is the list.

|Escape sequence|Character represented|
|:--|:--|
|\\a|Alert (bell, alarm)|
|\\b|Backspace|
|\\f|Form feed (new page)|
|\\n|New-line|
|\\r|Carriage return|
|\\t|Horizontal tab|
|\\v|Vertical tab|
|\\\'|Single quotation mark|
|\\\"|Double quotation mark|
|\\\?|Question mark|
|\\\\|Backslash|

[[Taking CLI Input in a C program]]