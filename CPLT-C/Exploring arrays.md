We have already studied the basics of arrays in C. We already know that 
1. An array is a constant sized block of memory, used for storing multiple instances of same data type
2. An array practically is a pointer pointing to the first element of the array.
3. To access an array element you add the number of indices you wanna move from the first index and then access the value at that address.

Now let's look at some of the properties of arrays in C which you have to keep in mind while programming in C.

1. If you try to index your array outside of your array bounds, you're not guaranteed an error.

Take a look at the following code:
```C
#include <stdio.h>
int main(int argc, char **argv) {
	int my_arr[10] = { [0 ... 9] = 0 };
	my_arr[11] = 12;

	printf("%d\n", my_arr[11]);
	return 0;
}
```
Output:
```
12
```

This code, though is erroneous produces neither compile time nor a guaranteed runtime error. This is because, C doesn't do bound checks on arrays, which means that if you index an array out of bounds you can tamper raw memory.

This is dangerous however and should be avoided because it may overwrite the memory being used by some other process at the moment or, it may end up causing a memory leak, which let's hackers have access to your code by back doors.

This is why, you should always bound check your use of arrays in functions, and you should always ask for length of array as a parameter in your function.

2. Arrays are almost always passed to functions as pointers, not arrays.

You can't pass an array to a function, if you do you must first coerce it to a pointer, because arrays have their size as a part of their type, so either you limit yourself to arrays of a specific size, or you take pointers.

Let's see this with an example.

Let's say, you have to write a function which reverses a given array in place, following is how you'd write it.

```C
#include <stdio.h>

void rev_arr(int *arr, int arr_len);

int main(int argc, char **argv) {
	int my_arr[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
	rev_arr(my_arr, 10);

	for(int i = 0; i < 10; ++i) {
		printf("%d, ", my_arr[i]);
	}

	printf("\n");

	int my_arr1[20];
	for(int i = 0; i < 20; ++i) {
		my_arr1[i] = i + 1;
	}
	rev_arr(my_arr1, 20);

	for(int i = 0; i < 20; ++i) {
		printf("%d, ", my_arr1[i]);
	}

	return 0;
}

void rev_arr(int *arr, int arr_len) {
	for(int i = 0; i < arr_len / 2; ++i) {
		int temp = arr[i];
		arr[i] = arr[arr_len - i - 1];
		arr[arr_len - i - 1] = temp;
	}
}
```

Now, note that you can technically you can write the following too, but it's effectively the same thing.

```C
#include <stdio.h>

void rev_arr(int arr[], int arr_len);

int main(int argc, char **argv) {
	int my_arr[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
	rev_arr(my_arr, 10);

	for(int i = 0; i < 10; ++i) {
		printf("%d, ", my_arr[i]);
	}

	printf("\n");

	int my_arr1[20];
	for(int i = 0; i < 20; ++i) {
		my_arr1[i] = i + 1;
	}
	rev_arr(my_arr1, 20);

	for(int i = 0; i < 20; ++i) {
		printf("%d, ", my_arr1[i]);
	}

	return 0;
}

void rev_arr(int arr[], int arr_len) {
	for(int i = 0; i < arr_len / 2; ++i) {
		int temp = arr[i];
		arr[i] = arr[arr_len - i - 1];
		arr[arr_len - i - 1] = temp;
	}
}
```

The type of `arr` is still `int *` this code is just syntax sugar, to give the . So, do what you will, doesn't really matter.

3. Since arrays are a data type, you can create arrays of arrays in C, or arrays of arrays of arrays, or arrays of arrays of arrays of arrays... you get the point.

Once you think about it, it really seems obvious, but before you do so, it really doesn't.

>Arrays of Arrays are often called 2D arrays or Matrices. 
 To create a matrix, you can simply use the syntax,
 `type variable_name[row_count][col_count];`