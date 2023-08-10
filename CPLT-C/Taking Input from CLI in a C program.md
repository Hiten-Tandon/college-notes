There are quite a few ways to take cli input in a c program. 
We'll be using `scanf` for the time being because it can get us data directly into a variable, instead of us needing to convert it from string(text) to the desired type.

Note that, there are more functions which are nothing but modifications of `scanf`, but they'll be discussed later because of them not having as much relevance now.

Let's take a look at `scanf`, much like `printf`, `scanf` is a standard input function declared in the `stdio.h` header file. The first argument to the function is a format specifier which is a string with stores formatting for the data which is to be entered by the user. 

You see, when data is entered by user, it's always in text format. It is then the job of programmer to convert it to the desired type. `scanf` does this by taking the text entered by the user, and matching it against the format specifier entered by the programmer, and using the variables given to it to store them.

Let's better understand this with a form. Let's say you're the middle man for some examination which is happening and you have been given forms from a lot of students, which you now have to manually type into a computer.

So you've been given a form like so
```
Name: ________
Age: _________
University: ___________
Course: __________
Contact number: __________
Mail ID: ____________
Student ID:___________
```
and you have to fill a form on the portal which looks something like so,

<body>
<input type = 'text' placeholder = 'Name'>  <input type = 'number' placeholder = 'age' size = 3> <input type = 'dropdown' placeholder = 'University' list = 'uninames'>  
<datalist id = 'uninames'>
	<option value = 'JECRC University'>
	<option value = 'Poornima University'>
	<option value = 'Cambridge University'>
	<option value = 'Hogwarts University of Magic Academy'>
	<option value = 'Nalanda vishwa vidyalaya'>
	<!--IDK how you're still alive but ok-->
</datalist>
<br><br>
<input type = 'dropdown' list = 'courses' placeholder = 'Course'> <input type = 'email' placeholder = 'Mail ID' pattern=".+@gmail\.com" required > 
<datalist id = 'courses'>
	<option value = 'B.Tech CSE'>
	<option value = 'B.Tech CSE with AI + ML'>
	<option value = 'B.Tech CSE with cyber security'>
	<option value = 'B.Tech CSE with cloud computing'>
	<option value = 'BCA'>
</datalist>
<br><br>
<input type = 'text' placeholder = 'Student ID'> <input type = 'number' placeholder = 'phone number'>
</body>

Now what will you do, you'd copy the name into the name field, the age into the age field and so on, right...
`scanf` does something similar, but you see computer can not understand the context like us humans can, so for example, in the form above, you know from context that even though in the Contact number is placed in different places and different names in the form filled by the applicant and the form to be filled by you but they'll have the same value, the computer does not understand this. It simply knows "I must obey my master."

What computer can do however, is it can check where the text 'name' occurs in the text entered by user and it can give you the text followed by that, until a special character comes. 

That's exactly what `scanf` does to get user inputs. Let's see this in action with an example.

Following is a program to add 2 numbers entered by the user. Try running it for yourself before you go to the output.
```C
#include <stdio.h>
int main(int argc, char ** argv) {
	int num1 = 0;
	int num2 = 0;
	
	printf("Enter the numbers you want to add in the format \"Add the numbers <num1> and <num2>\" \n");

	scanf("Add the numbers %d and %d", &num1, &num2); 
	/*
	* Ignore the & for now. It's the reference of operator, 
	* basically what it does here is, it tells the compiler 
	* to use these variables for the operations which happen next 
	* instead of copying them. It'll be discussed in more detail later,
	* when studying pointers
	*/

	printf("Sum of %d and %d is %d", num1, num2, num1 + num2);
	return 0;
}
```

Give the program the input `Add the numbers 32 and 15`
and see what it returns.

If you're too lazy to do it yourself here is the result as a photo of my terminal.
![[Pasted image 20230806203722.png]]

This might seem very magical at first but later down the line, when you learn DSA you'll realize that the part of it you're thinking is magical right now is the most basic part of it and the part that you're not even thinking of is the most wonderful thing (and most terrifying and ugly) about this function.

With that said, it really isn't rocket science to figure out what is going on from here and how to use `scanf`. You can use the same format specifiers you did for `printf` and you can simply prefix the variables you want to give to `scanf` with an ampersand (&) or the reference of operator, to better match with the lingo.

[[Conditionals in C(I)- if statements]]