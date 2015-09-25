### Chapter 3: Functions

###### # Small!
The first rule of funcs is that they should be small. The second rule of funcs is that *they should be smaller than that*.

Rules:
- **150** characters on a line
- Function should hardly ever be **20** lines long
- - -
- Every function in this program was just two, three or four lines long.
- Each was transparently obvious.
- Each told a story.
- Each led you to the next in a compelling order.

###### # Blocks and indenting
The blocks within `if`, `else`, `while`... statements should be one line long. Probably that line should be a function call.
- Keep the enclosing function small
- Adds documentary value (with nicely desscriptive name)

Functions should not be large enough to hold nested structures. Therefore, the indent level of a function should not be greater than one or two.

###### # Do one thing
> Functions should do one thing. They should do it well. They should do it only.

If a function does only those steps that are one level below the stated name of the function, then the function is doing one thing.

###### # Sections within functions
Functions that do onething cannot be reasonably divided into sections.

###### # One level of abstraction per function
Make sure that the statements within our function are all at the same level of abstraction.

###### # Reading code from Top to Bottom: The Stepdown Rule
We want the code to read like a top-down narrative.
We want every function to be followed by those at the next level of abstraction so that we can read the program, descending one level of abstraction at a time as we read down the list of functions.

To say this differently, we want to be able to read the program as though it were a set of *TO* paragraphs, each of which is describing the current level of abstraction and referencing subsequent *TO* paragraphs at the next level down.

> To include the setups and teardowns, we include setups, then we include the test page content, and then we include the teardowns.
To include the setups, we include the suite setup if this is a suite, then we include the regular setup.
To include the suite setup, we search the parent hierarchy for the “SuiteSetUp” page and add an include statement with the path of that page.
To search the parent. . .

###### # Switch statements

###### # Use descriptive names
- Don't be afraid to make a name long. A long descriptive name is better than a short enigmatic name. Along descriptive name is better than a long descriptive comment. Use naming convention that allows multiple words to be easily read in the function names.
- Don't be afraid to spend time choosing a name.
- Be consistent in your names. Use the same phrases, nouns, and verbs. The similar phraseology in names allows the sequence to tell a story.

###### # Function arguments
- Ideal number of arguments for a fucntion is zero to two
- Three arguments should be avoided where possible
- More than three requires very special justification

Arguments are even harder from a testing point of view. Imagine the diffuculty of writing all the test cases to ensure that all the various combinations of arguments work properly.

###### # Common monadic (single) forms

###### # Flag arguments
Flag arguments are ugly. Passing a boolean into a function is a truly terrible practice.

```java
render(boolean isSuite)
// should be splitted into
renderForSuite()
renderFroSingleTest()
```

###### # Dyadic (two) functions
Two arguments should be ordered components of a single value
E.g: `new Point(x, y);`
Even obvious dyadic functions like `assertEquals(expected, actual)` are problematic. The two arguments have no natural ordering.

###### # Triads (three)
Functions taht take three arguments significantly harder to understand than dyads.
The issues of ordering, pausing, and ignoring are more than doubled.

###### # Argument objects
Reducing the number of arguments by creating objects out of them.
E.g:
```java
Circle makeCircle(double x, double y, double radius);
// turns into
Circle makeCircle(Point center, double radius);
```

###### # Argument lists
```java
public String format(String format, Object... args)
```

###### # Verbs and keywords
Choosing good names for a function can go a long way toward explaining the intent of the function and the order and intent of the arguments. The function and argument should form a very nice verb/noun pair.
E.g: `writeField(name)`

###### # Have no side effects
Side effects are lies. Your function promises to do one thing, but it also does other *hidden* things.
- Sometimes it will make unexpected changes to the variables of its own class.
- Sometimes it will make them to the parameters passed into the function or to system globals.

###### # Output arguments

page 76












