Another type of loops that C offers are do-while loops. Unlike while loops which are entry controlled, do while loops are exit controlled loops, which is just a fancy way of saying, condition is checked after the statements of the loop are executed once.

The syntax for a do-while loop is simple:
```C
do {
	//statements
}while(/*condition*/);
```
Let's look at an example to understand this better.

Let's say you're to write a tic-tac-toe game. Now you've written the game, but you want to run the game until the user wants to quit. So to say, you want to write a game which will reset itself unless the user says, I don't wanna play anymore by pressing e. Assume that the function `start_game()` starts the game, and returns the control to you after the game is over.

Following would be the code for the problem.
```C
#include <stdbool.h>
#include <stdio.h>
void start_game();
bool has_game_ended();
bool place_tile(int x, int y, char player);
char get_winner();

int main(int argc, char **argv) {
	char user_choice;
	
	do {
		start_game();
		printf("Enter e to exit, any other key to continue");
		scanf("%c", &user_choice);
	} while(user_choice != 'e');
	
	return 0;
}

//Following functions are just here so that code works
//I can write the complete implementation, but it's not needed for our toy example.
//What's important with this is, what happens when you run this program
//You get endless Game started until you enter e

void start_game() { printf("Game started"); }
bool has_game_ended() { return true; }
bool place_tile(int x, int y, char player) { return true; }
char get_winner() { return 'D'; }
```

^317180

<!--Some C dev is puking right now because of how bad this code is, I for one am about to-->

Now you maybe asking yourself, Why on earth do we need do-while loops? Don't while loops just do the same job? I mean I can convert this do-while to a while and the program would work just fine.

And you'd be correct, which is why many new programming languages, actually got rid of do-while loops. Python, Go, Rust, Zig, etc. etc. don't have do-while loops, but back in the C days they actually had one use.

You see, C didn't come to a world where 256 GiB SSD + 8 GiB of RAM + 4 cores CPU is economical tier. C came to a world where 175 KiB Floppy + 125 bytes ram + 1 core CPU was a high-end cutting edge PC (I am not even kidding, look it up). Therefore every single bit mattered and every single assembly instruction mattered.

In such a world, you often times don't have the luxury to even initialize a variable, which you would have to do in order to use while, otherwise the program may error, hence devs added do-while, and that's also why it still exists.

So, use it if you want to, otherwise you can also work with simple while loops.
[[Loops In C(III)- For Loop]]