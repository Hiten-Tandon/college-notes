Other than if and else statements, which check for all the conditions, we also have switch-case statements in C.

switch-case statements in C work by checking equality of the variable to value, they have the following syntax

```C
switch(<variable>) {
	case <val_1>:
		//statements to be executed when variable == val_1
		break;
	case <val_2>:
		//statements to be executed when variable == val_2
		break;
	.
	.
	.
	default:
		//statemebts to be executed when <variable> equals none of the values.
}
```

Let's take an example program to see how switch works.

Let's say you have to write a program, which takes in a number and prints which day of the week the number represents. If it doesn't, print NA.

So for 1 you'd print "Monday", 2 you'd print "Tuesday" etc. etc.

Following is the program:
```C
int main(int arc, char **argv) {
	int day_of_the_week = 0;
	printf("Enter the day of the week: ");
	scanf("%d", &day_of_the_week);
	printf("\n");

	switch(day_of_the_week) {
		case 1: 
			printf("Monday\n");
			break;
		case 2: 
			printf("Tuesday\n");
			break;
		case 3: 
			printf("Wednesday\n");
			break;
		case 4: 
			printf("Thursday\n");
			break;
		case 5: 
			printf("Friday\n");
			break;
		case 6: 
			printf("Saturday\n");
			break;
		case 7: 
			printf("Sunday\n");
			break;
		default:
			printf("NA\n");
	}

	return 0;
}
```

Now, you maybe wondering, rightfully so, what does the break do here? Well the full details will be discussed while discussing the topic "Modifying the control flow of the program" topic, but, for now what break signifies is that stop executing code here and exit the switch statement. 

If you don't put break, you get what's called as stacking cases.
In stacking cases, the code starts executing and doesn't stop executing, till it finds a break statement.
Let's look at a program using them.

Let's say you have to write a program: Given a number, print it's ordinal indicator. Ordinal indicator of a number is the suffix added to the number to indicate that the number is indicative of a relative position. For example: "Rahul came 1<sup>st</sup> in his class", the 'st' suffix which follows 1 is the ordinal indicator.

Following is the program for this question:
```C
int main(int argc, char **argv) {
	int num = 0;
	printf("Enter the number, you want to know the ordinal suffix of: \n");
	scanf("%d", &num);

	switch(num % 100) {
		case 11:
		case 12:
		case 13:
			printf("th");
			break;
		default:
			switch(num % 10) {
				case 1:
					printf("st");
					break;
				case 2:
					printf("nd");
					break;
				case 3:
					printf("rd");
					break;
				default:
					printf("th");
			}
	}

	return 0;
}
```

This solution is slightly complex looking, so try doing a few testcases by hand to verify for yourself it works. However, what the main showcase was here was the stacking case statements.

11, 12, 13 don't need duplicated code to print th, the one line at the end does the work. 

[[Conditionals in C(III)- ternary operator]]