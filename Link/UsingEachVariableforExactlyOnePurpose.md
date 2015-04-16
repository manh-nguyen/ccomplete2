#Using Each Variable for Exactly One Purpose

**KEY POINT**
--------------
It's possible to use variables for more than one purpose in several subtle ways. You're better off without this kind of subtlety.

Use each variable for one purpose only. It's sometimes tempting to use one variable in two different places for two different activities. Usually, the variable is named inappropriately for one of its uses or a "temporary" variable is used in both cases (with the usual unhelpful name x or temp). Here's an example that shows a temporary variable that's used for two purposes:

```c++
Example 10-15.

// Compute roots of a quadratic equation.
// This code assumes that (b*b-4*a*c) is positive.
temp = Sqrt( b*b - 4*a*c );
root[O] = ( -b + temp ) / ( 2 * a );
root[1] = ( -b - temp ) / ( 2 * a );
...

// swap the roots
temp = root[0];
root[0] = root[1];
root[1] = temp;
```

Question: What is the relationship between temp in the first few lines and temp in the last few? Answer: The two temps have no relationship. Using the same variable in both instances makes it seem as though they're related when they're not. Creating unique variables for each purpose makes your code more readable. Here's an improvement:

**Cross-Reference**

*Routine parameters should also be used for one purpose only. For details on using routine parameters, see How to Use Routine Parameters.*

```c++
Example 10-16. C++ Example of Using Two Variables for Two Purposes---Good Practice

// Compute roots of a quadratic equation.
// This code assumes that (b*b-4*a*c) is positive.
discriminant = Sqrt( b*b - 4*a*c );
root[0] = ( -b + discriminant ) / ( 2 * a );
root[1] = ( -b - discriminant ) / ( 2 * a );
...

// swap the roots
oldRoot = root[0];
root[0] = root[1];
root[1] = oldRoot;
```
Avoid variables with hidden meanings. Another way in which a variable can be used for more than one purpose is to have different values for the variable mean different things. For example:

- The value in the variable pageCount might represent the number of pages printed, unless it equals -1, in which case it indicates that an error has occurred.

- The variable customerId might represent a customer number, unless its value is greater than 500,000, in which case you subtract 500,000 to get the number of a delinquent account.

- The variable bytesWritten might be the number of bytes written to an output file, unless its value is negative, in which case it indicates the number of the disk drive used for the output.

Avoid variables with these kinds of hidden meanings. The technical name for this kind of abuse is "hybrid coupling" (Page-Jones 1988). The variable is stretched over two jobs, meaning that the variable is the wrong type for one of the jobs. In the pageCount example, pageCount normally indicates the number of pages; it's an integer. When pageCount is -1, however, it indicates that an error has occurred; the integer is moonlighting as a boolean!

Even if the double use is clear to you, it won't be to someone else. The extra clarity you'll achieve by using two variables to hold two kinds of information will amaze you. And no one will begrudge you the extra storage.

Make sure that all declared variables are used. The opposite of using a variable for more than one purpose is not using it at all. A study by Card, Church, and Agresti found that unreferenced variables were correlated with higher fault rates (1986). Get in the habit of checking to be sure that all variables that are declared are used. Some compilers and utilities (such as lint) report unused variables as a warning.

-    Does each routine check input parameters for validity?

------

**Cross-Reference**

*For a checklist that applies to specific types of data rather than general issues, see the checklist in Chapter 12. For issues in naming variables, see the checklist in Chapter 11.*

-    Does the code declare variables close to where they're first used?

-    Does the code initialize variables as they're declared, if possible?

-    Does the code initialize variables close to where they're first used, if it isn't possible to declare and initialize them at the same time?

-    Are counters and accumulators initialized properly and, if necessary, reinitialized each time they are used?

-    Are variables reinitialized properly in code that's executed repeatedly?

-    Does the code compile with no warnings from the compiler? (And have you turned on all the available warnings?)

-    If your language uses implicit declarations, have you compensated for the problems they cause?

**Other General Issues in Using Data**

-    Do all variables have the smallest scope possible?

-    Are references to variables as close together as possible, both from each reference to a variable to the next reference and in total live time?

-    Do control structures correspond to the data types?

-    Are all the declared variables being used?

-    Are all variables bound at appropriate times—that is, are you striking a conscious balance between the flexibility of late binding and the increased complexity associated with late binding?

-    Does each variable have one and only one purpose?

-    Is each variable's meaning explicit, with no hidden meanings?
