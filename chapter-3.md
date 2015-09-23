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
