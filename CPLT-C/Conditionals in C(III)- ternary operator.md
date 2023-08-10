The ternary operator in C is a shorthand for an if else statement.
The syntax for ternary operator is as follows:
`<condition> ? <value if condition is non 0> : <value if condition is 0>`

So say you have a variable max and you want to assign it the greater value of the variables a and b.

Following is to code to accomplish the task with if-else.
```C
int max = 0;
if(a > b) {
	max = a;
} else {
	max = b;
}
```

This takes 5 lines for a seemingly simple task. This can be changed with the ternary operator.
```C
int max = a > b ? a : b;
```

There now it only takes one line, which makes the code look cleaner and more readable to an extent.

># <font color = 'yellow'>**⚠ Warning**</font>
>
>It looks like ternary operator can replace if else completely and it is true to some extent, however, too much ternary operator can reduce the readability of the program and hence it should only be used sparingly and in the cases where the `value_if_true` and `value_if_false` are already available as constants or variables and the `condition` contains no compounding i.e. no && and ||. You have been warned.

[[Loops In C(I)- While Loop]]