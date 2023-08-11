Surely you didn't think that was all there was to arrays, right? Let's take a deeper dive into arrays.

Technically this is an extension of the pointers topic but, arrays are present even in the languages which don't provide you access to raw pointers like Java, C#, etc. So it's important to learn about them as an individual entity separate from pointers.

Let's start by defining arrays.

Arrays are constant size continuous blocks of memory, used for storing multiple instances of a single data type.

Let's break it down so it's less confusing.

Let's take a look at the first property of arrays, constant size.

An array has a size defined by the user at the compile time or at the runtime, depending on the language you're using, but whichever it is, it can not be changed once the array has been declared.

That is to say, you created an array of length 10, now you can't increase it's length to 11.

You can create a new array of length 11, and copy the contents of the first array over to the new array and have an extra space left, however you can not increase the size of the pre-existing array, if you do, it's no longer considered the same array.

Now, those of you coming from Python and JS/TS will probably be like:
> Huh, interesting you say that because in Python or JS/TS, we can actually increase the size of the array at will, are you sure it's not a skill issue on C devs' side?

Well, Python and JS/TS offer Lists, not arrays. Python equivalent to arrays is `numpy's ndarray` of dimension 1, and in JS/TS the closest thing to Arrays is `Buffer` from `node:Buffer`.

However Lists are a worry for later, when we get to DSA, for now let's get back to arrays and discuss the second point in the definition i.e. continuous block of memory.

As we discussed in the [[Pointers in C(II)- Arrays & Pointer Arithmetic#^be9051|pointers portion of array]] arrays are continuous chunks of memory, i.e. An array will span from base address to base address + length of array \* size of type of array.

This really doesn't need much more explanation than this so, moving onto third point multiple instances of single type.

This is really important part of the definition, because, this statement can be very easily misunderstood and is misunderstood.

