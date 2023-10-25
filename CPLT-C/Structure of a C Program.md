Structure of a C Program is simple, at the top of the file you have preprocessor directives.

A preprocessor directive a statement in a C program which is executed before the compilation of program truly begins.

Next comes the [[Functions in C|function]] declarations.

After this comes the main function. Main function in C can be written effectively in 4 ways.
```c
int main() {
	// statements
	return 0;
}

int main(int argc, char **argv) {
	//statements
	return 0;
}

void main() {
	//statements
}

void main(int argc, char **argv) {
	//statements
}
```

By convention,
```c
int main(int argc, char **argv) {
	//statements
	return 0;
}
```
is used but really any of them can be used.

Also don't pay much attention to `char **v` that will be discussed while discussing pointers in detail.

Finally come the [[Functions in C|function]] definitions.


[[Hello World Program in C]]
