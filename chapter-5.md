### Chapter 5: Formatting
- You should take care that your code is nicely formatted.
- You should choose a set of simple rules that govern the format of your code, and then you should conststently apply those rules.

###### The purpose of formatting
Code formatting is important. Code formatting is about communication, and communication is the professional developer's first order of business.

###### Vertical formatting
Small files usually easier to understand than lerge files are.

###### The newspaper metaphor
We would like a source file to be like a newspaper article.
- The name should be simple but explanatory.
- The name, by itself, should be completely tell us whether we are in the right module or not.
- The topmost parts of the source file should provice the high-level concepts and algorithms. Detail should increase as we move downward, until at the end we find the lowest level functions and details in the source file.

###### Vertical openness between concepts
- Each line represents an expression or a clause
- Each group of lines represents a complete thought

Those thoughts should be separated from each other with blank lines.

###### Vertical density
Line of codes that are tightly related should appear vertically dense.

```java
/**
* The class name of the reporter listener
*/
private String m_className;
/**
* The properties of the reporter listener
*/
private List<Property> m_properties = new ArrayList<Property>();

// should be 

private String m_className;
private List<Property> m_properties = new ArrayList<Property>();
```

###### Vertical distance
Closly related concepts should not be separated into different files unless you have a very good reason.

###### Variable declarations
Variables should be declared as close to their usage as posiible. Because our functions are very short, local variables should appear a the top of each functions.

Control variables for loops should usually be declared within the loop statement.
```java
for (Test each : tests)
	count += each.countTestCases();
```

###### Instance variables
Should be declared at the top of the class, because, in a well-designed class, they are used by many (if not all) of the methods of the class.

###### Dependent functions
If one function calls another, they should be vertically close, and the **caller** should be above the **callee**. The function definitions will follow shortly after their use.

###### Conceptual Affinity
The stronger that affinity, the less vertical distance there should be between them.

The affinity might be based on a direct dependence, such as one function calling another, or a function using a variable. But there are other possible causes of affinity. Affinity might be caused because a group of functions perform a similar operation.
E.g:
```
public class Assert {
	static public void assertTrue(String message, boolean condition)
    {
	if (!condition)
		fail(message);
	}

	static public void assertTrue(boolean condition)
    {
		assertTrue(null, condition);
	}

    static public void assertFalse(String message, boolean condition) {
        assertTrue(message, !condition);
    }

    static public void assertFalse(boolean condition)
    {
    	assertFalse(null, condition);
    }
...
```

These functions share a common naming scheme and perform variations of the same basic task.

###### Vertical Ordering
A function that is called should be below a function that does the calling.

This creates a nice flow down the source code module from high level to low level.

###### Horizontal Formatting
Personally limit: 120 chars/line.

###### Horizontal Openness and Density

###### Horizontal Alignment
Unaligned declarations and assignments

###### Indentation

###### Dummy scopes
Sometimes the body of a *while* or *for* statement is a dummy. Make sure that the dummy body is properly indented and surreounded by braces.
E.g:
```
while (dis.read(buf, 0, readBufferSize) != -1)
	;
```

###### Team Rules
A team of developers should argree upon a single formatting style, and then every member of that team should use that style.

###### Uncle Bob's Formatting Rules















