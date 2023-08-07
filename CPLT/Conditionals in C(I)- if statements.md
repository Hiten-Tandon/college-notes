In programming, some times you have to make a choice, i.e. should I do action<sub>1</sub> or action<sub>2</sub> based on some condition, that's where conditional statements come in play.

Let's take an example.

Let's say you have to write a program which checks whether or not an entered number is odd or even.

We know that if a number leaves remainder 1 when divided by 2, it's odd, if it leaves remainder 0 it's even. 

Now a question may arise, how do I convey this to the computer? That's where conditionals come in.

In C there are three different types of conditional statements, if, switch and ternary expression. Let's take a look at if conditional construct.

The syntax for an if statement is
```C
if(/*0 or non 0 value*/) {
	//statements to be executed if value in the parenthesis above is non-zero
} else if (/*0 or non 0 value*/) {
	//statements to be executed if value in the above parenthesis is non zero, but all the values in the parenthesis of the blocks preceeding this block are zero
} else if (...) {
	...
}
.
.
.
else {
	//statements to be executed if none of the above blocks are executed
}
```

Note that everything except if block can be omitted if it's not needed.
Now let's use this to make our even odd program.


There are 2 possible values of `num % 2`, 0 and 1, and we know that if block will execute when the value in it is non-zero, otherwise the else block will execute. We can use this property to our advantage.

We can use `num % 2` in the if block then when it returns 1 (which is not 0) we know that if block will execute, otherwise, when it returns 0 (which is 0) we know that else block will execute.

```C
#include <stdio.h>

int main(int argc, char **argv) {
	int num = 0;
	
	printf("Enter a number, that you want to check is even or odd\n");
	scanf("%d", &num);
	
	if(num % 2) {
		printf("%d is odd\n", num);
	} else {
		printf("%d is even\n", num);
	}
	
	return 0;
}
```

However there is an obvious flaw in this. What if we want to check for specific value instead of just 0 and non 0, or what if we want to check the ordering of the values?

No doubt it's possible to use mathematics to do stuff like that, but, it would be so over complicated for something so simple.

That is why we have Boolean operations in C. 

Following is the list of Boolean operations and what they do:

|Operator|Syntax|Use|Name|
|:------:|:----:|:-:|:--:|
|\&\&|a \&\& b | returns 1 if a and b are non zero else 0| Logical And |
| \|\| | a \|\| b | returns 1 if either a or b or both are non zero else 0| Logical Or|
|!| !a | returns 1 if a is 0 else 0| Logical Not|
| == | a == b | returns 1 if a and b are equal, otherwise 0 | is equal to |
| != | a != b | returns 1 if a and b are not equal, otherwise 0| is not equal to|
| > | a > b | returns 1 if a is strictly greater than b, otherwise 0| is greater than |
| >= | a >= b| returns 1 if a is greater than or equal to b, otherwise 0| is greater than or equals to|
| \< | a \< b| returns 1 if a is strictly less than b, otherwise 0| is less than |
| \<= | a \<= b| returns 1 if a is less than or equal to b, else 0| is less than or equals to |

Note that, it is advised for readability that, you use one of the operators even if you can get away without them. 

For example, ideally the even odd program should be written like following:

```C
#include <stdio.h>

int main(int argc, char **argv) {
	int num = 0;
	
	printf("Enter a number, that you want to check is even or odd\n");
	scanf("%d", &num);
	
	if(num % 2 == 1) {
		printf("%d is odd\n", num);
	} else {
		printf("%d is even\n", num);
	}
	
	return 0;
}
```

It is because, even though, the `== 1` doesn't add any significance to a small program like this, in a bigger program, it can get challenging to keep up with conditionals which do not use Boolean operators.

Now, it isn't always necessary that you do this, for example if you have a function `is_odd` and you're using that instead of `num % 2` it is understood that, the if block will execute when the number is odd so an equality check is neither needed nor appreciated.

Let's take another example to fully understand the concept of conditionals.

Let's say you have to write a program, which takes a number and prints, fizz if the number is divisible by 3, buzz if the number is divisible by 5, "fizzbuzz" if the number is divisible by both 3 and 5 and finally, the number it self if neither of the conditions hold.

```C
#include <stdio.h>

int main(int argc, char **argv) {
	int num = 0;
	printf("Enter a number: \n");
	scanf("%d", &num);
	
    if ((num % 5 == 0) && (num % 3 == 0)) {
		printf("fizzbuzz\n");
	} else if (num % 3 == 0) {
		printf("fizz\n");
	} else if (num % 5 == 0) {
		printf("buzz\n");
	} else {
		printf("%d\n", num);
	}

	return 0;
}
```

I don't think this needs too much of an explanation, first you check if the number is divisible by both 5 and 3, then you check is it divisible by three, then is it divisible by 5, and if none of the conditions are true, the final block is executed.

# Extra

Generally in programming, the true false conditionals fall under their own type called boolean or bool in honor of George Bool, the inventor of the Boolean algebra, because that's where this construct comes from.

There, you end up having keywords like bool/boolean, true/True, and false/False for your language which represent the boolean type, true condition and false condition respectively.

It is to be noted that these types add no more functionality to the language, because, internally they're stored the same way they are in C, 0 or non 0, or well more generally 1. 

However they add a ton of readability to your program.

That's why, C developers decided to add bool type to C. To use bool type, you have to add the stdbool.h header file with `#include <stdbool.h>`

You can declare boolean variables in your code with the syntax `bool <var_name> = <true> or <false>;` However this is purely syntactic sugar for `int <var_name> = <non_zero> or <zero>;` and neither adds to nor removes from the complexity of the program. In fact the bool definition gets converted to the int definition(sort of) internally in the compiler. 

[[Conditionals in C(II)- switch statements]]