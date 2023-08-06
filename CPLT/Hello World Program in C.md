The Hello World Program in C is simple:
```C
#include <stdio.h>

int main(int argc, char **argv) {
	printf("Hello, World!");
	return 0;
}
```

Let's analyze this program. 
First we have the preprocessor directive `#include`

`#include` just takes a file, and copies it's contents to the top of your file.

Now, this include preprocessor directive is followed by `<stdio.h>`, the <> represent that the file name inside is a file which ships with compiler, if you wanted to use your own header file, you'd put it's name in "".

Then we don't have any function declarations, because the program doesn't use any functions other than main.

Now, inside main, the first line is `printf("Hello, World!");` which simply prints the text Hello, World to the terminal.

and the last line is return 0. The 0 here signifies that program ended without complications, if some other number is returned it means some error occurred while running the program.

[[Exploring printf]]