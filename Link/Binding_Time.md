#Binding Time

An initialization topic with far-reaching implications for program maintenance and modifiability is "binding time": the time at which the variable and its value are bound together (Thimbleby 1988). Are they bound together when the code is written? When it is compiled? When it is loaded? When the program is run? Some other time?

It can be to your advantage to use the latest binding time possible. In general, the later you make the binding time, the more flexibility you build into your code. The next example shows binding at the earliest possible time, when the code is written:

```java
Example 10-12. Java Example of a Variable That's Bound at Code-Writing Time

titleBar.color = 0xFF; // 0xFF is hex value for color blue
```
The value `0xFF` is bound to the variable `titleBar.color` at the time the code is written because `0xFF` is a literal value hard-coded into the program. Hard-coding like this is nearly always a bad idea because if this `0xFF` changes, it can get out of synch with `0xFFs` used elsewhere in the code that must be the same value as this one.

Here's an example of binding at a slightly later time, when the code is compiled:

```java
Example 10-13. Java Example of a Variable That's Bound at Compile Time

private static final int COLOR_BLUE = 0xFF;
private static final int TITLE_BAR_COLOR = COLOR_BLUE;
...
titleBar.color = TITLE_BAR_COLOR;
```
`TITLE_BAR_COLOR` is a named constant, an expression for which the compiler substitutes a value at compile time. This is nearly always better than hard-coding, if your language supports it. It increases readability because `TITLE_BAR_COLOR` tells you more about what is being represented than `0xFF` does. It makes changing the title bar color easier because one change accounts for all occurrences. And it doesn't incur a run-time performance penalty.

Here's an example of binding later, at run time:

```java
Example 10-14. Java Example of a Variable That's Bound at Run Time

titleBar.color = ReadTitleBarColor();
```
`ReadTitleBarColor()`is a routine that reads a value while a program is executing, perhaps from the Microsoft Windows registry file or a Java properties file.

The code is more readable and flexible than it would be if a value were hard-coded. You don't need to change the program to change `titleBar.color`; you simply change the contents of the source that's read by `ReadTitleBarColor()`. This approach is commonly used for interactive applications in which a user can customize the application environment.

There is still another variation in binding time, which has to do with when the `Read-TitleBarColor()` routine is called. That routine could be called once at program load time, each time the window is created, or each time the window is drawn—each alternative represents successively later binding times.

To summarize, following are the times a variable can be bound to a value in this example. (The details could vary somewhat in other cases.)

- Coding time (use of magic numbers)

- Compile time (use of a named constant)

- Load time (reading a value from an external source such as the Windows registry file or a Java properties file)

- Object instantiation time (such as reading the value each time a window is created)

- Just in time (such as reading the value each time the window is drawn)

In general, the earlier the binding time, the lower the flexibility and the lower the complexity. For the first two options, using named constants is preferable to using magic numbers for many reasons, so you can get the flexibility that named constants provide just by using good programming practices. Beyond that, the greater the flexibility desired, the higher the complexity of the code needed to support that flexibility and the more error-prone the code will be. Because successful programming depends on minimizing complexity, a skilled programmer will build in as much flexibility as needed to meet the software's requirements but will not add flexibility—and related complexity—beyond what's required.
