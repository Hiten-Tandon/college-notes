While programming, sometimes you need to repeat some task, maybe until a condition is true, or maybe a set number of times or maybe you need to do it at least once and then repeat it based on the user feedback.

This is called looping, and there are 3 kinds of loops in C.
1. While loops
2. Do-while loops
3. For loops

Let's have a look at while loops.

While loops are entry controlled loops, which is a fancy way of saying they check a condition before entering the loop then continue the execution of the loop till that condition remains true. Note that all the statements in the loops body are executed before the condition is checked again.

Let's say we have to write a function in C, which takes in a number, reverses it and returns it to the caller, let's call it `rev_num`.

Following would be the code for it:
```C
int rev_num(int num) {
	int res = 0;
	
	while(num != 0) {
		res *= 10; //res *= 10 is shorthand for res = res * 10
		res += num % 10; //similarly res += x is shorthand for res = res +
		num /= 10;//you get the idea.
	}
	
	return res;
}
```

Let's take a mock input say `num = 52345` for the function and solve the loop by hand to get a better idea of what's happening.
```
num = 52345
res = 0

is num not 0? Yes:
	res = res * 10 = 0 * 10 = 0
	res = res + num % 10 = 0 + 52345 % 10 = 0 + 5
	num = num / 10 = 52345 / 10 = 5234 (.5 is dropped because the type of data is int)
is num not 0? Yes:
	res = res * 10 = 5 * 10 = 50
	res = res + num % 10 = 50 + 5234 % 10 = 50 + 4 = 54
	num = num / 10 = 5234 / 10 = 523
is num not 0? Yes:
	res = res * 10 = 54 * 10 = 540
	res = res + num % 10 = 540 + 523 % 10 = 540 + 3 = 543
	num = num / 10 = 52
is num not 0? Yes:
	res = res * 10 = 5430
	res = res + num % 10 = 5430 + 52 % 10 = 5430 + 2 = 5432
	num = num / 10 = 52 / 10 = 5
is num not 0? Yes:
	res = res * 10 = 54320
	res = res + num % 10 = 54320 + 5 % 10 = 54320 + 5 = 54325
	num = num / 10 = 5 / 10 = 0
is num not 0? No:
	break.

return res
```

This is how the above program works, it's fairly simple but it tells us quite a lot about how while works.