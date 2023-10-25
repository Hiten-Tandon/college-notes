Now we move onto a topic, which is famous for it's off by one errors. 

Let's say you want to write a program which stores text. Like the word, notepad, or really almost any program, which needs text. How do you go about that?

Answer: Character arrays.

From [[Exploring arrays]] we already know that you can use arrays to store multiple instances of same data type, and from [[Types in C]] we already know that characters are used for representing single glyph of text. This means that, we can use an array of characters to store text.

However, note that, since text is used in almost every part of every program, and especially back when C was being developed, people used CUIs which functioned entirely on text, this posed a problem.

Remember that, for each array you have to store it's length separately. While I didn't really mention it in the arrays portion, the length is always stored in a word sized integer `size_t` or `ssize_t` which could be as big as 4 bytes back then.(now it's just 8 bytes)

The C devs really didn't like this, because, they didn't like the idea of wasting upto 4 extra bytes per string, because there are a lot of them, which means that this 4 bytes would compound really quick.

The solution they derived for this, was to use one extra character at the end of the string, which they would assign 0, also called the null character. The null character won't be used anywhere else and thus it wasn't really a problem to use it. Also, it would only take 1 byte of memory rather than the word sized integer's 4 bytes.

> You still don't have the length problem sorted though?

Oh yes we do. You see, since the last character of a string will always be null, you just traverse the array, and count the characters until you hit null. 

```C
int strlen(char *const str) { //const means, we don't change the pointer.
	int len = 0;
	
	while(str[len] != 0) {
		++len;
	}
	
	return len;
}
```

Try this, copy paste this function in a C file, and try calling it from main with some random character array, do add a '\\0' at it's end though. 

