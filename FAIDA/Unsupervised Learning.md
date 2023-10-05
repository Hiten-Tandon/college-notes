Unsupervised Learning is a subset of [[ml|ML]] algorithms which doesn't have clear input and output variables defined.

Basically, instead of having M<sub>I</sub> and M<sub>O</sub> you have only one matrix M, 
in which some of the elements are missing and you have to deduce their values.

<!-- Well the model has to. -->

In a sense you can say that you basically ask the user to enter some of the values for variables, then,
you mark the entered variables as the input variables and the rest variables as output variables, so, 
you have dynamic M<sub>I</sub> and M<sub>O</sub>, which means function (f) also, changes dynamically. (refer [[ml|this]])

Let's see an example to better understand where Unsupervised learning maybe useful.

Let's say, you work at a startup help center, where your organization helps new startups, by providing them funding, advice etc.

Let's say you analyze some data like the funding they received, or project market growth etc to help these people.

You can create an unsupervised ML model, to help yourselves with the task. 

You'd ask the user to enter whatever they already have figured out, with some compulsory fields, 
then your ML model would cluster these fields with the previous data and approximate the unknown fields.
