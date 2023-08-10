Functions in C are basically like small programs or sub programs if you will.

In some of the older books, functions are also called routines because of their linear nature of execution.

A function in C has three parts:
1. Return value (Output)
2. Argument list (Input)
3. Function Body (Process)

To declare a function in C (note declare not define), you only need to state it's interface, i.e. it's input and output types.

For example let's say you have a function, sum which takes in two integers, adds them and returns their sum. The declaration for this function at the top of the program (under the preprocessor directives) will look something like so

```C
int sum(int num1, int num2);
```

Here the first `int` is the return type of the function, i.e. it notifies the caller what kind of value does this function return. 

Why is this important? Look at [[Types in C]]

Next, in the parenthesis is the argument list of the function, it states that the function takes in two integers, one num1 and one num2.

A question may arise as to why the names are important, we can name the integers anything and nothing about the function will change, so why have them in declaration?

The simple reasoning for that can be explained by changing the function from sum to divide and removing the names.

```C
int divide(int, int);
```

Now, if I call say divide(3, 6), what's the expected output? Is it 2 or 0? 

If it's still not clear, the reason names are a part of declaration is because, they provide context regarding the use case of the variable.

Since not all the functions are Associative and Commutative, it's important to name your variables such that they describe their usage to the function's user.

Let's rename the function's variables to get an idea of what's going on and try to better understand what it does.

```C
int divide(int dividend, int divisor);
```

Just by adding in the names of the variables, now the context of the function is much more clear and now, we know divide(3, 6) should result in 0.

Now, you'll note that this declaration of the function doesn't contain any logic as to how it will process it's inputs. Then how does it know what to do? 

That's a genuine question, and the answer to that is, it simply doesn't.
If you call this function now, it will raise an error. 

So... how are we supposed to add logic? Simple:
You define the function. 

Yes, definition and declaration have different meanings in C.

When a function is declared, you provide it's user interface, i.e. you provide the things a user would care about, input and output, and leave the things which they should not be concerned with, i.e. implementation details or the core logic.

The reasoning behind this design choice is complicated and is discussed further down the line, while studying header files so don't think too much about it for now.

Now, moving to the more important part, how do you define a function?

Well you start by copying your declaration, (so that the compiler knows which function should the logic be attached to)

then, you remove the semi-colon and replace that with a pair of braces and place your logic in that like so:

```C
int sum(int num1, int num2) {
	return num1 + num2;
}

int divide(int dividend, int divisor) {
	return dividend / divisor;
}
``` 

Here `return` is a reserved keyword in C, which means that this function should give the value in front of it to the caller.