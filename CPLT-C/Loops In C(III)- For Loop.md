Now, having looked at [[Loops In C(I)- While Loop|while loop]] and [[Loops In C(II)- Do-while Loop|do-while loop]] in C, let's move on to for loops in C.

Which are also called, C-style for loops.

Let's look at the syntax of for loops in C:
```C
for(/*<loop control variable definition>*/; /*Loop Condition*/; /*updation the loop control variable*/) {
	//statements
}
```

Well... That escalated fast. So, let's take a step back and see what is a loop control variable, what is a loop condition and what does updation of the loop control variable mean.

Loop control variable is the variable which decides till when the loop must go on. For example, when we looked at how to [[Loops In C(I)- While Loop#^a2cddb|reverse a number with while loop in C]] we used the number entered by the user, to control the number of times the loops must be executed.

Then, when we wanted to [[Loops In C(II)- Do-while Loop#^317180|run a loop till user pressed e]] we used the character entered by the user to determine whether or not the loop should go further.

These variables are called loop control variables.

Up until now, we had variables defined outside the loop control our loop for us. However that's not always the case.

You see sometimes we create loop-control variables which serve only one purpose of loop control. They're not to be entered by the user, they're not of much relevance to the code outside the loop body, etc. etc. Under such circumstances, keeping the variable outside the loop is of no use.

Hence, in for loop, C devs made it so that, you declare the variable as a part of the loop. Meaning, the variable doesn't exist outside the loop (Something which will be discussed in detail when talking about heap allocations, don't think too much of it).

Second part is the condition of the loop. Much like the condition of while. Nothing too special here.

Third part is the updation of the loop control variable. Well, if the loop control variable doesn't change it's state, the condition will never become false, meaning, it will never end. Hence, it's important to update the variable.

Now why did the C devs decide on this syntax? Goes beyond me.

Let's look at an example of a program with for loop to better understand how to use it.

The problem statement is, you're to write a program which takes in a number and prints it's table up to 10. 

```C
int main(int argc, char **argv) {
	int num = 0;
	printf("Enter a number\n");
	scanf("%d", &num);
	
	for(int multiplicand = 1; multiplicand <= 10; ++multiplicand) {
		printf("%d X %d = %d\n", num * multiplicand);
	}
	
	return 0;
}
```

Let's do a hand unrolling of the loop, like we did for while. Let's say `num` is 2

```
num = 2

multiplicand = 1
is multiplicand <= 10: Yes:
	print "2 X 1 = 2" 
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 2 = 4"
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 3 = 6"
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 4 = 8" 
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 5 = 10"
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 6 = 12"
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 7 = 14"
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 8 = 16"
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 9 = 18"
	multiplicand = multiplicand + 1
is multiplicand <= 10: Yes:
	print "2 X 10 = 20"
	multiplicand = multiplicand + 1
is multiplicand <= 10: No:
	break

return 0
```

After this, it should be pretty clear, what for is doing. One thing you may be thinking to yourself though is "Can't this be solved with while? Why add one more type of loop when 1 does the job?" And my answer to that is, well, it's the designer's choice really, nothing I can do about.

If it helps, Go from google replaced all of these loops with only for loop. 

> # Personal Opinion
> It's not the best choice they made IMHO.
>
> The readability of the programs dropped and well while many developers didn't really care, it is one of my pet peeves because the syntax looked ugly.
> That said, Go otherwise is a really good language and I don't hate it.


[[Pointers in C(I)- Introduction to Pointers]]