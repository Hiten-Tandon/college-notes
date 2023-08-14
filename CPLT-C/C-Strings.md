Now we move onto a topic, which is famous for it's off by one errors. 
C-Strings, or simply put, char arrays, with null terminator, are what in my opinion showcase the sheer amount of memory limitations people had to work with in times of C.

First let's discuss C-strings then we'll get back to this point.

So, our problem, is that we have to create a report card for some student, and we have to print it like so

```
+----------------------------------------+
| +--------------+ +--------+ +--------+ |
| | Name         | |Class   | |Section | |
| +--------------+ +--------+ +--------+ |
|----------------------------------------|
| +----------------+---------+---------+ |
| | Subject        |Percent  |class top| |
| |----------------|---------|---------| |
| |                |         |         | |
| +----------------+---------+---------+ |
+----------------------------------------+
```
<!-- Varna parent's compare kaise krenge -->
Where user can add a max of 12 subjects, and Name has only the First and Last name, the middle name is ignored.

Class can be up to 12, and section is one character in the range A-Z.

Now, first question which should arise in your mind is 
> How are we gonna store names?

And the answer should be just as quick, just make character arrays.
