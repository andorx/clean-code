### Chapter 4: Comments

> Don't comment the bad code - rewrite it


- Nothing can be quite so helpful as a well-placed comment
- Nothing can clutter up a module more than frivolous dogmatic comments
- Nothing can be quite do damaging as an old crufty comment that propagrates lies and misinformation

Comments are, at best, a necessary evil.
Every time you express yourself in code, you should pat yourself on the back. Every time you write a comment, you should grimace and feel the failure of your ability of expression.

The older a comment is, and the farther away it is from the code it describes, the more likely it is to be just plain wrong.

Only the code can truly tell you what it does. It is only source of truly accurate information.

###### # Comments does not make up for bad code
One of the more common motivations for writing comments is bad code. We write a module and we know it is confusing and disorganized. We'd better clean it - not COMMENT it.

Rather than spend your time writing the comments that explain the mess you've made, spend it cleaning that mess.

###### # Explain yourself in code
```java
// Check to see if the employee is eligible for full benefits
if ((employee.flags & HOURLY_FLAG) && (employee.age > 65))
// should be
if (employee.isEligibleForFullBenefits())
```

###### # Good comments
Some comments are necessary or beneficial.
> The only truly good comment is the comment you found a way not to write

###### # Legal comments (copyright and authorship statements)

###### # Informative comments
It is sometimes useful to provide basic information with a comment. 

```java
// format matched kk:mm:ss EEE, MMM dd, yyyy
Pattern timeMatcher = Pattern.compile("\\d*:\\d*:\\d* \\w*, \\w* \\d*, \\d*");
```

###### # Explaination of intent
Sometimes a comment provides the intent behind a decision.
```java
public int compareTo(Object o)
{
	if(o instanceof WikiPagePath)
        {
            WikiPagePath p = (WikiPagePath) o;
            String compressedName = StringUtil.join(names, "");
            String compressedArgumentName = StringUtil.join(p.names, "");
            return compressedName.compareTo(compressedArgumentName);
	}
	return 1; // we are greater because we are the right type.
}
```
```java
...
AtomicBoolean failFlag = new AtomicBoolean();
failFlag.set(false);
//This is our best attempt to get a race condition
//by creating large number of threads.
for (int i = 0; i < 25000; i++) {
    WidgetBuilderThread widgetBuilderThread = new WidgetBuilderThread(widgetBuilder, text, parent, failFlag);
    Thread thread = new Thread(widgetBuilderThread);
    thread.start();
}
...
```

###### # Clarification
Sometimes it is just helpful to translate the meaning of some obscure argument or return value (called function as a part of standard library that you clearly cannot alter) into something that's readable.
```java
assertTrue(a.compareTo(a) == 0); // a == a
assertTrue(a.compareTo(b) != 0); // a != b
assertTrue(ab.compareTo(ab) == 0); // ab == ab
```
Before writing comment like that, take care that there is no better way, and then take even more care that they are accurate.

###### # Warning of consequences
Sometimes it is useful to warn other programmers about certain consequences.

###### # TODO comments
It it sometimes reasonable to leave "To do" notes in the form of *// TODO* comments.

*TODO*s are the job that the programmer think should be done, but for some reason can't do at the moment.

###### # Bad comments

- Mumbling
 - If you decide to write a comment, then spend the time necessary to make sure it is the best comment you can write.
 - Any comments that forces you to look in another module for meaning of that comment has failed to communicate to you	and it not worth the bits it consumes.
- Redundant comments
- Misleading comments
- Mandated comments
- Journal comments (log entries)
- Noise comments
- Scary Noise
 - Don't use the comment when you can use a function and a variable
- Position Markers
 - Mark a particular position in a source file
   E.g: // Actions //////////////////////////////////
- Closing Brace Comments
- Attributions and Bylines
 - E.g: // Added by Rick
- Commented-Out Code
- HTML Comments
- Nonlocal Information
- Too Much Information
- Inobvious Connection
- Function Headers
 - Short functions don't need much description. A well-chosen name for a small function that does one thing is usually better than a comment header.
